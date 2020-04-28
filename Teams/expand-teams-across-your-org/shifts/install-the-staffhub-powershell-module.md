---
title: Instalar el módulo de PowerShell de StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo instalar y conectarse al módulo de PowerShell de Microsoft StaffHub y mover los equipos de StaffHub a Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52b4e0c41520468bc1e05734644d1beb05fed5be
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905732"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

> [!IMPORTANT]
> A partir del 31 de diciembre de 2019, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 31 de diciembre de 2019. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).  

Siga los pasos que se indican en este artículo para instalar y conectar con el módulo de PowerShell de Microsoft StaffHub. Lo necesitará para [mover los equipos de StaffHub a teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

1. Descargue el [módulo de PowerShell de StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub).
2. Abra Windows PowerShell 3,0 o una versión posterior como administrador. Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.
    > [!NOTE]
    > Para obtener la versión más reciente de Windows PowerShell, consulte [instalar Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).
3. Ejecute lo siguiente:

    ```PowerShell
    $ENV:PSModulePath
    ```
4. Compruebe la ruta de la carpeta en la salida y asegúrese de que todas las carpetas de la ruta de acceso existen en el equipo antes de continuar con el siguiente paso. Si faltan las carpetas, créelos.
5. Ejecute lo siguiente para permitir la instalación del módulo de PowerShell de StaffHub:

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. Ejecute lo siguiente, donde &lt;rutaDeAcceso&gt; es la ruta de acceso del paso 3. Por ejemplo, la ruta de acceso podría ser similar a C:\Users\User1\Documents\WindowsPowerShell\Modules.

    Asegúrese de ejecutar cada comando por separado.

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. Salga de Windows PowerShell.
8. Abra Windows PowerShell 3,0 o una versión posterior como administrador global y, a continuación, ejecute lo siguiente:

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectarse al módulo de PowerShell de Microsoft StaffHub

1. Ejecute lo siguiente:

    ```PowerShell
    Connect-StaffHub
    ```

2. Cuando se le solicite, inicie sesión como administrador global.

## <a name="related-topics"></a>Temas relacionados

- [Referencia de PowerShell de Microsoft StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Mover los equipos de Microsoft StaffHub a Turnos en Teams](move-staffhub-teams-to-shifts-in-teams.md)
