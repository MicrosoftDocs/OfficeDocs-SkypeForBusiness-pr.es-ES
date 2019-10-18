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
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa7f84342b2d4ae16cf801be513e1ae9d6440802
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569215"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="f76b0-103">Instalar el módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="f76b0-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f76b0-104">A partir del 31 de diciembre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="f76b0-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="f76b0-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f76b0-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="f76b0-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="f76b0-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="f76b0-107">StaffHub dejará de funcionar para todos los usuarios el 31 de diciembre de 2019.</span><span class="sxs-lookup"><span data-stu-id="f76b0-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="f76b0-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="f76b0-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="f76b0-109">Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="f76b0-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="f76b0-110">Siga los pasos que se indican en este artículo para instalar y conectarse a la versión preliminar del módulo de PowerShell de Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="f76b0-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="f76b0-111">Lo necesitará para [mover los equipos de StaffHub a teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f76b0-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="f76b0-112">Instalar la versión preliminar del módulo de PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="f76b0-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="f76b0-113">Abra Windows PowerShell 3,0 o una versión posterior como administrador. Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="f76b0-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="f76b0-114">Para obtener la versión más reciente de Windows PowerShell, consulte [instalar Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f76b0-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="f76b0-115">Ejecute lo siguiente para instalar la versión preliminar del módulo de PowerShell de StaffHub:</span><span class="sxs-lookup"><span data-stu-id="f76b0-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="f76b0-116">Es posible que vea el mensaje de ADVERTENCIA:</span><span class="sxs-lookup"><span data-stu-id="f76b0-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="f76b0-117">Escriba `Y`y, a continuación `Enter`, haga clic en.</span><span class="sxs-lookup"><span data-stu-id="f76b0-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="f76b0-118">Salga de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f76b0-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="f76b0-119">Conectarse al módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="f76b0-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="f76b0-120">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f76b0-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="f76b0-121">Cuando se le solicite, inicie sesión como administrador global.</span><span class="sxs-lookup"><span data-stu-id="f76b0-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f76b0-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f76b0-122">Related topics</span></span>

- [<span data-ttu-id="f76b0-123">Referencia de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="f76b0-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="f76b0-124">Mover los equipos de Microsoft StaffHub a Turnos en Teams</span><span class="sxs-lookup"><span data-stu-id="f76b0-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
