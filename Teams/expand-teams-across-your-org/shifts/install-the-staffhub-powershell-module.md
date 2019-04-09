---
title: Instalar el módulo de StaffHub PowerShell
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
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555139"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="88dba-103">Instalar el módulo de Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="88dba-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88dba-104">Eficaces se deben retirarse el 1 de octubre de 2019, Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="88dba-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="88dba-105">Capacidades de StaffHub que estamos creando en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="88dba-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="88dba-106">En la actualidad, los equipos incluye la aplicación de turnos para la administración de programación y funciones adicionales se lleve a cabo a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="88dba-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="88dba-107">StaffHub dejará de funcionar para todos los usuarios en el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="88dba-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="88dba-108">Cualquier persona que intenta abrir StaffHub se mostrará un mensaje que les dirige a descargar los equipos.</span><span class="sxs-lookup"><span data-stu-id="88dba-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="88dba-109">Para obtener más información, vea [Microsoft StaffHub retirarse](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="88dba-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="88dba-110">Use los pasos de este artículo para instalar y conectar con el módulo de Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88dba-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="88dba-111">Necesitará esta para administrar StaffHub mediante el uso de PowerShell y para mover los equipos de StaffHub a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="88dba-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="88dba-112">Instalar el módulo de Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="88dba-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="88dba-113">Descargar el [módulo de StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="88dba-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="88dba-114">Abra Windows PowerShell 3.0 o posterior como administrador.</span><span class="sxs-lookup"><span data-stu-id="88dba-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="88dba-115">Para ello, haga clic en **Inicio**, escriba **Windows PowerShell**, haga clic en **Windows PowerShell**y, a continuación, seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="88dba-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="88dba-116">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88dba-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```

4. <span data-ttu-id="88dba-117">Compruebe la ruta de acceso de la carpeta en la salida y asegúrese de que todas las carpetas en la ruta de acceso existen en el equipo antes de pasar al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="88dba-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="88dba-118">Si faltan carpetas, crearlos.</span><span class="sxs-lookup"><span data-stu-id="88dba-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="88dba-119">Ejecute la siguiente, donde &lt;ruta de acceso&gt; es la ruta de acceso en el resultado del paso 2.</span><span class="sxs-lookup"><span data-stu-id="88dba-119">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="88dba-120">Por ejemplo, es posible que la ruta de acceso aspecto C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="88dba-120">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="88dba-121">Conectar con el módulo de Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="88dba-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="88dba-122">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88dba-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="88dba-123">Cuando se le solicite, inicie sesión como un administrador global.</span><span class="sxs-lookup"><span data-stu-id="88dba-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="88dba-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="88dba-124">Related topics</span></span>

- [<span data-ttu-id="88dba-125">Referencia de Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="88dba-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="88dba-126">Mover los equipos de Microsoft StaffHub a Turnos en Teams</span><span class="sxs-lookup"><span data-stu-id="88dba-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
