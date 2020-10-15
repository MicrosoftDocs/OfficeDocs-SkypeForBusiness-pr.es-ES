---
title: Desplazarse desde el conector de Skype empresarial online al módulo de PowerShell de Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Aprenda a cambiar de conector de Skype empresarial online al módulo de Teams PowerShell para administrar equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469675"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="61261-103">Desplazarse desde el conector de Skype empresarial online al módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="61261-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="61261-104">Para pasar de usar el conector de Skype empresarial online al módulo de PowerShell de Teams para administrar Teams, tendrá que actualizar los scripts de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="61261-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="61261-105">En este artículo se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="61261-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="61261-106">Instale el módulo de PowerShell más reciente de Teams.</span><span class="sxs-lookup"><span data-stu-id="61261-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="61261-107">Para conocer los pasos, consulte [instalar Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="61261-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="61261-108">Desinstale el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="61261-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="61261-109">Para hacerlo, vaya a **programas y características**en el panel de control, seleccione **Skype empresarial online, módulo de Windows PowerShell**y, a continuación, seleccione **desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="61261-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="61261-110">En los scripts de PowerShell, cambie el nombre del módulo al que se hace referencia en ```Import-Module``` de ```SkypeOnlineConnector``` o ```LyncOnlineConnector``` a ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="61261-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="61261-111">Por ejemplo, cambie ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="61261-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="61261-112">Los administradores deben seguir usando [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importar la sesión antes de usar los cmdlets de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="61261-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="61261-113">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="61261-113">Related topics</span></span>

[<span data-ttu-id="61261-114">Instalar Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="61261-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="61261-115">Administrar equipos con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="61261-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="61261-116">Notas de la versión de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="61261-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="61261-117">Referencia del cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61261-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="61261-118">Referencia de cmdlet de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="61261-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
