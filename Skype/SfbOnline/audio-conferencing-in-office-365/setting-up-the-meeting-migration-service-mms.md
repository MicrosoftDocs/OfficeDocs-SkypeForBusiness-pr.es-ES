---
title: Uso del servicio de migración de reunión (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Servicio de migración (MMS) de la reunión es un servicio que se ejecuta en segundo plano y Skype se actualiza automáticamente para las reuniones de negocios y Microsoft Teams para los usuarios. MMS está diseñado para eliminar la necesidad de los usuarios ejecutar la herramienta de migración de la reunión para actualizar su Skype para las reuniones de negocios y Microsoft Teams.
ms.openlocfilehash: 9a133cb2a91e50ad21b263009f8f2c64cd3d8ccb
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835123"
---
# <a name="using-the-meeting-migration-service-mms"></a>Uso del servicio de migración de reunión (MMS)

El servicio de migración de reunión (MMS) es el servicio que actualiza las reuniones existentes de un usuario en los siguientes escenarios:

- Cuando un usuario se migra desde local a la nube (si va a Skype para profesionales en línea o TeamsOnly).
- Cuando un administrador realiza un cambio a la configuración del usuario conferencias de audio 
- Cuando se actualiza un usuario en línea para los equipos sólo, o cuando se establece el modo de un usuario en TeamsUpgradePolicy en SfBwithTeamsCollabAndMeetings
- Cuándo usar PowerShell 


De forma predeterminada, MMS se activa automáticamente en cada uno de estos casos, aunque los administradores pueden deshabilitar en el nivel de inquilino. Además, los administradores pueden utilizar un cmdlet de PowerShell para activar manualmente la migración de la reunión para un usuario determinado.


**Limitaciones**: la reunión no se puede utilizar el servicio de migración si cualquiera de las condiciones siguientes:

- El buzón del usuario se hospeda en Exchange local.
- El usuario se están migrando desde la nube a Skype para Business Server local.

En estas situaciones, los usuarios finales puede usar la [Herramienta de migración de reunión](https://www.microsoft.com/en-us/download/details.aspx?id=51659) para migrar sus propias reuniones en su lugar.

## <a name="how-mms-works"></a>Cómo funciona la MMS

Cuando se desencadena MMS para un usuario determinado, una solicitud de migración para que el usuario se coloca en una cola. Para evitar las condiciones de carrera, deliberadamente, no se procesa la solicitud en cola hasta que se han pasado al menos 90 minutos. Una vez MMS procesa la solicitud, realiza las tareas siguientes:

1. Busca en el buzón de ese usuario para todas las reuniones organizadas por ese usuario y programadas en el futuro.
2. En función de la información que se encuentran en el buzón del usuario, que actualiza o programa reuniones nuevo en los equipos o Skype para empresarial en línea para dicho usuario, según el caso concreto.
3. En el mensaje de correo electrónico, reemplaza el bloque de reunión en línea en los detalles de la reunión.
4. La versión actualizada de la reunión envía a todos los destinatarios de la reunión en nombre del organizador de la reunión. Los invitados de la reunión recibirán una actualización de la reunión con las coordenadas de la reunión actualizada en su correo electrónico. 

    ![El bloque de reunión que MMS actualiza](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Desde el momento en que se desencadena MMS, normalmente se tarda aproximadamente 2 horas hasta que se migran las reuniones del usuario. Sin embargo, si el usuario tiene un gran número de las reuniones, puede tardar más tiempo. Si MMS encuentra un error en la migración de una o más reuniones para el usuario, reintentará periódicamente hasta 9 veces en el intervalo de 24 horas.

**Notas**:

- Cuando migra una reunión, MMS sustituye todo el contenido del bloque de información de la reunión en línea. Por lo tanto, si el usuario ha editado ese bloque, los cambios se sobrescriben. No se verá afectado por esta acción ningún contenido que el usuario tenga en los detalles de la reunión, fuera del bloque de información de la reunión en línea.
- Se migran sólo el Skype para las reuniones de negocios o Teams de Microsoft que se han programado haciendo clic en el botón **Agregar Skype reunión** en Outlook en el Web o mediante el complemento de reunión de Skype para Outlook. Si un usuario copia y pega la información de la reunión en línea de Skype de una reunión a una nueva reunión, dicha reunión nueva no se actualizan porque no hay ninguna reunión en el servicio original.
- No se conserva el contenido que se ha creado o adjunto a la reunión (pizarras, sondeos y así sucesivamente) de la reunión después de que se ejecuta MMS. Si sus organizadores de reuniones adjuntaron contenido a las reuniones antes de la ejecución de MMS, será necesario volver a crear el contenido una vez finalizada la operación.
- También se sobrescribirá el vínculo a las notas de la reunión compartidas en el elemento de calendario y en la reunión de Skype. Tenga en cuenta que las notas de la reunión real almacenadas en OneNote seguirá estar allí; es solo el vínculo a las notas compartidas se sobrescribe.
- Las reuniones que tengan más de 250 participantes (incluido el organizador) no se migrarán.
- Es posible que se actualizan correctamente algunos caracteres UNICODE en el cuerpo de la invitación a uno de los siguientes caracteres especiales: ï, ø, ½,.

## <a name="triggering-mms-for-a-user"></a>Desencadenar MMS para un usuario

En esta sección se describe lo que sucede cuando se desencadena MMS en cada uno de los siguientes casos:

- Cuando un usuario se migra desde local a la nube
- Cuando un administrador realiza un cambio a la configuración del usuario conferencias de audio 
- Cuando se establece el modo de usuario en TeamsUpgradePolicy a TeamsOnly o SfBWithTeamsCollabAndMeetings (mediante Powershell o el Portal de administración de equipos)
- Al usar el cmdlet de PowerShell, CsExMeetingMigration de inicio

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Actualización de reuniones al mover un usuario local a la nube

Este es el escenario más común donde MMS ayuda a crear una transición más fácil para los usuarios. Sin migración de reunión, las reuniones existentes organizadas por un usuario en Skype para Business Server local ya no funcionará una vez que el usuario se mueva en línea. Por lo tanto, al usar las herramientas de administración local (ya sea `Move-CsUser` o el Panel de Control de administración) para mover un usuario a la nube, las reuniones existentes se mueven automáticamente a la nube como sigue:

- Si el `MoveToTeams` cambiar en `Move-CsUser` se especifica, las reuniones se migran directamente a los equipos y el usuario estará en modo de TeamsOnly. Uso de este modificador requiere Skype para Business Server con CU8 o posterior. Estos usuarios todavía pueden unirse a cualquier Skype para la reunión de negocios que pueden ser invitados a, con el Skype para clientes empresariales o la aplicación de reunión de Skype.
- En caso contrario, las reuniones se migran a Skype para profesionales en línea.

En cualquier caso, si el usuario se ha asignado una licencia de conferencias de Audio antes de moverse a la nube, las reuniones se creará con las coordenadas de marcado. Si mueve un usuario desde local a la nube y que piensa para que ese usuario usar la conferencia de Audio, se recomienda asignar en primer lugar la conferencia de audio antes de mover el usuario para que se desencadena la migración de reunión sólo 1.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Actualización de reuniones cuando cambie la configuración de conferencia de audio de un usuario

En los siguientes casos, MMS actualizará Skype existente para las reuniones de negocios y Microsoft Teams para agregar, quitar o modificar las coordenadas de marcado:

- Al asignar o quitar una licencia de servicio de conferencia de Audio de Microsoft a un usuario y el usuario no está habilitado para un proveedor de conferencia de audio de terceros.
- Al cambiar el proveedor de conferencia de audio de un usuario desde cualquier otro proveedor a proporcionados por Microsoft, el usuario se le asigna una licencia de conferencia de Audio de Microsoft. Para obtener más información, vea [Asignar Microsoft como proveedor de conferencias de audio](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Tenga en cuenta también que soporte para proveedores de audioconferencia de terceros [ACP] está programada para el final del ciclo de vida en el 1 de abril de 2019 como [anunciado previamente](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Al habilitar o deshabilitar conferencias de audio para un usuario.
- Al cambiar o restablecer el identificador de conferencia para un usuario configurado para usar reuniones públicas.
- Cuando el usuario se mueve a un nuevo puente de conferencia de audio.
- Cuando un número de teléfono de un puente de conferencia de audio es sin asignar. Este es un escenario complejo que requiere pasos adicionales. Para obtener más información, vea [cambiar los números de teléfono en el puente de conferencia de audio](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

No todos los cambios a la configuración de conferencia de audio de un usuario desencadenan MMS. Concretamente, los siguientes cambios no provocan que MMS actualice las reuniones:

- Cuando cambia la dirección SIP del organizador de la reunión (tanto el nombre de usuario SIP como el dominio SIP).
- Cuando se cambia la organización reunión de dirección URL mediante el `Update-CsTenantMeetingUrl` comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Actualización de reuniones al asignar TeamsUpgradePolicy

De forma predeterminada, migración de la reunión se desencadena automáticamente cuando un usuario se le concede a una instancia de `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode= SfBWithTeamsCollabAndMeetings`. Si no desea migrar las reuniones cuando la concesión de cualquiera de estos modos, a continuación, especifique `MigrateMeetingsToTeams $false` en `Grant-CsTeamsUpgradePolicy` (si se usa PowerShell) o desactive la casilla para migrar las reuniones al establecer el modo de coexistencia de un usuario (si se usa el portal de administración de equipos).

También tenga en cuenta lo siguiente:

- Migración de la reunión sólo se invoca al conceder `TeamsUpgradePolicy` para un usuario específico. Si concede `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode=SfBWithTeamsCollabAndMeetings` en *todo el inquilino* , no se invoca migración de la reunión.
- Un usuario sólo puede concederse TeamsOnly modo si el usuario está hospedado en línea. Deben mover los usuarios que están hospedados en implementaciones locales con `Move-CsUser` como se describió anteriormente.
- Concesión de un modo distinto de TeamsOnly o SfBWithTeamsCollabAndMeetings no convierte las reuniones de los equipos existentes en Skype para reuniones de negocios.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Migración de reunión de desencadenador manualmente mediante el cmdlet de PowerShell

Además de las migraciones de reunión automática, los administradores pueden desencadenar manualmente migración de reunión para un usuario ejecutando el cmdlet `Start-CsExMeetingMigration`. Este cmdlet pone en cola una solicitud de migración para el usuario especificado.  Además de los necesarios `Identity` parámetro, toma dos parámetros opcionales, `SourceMeetingType` y `TargetMeetingType`, que le permiten especificar cómo migrar las reuniones:

**TargetMeetingType:**

- Uso de `TargetMeetingType Current` especifica que Skype para reuniones de negocios permanecen Skype para reuniones de negocios y reuniones de los equipos permanecen las reuniones de los equipos. Coordenadas de conferencias de audio sin embargo es posible que se pueden cambiar, y cualquier Skype local para reuniones de negocios se migrará a Skype para profesionales en línea. Esto es el valor predeterminado para TargetMeetingType.
- Uso de `TargetMeetingType Teams` especifica que se debe migrar cualquier reunión existente a los equipos, independientemente de si la reunión está hospedada en Skype para negocios en línea o local e independientemente de si se requiere cualquier actualización de conferencias de audio. 

**SourceMeetingType:**
- Uso de `SourceMeetingType SfB` indica que sólo Skype para reuniones de negocios (si local o en línea) debe actualizarse.
- Uso de `SourceMeetingType Teams` indica que se deben actualizar sólo las reuniones de los equipos.
- Uso de `SourceMeetingType All` indica que se debe actualizar ambos Skyep para reuniones de negocios y reuniones de los equipos. Esto es el valor predeterminado para SourceMeetingType.
    

En el ejemplo siguiente se muestra cómo iniciar la migración de la reunión para usuario ashaw@contoso.com para que todas las reuniones se migran a los equipos:

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Administrar MMS

Con Windows PowerShell, puede comprobar el estado de las migraciones continuadas, manualmente desencadenar la migración de la reunión y deshabilitar totalmente la migración. 

### <a name="check-the-status-of-meeting-migrations"></a>Comprobar el estado de las migraciones de la reunión

Usar el `Get-CsMeetingMigrationStatus` cmdlet para comprobar el estado de las migraciones de la reunión. A continuación puede ver algunos ejemplos.

- Para obtener un estado del resumen de todas las migraciones de MMS, ejecute el siguiente comando, que proporciona una vista tabular de todos los Estados de migración:

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Para obtener detalles completos de todas las migraciones dentro de un período de tiempo específico, utilice la `StartTime` y `EndTime` parámetros. Por ejemplo, el siguiente comando devolverá detalles completos en todas las migraciones que se ha producido desde el 1 de octubre de 2018 a 8 de octubre de 2018.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Para comprobar el estado de la migración de un usuario específico, use el `Identity` parámetro. Por ejemplo, el siguiente comando devolverá el estado del usuario ashaw@contoso.com:

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Si ve cualquier migraciones que se han producido un error, tomar medidas para resolver estos problemas tan pronto como sea posible, ya que las personas no serán capaz de marcado en las reuniones organizadas por los usuarios hasta que se resuelven. Si `Get-CsMeetingMigrationStatus` muestra las migraciones en un estado de error, siga estos pasos:
 
1. Determine a qué usuarios afecta. Ejecute el siguiente comando para obtener la lista de usuarios afectados y el error concreto registrado:

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. Para cada usuario afectado, ejecute la herramienta de migración de reunión para migrar manualmente sus reuniones.

3. Si la migración sigue sin funcionar con la Herramienta de migración de reuniones, tiene dos opciones:

    - Hacer que los usuarios creen reuniones de Skype nuevas.
    - [Ponerse en contacto con el equipo de soporte técnico](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Habilitar y deshabilitar MMS

MMS está habilitada de forma predeterminada para todas las organizaciones, pero se puede deshabilitar de manera:

- Deshabilitar por completo para el inquilino. 
- Deshabilitar sólo para los cambios relacionados con las conferencias de audio. En este caso, MMS aún se ejecutará cuando un usuario se migra desde local a la nube o al conceder modo TeamsOnly o SfBWithTeamsCollabAndMeetings en `TeamsUpgradePolicy`.

Por ejemplo, es posible que desee migrar todas las reuniones de forma manual o deshabilitar temporalmente MMS mientras realiza cambios importantes en la configuración de conferencia de audio para la organización

Para ver si MMS está habilitada para la organización, ejecute el siguiente comando. MMS está habilitado si la `MeetingMigrationEnabled` parámetro es `$true`.
```
Get-CsTenantMigrationConfiguration
```
Para habilitar o deshabilitar totalmente la MMS, use la `Set-CsTenantMigrationConfiguration` comando. Por ejemplo, para deshabilitar MMS, ejecute el siguiente comando:

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Si MMS está habilitado en la organización y que desea comprobar si se habilita para actualizaciones en las conferencias de audio, compruebe el valor de la `AutomaticallyMigrateUserMeetings` parámetro en la salida de `Get-CsOnlineDialInConferencingTenantSettings`. Para habilitar o deshabilitar MMS para conferencias de audio, use `Set-CsOnlineDialInConferencingTenantSettings`. Por ejemplo, para deshabilitar MMS para conferencias de audio, ejecute el siguiente comando:

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Mover usuarios entre local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
