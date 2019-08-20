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
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b76b4-103">Instalar el módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b76b4-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b76b4-104">A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="b76b4-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="b76b4-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b76b4-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b76b4-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="b76b4-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b76b4-107">StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="b76b4-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="b76b4-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="b76b4-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="b76b4-109">Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.</span><span class="sxs-lookup"><span data-stu-id="b76b4-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="b76b4-110">Siga los pasos que se indican en este artículo para instalar y conectar con el módulo de PowerShell de Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b76b4-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="b76b4-111">Necesitará esto para administrar StaffHub mediante PowerShell y para mover los equipos de StaffHub a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b76b4-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b76b4-112">Instalar el módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b76b4-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="b76b4-113">Abra Windows PowerShell 3,0 o una versión posterior como administrador. Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b76b4-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b76b4-114">Para obtener la versión más reciente de Windows PowerShell, consulte [instalar Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b76b4-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="b76b4-115">Ejecute lo siguiente para instalar la versión estable actual del módulo de PowerShell de StaffHub:</span><span class="sxs-lookup"><span data-stu-id="b76b4-115">Run the following to install the current stable version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    <span data-ttu-id="b76b4-116">Puede ejecutar este comando solo si necesita instalar la última versión, que puede tener más inestabilidades que la versión estable actual:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span><span class="sxs-lookup"><span data-stu-id="b76b4-116">You can run this command only if you need to install the latest version, which may have more instabilities than the current stable version: `Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span></span>

     > [!NOTE]
     > <span data-ttu-id="b76b4-117">Si recibe un error durante la instalación de la última versión con más inestabilidades, puede ejecutar:`Install-Module PowershellGet -Force`</span><span class="sxs-lookup"><span data-stu-id="b76b4-117">If you receive an error during the installation of the latest version with more instabilities, you can run: `Install-Module PowershellGet -Force`</span></span>

3. <span data-ttu-id="b76b4-118">Es posible que vea el mensaje de ADVERTENCIA:</span><span class="sxs-lookup"><span data-stu-id="b76b4-118">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

<span data-ttu-id="b76b4-119">Escriba `Y` y haga `Enter`clic.</span><span class="sxs-lookup"><span data-stu-id="b76b4-119">Type `Y` and click `Enter`.</span></span>
 
4. <span data-ttu-id="b76b4-120">Salga de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b76b4-120">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b76b4-121">Conectarse al módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b76b4-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="b76b4-122">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b76b4-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="b76b4-123">Cuando se le solicite, inicie sesión como administrador global.</span><span class="sxs-lookup"><span data-stu-id="b76b4-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b76b4-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b76b4-124">Related topics</span></span>

- [<span data-ttu-id="b76b4-125">Referencia de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b76b4-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="b76b4-126">Mover los equipos de Microsoft StaffHub a Turnos en Teams</span><span class="sxs-lookup"><span data-stu-id="b76b4-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
