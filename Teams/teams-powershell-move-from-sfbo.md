---
title: Pasar de Skype Empresarial Online Connector al módulo de PowerShell de Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo pasar de Skype Empresarial Online Connector al módulo de PowerShell de Teams para administrar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094131"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="0207d-103">Pasar de Skype Empresarial Online Connector al módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="0207d-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="0207d-104">Para pasar de usar Skype Empresarial Online Connector al módulo de PowerShell de Teams para administrar Teams, tendrá que actualizar los scripts de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="0207d-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="0207d-105">En este artículo se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="0207d-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="0207d-106">Instale el módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="0207d-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="0207d-107">Para ver los pasos, [vea Instalar Microsoft Teams Powershell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="0207d-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="0207d-108">Desinstale Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="0207d-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="0207d-109">Para ello, en el Panel de control, vaya a Programas y **características,** seleccione Skype Empresarial **Online, Windows PowerShell Módulo** y, a continuación, **seleccione Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="0207d-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="0207d-110">En los scripts de PowerShell, cambie el nombre del módulo al que se hace referencia ```Import-Module``` desde ```SkypeOnlineConnector``` o a ```LyncOnlineConnector``` ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="0207d-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="0207d-111">Por ejemplo, cambie ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="0207d-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="0207d-112">Al usar El módulo de PowerShell de Teams 2.0 o posterior, cambie New-csOnlineSession a Connect-MicrosoftTeams.</span><span class="sxs-lookup"><span data-stu-id="0207d-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a><span data-ttu-id="0207d-113">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0207d-113">Related topics</span></span>

[<span data-ttu-id="0207d-114">Instalar Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="0207d-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="0207d-115">Administrar Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="0207d-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="0207d-116">Notas de la versión de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="0207d-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="0207d-117">Referencia de cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0207d-117">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="0207d-118">Referencia de cmdlet de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0207d-118">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)