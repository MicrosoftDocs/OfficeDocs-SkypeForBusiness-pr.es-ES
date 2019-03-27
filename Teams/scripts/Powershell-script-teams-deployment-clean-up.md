---
title: 'Ejemplo de script de PowerShell: asistencia con la limpieza de implementaciones de Microsoft Teams'
ms.reviewer: ''
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: Use este script de PowerShell para limpiar Microsoft Teams en máquinas de destino o usuarios específicos.
localization_priority: Normal
ms.openlocfilehash: a047326a1598ea497318b77ce27c09c6807f25dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879907"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="80bca-103">Ejemplo de script de PowerShell: limpieza de implementaciones de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80bca-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="80bca-104">Este script de PowerShell se puede utilizar para la limpieza de Microsoft Teams en usuarios o máquinas de destino.</span><span class="sxs-lookup"><span data-stu-id="80bca-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="80bca-105">Se debe ejecutar para cada usuario de una máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="80bca-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="80bca-106">Ejemplo de script</span><span class="sxs-lookup"><span data-stu-id="80bca-106">Sample script</span></span>

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


