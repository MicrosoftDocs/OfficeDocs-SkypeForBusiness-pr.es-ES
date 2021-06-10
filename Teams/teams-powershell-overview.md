---
title: Microsoft Teams Información general de PowerShell
ms.reviewer: ''
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
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768359"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="16ed4-103">Microsoft Teams Información general de PowerShell</span><span class="sxs-lookup"><span data-stu-id="16ed4-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="16ed4-104">Microsoft Teams PowerShell es un conjunto de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16ed4-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="16ed4-105">Escrito en .NET Standard, Teams PowerShell funciona en PowerShell 5.1 en Windows, PowerShell 6.x y posteriores en todas las plataformas, incluido Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="16ed4-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="16ed4-106">Antes de empezar a usar PowerShell, tendrá que [instalarlo.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="16ed4-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="16ed4-107">Hay problemas conocidos con PowerShell 7 y Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16ed4-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="16ed4-108">Se recomienda usar PowerShell 5.1 hasta que se resuelvan los problemas.</span><span class="sxs-lookup"><span data-stu-id="16ed4-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="16ed4-109">Versiones</span><span class="sxs-lookup"><span data-stu-id="16ed4-109">Releases</span></span>


<span data-ttu-id="16ed4-110">Teams PowerShell está disponible en la [Galería de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) en dos tipos de versión.</span><span class="sxs-lookup"><span data-stu-id="16ed4-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="16ed4-111">**Disponibilidad general (GA):** cmdlets listos para producción, actualizados mensualmente.</span><span class="sxs-lookup"><span data-stu-id="16ed4-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="16ed4-112">**Vista previa pública:** Acceso anticipado a las características.</span><span class="sxs-lookup"><span data-stu-id="16ed4-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="16ed4-113">Es posible que se actualice con más frecuencia que GA.</span><span class="sxs-lookup"><span data-stu-id="16ed4-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="16ed4-114">Para obtener información detallada sobre las adiciones y mejoras de características de ambas versiones, lea las Teams de la versión [de PowerShell.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="16ed4-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="16ed4-115">Administrar Teams con PowerShell</span><span class="sxs-lookup"><span data-stu-id="16ed4-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="16ed4-116">Usará los módulos Teams PowerShell para administrar por completo Teams:</span><span class="sxs-lookup"><span data-stu-id="16ed4-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="16ed4-117">[Microsoft Teams de PowerShell:](https://www.powershellgallery.com/packages/MicrosoftTeams/)el módulo Teams PowerShell contiene cmdlets para administrar equipos, chat y canales.</span><span class="sxs-lookup"><span data-stu-id="16ed4-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="16ed4-118">La Teams versión pública 2.0 o posterior de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) incluye todos los cmdlets de Skype Empresarial Online Connector, lo que proporciona un único módulo para Teams administración de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16ed4-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 2.0 or higher includes all  Skype for Business Online Connector cmdlets, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="16ed4-119">[Skype Empresarial conector de PowerShell:](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)el Skype Empresarial de PowerShell es ahora parte de Teams módulo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16ed4-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="16ed4-120">Para obtener una guía completa sobre cómo administrar Teams estos módulos, vea Administrar Teams [con Teams PowerShell](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="16ed4-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="16ed4-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="16ed4-121">Related topics</span></span>

[<span data-ttu-id="16ed4-122">Instalar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="16ed4-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="16ed4-123">Administrar Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="16ed4-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="16ed4-124">Teams Notas de la versión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="16ed4-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="16ed4-125">Microsoft Teams referencia de cmdlet</span><span class="sxs-lookup"><span data-stu-id="16ed4-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="16ed4-126">Skype Empresarial referencia de cmdlet</span><span class="sxs-lookup"><span data-stu-id="16ed4-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="16ed4-127">Usar los roles de administrador de Microsoft Teams para administrar Teams</span><span class="sxs-lookup"><span data-stu-id="16ed4-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
