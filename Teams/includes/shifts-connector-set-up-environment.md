---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976027"
---
1. Instale PowerShell versión 7 o posterior. Para obtener instrucciones detalladas, vea [Instalar PowerShell en Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Ejecute PowerShell en modo de administrador.
1. Instale el módulo De Microsoft Graph PowerShell.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Compruebe que es la versión 1.6.1 o posterior.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Instale el módulo de PowerShell de Teams Preview.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Compruebe que es al menos la versión 4.1.0 y que contiene los cmdlets del conector Shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. Establezca PowerShell para que salga si se produce un error al ejecutar el script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Permitir que los scripts se ejecuten en Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```