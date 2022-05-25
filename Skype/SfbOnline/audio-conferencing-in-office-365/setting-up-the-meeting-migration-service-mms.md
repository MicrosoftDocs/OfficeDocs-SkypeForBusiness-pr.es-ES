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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: El Servicio de migración de reuniones (MMS) es un servicio que se ejecuta en segundo plano y actualiza automáticamente las reuniones de Skype Empresarial y Microsoft Teams para los usuarios.
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671646"
---
# <a name="using-the-meeting-migration-service-mms"></a>Usar el servicio de migración de reuniones (MMS)

El Servicio de migración de reuniones (MMS) es un servicio que actualiza las reuniones existentes de un usuario en los siguientes escenarios:

- Cuando se migra un usuario de local a la nube.
- Cuando un administrador realiza un cambio en la configuración de audioconferencia del usuario
- Cuando un usuario en línea se actualiza a solo Teams, o cuando el modo de un usuario en TeamsUpgradePolicy se establece en SfBwithTeamsCollabAndMeetings
- Al usar PowerShell

De forma predeterminada, MMS se activa automáticamente en cada uno de estos casos. Además, los administradores pueden usar un cmdlet de PowerShell para desencadenar manualmente la migración de reuniones para un usuario determinado.

**Limitaciones**: el servicio de migración de reuniones no se puede usar si se aplica alguna de las siguientes opciones:

- El buzón del usuario se hospeda en Exchange local.
- El usuario se está migrando de la nube a Skype Empresarial Server local.

## <a name="how-mms-works"></a>Cómo funciona MMS

Cuando se activa MMS para un usuario determinado, se coloca una solicitud de migración para ese usuario en una cola. Para evitar las condiciones de la carrera, la solicitud en cola se procesa deliberadamente hasta que hayan pasado al menos 90 minutos. Una vez que MMS procesa la solicitud, realiza las siguientes tareas:

1. Busca en el buzón de ese usuario todas las reuniones existentes organizadas por ese usuario y programadas en el futuro.
2. En función de la información que se encuentra en el buzón del usuario, actualiza o programa nuevas reuniones en Teams para ese usuario, según el escenario exacto.
3. En el mensaje de correo electrónico, reemplaza el bloque de la reunión en línea en los detalles de la reunión.
4. Envía la versión actualizada de esa reunión a todos los destinatarios de la reunión en nombre del organizador de la reunión. Los invitados a la reunión recibirán una actualización de la reunión con las coordenadas actualizadas de la reunión en su correo electrónico.

    ![El bloque de reuniones que actualiza MMS.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

A partir del momento en que mms se desencadena, normalmente tarda unas 2 horas hasta que se migran las reuniones del usuario. Sin embargo, si el usuario tiene un gran número de reuniones, puede tardar más tiempo. Si MMS detecta un error al migrar una o varias reuniones para el usuario, periódicamente reintentará hasta 9 veces durante el intervalo de 24 horas.

**Notas**:

- Cuando migra una reunión, MMS sustituye todo el contenido del bloque de información de la reunión en línea. Por lo tanto, si el usuario ha editado ese bloque, los cambios se sobrescriben. No se verá afectado por esta acción ningún contenido que el usuario tenga en los detalles de la reunión, fuera del bloque de información de la reunión en línea. Esto significa que se seguirán incluyendo los archivos adjuntos a la invitación a la reunión.
- Solo se migran las reuniones Skype Empresarial o Microsoft Teams programadas haciendo clic en el botón **Agregar Skype reunión** en Outlook en la Web o mediante el complemento Reunión de Skype para Outlook. Si un usuario copia y pega la información de la Skype reunión en línea de una reunión en una reunión nueva, esa nueva reunión no se actualizará porque no hay ninguna reunión en el servicio original.
- El contenido de la reunión que se creó o adjuntó a la reunión (pizarras, sondeos, etc.) no se conservará después de ejecutar MMS. Si sus organizadores de reuniones adjuntaron contenido a las reuniones antes de la ejecución de MMS, será necesario volver a crear el contenido una vez finalizada la operación.
- También se sobrescribirá el vínculo a las notas de la reunión compartidas en el elemento de calendario y en la reunión de Skype. Tenga en cuenta que las notas de la reunión almacenadas en OneNote seguirán estando ahí; solo se sobrescribe el vínculo a las notas compartidas.
- Las reuniones que tengan más de 250 participantes (incluido el organizador) no se migrarán.
- Es posible que algunos caracteres UNICODE del cuerpo de la invitación se actualicen incorrectamente a uno de los siguientes caracteres especiales: ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Activación de MMS para un usuario

En esta sección se describe lo que ocurre cuando se activa MMS en cada uno de los siguientes casos:

- Cuando se migra un usuario de local a la nube
- Cuando un administrador realiza un cambio en la configuración de audioconferencia del usuario
- Cuando el modo del usuario en TeamsUpgradePolicy se establece en TeamsOnly o SfBWithTeamsCollabAndMeetings (mediante Powershell o el Portal de Teams Administración)
- Al usar el cmdlet de PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Actualización de reuniones al mover un usuario local a la nube

Este es el escenario más común en el que MMS ayuda a crear una transición más fluida para los usuarios. Sin la migración de reuniones, las reuniones existentes organizadas por un usuario en Skype Empresarial Server local ya no funcionarán una vez que el usuario se mueva en línea. Por lo tanto, al usar las herramientas de administración locales (o `Move-CsUser` el Administración Panel de control) para mover un usuario a la nube, las reuniones existentes se mueven automáticamente a la nube y se convierten en TeamsOnly.

Si se ha asignado al usuario una licencia de Audioconferencia antes de moverlo a la nube, las reuniones se crearán con coordenadas de acceso telefónico local. Si mueve un usuario de un entorno local a la nube y su intención es que ese usuario use Audioconferencia, le recomendamos que primero asigne la audioconferencia antes de mover el usuario para que solo se desencadene una migración de reuniones.

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Actualización de reuniones cuando cambia la configuración de audioconferencia de un usuario

En los siguientes casos, MMS actualizará las Skype Empresarial existentes y Microsoft Teams reuniones para agregar, quitar o modificar las coordenadas de acceso telefónico local:

- Al asignar o quitar una licencia de servicio de Microsoft Audioconferencia a un usuario y ese usuario no está habilitado para un proveedor de servicios de audioconferencia de terceros.
- Al cambiar el proveedor de servicios de audioconferencia de un usuario de cualquier otro proveedor a Microsoft, siempre que se asigne al usuario una licencia de Microsoft Audioconferencia. Para obtener más información, vea [Asignar Microsoft como el proveedor de servicios de audioconferencia](./assign-microsoft-as-the-audio-conferencing-provider.md). Tenga también en cuenta que el soporte técnico para proveedores de audioconferencias de terceros [ACP] está programado para el fin de vida el 1 de abril de 2019, como [se ha anunciado anteriormente](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md).
- Al habilitar o deshabilitar la audioconferencia para un usuario.
- Al cambiar o restablecer el id. de conferencia de un usuario configurado para usar reuniones públicas.
- Al mover el usuario a un puente de audioconferencia nuevo.
- Cuando un número de teléfono de un puente de audioconferencia no está asignado. Este es un escenario complejo que requiere pasos adicionales. Para obtener más información, vea [Cambiar los números de teléfono en el puente de audioconferencia](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

No todos los cambios en la configuración de audioconferencia de un usuario desencadenan MMS. Concretamente, los siguientes cambios no provocan que MMS actualice las reuniones:

- Cuando cambia la dirección SIP del organizador de la reunión (tanto el nombre de usuario SIP como el dominio SIP).
- Al cambiar la dirección URL de la reunión de su organización con el `Update-CsTenantMeetingUrl` comando.

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Actualización de reuniones al asignar TeamsUpgradePolicy

De forma predeterminada, la migración de reuniones se activa automáticamente cuando se concede a un usuario una instancia de `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode= SfBWithTeamsCollabAndMeetings`. Si no desea migrar reuniones al conceder cualquiera de estos modos, especifique `MigrateMeetingsToTeams $false` en `Grant-CsTeamsUpgradePolicy` (si usa PowerShell) o desactive la casilla para migrar reuniones al establecer el modo de coexistencia de un usuario (si usa el portal de administración de Teams).

Tenga también en cuenta lo siguiente:

- La migración de reuniones solo se invoca cuando concede `TeamsUpgradePolicy` para un usuario específico. Si concede `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode=SfBWithTeamsCollabAndMeetings` en todo el *espacio* empresarial, no se invoca la migración de reuniones.
- Solo se puede conceder al usuario el modo TeamsOnly si el usuario está alojado en línea. Los usuarios que se alojan en local deben moverse usando `Move-CsUser` como se describió anteriormente.
- Conceder un modo distinto de TeamsOnly o SfBWithTeamsCollabAndMeetings no convierte las reuniones de Teams existentes a reuniones Skype Empresarial.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Desencadenar la migración de reuniones manualmente a través del cmdlet de PowerShell

Además de las migraciones automáticas de reuniones, los administradores pueden desencadenar manualmente la migración de reuniones de un usuario mediante la ejecución del cmdlet `Start-CsExMeetingMigration`. Este cmdlet pone en cola una solicitud de migración para el usuario especificado.  Además del parámetro necesario `Identity` , toma dos parámetros opcionales `SourceMeetingType` y `TargetMeetingType`, que le permiten especificar cómo migrar las reuniones:

**TargetMeetingType:**

- Usando `TargetMeetingType Current` especifica que las reuniones Skype Empresarial permanecen Skype Empresarial las reuniones y las reuniones Teams permanecen Teams reuniones. Sin embargo, es posible que se cambien las coordenadas de las audioconferencias y que las reuniones de Skype Empresarial locales se migren a Skype Empresarial En línea. Este es el valor predeterminado de TargetMeetingType.
- Mediante `TargetMeetingType Teams` especifica que cualquier reunión existente debe migrarse a Teams, independientemente de si la reunión se hospeda en Skype Empresarial en línea o local, e independientemente de si se requieren actualizaciones de audioconferencia.

**SourceMeetingType:**

- El uso `SourceMeetingType SfB` indica que solo Skype Empresarial reuniones (tanto locales como en línea) deben actualizarse.
- Usar `SourceMeetingType Teams` indica que solo Teams reuniones deben actualizarse.
- Usar `SourceMeetingType All` indica que deben actualizarse tanto las reuniones de Skype Empresarial como las reuniones de Teams. Este es el valor predeterminado de SourceMeetingType.

El ejemplo siguiente muestra cómo iniciar la migración de reuniones para ashaw@contoso.com de usuario para que todas las reuniones se migren a Teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>Administrar MMS

Con Windows PowerShell, puede comprobar el estado de las migraciones en curso, desencadenar manualmente la migración de reuniones y deshabilitar la migración por completo.

### <a name="check-the-status-of-meeting-migrations"></a>Comprobar el estado de las migraciones de reuniones

Use el `Get-CsMeetingMigrationStatus` cmdlet para comprobar el estado de las migraciones de reuniones. A continuación puede ver algunos ejemplos.

- Para obtener un estado de resumen de todas las migraciones de MMS, ejecute el comando siguiente que proporciona una vista tabular de todos los estados de migración:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- Para obtener todos los detalles de todas las migraciones dentro de un período de tiempo específico, use los `StartTime` parámetros y `EndTime` . Por ejemplo, el siguiente comando devolverá todos los detalles de todas las migraciones que se realizaron del 1 de octubre de 2018 al 8 de octubre de 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- Para comprobar el estado de la migración de un usuario específico, use el `Identity` parámetro. Por ejemplo, el siguiente comando devolverá el estado del usuario ashaw@contoso.com:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

Si ve alguna migración que haya fallado, tome medidas para resolver estos problemas lo antes posible, ya que los usuarios no podrán llamar a las reuniones organizadas por esos usuarios hasta que usted los resuelva. Si `Get-CsMeetingMigrationStatus` se muestra alguna migración con un estado de error, siga estos pasos:

1. Determine a qué usuarios afecta. Ejecute el siguiente comando para obtener la lista de usuarios afectados y el error concreto registrado:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. Para cada usuario afectado, revise el valor de la propiedad LastMessage para determinar por qué no se pudo realizar la migración de la reunión y qué acción correctiva realizar. Una vez que se haya realizado la acción correctiva, vuelva a desencadenar la migración de reuniones para los usuarios afectados con el `Start-CsExMeetingMigration` cmldet de PowerShell, como se describió anteriormente.

3. Si la migración sigue sin funcionar, tiene dos opciones:

    - Hacer que los usuarios creen reuniones de Skype nuevas.
    - [Ponerse en contacto con el equipo de soporte técnico](/microsoft-365/Admin/contact-support-for-business-products).

El `Get-CsMeetingMigrationStatus` cmdlet se puede usar para recuperar el estado de las migraciones que se desencadenaron en los últimos 150 días. Los registros de migraciones de más de 150 días se purgan del sistema.

### <a name="enabling-and-disabling-mms"></a>Habilitar y deshabilitar MMS

MMS está habilitado de manera predeterminada para todas las organizaciones, pero se puede deshabilitar de la siguiente manera:

- Deshabilite completamente para el espacio empresarial.
- Deshabilite solo los cambios relacionados con las audioconferencias. En este caso, MMS seguirá ejecutándose cuando se migre un usuario de local a la nube o al conceder el modo TeamsOnly o SfBWithTeamsCollabAndMeetings en `TeamsUpgradePolicy`.

Por ejemplo, es posible que desee migrar manualmente todas las reuniones o deshabilitar temporalmente MMS mientras realiza cambios importantes en la configuración de audioconferencia de su organización

Para ver si MMS está habilitado para su organización, ejecute el siguiente comando. MMS se habilita si el `MeetingMigrationEnabled` parámetro es `$true`.

```PowerShell
Get-CsTenantMigrationConfiguration
```

Si MMS está habilitado en la organización y desea comprobar si está habilitado para las actualizaciones de audioconferencia, compruebe el valor del `AutomaticallyMigrateUserMeetings` parámetro en la salida desde `Get-CsOnlineDialInConferencingTenantSettings`. Para habilitar o deshabilitar MMS para audioconferencia, use `Set-CsOnlineDialInConferencingTenantSettings`. Por ejemplo, para deshabilitar MMS para audioconferencia, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Mover usuarios entre la implementación local y la nube](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
