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
description: El Servicio de migración de reuniones (MMS) es un servicio que se ejecuta en segundo plano y actualiza automáticamente las reuniones de Skype Empresarial y Microsoft Teams para los usuarios. MMS está diseñado para eliminar la necesidad de que los usuarios ejecuten la Herramienta de migración de reuniones para actualizar sus reuniones de Skype Empresarial y Microsoft Teams.
ms.openlocfilehash: 9223102ef9c264fdafdb9f52ec74d6edb383f987
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47765352"
---
# <a name="using-the-meeting-migration-service-mms"></a>Usar el servicio de migración de reuniones (MMS)

El Servicio de migración de reuniones (MMS) es un servicio que actualiza las reuniones existentes de un usuario en los siguientes escenarios:

- Cuando se migra un usuario desde la implementación local a la nube (ya sea a Skype Empresarial Online o a TeamsOnly).
- Cuando un administrador realiza un cambio en la configuración de audioconferencia del usuario 
- Cuando un usuario en línea se actualiza solo a Teams o cuando el modo de un usuario en TeamsUpgradePolicy se establece en SfBwithTeamsCollabAndMeetings
- Al usar PowerShell 


De forma predeterminada, MMS se activa automáticamente en cada uno de estos casos, aunque los administradores pueden deshabilitarlo en el nivel de inquilino. Además, los administradores pueden usar un cmdlet de PowerShell para desencadenar manualmente la migración de reuniones de un usuario determinado.


**Limitaciones:** El servicio de migración de reuniones no se puede usar si se aplica alguna de las siguientes opciones:

- El buzón del usuario está hospedado en Exchange local.
- El usuario se está migrando desde la nube a Skype Empresarial Server local.

En estas situaciones, los usuarios finales pueden usar la [Herramienta de migración de reuniones](https://www.microsoft.com/download/details.aspx?id=51659) para migrar sus propias reuniones.

## <a name="how-mms-works"></a>Cómo funciona MMS

Cuando mms se activa para un usuario determinado, una solicitud de migración para ese usuario se coloca en una cola. To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by. Una vez que MMS procesa la solicitud, realiza las siguientes tareas:

1. Busca en el buzón de ese usuario todas las reuniones existentes organizadas por ese usuario y programadas en el futuro.
2. Según la información que se encuentra en el buzón del usuario, este actualiza o programa nuevas reuniones en Teams o Skype Empresarial Online para ese usuario, según el escenario exacto.
3. En el mensaje de correo electrónico, reemplaza el bloque de reunión en línea en los detalles de la reunión.
4. Envía la versión actualizada de la reunión a todos los destinatarios de la reunión en nombre del organizador de la reunión. Los invitados a la reunión recibirán una actualización de la reunión con las coordenadas de reunión actualizadas en su correo electrónico. 

    ![El bloque de reunión que MMS actualiza](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Desde el momento en que mms se activa, normalmente tarda unas 2 horas hasta que se migran las reuniones del usuario. Sin embargo, si el usuario tiene un gran número de reuniones, puede tardar más tiempo. Si MMS encuentra un error al migrar una o varias reuniones para el usuario, periódicamente volverá a intentar hasta 9 veces durante un intervalo de 24 horas.

**Notas:**

- Cuando migra una reunión, MMS sustituye todo el contenido del bloque de información de la reunión en línea. Por lo tanto, si el usuario ha editado ese bloque, los cambios se sobrescriben. No se verá afectado por esta acción ningún contenido que el usuario tenga en los detalles de la reunión, fuera del bloque de información de la reunión en línea. Esto significa que se seguirán incluidos todos los archivos adjuntos a la invitación a la reunión. 
- Solo se migran las reuniones de Skype Empresarial o Microsoft Teams que se programaron haciendo clic en el botón Agregar reunión de **Skype** en Outlook en la web o usando el complemento para reunión de Skype para Outlook. Si un usuario copia y pega la información de una reunión en línea de Skype en una nueva reunión, esa nueva reunión no se actualizará puesto que no hay ninguna reunión en el servicio original.
- El contenido de la reunión que se haya creado o adjuntado a la reunión (pizarras, sondeos, entre otros) no se conservará una vez que se ejecute MMS. Si sus organizadores de reuniones adjuntaron contenido a las reuniones antes de la ejecución de MMS, será necesario volver a crear el contenido una vez finalizada la operación.
- También se sobrescribirá el vínculo a las notas de la reunión compartidas en el elemento de calendario y en la reunión de Skype. Tenga en cuenta que las notas de reunión almacenadas en OneNote seguirán ahí; es solo el vínculo a las notas compartidas que se sobrescribe.
- Las reuniones que tengan más de 250 participantes (incluido el organizador) no se migrarán.
- Es posible que algunos caracteres UNICODE del cuerpo de la invitación se actualicen incorrectamente a uno de los siguientes caracteres especiales: ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Desencadenar MMS para un usuario

En esta sección se describe lo que ocurre cuando MMS se activa en cada uno de los siguientes casos:

- Cuando se migra un usuario desde la implementación local a la nube
- Cuando un administrador realiza un cambio en la configuración de audioconferencia del usuario 
- Cuando el modo del usuario en TeamsUpgradePolicy se establece en TeamsOnly o SfBWithTeamsCollabAndMeetings (usando Powershell o el Portal de administración de Teams)
- Al usar el cmdlet de PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Actualizar reuniones al mover un usuario local a la nube

Este es el escenario más común en el que MMS le ayuda a realizar una transición más suave para sus usuarios. Sin la migración de reuniones, las reuniones existentes organizadas por un usuario en Skype Empresarial Server local ya no funcionaban una vez que se movía el usuario en línea. Por lo tanto, al usar las herramientas de administración locales (o el Panel de control de administración) para mover un usuario a la nube, las reuniones existentes se mueven automáticamente a la nube de la siguiente `Move-CsUser` manera:

- Si se especifica el cambio, las reuniones se migran directamente a Teams y el usuario estará en `MoveToTeams` `Move-CsUser` modo TeamsOnly. El uso de este modificador requiere Skype Empresarial Server 2015 con CU8 o posterior. Estos usuarios aún pueden unirse a cualquier reunión de Skype Empresarial a la que se les pueda invitar, mediante el cliente de Skype Empresarial o la aplicación Reunión de Skype.
- En caso contrario, las reuniones se migran a Skype Empresarial Online.

En cualquier caso, si al usuario se le ha asignado una licencia de Audioconferencia antes de moverlo a la nube, las reuniones se crearán con coordenadas de acceso telefónico local. Si mueve un usuario de un entorno local a la nube e intenta que dicho usuario use Audioconferencia, le recomendamos que primero asigne la audioconferencia antes de mover el usuario para que solo se desencadene una migración de reuniones.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Actualizar reuniones cuando cambia la configuración de audioconferencia de un usuario

En los casos siguientes, MMS actualizará las reuniones existentes de Skype Empresarial y Microsoft Teams para agregar, quitar o modificar las coordenadas de acceso telefónico:

- Al asignar o quitar una licencia del servicio de Audioconferencia de Microsoft a un usuario y dicho usuario no está habilitado para un proveedor de servicios de audioconferencia de terceros.
- Cuando cambie el proveedor de servicios de audioconferencia de un usuario de cualquier otro proveedor a Microsoft, siempre y cuando se le asigne una licencia de Audioconferencia de Microsoft. Para obtener más información, [vea Asignar Microsoft como el proveedor de servicios de audioconferencia.](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider) Tenga en cuenta también que la compatibilidad con proveedores de servicios de audioconferencia [ACP] de terceros está programada para su fin de vida el 1 de abril de 2019, tal y como se anunció [anteriormente.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)
- Cuando habilite o deshabilite la audioconferencia para un usuario.
- Al cambiar o restablecer el id. de conferencia de un usuario configurado para usar reuniones públicas.
- Al mover el usuario a un nuevo puente de audioconferencia.
- Cuando se desasigna un número de teléfono de un puente de audioconferencia. Este es un escenario complejo que requiere pasos adicionales. Para obtener más información, vea [Cambiar los números de teléfono del puente de audioconferencia.](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

No todos los cambios en la configuración de audioconferencia de un usuario activan el servicio MMS. Concretamente, los siguientes cambios no provocan que MMS actualice las reuniones:

- Cuando cambia la dirección SIP del organizador de la reunión (tanto el nombre de usuario SIP como el dominio SIP).
- Al cambiar la dirección URL de la reunión de su organización mediante el `Update-CsTenantMeetingUrl` comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Actualizar reuniones al asignar TeamsUpgradePolicy

De forma predeterminada, la migración de reuniones se activa automáticamente cuando se concede a un usuario una instancia `TeamsUpgradePolicy` de `mode=TeamsOnly` o `mode= SfBWithTeamsCollabAndMeetings` . Si no desea migrar reuniones al conceder alguno de estos modos, especifique en (si usa PowerShell) o desactive la casilla para migrar reuniones al configurar el modo de coexistencia de un usuario (si usa el Portal de administración de `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` Teams).

Tenga en cuenta lo siguiente:

- La migración de reuniones solo se invoca cuando se concede `TeamsUpgradePolicy` para un usuario específico. Si concede con o en todo el espacio empresarial, no se invoca la `TeamsUpgradePolicy` `mode=TeamsOnly` migración de `mode=SfBWithTeamsCollabAndMeetings` reuniones. 
- Solo se puede conceder el modo TeamsOnly a un usuario si el usuario está conectado. Los usuarios que se encuentran en local se deben mover usando como `Move-CsUser` se describió anteriormente.
- La concesión de un modo distinto de TeamsOnly o SfBWithTeamsCollabAndMeetings no convierte las reuniones existentes de Teams en reuniones de Skype Empresarial.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Desencadenar la migración de reuniones manualmente mediante el cmdlet de PowerShell

Además de las migraciones automáticas de reuniones, los administradores pueden desencadenar manualmente la migración de reuniones de un usuario ejecutando el `Start-CsExMeetingMigration` cmdlet. Este cmdlet pone en cola una solicitud de migración para el usuario especificado.  Además del parámetro necesario, se necesitan dos parámetros opcionales y, que le permiten especificar cómo `Identity` `SourceMeetingType` migrar `TargetMeetingType` reuniones:

**TargetMeetingType:**

- Especifica que las reuniones de Skype Empresarial siguen siendo reuniones de Skype Empresarial y las reuniones de `TargetMeetingType Current` Teams siguen siendo reuniones de Teams. Sin embargo, las coordenadas de las audioconferencias podrían cambiarse y las reuniones locales de Skype Empresarial se migrarían a Skype Empresarial Online. Este es el valor predeterminado para TargetMeetingType.
- El uso especifica que cualquier reunión existente debe migrarse a Teams, independientemente de si la reunión está hospedada en Skype Empresarial Online o local, y independientemente de si se necesitan actualizaciones de `TargetMeetingType Teams` audioconferencia. 

**SourceMeetingType:**
- El uso indica que solo deben actualizarse las reuniones de Skype Empresarial (ya sea local `SourceMeetingType SfB` o en línea).
- El `SourceMeetingType Teams` uso indica que solo deben actualizarse las reuniones de Teams.
- El uso indica que tanto las reuniones de Skype Empresarial como `SourceMeetingType All` las reuniones de Teams deben actualizarse. Este es el valor predeterminado para SourceMeetingType.
    

El ejemplo siguiente muestra cómo iniciar la migración de reuniones para el usuario ashaw@contoso.com para que todas las reuniones se migren a Teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Administrar MMS

Con Windows PowerShell, puede comprobar el estado de las migraciones en curso, desencadenar manualmente la migración de reuniones y deshabilitar la migración por completo. 

### <a name="check-the-status-of-meeting-migrations"></a>Comprobar el estado de las migraciones de reuniones

Use el `Get-CsMeetingMigrationStatus` cmdlet para comprobar el estado de las migraciones de las reuniones. A continuación puede ver algunos ejemplos.

- Para obtener un resumen del estado de todas las migraciones de MMS, ejecute el siguiente comando que proporciona una vista tabular de todos los estados de migración:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Para obtener información completa de todas las migraciones dentro de un período de tiempo específico, use los `StartTime` parámetros `EndTime` y los parámetros. Por ejemplo, el siguiente comando devolverá información detallada sobre todas las migraciones que se realizaron del 1 de octubre de 2018 al 8 de octubre de 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Para comprobar el estado de la migración de un usuario específico, use el `Identity` parámetro. Por ejemplo, el siguiente comando devolverá el estado del usuario ashaw@contoso.com:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Si ve alguna migración que haya dado error, tome medidas para resolver estos problemas lo antes posible, ya que los usuarios no podrán acceder mediante acceso telefónico a las reuniones organizadas por esos usuarios hasta que los resuelva. Si `Get-CsMeetingMigrationStatus` se muestra alguna migración en estado fallido, realice estos pasos:
 
1. Determine a qué usuarios afecta. Ejecute el siguiente comando para obtener la lista de usuarios afectados y el error concreto registrado:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Para cada usuario afectado, ejecute la Herramienta de migración de reuniones para migrar manualmente sus reuniones.

3. Si la migración sigue sin funcionar con la Herramienta de migración de reuniones, tiene dos opciones:

    - Hacer que los usuarios creen reuniones de Skype nuevas.
    - [Ponerse en contacto con el equipo de soporte técnico](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Habilitar y deshabilitar MMS

MMS está habilitado de forma predeterminada para todas las organizaciones, pero se puede deshabilitar de la siguiente manera:

- Deshabilite completamente para el inquilino. 
- Deshabilitar solo para los cambios relacionados con la audioconferencia. En este caso, MMS aún se ejecutará cuando se migre un usuario desde la implementación local a la nube o cuando conceda el modo TeamsOnly o el modo SfBWithTeamsCollabAndMeetings en `TeamsUpgradePolicy` .

Por ejemplo, puede que desee migrar manualmente todas las reuniones o deshabilitar temporalmente MMS mientras realiza cambios importantes en la configuración de audioconferencia de su organización

Para ver si MMS está habilitado para su organización, ejecute el siguiente comando. MMS se habilita si el `MeetingMigrationEnabled` parámetro es `$true` .
```PowerShell
Get-CsTenantMigrationConfiguration
```
Para habilitar o deshabilitar MMS por completo, use el `Set-CsTenantMigrationConfiguration` comando. Por ejemplo, para deshabilitar MMS, ejecute el comando siguiente:

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Si MMS está habilitado en la organización y desea comprobar si está habilitado para las actualizaciones de audioconferencia, compruebe el valor del parámetro en `AutomaticallyMigrateUserMeetings` el `Get-CsOnlineDialInConferencingTenantSettings` resultado. Para habilitar o deshabilitar MMS para audioconferencias, use `Set-CsOnlineDialInConferencingTenantSettings` . Por ejemplo, para deshabilitar MMS para audioconferencias, ejecute el comando siguiente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
