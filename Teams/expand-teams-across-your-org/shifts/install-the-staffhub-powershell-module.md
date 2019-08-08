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
ms.openlocfilehash: 179276a049a30f1d049521cc3b4db326b988667c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246184"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="ae927-103">Instalar el módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="ae927-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae927-104">A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="ae927-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="ae927-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ae927-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="ae927-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="ae927-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="ae927-107">StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="ae927-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="ae927-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="ae927-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="ae927-109">Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.</span><span class="sxs-lookup"><span data-stu-id="ae927-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="ae927-110">Siga los pasos que se indican en este artículo para instalar y conectar con el módulo de PowerShell de Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="ae927-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="ae927-111">Necesitará esto para administrar StaffHub mediante PowerShell y para mover los equipos de StaffHub a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ae927-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="ae927-112">Instalar el módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="ae927-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="ae927-113">Descargue el [módulo de PowerShell de StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="ae927-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="ae927-114">Abra Windows PowerShell 3,0 o una versión posterior como administrador. Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="ae927-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="ae927-115">Para obtener la versión más reciente de Windows PowerShell, consulte [instalar Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ae927-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
3. <span data-ttu-id="ae927-116">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae927-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="ae927-117">Compruebe la ruta de la carpeta en la salida y asegúrese de que todas las carpetas de la ruta de acceso existen en el equipo antes de continuar con el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="ae927-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="ae927-118">Si faltan las carpetas, créelos.</span><span class="sxs-lookup"><span data-stu-id="ae927-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="ae927-119">Ejecute lo siguiente para permitir la instalación del módulo de PowerShell de StaffHub:</span><span class="sxs-lookup"><span data-stu-id="ae927-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. <span data-ttu-id="ae927-120">Ejecute lo siguiente, donde &lt;rutaDeAcceso&gt; es la ruta de acceso del paso 2.</span><span class="sxs-lookup"><span data-stu-id="ae927-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="ae927-121">Por ejemplo, la ruta de acceso podría ser similar a C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="ae927-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="ae927-122">Asegúrese de ejecutar cada comando por separado.</span><span class="sxs-lookup"><span data-stu-id="ae927-122">Be sure to run each command separately.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. <span data-ttu-id="ae927-123">Salga de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae927-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="ae927-124">Abra Windows PowerShell 3,0 o una versión posterior como administrador global y, a continuación, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae927-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="ae927-125">Conectarse al módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="ae927-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="ae927-126">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae927-126">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="ae927-127">Cuando se le solicite, inicie sesión como administrador global.</span><span class="sxs-lookup"><span data-stu-id="ae927-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae927-128">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ae927-128">Related topics</span></span>

- [<span data-ttu-id="ae927-129">Referencia de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="ae927-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="ae927-130">Mover los equipos de Microsoft StaffHub a Turnos en Teams</span><span class="sxs-lookup"><span data-stu-id="ae927-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
