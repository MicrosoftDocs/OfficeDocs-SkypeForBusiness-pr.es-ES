---
title: Instalar Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Aprenda a usar los controles de PowerShell para administrar Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947572"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="1c148-103">Instalar Microsoft Teams módulo de PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c148-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="1c148-104">En este artículo se explica cómo instalar el módulo Microsoft Teams PowerShell con la Galería de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c148-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="1c148-105">El Microsoft Teams de PowerShell es compatible con todas Windows plataformas.</span><span class="sxs-lookup"><span data-stu-id="1c148-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="1c148-106">Requirements</span><span class="sxs-lookup"><span data-stu-id="1c148-106">Requirements</span></span>

<span data-ttu-id="1c148-107">Microsoft Teams El módulo PowerShell requiere PowerShell 5.1 o posterior en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="1c148-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="1c148-108">Instale la [versión más reciente de PowerShell](/powershell/scripting/install/installing-powershell)disponible para su sistema   operativo.</span><span class="sxs-lookup"><span data-stu-id="1c148-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="1c148-109">Para comprobar la versión de PowerShell, ejecute el siguiente comando desde una sesión de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1c148-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="1c148-110">Le recomendamos que use el cmdlet Install-Module para instalar el módulo Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c148-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="1c148-111">Si la Galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet**, la primera vez que use la PSGallery verá el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="1c148-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="1c148-112">Responda **Sí** o **Sí a Todos** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="1c148-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="1c148-113">Instalación con PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="1c148-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="1c148-114">Microsoft Teams El módulo PowerShell es compatible actualmente para su uso con PowerShell 5.1 en Windows.</span><span class="sxs-lookup"><span data-stu-id="1c148-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="1c148-115">Siga estos pasos para instalar el módulo:</span><span class="sxs-lookup"><span data-stu-id="1c148-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="1c148-116">Actualizar a [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1c148-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="1c148-117">Si está en Windows 10 versión 1607 o posterior, ya tiene PowerShell 5.1 instalado.</span><span class="sxs-lookup"><span data-stu-id="1c148-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="1c148-118">Instale [.NET Framework 4.7.2](/dotnet/framework/install) o posterior.</span><span class="sxs-lookup"><span data-stu-id="1c148-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="1c148-119">Ejecute el siguiente comando para instalar la versión más reciente de PowerShellGet:</span><span class="sxs-lookup"><span data-stu-id="1c148-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="1c148-120">Instale el Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c148-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="1c148-121">Instalación sin conexión</span><span class="sxs-lookup"><span data-stu-id="1c148-121">Offline Installation</span></span> 

<span data-ttu-id="1c148-122">En algunos entornos, no es posible conectarse a la Galería de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c148-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="1c148-123">En esas situaciones, siga estos [pasos de instalación manuales.](https://aka.ms/psgallery-manualdownload)</span><span class="sxs-lookup"><span data-stu-id="1c148-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="1c148-124">Iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="1c148-124">Sign in</span></span>

<span data-ttu-id="1c148-125">Para empezar a trabajar con Microsoft Teams de PowerShell, inicie sesión con sus credenciales de Azure.</span><span class="sxs-lookup"><span data-stu-id="1c148-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="1c148-126">Actualizar Teams módulo de PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c148-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="1c148-127">Para actualizar cualquier módulo de PowerShell, debe usar el mismo método usado para instalar el módulo.</span><span class="sxs-lookup"><span data-stu-id="1c148-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="1c148-128">Por ejemplo, si usó originalmente Install-Module, debe usar [Update-Module](/powershell/module/powershellget/update-module) para obtener la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="1c148-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="1c148-129">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al actualizar el módulo.</span><span class="sxs-lookup"><span data-stu-id="1c148-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="1c148-130">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="1c148-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="1c148-131">Desinstalar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c148-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="1c148-132">Para desinstalar Microsoft Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c148-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="1c148-133">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1c148-133">Next Steps</span></span> 

<span data-ttu-id="1c148-134">Ahora ya está listo para administrar Microsoft Teams con Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c148-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="1c148-135">Vea [Administrar Teams con Teams PowerShell para](teams-powershell-managing-teams.md) empezar.</span><span class="sxs-lookup"><span data-stu-id="1c148-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="1c148-136">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1c148-136">Related topics</span></span>

[<span data-ttu-id="1c148-137">Administrar Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c148-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="1c148-138">Teams Notas de la versión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c148-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="1c148-139">Microsoft Teams referencia de cmdlet</span><span class="sxs-lookup"><span data-stu-id="1c148-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="1c148-140">Skype Empresarial referencia de cmdlet</span><span class="sxs-lookup"><span data-stu-id="1c148-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
