---
title: Información general sobre PowerShell de Microsoft Teams
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
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="d06f6-103">Información general sobre PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d06f6-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="d06f6-104">Microsoft Teams PowerShell es un conjunto de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d06f6-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="d06f6-105">Escrito en .NET Standard, Teams PowerShell funciona en PowerShell 5.1 en Windows, PowerShell 6.x y versiones posteriores en todas las plataformas, incluido Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="d06f6-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="d06f6-106">Antes de empezar a usar PowerShell, tendrá que [instalarlo.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="d06f6-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="d06f6-107">Hay problemas conocidos con PowerShell 7 y Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d06f6-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="d06f6-108">Se recomienda usar PowerShell 5.1 hasta que se resuelvan los problemas.</span><span class="sxs-lookup"><span data-stu-id="d06f6-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="d06f6-109">Versiones</span><span class="sxs-lookup"><span data-stu-id="d06f6-109">Releases</span></span>


<span data-ttu-id="d06f6-110">Teams PowerShell está disponible en la Galería [de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) en dos tipos de versión.</span><span class="sxs-lookup"><span data-stu-id="d06f6-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="d06f6-111">**Disponibilidad general (GA):** cmdlets listos para producción, actualizados mensualmente.</span><span class="sxs-lookup"><span data-stu-id="d06f6-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="d06f6-112">**Vista previa pública:** Acceso anticipado a las características.</span><span class="sxs-lookup"><span data-stu-id="d06f6-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="d06f6-113">Es posible que se actualice con más frecuencia que GA.</span><span class="sxs-lookup"><span data-stu-id="d06f6-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="d06f6-114">Para obtener información detallada sobre las adiciones y mejoras de características para ambas versiones, lea las notas de la versión [de PowerShell de Teams.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="d06f6-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="d06f6-115">Administrar Teams con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d06f6-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="d06f6-116">Usará módulos de PowerShell de Teams para administrar por completo Teams:</span><span class="sxs-lookup"><span data-stu-id="d06f6-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="d06f6-117">[Módulo De PowerShell de Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)el módulo de PowerShell de Teams contiene cmdlets para administrar equipos, chats y canales.</span><span class="sxs-lookup"><span data-stu-id="d06f6-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="d06f6-118">La versión pública 2.0 o posterior de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams incluye todos los cmdlets de Skype Empresarial Online Connector, lo que proporciona un único módulo para la administración de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="d06f6-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 2.0 or higher includes all  Skype for Business Online Connector cmdlets, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="d06f6-119">[Conector de PowerShell de Skype](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)Empresarial: el conector de PowerShell de Skype Empresarial ahora forma parte del módulo PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="d06f6-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="d06f6-120">Para obtener una guía completa sobre cómo administrar Teams con estos módulos, consulte Administrar [equipos con PowerShell de Teams.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d06f6-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="d06f6-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d06f6-121">Related topics</span></span>

[<span data-ttu-id="d06f6-122">Instalación de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d06f6-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="d06f6-123">Administrar Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d06f6-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="d06f6-124">Notas de la versión de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="d06f6-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="d06f6-125">Referencia de cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d06f6-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="d06f6-126">Referencia de cmdlet de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="d06f6-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="d06f6-127">Usar los roles de administrador de Microsoft Teams para administrar Teams</span><span class="sxs-lookup"><span data-stu-id="d06f6-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
