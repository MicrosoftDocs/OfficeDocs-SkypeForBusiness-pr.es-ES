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
description: Obtenga información sobre cómo instalar y conectarse a la versión preliminar del módulo de PowerShell de Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142039"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

> [!IMPORTANT]
> A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).  

Siga los pasos que se indican en este artículo para instalar y conectarse a la versión preliminar del módulo de PowerShell de Microsoft StaffHub. Lo necesitará para [mover los equipos de StaffHub a teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a>Instalar la versión preliminar del módulo de PowerShell Microsoft StaffHub

1. Abra Windows PowerShell 3,0 o una versión posterior como administrador. Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.
    > [!NOTE]
    > Para obtener la versión más reciente de Windows PowerShell, consulte [instalar Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Ejecute lo siguiente para instalar la versión preliminar del módulo de PowerShell de StaffHub:

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. Es posible que vea el mensaje de ADVERTENCIA:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    Escriba `Y`y, a continuación `Enter`, haga clic en.
 
4. Salga de Windows PowerShell.

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectarse al módulo de PowerShell de Microsoft StaffHub

1. Ejecute lo siguiente:

    ```
    Connect-StaffHub
    ```

2. Cuando se le solicite, inicie sesión como administrador global.

## <a name="related-topics"></a>Temas relacionados

- [Referencia de PowerShell de Microsoft StaffHub](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Mover los equipos de Microsoft StaffHub a Turnos en Teams](move-staffhub-teams-to-shifts-in-teams.md)
