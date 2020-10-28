---
title: 'Ejemplo de script de PowerShell: limpieza de implementación de Teams'
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Use este script de PowerShell para desinstalar Teams y quitar la carpeta Teams de los usuarios.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7245e3cfee88beb51389f20bc99bbcc312f55b0
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778920"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>Ejemplo de script de PowerShell: limpieza de la implementación de equipos

Use este script para quitar equipos. Este script desinstala Teams y quita la carpeta Teams de un usuario. Ejecute este script para cada perfil de usuario en el que se instalaron Teams en un equipo.


## <a name="sample-script"></a>Ejemplo de script

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
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

## <a name="related-topics"></a>Temas relacionados

- [Instalar Microsoft Teams con Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [Implementar equipos con aplicaciones de Microsoft 365](https://docs.microsoft.com/deployoffice/teams-install)
