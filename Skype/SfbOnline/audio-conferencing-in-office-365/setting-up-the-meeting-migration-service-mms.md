---
title: Usar el servicio de migración de reuniones (MMS)
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) is a service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: da04e98269f20eca327b30c2bd40f3e5181523d0
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012186"
---
# <a name="using-the-meeting-migration-service-mms"></a>Usar el servicio de migración de reuniones (MMS)

El servicio de migración de reuniones (MMS) es un servicio que actualiza las reuniones existentes de un usuario en los siguientes escenarios:

- Cuando un usuario se migra de local a la nube (ya sea a Skype empresarial online o a TeamsOnly).
- Cuando un administrador realiza un cambio en la configuración de las conferencias de audio del usuario 
- Cuando se actualiza un usuario en línea a Teams, o cuando el modo de un usuario de TeamsUpgradePolicy se establece en SfBwithTeamsCollabAndMeetings
- Al usar PowerShell 


De forma predeterminada, MMS se desencadena de forma automática en cada uno de estos casos, aunque los administradores pueden deshabilitarlo en el nivel de espacio empresarial. Además, los administradores pueden usar un cmdlet de PowerShell para desencadenar de forma manual la migración de reuniones para un usuario determinado.


**Limitaciones**: el servicio de migración de reuniones no se puede usar si se cumple alguna de las siguientes opciones:

- El buzón del usuario se hospeda en Exchange local.
- El usuario se está migrando de la nube a Skype empresarial Server local.

En estos casos, los usuarios finales pueden usar la [herramienta de migración de reuniones](https://www.microsoft.com/download/details.aspx?id=51659) para migrar sus propias reuniones.

## <a name="how-mms-works"></a>Cómo funciona MMS

Cuando se desencadena MMS para un usuario determinado, se coloca en una cola una solicitud de migración para ese usuario. Para evitar cualquier condición de carrera, la solicitud en cola no se procesa deliberadamente hasta que hayan pasado al menos 90 minutos. Una vez que MMS procesa la solicitud, realiza las siguientes tareas:

1. Busca en el buzón de ese usuario todas las reuniones existentes organizadas por ese usuario y programadas en el futuro.
2. En función de la información que se encuentra en el buzón del usuario, se actualizan o programan nuevas reuniones en Teams o Skype empresarial online para ese usuario, según el escenario exacto.
3. En el mensaje de correo electrónico, reemplaza el bloque de la reunión en línea en los detalles de la reunión.
4. Envía la versión actualizada de esa reunión a todos los destinatarios de la reunión en nombre del organizador de la reunión. Los invitados de la reunión recibirán una actualización de la reunión con las coordenadas de reunión actualizadas en su correo electrónico. 

    ![El bloque de reunión que MMS actualiza](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Desde el momento en que se desencadena MMS, normalmente tarda aproximadamente 2 horas hasta que se migren las reuniones del usuario. Sin embargo, si el usuario tiene una gran cantidad de reuniones, puede demorar más. Si MMS detecta un error al migrar una o más reuniones para el usuario, se volverá a intentar de forma periódica 9 veces durante un período de 24 horas.

**Notas**:

- Cuando migra una reunión, MMS sustituye todo el contenido del bloque de información de la reunión en línea. Por lo tanto, si el usuario ha editado ese bloque, los cambios se sobrescriben. No se verá afectado por esta acción ningún contenido que el usuario tenga en los detalles de la reunión, fuera del bloque de información de la reunión en línea. Esto significa que todos los archivos adjuntos a la invitación a la reunión se incluirán. 
- Solo se migran las reuniones de Skype empresarial o de Microsoft Teams programadas haciendo clic en el botón **Agregar reunión de Skype** en Outlook en la web o mediante el complemento de reunión de Skype para Outlook. Si un usuario copia y pega la información de la reunión en línea de Skype desde una reunión a una nueva reunión, esa nueva reunión no se actualizará porque no hay ninguna reunión en el servicio original.
- El contenido de la reunión que se ha creado o adjuntado a la reunión (pizarras, sondeos, etc.) no se retendrá después de la ejecución de MMS. Si sus organizadores de reuniones adjuntaron contenido a las reuniones antes de la ejecución de MMS, será necesario volver a crear el contenido una vez finalizada la operación.
- También se sobrescribirá el vínculo a las notas de la reunión compartidas en el elemento de calendario y en la reunión de Skype. Tenga en cuenta que las notas de la reunión reales almacenadas en OneNote seguirán estando allí; solo es el vínculo a las notas compartidas que se sobrescriben.
- Las reuniones que tengan más de 250 participantes (incluido el organizador) no se migrarán.
- Es posible que algunos caracteres Unicode en el cuerpo de la invitación no se actualicen correctamente a uno de los siguientes caracteres especiales: ï, ¿, 1/2,.

## <a name="triggering-mms-for-a-user"></a>Desencadenar MMS para un usuario

En esta sección se describe lo que ocurre cuando se desencadena MMS en cada uno de los siguientes casos:

- Cuando un usuario se migra de local a la nube
- Cuando un administrador realiza un cambio en la configuración de las conferencias de audio del usuario 
- Cuando el modo del usuario de TeamsUpgradePolicy se establece en TeamsOnly o SfBWithTeamsCollabAndMeetings (mediante PowerShell o el portal de administración de Teams)
- Cuando use el cmdlet de PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Actualizar reuniones al mover un usuario local a la nube

Este es el escenario más común en el que MMS ayuda a crear una transición más suave para los usuarios. Sin la migración de reuniones, las reuniones existentes organizadas por un usuario en Skype empresarial Server local ya no funcionarán una vez que el usuario se mueva a Internet. Por lo tanto, cuando usa las herramientas de administración local ( `Move-CsUser` o el panel de control del administrador) para mover un usuario a la nube, las reuniones existentes se mueven automáticamente a la nube de la siguiente manera:

- Si `MoveToTeams` `Move-CsUser` se especifica el cambio, las reuniones se migran directamente a teams y el usuario estará en el modo de TeamsOnly. El uso de este modificador requiere Skype empresarial Server 2015 con CU8 o posterior. Estos usuarios pueden unirse a cualquier reunión de Skype empresarial a la que se le pueda invitar con el cliente de Skype empresarial o la aplicación de reunión de Skype.
- De lo contrario, las reuniones se migran a Skype empresarial online.

En cualquiera de los casos, si el usuario tiene asignada una licencia de audioconferencia antes de moverla a la nube, las reuniones se crearán con las coordenadas de acceso telefónico. Si mueve un usuario de local a la nube y quiere que el usuario Use las conferencias de audio, le recomendamos que primero asigne la Conferencia de audio antes de mover el usuario para que solo se desencadene una migración de reunión.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Actualización de reuniones cuando cambia la configuración de conferencia de audio de un usuario

En los casos siguientes, MMS actualizará las reuniones existentes de Skype empresarial y Microsoft Teams para agregar, quitar o modificar las coordenadas de acceso telefónico:

- Al asignar o quitar una licencia de servicio de conferencia de audio de Microsoft a un usuario, y ese usuario no está habilitado para un proveedor de audioconferencias de terceros.
- Cuando se cambia el proveedor de servicios de audioconferencia de un usuario de cualquier otro proveedor a Microsoft, se proporciona al usuario una licencia de conferencia de audio de Microsoft. Para obtener más información, consulte [asignar Microsoft como el proveedor de servicios de audioconferencia](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Además, tenga en cuenta que el soporte técnico para proveedores de servicios de audioconferencia de terceros [ACP] está programado para el fin de la vida el 1 de abril de 2019, como se ha [anunciado anteriormente](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Al habilitar o deshabilitar las conferencias de audio de un usuario.
- Al cambiar o restablecer el identificador de conferencia para un usuario configurado para usar reuniones públicas.
- Al mover el usuario a un nuevo puente de conferencias de audio.
- Cuando un número de teléfono de un puente de audioconferencia no está asignado. Este es un escenario complejo que requiere pasos adicionales. Para obtener más información, consulte [cambiar los números de teléfono en el puente de audioconferencia](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

No todos los cambios en la configuración de conferencia de audio de un usuario desencadenan MMS. Concretamente, los siguientes cambios no provocan que MMS actualice las reuniones:

- Cuando cambia la dirección SIP del organizador de la reunión (tanto el nombre de usuario SIP como el dominio SIP).
- Al cambiar la dirección URL de la reunión de su organización con el `Update-CsTenantMeetingUrl` comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Actualización de reuniones al asignar TeamsUpgradePolicy

De forma predeterminada, la migración de la reunión se desencadena automáticamente cuando se concede a un usuario una instancia de `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode= SfBWithTeamsCollabAndMeetings` . Si no desea migrar reuniones al conceder alguno de estos modos, especifique `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` (si usa PowerShell) o desactive la casilla para migrar reuniones al configurar el modo de coexistencia de un usuario (si usa el portal de administración de equipos).

Además, tenga en cuenta lo siguiente:

- La migración de reuniones solo se invoca cuando se concede a `TeamsUpgradePolicy` un usuario específico. Si concede `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode=SfBWithTeamsCollabAndMeetings` a escala de *inquilinos* , no se invoca la migración de reuniones.
- A un usuario solo se le puede conceder el modo TeamsOnly si el usuario está conectado. Los usuarios que estén alojados en locales deben moverse con las `Move-CsUser` descritas anteriormente.
- Al conceder un modo distinto de TeamsOnly o SfBWithTeamsCollabAndMeetings, no se convierten las reuniones de Teams existentes en reuniones de Skype empresarial.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Desencadenar la migración de reunión manualmente mediante el cmdlet de PowerShell

Además de las migraciones de reuniones automáticas, los administradores pueden desencadenar manualmente la migración de reuniones para un usuario ejecutando el cmdlet `Start-CsExMeetingMigration` . Este cmdlet pone en cola una solicitud de migración para el usuario especificado.  Además del `Identity` parámetro obligatorio, toma dos parámetros opcionales, `SourceMeetingType` `TargetMeetingType` que le permiten especificar cómo migrar las reuniones:

**TargetMeetingType:**

- Usar `TargetMeetingType Current` especifica que las reuniones de Skype empresarial siguen siendo las reuniones de Skype empresarial y las reuniones de Teams siguen formando reuniones de Teams. Sin embargo, las coordenadas de las conferencias de audio se pueden cambiar, y cualquier reunión local de Skype empresarial se migrará a Skype empresarial online. Este es el valor predeterminado para TargetMeetingType.
- Usar `TargetMeetingType Teams` especifica que cualquier reunión existente se debe migrar a Teams, independientemente de si la reunión se hospeda en Skype empresarial online o en local, y con independencia de si se necesitan actualizaciones de audioconferencia. 

**SourceMeetingType:**
- `SourceMeetingType SfB`Indica que solo se deben actualizar las reuniones de Skype empresarial (estén locales o en línea).
- `SourceMeetingType Teams`Indica que solo se deben actualizar las reuniones de Teams.
- Usar `SourceMeetingType All` indica que las reuniones de Skype empresarial y las reuniones de Teams deben actualizarse. Este es el valor predeterminado para SourceMeetingType.
    

En el siguiente ejemplo se muestra cómo iniciar la migración de reuniones para los usuarios ashaw@contoso.com para que todas las reuniones se migren a teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Administrar MMS

Con Windows PowerShell, puede comprobar el estado de las migraciones actuales, desencadenar manualmente la migración de reuniones y deshabilitar la migración por completo. 

### <a name="check-the-status-of-meeting-migrations"></a>Comprobar el estado de las migraciones de reuniones

Use el `Get-CsMeetingMigrationStatus` cmdlet para comprobar el estado de las migraciones de reuniones. A continuación puede ver algunos ejemplos.

- Para obtener un resumen del estado de todas las migraciones de MMS, ejecute el siguiente comando, que proporciona una vista tabular de todos los Estados de migración:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Para obtener detalles completos de todas las migraciones dentro de un período de tiempo específico, use los `StartTime` `EndTime` parámetros y. Por ejemplo, el siguiente comando devolverá detalles completos sobre todas las migraciones que se realizaron desde el 1 de octubre de 2018 al 8 de octubre de 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Para comprobar el estado de la migración de un usuario específico, use el `Identity` parámetro. Por ejemplo, el siguiente comando devolverá el estado del usuario ashaw@contoso.com:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Si ve alguna migración que ha fallado, realice una acción para resolver estos problemas lo antes posible, ya que los usuarios no podrán llamar a las reuniones organizadas por esos usuarios hasta que se resuelvan. Si `Get-CsMeetingMigrationStatus` muestra cualquier migración en estado de error, siga estos pasos:
 
1. Determine a qué usuarios afecta. Ejecute el siguiente comando para obtener la lista de usuarios afectados y el error concreto registrado:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Para cada usuario afectado, ejecute la herramienta de migración de reuniones para migrar manualmente sus reuniones.

3. Si la migración sigue sin funcionar con la Herramienta de migración de reuniones, tiene dos opciones:

    - Hacer que los usuarios creen reuniones de Skype nuevas.
    - [Ponerse en contacto con el equipo de soporte técnico](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Habilitar y deshabilitar MMS

MMS está habilitado de forma predeterminada en todas las organizaciones, pero se puede deshabilitar de la siguiente manera:

- Deshabilitar por completo para el inquilino. 
- Deshabilitar solo para los cambios relacionados con la audioconferencia. En este caso, MMS seguirá ejecutándose cuando un usuario se migra de local a la nube o cuando se le concede el modo TeamsOnly o SfBWithTeamsCollabAndMeetings `TeamsUpgradePolicy` .

Por ejemplo, es posible que desee migrar manualmente todas las reuniones o deshabilitar de forma temporal MMS mientras realiza cambios sustanciales en la configuración de la audioconferencia de su organización.

Para ver si MMS está habilitado para su organización, ejecute el siguiente comando. MMS está habilitado si el `MeetingMigrationEnabled` parámetro es `$true` .
```PowerShell
Get-CsTenantMigrationConfiguration
```
Para habilitar o deshabilitar MMS por completo, use el `Set-CsTenantMigrationConfiguration` comando. Por ejemplo, para deshabilitar MMS, ejecute el siguiente comando:

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Si MMS está habilitado en la organización y desea comprobar si está habilitada para las actualizaciones de audioconferencia, compruebe el valor del `AutomaticallyMigrateUserMeetings` parámetro en la salida de `Get-CsOnlineDialInConferencingTenantSettings` . Para habilitar o deshabilitar MMS para audioconferencias, use `Set-CsOnlineDialInConferencingTenantSettings` . Por ejemplo, para deshabilitar MMS para audioconferencias, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencia en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
