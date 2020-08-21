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
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824941"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="8217e-103">Instalar Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8217e-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="8217e-104">En este artículo se explica cómo instalar el módulo Microsoft Teams PowerShell con [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="8217e-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="8217e-105">Estas instrucciones funcionan en plataformas de [Shell en la nube de Azure](/azure/cloud-shell/overview), Linux, MacOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="8217e-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="8217e-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8217e-106">Requirements</span></span>

<span data-ttu-id="8217e-107">Teams PowerShell requiere PowerShell 5,1 o superior en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="8217e-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="8217e-108">Instale la [versión más reciente de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8217e-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="8217e-109">Hay problemas conocidos con PowerShell 7 y Teams.</span><span class="sxs-lookup"><span data-stu-id="8217e-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="8217e-110">Para obtener la mejor experiencia, le recomendamos que use el PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="8217e-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="8217e-111">Instalar el módulo de PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="8217e-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="8217e-112">Para obtener la mejor experiencia, use los módulos disponibilidad general (GA) o Public Preview, no ambos.</span><span class="sxs-lookup"><span data-stu-id="8217e-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="8217e-113">No están diseñados para trabajar en conjunto.</span><span class="sxs-lookup"><span data-stu-id="8217e-113">They're not intended to work together.</span></span>


<span data-ttu-id="8217e-114">Use los cmdlets de **PowerShellGet** para instalar el módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="8217e-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="8217e-115">La instalación del módulo para todos los usuarios de un sistema requiere privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="8217e-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="8217e-116">Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el `sudo` comando en MacOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="8217e-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="8217e-117">De forma predeterminada, la galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="8217e-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="8217e-118">La primera vez que use el PSGallery, verá el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="8217e-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="8217e-119">Responda **sí** o **sí a todo** para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="8217e-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="8217e-120">Instalar la versión preliminar pública de Team PowerShell</span><span class="sxs-lookup"><span data-stu-id="8217e-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="8217e-121">Si está usando la versión de la versión preliminar pública de Teams, le recomendamos encarecidamente que desinstale primero el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="8217e-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="8217e-122">La instalación del módulo de vista previa pública de Teams PowerShell para todos los usuarios de un sistema requiere privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="8217e-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="8217e-123">Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el `sudo` comando en MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="8217e-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="8217e-124">Si está usando PowerShell 5,1, debe actualizar el módulo **PowerShellGet** de antemano.</span><span class="sxs-lookup"><span data-stu-id="8217e-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="8217e-125">Después de actualizar **powershellget**, cierre y vuelva a abrir una sesión de PowerShell elevada para asegurarse de que se cargue el último **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="8217e-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="8217e-126">Para instalar la versión preliminar pública de Teams PowerShell, ejecute el siguiente comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8217e-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="8217e-127">Puede encontrar la versión preliminar más reciente en la [Galería de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o en PowerShell ejecutando "Find-Module MicrosoftTeams-AllowPrerelease"</span><span class="sxs-lookup"><span data-stu-id="8217e-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="8217e-128">Instalar el conector de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="8217e-128">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="8217e-129">En este momento, el conector de Skype empresarial online forma parte de Team PowerShell Public Preview.</span><span class="sxs-lookup"><span data-stu-id="8217e-129">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="8217e-130">Una vez que hayamos implementado esta característica en la versión GA de Teams, ya no estará disponible el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="8217e-130">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="8217e-131">Descargue e instale el [módulo de PowerShell de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=39366)y, a continuación, ejecute lo siguiente en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8217e-131">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="8217e-132">Iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="8217e-132">Sign in</span></span>

<span data-ttu-id="8217e-133">Para empezar a trabajar con Teams PowerShell, inicie sesión con sus credenciales de Azure.</span><span class="sxs-lookup"><span data-stu-id="8217e-133">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="8217e-134">Si está usando la última versión de la [versión preliminar pública de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), no necesita instalar el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="8217e-134">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="8217e-135">Actualizar PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="8217e-135">Update Teams PowerShell</span></span>

<span data-ttu-id="8217e-136">Para actualizar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8217e-136">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="8217e-137">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, no se podrá actualizar el módulo.</span><span class="sxs-lookup"><span data-stu-id="8217e-137">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="8217e-138">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="8217e-138">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="8217e-139">Desinstalar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8217e-139">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="8217e-140">Para desinstalar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell elevado y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8217e-140">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="8217e-141">Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al desinstalar el módulo.</span><span class="sxs-lookup"><span data-stu-id="8217e-141">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="8217e-142">Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="8217e-142">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8217e-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8217e-143">Next Steps</span></span>

<span data-ttu-id="8217e-144">Ahora ya está listo para administrar equipos con el PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="8217e-144">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="8217e-145">Consulte [Administración de equipos con el PowerShell de Teams](teams-powershell-managing-teams.md) para comenzar.</span><span class="sxs-lookup"><span data-stu-id="8217e-145">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8217e-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8217e-146">Related topics</span></span>

[<span data-ttu-id="8217e-147">Administración de equipos con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8217e-147">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="8217e-148">Notas de la versión de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8217e-148">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="8217e-149">Referencia del cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8217e-149">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="8217e-150">Referencia de cmdlet de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="8217e-150">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
