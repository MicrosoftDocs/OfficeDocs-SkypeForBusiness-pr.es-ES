---
title: 'Ejemplo de script de PowerShell: Teams de implementación'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Use este script de PowerShell para desinstalar Teams y quitar la carpeta Teams para los usuarios.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96f3c7f6d9d9fa52edd09b7ecf690f43d6730367
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428196"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>Ejemplo de script de PowerShell: Teams de implementación

Use este script para quitar Teams. Este script desinstala Teams y quita la carpeta Teams para un usuario. Ejecute este script para cada perfil de usuario en el que Teams instalado en un equipo.


## <a name="sample-script"></a>Ejemplo de script

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

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
- [Implementar Teams con Aplicaciones Microsoft 365](/deployoffice/teams-install)
