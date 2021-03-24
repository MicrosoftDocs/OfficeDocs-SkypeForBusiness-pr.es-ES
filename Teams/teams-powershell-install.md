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
ms.openlocfilehash: e5526a7a7d782b8a30edd5b5169c3ba78953cc7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094160"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="fd08a-103">Instalar Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd08a-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="fd08a-104">En este artículo se explica cómo instalar el módulo PowerShell de Microsoft Teams con [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="fd08a-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="fd08a-105">Estas instrucciones funcionan en [plataformas Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="fd08a-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd08a-106">Requirements</span><span class="sxs-lookup"><span data-stu-id="fd08a-106">Requirements</span></span>

<span data-ttu-id="fd08a-107">Teams PowerShell requiere PowerShell 5.1 o posterior en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="fd08a-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="fd08a-108">Instale la [versión más reciente de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fd08a-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="fd08a-109">Hay problemas conocidos con PowerShell 7 y Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd08a-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="fd08a-110">Para obtener la mejor experiencia, le recomendamos que use PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="fd08a-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="fd08a-111">Instalar el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="fd08a-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="fd08a-112">Para obtener la mejor experiencia, use los módulos Disponibilidad general (GA) o Vista previa pública, no ambos.</span><span class="sxs-lookup"><span data-stu-id="fd08a-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="fd08a-113">No están pensados para trabajar juntos.</span><span class="sxs-lookup"><span data-stu-id="fd08a-113">They're not intended to work together.</span></span>


<span data-ttu-id="fd08a-114">Use los cmdlets **de PowerShellGet** para instalar el módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="fd08a-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="fd08a-115">La instalación del módulo para todos los usuarios en un sistema requiere privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="fd08a-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="fd08a-116">Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el comando en `sudo` macOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="fd08a-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="fd08a-117">De forma predeterminada, la Galería de PowerShell (PSGallery) no está configurada como un repositorio de confianza para **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="fd08a-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="fd08a-118">La primera vez que use psgallery, verá el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="fd08a-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="fd08a-119">Responda **Sí** o **Sí a Todos** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="fd08a-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="fd08a-120">Instalar la vista previa pública de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="fd08a-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="fd08a-121">Si usa la versión de vista previa pública de Teams PowerShell, le recomendamos que desinstale primero Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="fd08a-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="fd08a-122">Instalar el módulo de vista previa pública de PowerShell de Teams para todos los usuarios de un sistema requiere privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="fd08a-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="fd08a-123">Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el comando en `sudo` macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="fd08a-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="fd08a-124">Si usa PowerShell 5.1, debe actualizar el módulo **PowerShellGet** previamente.</span><span class="sxs-lookup"><span data-stu-id="fd08a-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="fd08a-125">Después de actualizar **PowerShellGet**, cierre y vuelva a abrir una sesión de PowerShell con privilegios elevados para asegurarse de que se carga el **PowerShellGet** más reciente.</span><span class="sxs-lookup"><span data-stu-id="fd08a-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="fd08a-126">Para instalar la vista previa pública de PowerShell de Teams, ejecute el comando de PowerShell siguiente.</span><span class="sxs-lookup"><span data-stu-id="fd08a-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="fd08a-127">Puede encontrar la versión preliminar más reciente en la Galería de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o en PowerShell ejecutando "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span><span class="sxs-lookup"><span data-stu-id="fd08a-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="fd08a-128">Instalar skype empresarial Online Connector</span><span class="sxs-lookup"><span data-stu-id="fd08a-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="fd08a-129">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="fd08a-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="fd08a-130">Si usa la última versión pública de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="fd08a-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a><span data-ttu-id="fd08a-131">Iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="fd08a-131">Sign in</span></span>

<span data-ttu-id="fd08a-132">Para empezar a trabajar con Teams PowerShell, inicie sesión con sus credenciales de Azure.</span><span class="sxs-lookup"><span data-stu-id="fd08a-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="fd08a-133">Si usa la versión preliminar pública más reciente de [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="fd08a-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="fd08a-134">Iniciar sesión con MFA y autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="fd08a-134">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="fd08a-135">Si su cuenta usa la autenticación multifactor, siga los pasos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="fd08a-135">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="fd08a-136">Actualizar PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="fd08a-136">Update Teams PowerShell</span></span>

<span data-ttu-id="fd08a-137">Para actualizar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd08a-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="fd08a-138">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al actualizar el módulo.</span><span class="sxs-lookup"><span data-stu-id="fd08a-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="fd08a-139">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="fd08a-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="fd08a-140">Desinstalar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd08a-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="fd08a-141">Para desinstalar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd08a-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="fd08a-142">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al desinstalar el módulo.</span><span class="sxs-lookup"><span data-stu-id="fd08a-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="fd08a-143">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="fd08a-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fd08a-144">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="fd08a-144">Next Steps</span></span>

<span data-ttu-id="fd08a-145">Ahora ya está listo para administrar Teams con Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd08a-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="fd08a-146">Vea [Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md) para empezar.</span><span class="sxs-lookup"><span data-stu-id="fd08a-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fd08a-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fd08a-147">Related topics</span></span>

[<span data-ttu-id="fd08a-148">Administrar Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd08a-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="fd08a-149">Notas de la versión de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="fd08a-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="fd08a-150">Referencia de cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd08a-150">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="fd08a-151">Referencia de cmdlet de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="fd08a-151">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)