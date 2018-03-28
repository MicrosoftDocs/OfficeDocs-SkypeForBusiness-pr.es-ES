---
title: Ejemplo de secuencia de comandos de PowerShell - le ayuda con la implementación de equipos de Microsoft de limpieza
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: Use este script de PowerShell para crear un equipo público que abarque toda la empresa en Teams.
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1466a08d493538eadb6cd2bfc2f50ac15acb0fa7
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="627cc-103">Ejemplo de secuencia de comandos de PowerShell: implementación de Microsoft Teams limpiar</span><span class="sxs-lookup"><span data-stu-id="627cc-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="627cc-104">Esta secuencia de comandos de PowerShell se puede aprovechar para la limpieza de Microsoft Teams de machines\users de destino.</span><span class="sxs-lookup"><span data-stu-id="627cc-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines\users.</span></span> <span data-ttu-id="627cc-105">Se debe ejecutar para cada usuario en un equipo destino.</span><span class="sxs-lookup"><span data-stu-id="627cc-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="627cc-106">Ejemplo de script</span><span class="sxs-lookup"><span data-stu-id="627cc-106">Sample script</span></span>

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
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````


