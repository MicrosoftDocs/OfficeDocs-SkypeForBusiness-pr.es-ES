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
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="fd4d6-103">Instalar el módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="fd4d6-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd4d6-104">A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="fd4d6-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="fd4d6-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="fd4d6-107">StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="fd4d6-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="fd4d6-109">Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="fd4d6-110">Siga los pasos que se indican en este artículo para instalar y conectar con el módulo de PowerShell de Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="fd4d6-111">Necesitará esto para administrar StaffHub mediante PowerShell y para mover los equipos de StaffHub a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="fd4d6-112">Instalar el módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="fd4d6-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="fd4d6-113">Descargue el [módulo de PowerShell de StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="fd4d6-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="fd4d6-114">Abra Windows PowerShell 3,0 o una versión posterior como administrador.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="fd4d6-115">Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="fd4d6-116">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd4d6-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="fd4d6-117">Compruebe la ruta de la carpeta en la salida y asegúrese de que todas las carpetas de la ruta de acceso existen en el equipo antes de continuar con el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="fd4d6-118">Si faltan las carpetas, créelos.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="fd4d6-119">Ejecute lo siguiente para permitir la instalación del módulo de PowerShell de StaffHub:</span><span class="sxs-lookup"><span data-stu-id="fd4d6-119">Run the following to allow for the installation of the StaffHub PowerShell module:</span></span>

```
Set-ExecutionPolicy RemoteSigned
```

6. <span data-ttu-id="fd4d6-120">Ejecute lo siguiente, donde &lt;rutaDeAcceso&gt; es la ruta de acceso del paso 2.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="fd4d6-121">Por ejemplo, la ruta de acceso podría ser similar a C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="fd4d6-122">Conectarse al módulo de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="fd4d6-122">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="fd4d6-123">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd4d6-123">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="fd4d6-124">Cuando se le solicite, inicie sesión como administrador global.</span><span class="sxs-lookup"><span data-stu-id="fd4d6-124">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fd4d6-125">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fd4d6-125">Related topics</span></span>

- [<span data-ttu-id="fd4d6-126">Referencia de PowerShell de Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="fd4d6-126">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="fd4d6-127">Mover los equipos de Microsoft StaffHub a Turnos en Teams</span><span class="sxs-lookup"><span data-stu-id="fd4d6-127">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
