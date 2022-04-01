---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593702"
---
1. Instale PowerShell versión 7 o posterior. Para obtener instrucciones paso a paso, vea [Instalar PowerShell en Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Ejecute PowerShell en modo de administrador.
1. Instale el módulo Graph PowerShell de Microsoft.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Compruebe que es la versión 1.6.1 o posterior.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Instale el Teams vista previa de PowerShell.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Compruebe que es al menos la versión 4.1.0 y que contiene los cmdlets del conector Turnos.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. Instale el módulo de PowerShell de MSAL.

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. Establezca PowerShell para que salga si se produce un error al ejecutar el script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Permitir que los scripts se ejecuten en Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```