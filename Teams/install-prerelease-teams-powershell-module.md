---
title: Instalar la versión preliminar del módulo de PowerShell de Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Siga estos pasos para instalar la versión preliminar del módulo Teams PowerShell desde la galería de pruebas de PowerShell.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321773"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="82bcf-103">Instalar la versión preliminar del módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="82bcf-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="82bcf-104">En este artículo se describe cómo instalar la última versión preliminar del módulo Teams PowerShell desde la [Galería de pruebas de PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="82bcf-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="82bcf-105">Necesitará la versión preliminar del módulo de PowerShell de Teams, en aquellos casos en los que los cmdlets para administrar una característica de Teams no se admiten en la versión de general disponible del módulo y solo están disponibles en la versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="82bcf-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="82bcf-106">Siga estos pasos para instalar la versión preliminar más reciente del módulo de PowerShell de Teams en la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82bcf-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="82bcf-107">No instale el módulo de Teams PowerShell desde la galería de pruebas de PowerShell en paralelo con una versión del módulo de la [Galería de PowerShell pública](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="82bcf-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="82bcf-108">Siga estos pasos para desinstalar primero el módulo de PowerShell de Teams de la galería de PowerShell pública y, a continuación, instale la última versión del módulo desde la galería de pruebas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82bcf-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="82bcf-109">Cierre todas las sesiones de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="82bcf-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="82bcf-110">Inicie una nueva instancia del módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82bcf-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="82bcf-111">Ejecute lo siguiente para desinstalar el módulo de PowerShell de Teams de la galería pública de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82bcf-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="82bcf-112">Cierre todas las sesiones de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="82bcf-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="82bcf-113">Inicie el módulo de Windows PowerShell de nuevo y, a continuación, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como una fuente de confianza:</span><span class="sxs-lookup"><span data-stu-id="82bcf-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="82bcf-114">Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82bcf-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="82bcf-115">Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82bcf-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="82bcf-116">Actualice a la última versión del módulo de PowerShell de Teams desde la galería de pruebas de PowerShell</span><span class="sxs-lookup"><span data-stu-id="82bcf-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="82bcf-117">Si ya ha instalado el módulo de Teams PowerShell desde la galería de pruebas de PowerShell, siga estos pasos para actualizar a la última versión.</span><span class="sxs-lookup"><span data-stu-id="82bcf-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="82bcf-118">Cierre todas las sesiones de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="82bcf-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="82bcf-119">Inicie una nueva instancia del módulo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82bcf-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="82bcf-120">Ejecute lo siguiente para actualizar la versión del módulo de PowerShell instalada actualmente desde la galería de pruebas de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82bcf-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="82bcf-121">Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82bcf-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="82bcf-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="82bcf-122">Related topics</span></span>

- [<span data-ttu-id="82bcf-123">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="82bcf-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
