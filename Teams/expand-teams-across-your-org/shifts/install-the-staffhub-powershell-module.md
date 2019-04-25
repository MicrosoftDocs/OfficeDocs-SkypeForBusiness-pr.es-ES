---
title: Instalar el módulo de PowerShell de StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo instalar y conectar con el módulo de Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245919"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

> [!IMPORTANT]
> Eficaces se deben retirarse el 1 de octubre de 2019, Microsoft StaffHub. Capacidades de StaffHub que estamos creando en Microsoft Teams. En la actualidad, los equipos incluye la aplicación de turnos para la administración de programación y funciones adicionales se lleve a cabo a través del tiempo. StaffHub dejará de funcionar para todos los usuarios en el 1 de octubre de 2019. Cualquier persona que intenta abrir StaffHub se mostrará un mensaje que les dirige a descargar los equipos. Para obtener más información, vea [Microsoft StaffHub retirarse](microsoft-staffhub-to-be-retired.md).  

Use los pasos de este artículo para instalar y conectar con el módulo de Microsoft StaffHub PowerShell. Necesitará esta para administrar StaffHub mediante el uso de PowerShell y para mover los equipos de StaffHub a Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

1. Descargar el [módulo de StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Abra Windows PowerShell 3.0 o posterior como administrador. Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.
3. Ejecute lo siguiente:

    ```
    $ENV:PSModulePath
    ```

4. Compruebe la ruta de acceso de la carpeta en la salida y asegúrese de que todas las carpetas en la ruta de acceso existen en el equipo antes de pasar al paso siguiente. Si faltan carpetas, crearlos.
5. Ejecute la siguiente, donde &lt;ruta de acceso&gt; es la ruta de acceso en el resultado del paso 2. Por ejemplo, es posible que la ruta de acceso aspecto C:\Users\User1\Documents\WindowsPowerShell\Modules.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectar con el módulo de Microsoft StaffHub PowerShell

1. Ejecute lo siguiente:

    ```
    Connect-StaffHub
    ```

2. Cuando se le solicite, inicie sesión como un administrador global.

## <a name="related-topics"></a>Temas relacionados

- [Referencia de Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Mover los equipos de Microsoft StaffHub a Turnos en Teams](move-staffhub-teams-to-shifts-in-teams.md)
