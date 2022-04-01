---
title: Usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management
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
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593691"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management

## <a name="overview"></a>Información general

El [Microsoft Teams de turnos para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) le permite integrar la aplicación Turnos en Microsoft Teams con Blue Yonder Workforce Management (Blue Yonder WFM). Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en Blue Yonder WFM desde Turnos.

Puede usar el Asistente [para conectores de turnos](shifts-connector-wizard.md) en el Centro de administración de Microsoft 365 [o PowerShell](shifts-connector-blue-yonder-powershell-setup.md) para configurar una conexión. Una vez configurada una conexión, puede administrarla mediante [cmdlets de PowerShell del conector de Turnos](#shifts-connector-cmdlets).

En este artículo se describe cómo usar PowerShell para hacer lo siguiente:

- [Comprobar el estado de configuración de la conexión](#check-connection-setup-status)
- [Ver un informe de errores para una conexión](#view-an-error-report-for-a-connection)
- [Resolver errores de conexión](#resolve-connection-errors)
- [Cambiar la configuración de conexión](#change-connection-settings)
- [Desamapear un equipo de una conexión y asignarlo a otra conexión](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Deshabilitar la sincronización para una conexión](#disable-sync-for-a-connection)

> [!NOTE]
> En este artículo se presupone que ya ha configurado una conexión a Blue Yonder WFM, ya sea mediante el asistente o PowerShell.

## <a name="before-you-begin"></a>Antes de empezar

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configure su entorno

> [!NOTE]
> Asegúrese de seguir estos pasos para configurar su entorno antes de ejecutar cualquiera de los comandos o scripts de este artículo.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>Comprobar el estado de configuración de la conexión
<a name="setup_status"> </a>

Para comprobar el estado de la conexión que ha configurado con el id. de operación que recibió por correo electrónico:

1. [Configure su entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Ejecute el siguiente comando. Este comando le proporciona el estado general de las asignaciones de equipo para la conexión.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Para obtener más información, [vea Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps).

## <a name="view-an-error-report-for-a-connection"></a>Ver un informe de errores para una conexión
<a name="error_report"> </a>

Puede ejecutar un informe que muestre detalles de error para una conexión. En el informe se enumeran las asignaciones de usuario y de equipo que se han hecho correctamente y que no se han podido hacer correctamente. También proporciona información sobre los problemas relacionados con las cuentas asociadas a la conexión.

1. [Configure su entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Obtenga una lista de informes de errores para una conexión.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Para ver un informe de errores específico, ejecute el siguiente comando:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Para obtener más información, [vea Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps).

## <a name="resolve-connection-errors"></a>Resolver errores de conexión

### <a name="user-mapping-errors"></a>Errores de asignación de usuarios

Es posible que se produzcan errores de asignación de usuarios si uno o varios usuarios de un sitio wfm de Yonder azul no son miembros del equipo asignado en Teams. Para resolver este problema, asegúrese de que los usuarios del equipo asignado coincidan con los usuarios del sitio WFM de Yonder azul.

Para ver los detalles de los usuarios no configurados, [configure](#set-up-your-environment) su entorno (si aún no lo ha hecho) y, a continuación, ejecute el siguiente script.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

### <a name="account-authorization-errors"></a>Errores de autorización de la cuenta

Los errores de autorización de la cuenta pueden producirse si las credenciales de la cuenta de servicio WFM de Blue Yonder o Microsoft 365 del sistema son incorrectas o no tienen los permisos necesarios.

Para cambiar la cuenta de servicio WF Microsoft 365 M blue yonder o las credenciales de una cuenta del sistema para la conexión, puede ejecutar el cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) o usar el script de PowerShell en la sección Cambiar configuración de conexión de este artículo.[](#change-connection-settings)

## <a name="change-connection-settings"></a>Cambiar la configuración de conexión
<a name="change_settings"> </a>

Use este script para cambiar la configuración de conexión. Configuración que puede cambiar incluyen la contraseña y la cuenta de servicio WFM de Blue Yonder, Microsoft 365 cuenta del sistema, asignaciones de equipo y configuración de sincronización.

La configuración de sincronización incluye la frecuencia de sincronización (en minutos) y los datos de programación que se sincronizan entre Blue Yonder WFM y Mayúss. Los datos de programación se definen en los siguientes parámetros, que puede ver ejecutando [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps).

- El **parámetro enabledConnectorScenarios** define los datos que se sincronizan de Blue Yonder WFM a Shifts. Las opciones son , , `OpenShift`, , , `TimeOffRequest``TimeOff`. `OpenShiftRequest``UserShiftPreferences``SwapRequest``Shift`
- El **parámetro enabledWfiScenarios** define los datos que se sincronizan de Mayús a Blue Yonder WFM. Las opciones son `SwapRequest`, `TimeOffRequest``OpenShiftRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Si decide no sincronizar turnos abiertos, solicitudes de turno abiertas, solicitudes de intercambio u solicitudes de permiso entre Turnos y Wfm de Yonder azul, hay otro paso que debe hacer para ocultar la capacidad en Turnos. Después de ejecutar este script, asegúrese de seguir los pasos de la sección Deshabilitar turnos abiertos, abrir solicitudes de [turnos,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) solicitudes de intercambio y solicitudes de permiso más adelante en este artículo.

> [!IMPORTANT]
> Para las opciones de configuración que no quiera cambiar, deberá volver a introducir la configuración original cuando se le solicite por el script.

[Configure su entorno](#set-up-your-environment) (si aún no lo ha hecho) y, a continuación, ejecute el siguiente script.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deshabilitar turnos abiertos, abrir solicitudes de turnos, solicitudes de intercambio y solicitudes de permiso

> [!IMPORTANT]
> Siga estos pasos solo si ha elegido deshabilitar turnos abiertos, abrir solicitudes de turno, solicitudes de intercambio o solicitudes de permiso mediante el script de la sección Cambiar configuración [](#change-connection-settings) de conexión anteriormente en este artículo o mediante el cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps). Al completar este paso, se oculta la capacidad en Turnos. Sin este segundo paso, los usuarios seguirán teniendo la capacidad en Turnos y recibirán un mensaje de error de "operación no compatible" si intentan usarlo.

Para ocultar turnos abiertos, solicitudes de intercambio y solicitudes de permiso en Turnos, use el tipo de recurso programación de Graph API para establecer los siguientes [parámetros para cada](/graph/api/resources/schedule?view=graph-rest-1.0) equipo asignado a ```false``` un sitio WFM de Yonder azul:

- Abrir turnos: ```openShiftsEnabled```
- Solicitudes de intercambio:  ```swapShiftsRequestsEnabled```
- Solicitudes de permiso: ```timeOffRequestsEnabled```

Para ocultar las solicitudes de turnos abiertos en Turnos, vaya a **Configuración** en Turnos y, después, desactive la configuración **Abrir turnos**.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Desamapear un equipo de una conexión y asignarlo a otra conexión

> [!NOTE]
> La Microsoft 365 del sistema debe ser la misma para ambas conexiones. Si no es así, verá el mensaje de error "Este perfil de actor designado no tiene privilegios de propiedad de equipo".

Si desea desamapear un equipo de una conexión y asignarlo a otra conexión:

1. [Configure su entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Vea una lista de todas las asignaciones de equipo para una conexión.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Quite una asignación de equipo de la conexión.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Asigne el equipo a otra conexión.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Para obtener más información, vea [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps) y [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps).

## <a name="disable-sync-for-a-connection"></a>Deshabilitar la sincronización para una conexión

Use este script para deshabilitar la sincronización de una conexión. Tenga en cuenta que este script no quita ni elimina una conexión. Desactiva la sincronización para que no se sincronice ningún dato entre Mayúss y Blue Yonder WFM para la conexión que especifique.

[Configure su entorno](#set-up-your-environment) (si aún no lo ha hecho) y, a continuación, ejecute el siguiente script.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

## <a name="shifts-connector-cmdlets"></a>Cmdlets de conector de turnos

Para obtener ayuda con los cmdlets del conector de Turnos, busque **CsTeamsShiftsConnection** en la Teams [cmdlet de PowerShell](/powershell/teams/intro?view=teams-ps). A continuación se incluyen vínculos a algunos cmdlets que se usan con frecuencia.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de turnos](shifts-connectors.md)
- [Usar el Asistente para conectores de turnos para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Usar PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Administrar la aplicación Turnos](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Descripción de PowerShell para Teams](../../teams-powershell-overview.md)