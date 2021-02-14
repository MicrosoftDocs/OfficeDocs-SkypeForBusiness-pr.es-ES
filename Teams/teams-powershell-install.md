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
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662025"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="1e1ef-103">Instalar Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e1ef-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="1e1ef-104">En este artículo se explica cómo instalar el módulo De PowerShell de Microsoft Teams con [PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="1e1ef-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="1e1ef-105">Estas instrucciones funcionan en [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS y plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e1ef-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e1ef-106">Requirements</span></span>

<span data-ttu-id="1e1ef-107">Teams PowerShell requiere PowerShell 5.1 o posterior en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="1e1ef-108">Instale la [última versión de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="1e1ef-109">Hay problemas conocidos con PowerShell 7 y Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="1e1ef-110">Para obtener la mejor experiencia, se recomienda usar PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="1e1ef-111">Instalar el módulo PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="1e1ef-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="1e1ef-112">Para obtener la mejor experiencia, use los módulos de disponibilidad general (GA) o vista previa pública (no ambos).</span><span class="sxs-lookup"><span data-stu-id="1e1ef-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="1e1ef-113">No están pensadas para trabajar en conjunto.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-113">They're not intended to work together.</span></span>


<span data-ttu-id="1e1ef-114">Use los **cmdlets de PowerShellGet** para instalar el módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="1e1ef-115">Instalar el módulo para todos los usuarios de un sistema requiere privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="1e1ef-116">Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el comando en `sudo` macOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="1e1ef-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="1e1ef-117">De forma predeterminada, la galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="1e1ef-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="1e1ef-118">La primera vez que use la PSGallery, verá el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="1e1ef-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="1e1ef-119">Responda **Sí** o **Sí a Todos** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="1e1ef-120">Instalar teams vista previa pública de PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e1ef-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="1e1ef-121">Si usa la versión Public Preview de Teams PowerShell, le recomendamos encarecidamente que desinstale primero Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="1e1ef-122">Instalar el módulo de vista previa pública de PowerShell de Teams para todos los usuarios de un sistema requiere privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="1e1ef-123">Inicie la sesión de PowerShell usando **Ejecutar como administrador** en Windows o use el comando en `sudo` macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="1e1ef-124">Si usa PowerShell 5.1, debe actualizar el módulo **PowerShellGet** previamente.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="1e1ef-125">Después de actualizar **PowerShellGet,** cierre y vuelva a abrir una sesión de PowerShell con privilegios elevados para asegurarse de que se carga la última **sesión de PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="1e1ef-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="1e1ef-126">Para instalar teams powershell público preview, ejecute el siguiente comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="1e1ef-127">Puede encontrar la versión preliminar más reciente en la galería de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o en PowerShell ejecutando "Find-Module MicrosoftTeams -AllowPrerelease"</span><span class="sxs-lookup"><span data-stu-id="1e1ef-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="1e1ef-128">Instalar Skype Empresarial Online Connector</span><span class="sxs-lookup"><span data-stu-id="1e1ef-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="1e1ef-129">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="1e1ef-130">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="1e1ef-131">Iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="1e1ef-131">Sign in</span></span>

<span data-ttu-id="1e1ef-132">Para empezar a trabajar con Teams PowerShell, inicie sesión con sus credenciales de Azure.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="1e1ef-133">Si usa la versión preliminar pública de PowerShell más reciente de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="1e1ef-134">Actualizar Teams con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e1ef-134">Update Teams PowerShell</span></span>

<span data-ttu-id="1e1ef-135">Para actualizar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e1ef-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="1e1ef-136">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al actualizar el módulo.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="1e1ef-137">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="1e1ef-138">Desinstalar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e1ef-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="1e1ef-139">Para desinstalar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e1ef-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="1e1ef-140">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al desinstalar el módulo.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="1e1ef-141">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1e1ef-142">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="1e1ef-142">Next Steps</span></span>

<span data-ttu-id="1e1ef-143">Ahora ya está listo para administrar Teams con Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="1e1ef-144">Consulte [Administrar Equipos con PowerShell de Teams](teams-powershell-managing-teams.md) para empezar.</span><span class="sxs-lookup"><span data-stu-id="1e1ef-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e1ef-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1e1ef-145">Related topics</span></span>

[<span data-ttu-id="1e1ef-146">Administrar Teams con PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="1e1ef-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="1e1ef-147">Notas de la versión de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="1e1ef-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="1e1ef-148">Referencia de cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e1ef-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="1e1ef-149">Referencia de cmdlet de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1e1ef-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
