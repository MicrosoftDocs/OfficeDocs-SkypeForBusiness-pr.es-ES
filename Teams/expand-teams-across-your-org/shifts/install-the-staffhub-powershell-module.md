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
description: Obtenga información sobre cómo instalar y conectar con el módulo de PowerShell de Microsoft StaffHub.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6eab331c8d8b2213225ad8c7ee216f9f6ec2b51
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681884"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

> [!IMPORTANT]
> A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.  

Siga los pasos que se indican en este artículo para instalar y conectar con el módulo de PowerShell de Microsoft StaffHub. Necesitará esto para administrar StaffHub mediante PowerShell y para mover los equipos de StaffHub a Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

1. Descargue el [módulo de PowerShell de StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Abra Windows PowerShell 3,0 o una versión posterior como administrador. Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.
3. Ejecute lo siguiente:

    ```
    $ENV:PSModulePath
    ```
    

4. Compruebe la ruta de la carpeta en la salida y asegúrese de que todas las carpetas de la ruta de acceso existen en el equipo antes de continuar con el siguiente paso. Si faltan las carpetas, créelos.
5. Ejecute lo siguiente para permitir la instalación del módulo de PowerShell de StaffHub:

```
Set-ExecutionPolicy RemoteSigned
```

6. Ejecute lo siguiente, donde &lt;rutaDeAcceso&gt; es la ruta de acceso del paso 2. Por ejemplo, la ruta de acceso podría ser similar a C:\Users\User1\Documents\WindowsPowerShell\Modules.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectarse al módulo de PowerShell de Microsoft StaffHub

1. Ejecute lo siguiente:

    ```
    Connect-StaffHub
    ```

2. Cuando se le solicite, inicie sesión como administrador global.

## <a name="related-topics"></a>Temas relacionados

- [Referencia de PowerShell de Microsoft StaffHub](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Mover los equipos de Microsoft StaffHub a Turnos en Teams](move-staffhub-teams-to-shifts-in-teams.md)
