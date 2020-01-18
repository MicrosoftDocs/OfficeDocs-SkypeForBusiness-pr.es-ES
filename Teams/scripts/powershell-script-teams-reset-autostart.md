---
title: 'Ejemplo de script de PowerShell: restablecer la configuración de AutoStart en Teams'
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Use este script de PowerShell para restablecer la configuración de AutoStart en Teams para cada usuario.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 789b187dccb0cc654e3b8ad771b56627d58057a8
ms.sourcegitcommit: 416a2d404a2ea15b484cd7579035e7f2282ac2cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233342"
---
# <a name="powershell-script-sample---reset-the-autostart-setting-in-teams"></a>Ejemplo de script de PowerShell: restablecer la configuración de AutoStart en Teams

Use este script para restablecer la configuración de AutoStart de Teams para cada usuario. Esto incluye cualquier valor establecido por el usuario o la aplicación de Teams. De forma predeterminada, Teams se inicia automáticamente cuando un usuario inicia sesión en el equipo después de instalarlo.

Si ya ha implementado Teams y desea establecer la [configuración de directiva de grupo impedir que Microsoft Teams se inicie automáticamente después](../msi-deployment.md#use-group-policy-recommended) de la instalación para deshabilitar el inicio automático de equipo, tendrá que establecer la configuración de directiva de grupo en el valor que desee y, a continuación, ejecutar este script.

Después de iniciar Teams para un usuario, la configuración de AutoStart no se puede deshabilitar mediante la Directiva de grupo.

## <a name="sample-script"></a>Ejemplo de script

````powershell
<#
.SYNOPSIS
This script allows you to reset all autostart settings to the default settings for Teams.
.DESCRIPTION
If you want to use the "Prevent Microsoft Teams from starting automatically after installation"
Group Policy setting, make sure you first set the Group Policy setting to the value you want 
before you run this script.
#>

$ErrorActionPreference = "Stop"

$TeamsDesktopConfigJsonPath = [System.IO.Path]::Combine($env:APPDATA, 'Microsoft', 'Teams', 'desktop-config.json')

$TeamsUpdatePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

Function Test-RegistryValue {
    param(
        [Alias("PSPath")]
        [Parameter(Position = 0, Mandatory = $true, ValueFromPipeline = $true, ValueFromPipelineByPropertyName = $true)]
        [String]$Path
        ,
        [Parameter(Position = 1, Mandatory = $true)]
        [String]$Name
    ) 

    process {
        if (Test-Path $Path) {
            $Key = Get-Item -LiteralPath $Path
            if ($null -ne $Key.GetValue($Name, $null)) {
                $true
            } else {
                $false
            }
        } else {
            $false
        }
    }
}

Function Test-Remove-RegistryValue {
    param (
        [Alias("PSPath")]
        [Parameter(Position = 0, Mandatory = $true, ValueFromPipeline = $true, ValueFromPipelineByPropertyName = $true)]
        [String]$Path
        ,
        [Parameter(Position = 1, Mandatory = $true)]
        [String]$Name
    )

    process {
        if (Test-RegistryValue -Path $Path -Name $Name) {
            Write-Host "Removing registry key $Path\$Name"
            Remove-ItemProperty -Path $Path -Name $Name
        }
    }
}

# when determining whether Teams should be auto-started we are checking three flags
Write-Host "Removing Auto-Start-related artifacts"

# 0. Close Teams, if running
$teamsProc = Get-Process -name Teams -ErrorAction SilentlyContinue
if ($null -ne $teamsProc) {
    Write-Host  "Stopping Microsoft Teams..."
    Stop-Process -Name Teams -Force
    # wait some time
    Start-Sleep 5
} else {
    Write-Host  "No running Teams process found"
}

# 1. Check that Teams process isn't still running
$teamsProc = Get-Process -name Teams -ErrorAction SilentlyContinue

if($null -eq $teamsProc) {
    # 2. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\LoggedInOnce registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "LoggedInOnce"

    # 3. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\HomeUserUpn registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "HomeUserUpn"

    # 4. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\DeadEnd registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "DeadEnd"

    # 5. remove HKCU:\Software\Microsoft\Office\Outlook\Addins\TeamsAddin.FastConnect registry key
    Remove-Item -Path "HKCU:\Software\Microsoft\Office\Outlook\Addins\TeamsAddin.FastConnect" -ErrorAction SilentlyContinue

    # 6. restore HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run\com.squirrel.Teams.Teams
    if (!(Test-RegistryValue -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "com.squirrel.Teams.Teams")) {
        Write-Host "Restoring registry key HKCU\Software\Microsoft\Windows\CurrentVersion\Run\com.squirrel.Teams.Teams"
        Set-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "com.squirrel.Teams.Teams" -Value "$TeamsUpdatePath --processStart ""Teams.exe"" --process-start-args ""--system-initiated"""
    }

    # 7. We are checking whether there are entries 'isLoggedOut' and 'openAtLogin' in the desktop-config.json file
    if (Test-Path -Path $TeamsDesktopConfigJsonPath) {
        Write-Host "Changing entries 'guestTenantId', 'isLoggedOut' and 'openAtLogin' in the desktop-config.json, if exist"

        # open desktop-config.json file
        $desktopConfigFile = Get-Content -path $TeamsDesktopConfigJsonPath -Raw | ConvertFrom-Json
        $desktopConfigFile.PSObject.Properties.Remove("guestTenantId")
        $desktopConfigFile.PSObject.Properties.Remove("isLoggedOut")
        try {
            $desktopConfigFile.appPreferenceSettings.openAtLogin = $true
        } catch {
            Write-Host  "openAtLogin JSON element doesn't exist"
        }
        $desktopConfigFile | ConvertTo-Json -Compress | Set-Content -Path $TeamsDesktopConfigJsonPath -Force
    }
} else {
    Write-Host  "Teams process is still running, aborting script execution"
}
````

## <a name="related-topics"></a>Temas relacionados

- [Instalar Teams con MSI](../msi-deployment.md)
- [Implementar Teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install)
