---
title: Use PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4edf815a3ce21a820fa292a06d41275c97d78a5
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647817"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Use PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management

## <a name="overview"></a>Información general

El [conector Turnos de Microsoft Teams para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) le permite integrar la aplicación Turnos en Microsoft Teams con Blue Yonder Workforce Management (Blue Yonder WFM). Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en Blue Yonder WFM desde Turnos.

Puede usar el [asistente del conector Mayús](shifts-connector-wizard.md) en la Centro de administración de Microsoft 365 o [PowerShell](shifts-connector-blue-yonder-powershell-setup.md) para configurar una conexión. Después de configurar una conexión, puede administrarla mediante [los cmdlets de PowerShell del conector Mayús](#shifts-connector-cmdlets).

En este artículo se describe cómo usar PowerShell para hacer lo siguiente:

- [Comprobar el estado de configuración de la conexión](#check-connection-setup-status)
- [Ver un informe de errores para una conexión](#view-an-error-report-for-a-connection)
- [Resolver errores de conexión](#resolve-connection-errors)
- [Cambiar la configuración de conexión](#change-connection-settings)
- [Anular la asignación de un equipo de una conexión y asignarlo a otra conexión](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Deshabilitar la sincronización para una conexión](#disable-sync-for-a-connection)

> [!NOTE]
> En este artículo se supone que ya ha configurado una conexión a Blue Yonder WFM, ya sea mediante el asistente o PowerShell.

## <a name="before-you-begin"></a>Antes de empezar

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configure su entorno

> [!NOTE]
> Asegúrese de seguir estos pasos para configurar el entorno antes de ejecutar cualquiera de los comandos o scripts de este artículo.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. Conéctese a Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Cuando se le solicite, inicie sesión con sus credenciales de administrador. Ahora está configurado para ejecutar los scripts de este artículo y los cmdlets del conector Shifts.

## <a name="check-connection-setup-status"></a>Comprobar el estado de configuración de la conexión

<a name="setup_status"> </a>

Para comprobar el estado de la conexión que configuró con el id. de la operación que recibió por correo electrónico:

1. [Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Ejecute el comando siguiente. Este comando le proporciona el estado general de las asignaciones de equipo para la conexión.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Para obtener más información, vea [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation).

## <a name="view-an-error-report-for-a-connection"></a>Ver un informe de errores para una conexión

<a name="error_report"> </a>

Puede ejecutar un informe que muestre los detalles de error de una conexión. En el informe se muestra una lista de asignaciones de usuarios y equipos que se realizaron correctamente y con errores. También proporciona información sobre cualquier problema relacionado con las cuentas asociadas con la conexión.

1. [Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Obtenga una lista de informes de errores para una conexión.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Para ver un informe de errores específico, ejecute el siguiente comando:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Para obtener más información, vea [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport).

## <a name="resolve-connection-errors"></a>Resolver errores de conexión

### <a name="user-mapping-errors"></a>Errores de asignación de usuarios

Los errores de asignación de usuarios pueden producirse si uno o más usuarios de un WFM instancia de Blue Yonder no son miembros del equipo asignado en Teams. Para resolver este problema, asegúrese de que los usuarios del equipo asignado coincidan con los usuarios de la instancia de WFM de Blue Yonder.

Para ver los detalles de los usuarios no asignados, [configure el entorno](#set-up-your-environment) (si aún no lo ha hecho) y, después, ejecute el siguiente script.

```powershell
#View sync errors script
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>Errores de autorización de cuenta

Pueden producirse errores de autorización de la cuenta si las credenciales de la cuenta del sistema de Blue Yonder WFM o Microsoft 365 son incorrectas o no tienen los permisos necesarios.

Para cambiar su cuenta de servicio de Blue Yonder WFM o las credenciales de la cuenta del sistema de Microsoft 365 para la conexión, puede ejecutar el cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) o usar el script de PowerShell en la sección [Cambiar configuración de conexión](#change-connection-settings) de este artículo.

## <a name="change-connection-settings"></a>Cambiar la configuración de conexión
<a name="change_settings"> </a>

Use este script para cambiar la configuración de conexión. Entre las opciones de configuración que puede cambiar se incluyen la cuenta de servicio de Blue Yonder WFM y la contraseña, la cuenta del sistema de Microsoft 365, las asignaciones de equipos y la configuración de sincronización.

La configuración de sincronización incluye la frecuencia de sincronización (en minutos) y los datos de programación que se sincronizan entre Blue Yonder WFM y Shifts. Los datos de programación se definen en los siguientes parámetros, que puede ver ejecutando [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector).

- El parámetro **enabledConnectorScenarios** define los datos que se sincronizan de Blue Yonder WFM a Shifts. Las opciones son `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff`. `TimeOffRequest`
- El parámetro **enabledWfiScenarios** define los datos que se sincronizan de Shifts a Blue Yonder WFM. Las opciones son `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Si elige no sincronizar turnos abiertos, solicitudes de turnos abiertas, solicitudes de intercambio o solicitudes de permisos entre turnos y Blue Yonder WFM, hay otro paso que debe hacer para ocultar la funcionalidad en Turnos. Después de ejecutar este script, asegúrese de seguir los pasos de la sección [Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de permisos](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) más adelante en este artículo.

> [!IMPORTANT]
> Para las opciones de configuración que no desea cambiar, tendrá que volver a introducir la configuración original cuando se le solicite por el script.

[Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho) y, a continuación, ejecute el siguiente script.

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de permisos

> [!IMPORTANT]
> Siga estos pasos solo si decide deshabilitar turnos abiertos, solicitudes de turno abiertas, solicitudes de intercambio o solicitudes de permisos mediante el script de la sección [Cambiar configuración de conexión](#change-connection-settings) anteriormente en este artículo o mediante el cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) . Al completar este paso, se oculta la funcionalidad en Turnos. Sin este segundo paso, los usuarios seguirán viendo la funcionalidad en Turnos y recibirán un mensaje de error de "operación no compatible" si intentan usarla.

Para ocultar los turnos abiertos, las solicitudes de permuta y las solicitudes de permisos en turnos, use el [Graph API tipo de recurso de programación](/graph/api/resources/schedule) para establecer los siguientes parámetros ```false``` para cada equipo que haya asignado a una instancia de blue yonder WFM:

- Abrir turnos: ```openShiftsEnabled```
- Solicitudes de intercambio:  ```swapShiftsRequestsEnabled```
- Solicitudes de permisos: ```timeOffRequestsEnabled```

Para ocultar las solicitudes de turnos abiertas en Turnos, vaya a **Configuración** en Turnos y desactive la configuración **Abrir turnos** .

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Anular la asignación de un equipo de una conexión y asignarlo a otra conexión

> [!NOTE]
> La cuenta del sistema de Microsoft 365 debe ser la misma para ambas conexiones. Si no es así, recibirá el mensaje de error "Este perfil de actor designado no tiene privilegios de propiedad del equipo".

Si desea anular la asignación de un equipo de una conexión y asignarlo a otra conexión:

1. [Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Ver una lista de todas las asignaciones de equipo para una conexión.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Quitar la asignación de un equipo de la conexión.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Asigne el equipo a otra conexión.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Para obtener más información, vea [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) y [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap).

## <a name="disable-sync-for-a-connection"></a>Deshabilitar la sincronización para una conexión

Use este script para deshabilitar la sincronización para una conexión. Tenga en cuenta que este script no quita ni elimina una conexión. Desactiva la sincronización para que no se sincronicen datos entre Turnos y Blue Yonder WFM para la conexión que especifique.

[Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho) y, a continuación, ejecute el siguiente script.

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Cmdlets de conector de Turnos

Para obtener ayuda con los cmdlets de conector de Shifts, busque **CsTeamsShiftsConnection** en la [referencia de cmdlets de PowerShell de Teams](/powershell/teams/intro). Estos son vínculos a algunos cmdlets de uso habitual.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Usar el asistente del conector Mayús para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Usar PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Administrar la aplicación Turnos](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Descripción de PowerShell para Teams](../../teams-powershell-overview.md)
