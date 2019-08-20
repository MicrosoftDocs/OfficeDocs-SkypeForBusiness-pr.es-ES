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
description: Obtenga información sobre cómo instalar y conectar con el módulo de PowerShell de Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464670"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

> [!IMPORTANT]
> A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.  

Siga los pasos que se indican en este artículo para instalar y conectar con el módulo de PowerShell de Microsoft StaffHub. Necesitará esto para administrar StaffHub mediante PowerShell y para mover los equipos de StaffHub a Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de Microsoft StaffHub

1. Abra Windows PowerShell 3,0 o una versión posterior como administrador. Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.
    > [!NOTE]
    > Para obtener la versión más reciente de Windows PowerShell, consulte [instalar Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Ejecute lo siguiente para instalar la versión estable actual del módulo de PowerShell de StaffHub:

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    Puede ejecutar este comando solo si necesita instalar la última versión, que puede tener más inestabilidades que la versión estable actual:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > Si recibe un error durante la instalación de la última versión con más inestabilidades, puede ejecutar:`Install-Module PowershellGet -Force`

3. Es posible que vea el mensaje de ADVERTENCIA:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

Escriba `Y` y haga `Enter`clic.
 
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
