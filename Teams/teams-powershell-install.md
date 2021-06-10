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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768349"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="d4e6d-103">Instalar Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4e6d-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="d4e6d-104">En este artículo se explica cómo instalar el Microsoft Teams PowerShell con [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="d4e6d-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="d4e6d-105">Estas instrucciones funcionan en [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS y Windows plataformas.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="d4e6d-106">Requirements</span><span class="sxs-lookup"><span data-stu-id="d4e6d-106">Requirements</span></span>

<span data-ttu-id="d4e6d-107">Teams PowerShell requiere PowerShell 5.1 o posterior en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="d4e6d-108">Instale la [versión más reciente de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!NOTE]
> <span data-ttu-id="d4e6d-109">Para obtener la mejor experiencia, le recomendamos que use PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-109">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="d4e6d-110">Instalar el Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4e6d-110">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="d4e6d-111">Para obtener la mejor experiencia, use los módulos Disponibilidad general (GA) o Vista previa pública, no ambos.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-111">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="d4e6d-112">No están pensados para trabajar juntos.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-112">They're not intended to work together.</span></span>


<span data-ttu-id="d4e6d-113">Use los cmdlets **de PowerShellGet** para instalar el Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-113">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="d4e6d-114">La instalación del módulo para todos los usuarios en un sistema requiere privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-114">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="d4e6d-115">Inicie la sesión de PowerShell con **Ejecutar** como administrador en Windows o use el `sudo` comando en macOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="d4e6d-115">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="d4e6d-116">De forma predeterminada, la Galería de PowerShell (PSGallery) no está configurada como un repositorio de confianza para **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-116">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="d4e6d-117">La primera vez que use psgallery, verá el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="d4e6d-117">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="d4e6d-118">Responda **Sí** o **Sí a Todos** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-118">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="d4e6d-119">Iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="d4e6d-119">Sign in</span></span>

<span data-ttu-id="d4e6d-120">Para empezar a trabajar con Teams PowerShell, inicie sesión con sus credenciales de Azure.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-120">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="d4e6d-121">Si usa la última versión Teams versión preliminar pública de [PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar el Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-121">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="d4e6d-122">Iniciar sesión con MFA y autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="d4e6d-122">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="d4e6d-123">Si su cuenta usa la autenticación multifactor, siga los pasos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-123">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a><span data-ttu-id="d4e6d-124">Actualizar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4e6d-124">Update Teams PowerShell</span></span>

<span data-ttu-id="d4e6d-125">Para actualizar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4e6d-125">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="d4e6d-126">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al actualizar el módulo.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-126">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="d4e6d-127">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-127">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="d4e6d-128">Desinstalar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4e6d-128">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="d4e6d-129">Para desinstalar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4e6d-129">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="d4e6d-130">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al desinstalar el módulo.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-130">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="d4e6d-131">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-131">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="d4e6d-132">Instalar Teams vista previa pública de PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4e6d-132">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="d4e6d-133">Si usa la versión de vista previa pública de Teams PowerShell, le recomendamos que desinstale primero Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-133">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="d4e6d-134">Instalar el Teams de vista previa pública de PowerShell para todos los usuarios de un sistema requiere privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-134">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="d4e6d-135">Inicie la sesión de PowerShell con **Ejecutar** como administrador en Windows o use el `sudo` comando en macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-135">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="d4e6d-136">Si usa PowerShell 5.1, debe actualizar el módulo **PowerShellGet** previamente.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-136">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="d4e6d-137">Después de actualizar **PowerShellGet**, cierre y vuelva a abrir una sesión de PowerShell con privilegios elevados para asegurarse de que se carga el **PowerShellGet** más reciente.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-137">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="d4e6d-138">Para instalar Teams vista previa pública de PowerShell, ejecute el comando de PowerShell siguiente.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-138">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="d4e6d-139">Puede encontrar la versión preliminar más reciente en la Galería de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o en PowerShell ejecutando "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span><span class="sxs-lookup"><span data-stu-id="d4e6d-139">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="d4e6d-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d4e6d-140">Next Steps</span></span>

<span data-ttu-id="d4e6d-141">Ahora ya está listo para administrar Teams con Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-141">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="d4e6d-142">Vea [Administrar Teams con Teams PowerShell para](teams-powershell-managing-teams.md) empezar.</span><span class="sxs-lookup"><span data-stu-id="d4e6d-142">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d4e6d-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d4e6d-143">Related topics</span></span>

[<span data-ttu-id="d4e6d-144">Administrar Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4e6d-144">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="d4e6d-145">Teams Notas de la versión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4e6d-145">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="d4e6d-146">Microsoft Teams referencia de cmdlet</span><span class="sxs-lookup"><span data-stu-id="d4e6d-146">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="d4e6d-147">Skype Empresarial referencia de cmdlet</span><span class="sxs-lookup"><span data-stu-id="d4e6d-147">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
