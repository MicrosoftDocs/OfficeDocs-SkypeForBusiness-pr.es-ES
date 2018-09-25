---
title: 'Ejemplo de script de PowerShell: asistencia con la limpieza de implementaciones de Microsoft Teams'
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
description: Use este script de PowerShell para limpiar Microsoft Teams en máquinas de destino o usuarios específicos.
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
ms.openlocfilehash: 7a0d12fb59b8f5f513ed4f0c64502d6c9ff369e2
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011900"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>Ejemplo de script de PowerShell: limpieza de implementaciones de Microsoft Teams
-------------------------------------------------------------------------

Puede aprovechar esta secuencia de comandos de PowerShell para la limpieza de Microsoft Teams desde equipos de destino o los usuarios. Se debe ejecutar para todos los usuarios en un equipo de destino. 


## <a name="sample-script"></a>Ejemplo de script

````powershell
<#
.SYNOPSIS
This script allows you to uninstall the Microsoft Teams app and remove Teams directory for a user.
.DESCRIPTION
Use this script to clear the installed Microsoft Teams application. Run this PowerShell script for each user profile for which the Teams App was installed on a machine. After the PowerShell has executed on all user profiles, Teams can be redeployed.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if (Test-Path -Path $TeamsUpdateExePath) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process -FilePath $TeamsUpdateExePath -ArgumentList "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    if (Test-Path -Path $TeamsPath) {
        Write-Host "Deleting Teams directory"
        Remove-Item –Path $TeamsPath -Recurse
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}

````


