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
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852161"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="f33a7-103">Información general sobre PowerShell de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f33a7-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="f33a7-104">Microsoft Teams PowerShell es un conjunto de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f33a7-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="f33a7-105">Escrito en .NET Standard, Teams PowerShell funciona en PowerShell 5.1 en Windows, PowerShell 6.x y versiones posteriores en todas las plataformas, incluido Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="f33a7-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="f33a7-106">Antes de empezar a usar PowerShell, debe [instalarlo.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="f33a7-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="f33a7-107">Hay problemas conocidos con PowerShell 7 y Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f33a7-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="f33a7-108">Se recomienda usar PowerShell 5.1 hasta que se resuelvan los problemas.</span><span class="sxs-lookup"><span data-stu-id="f33a7-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="f33a7-109">Versiones</span><span class="sxs-lookup"><span data-stu-id="f33a7-109">Releases</span></span>


<span data-ttu-id="f33a7-110">Teams PowerShell está disponible en la galería [de PowerShell en](https://www.powershellgallery.com/packages/MicrosoftTeams) dos tipos de versión.</span><span class="sxs-lookup"><span data-stu-id="f33a7-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="f33a7-111">**Disponibilidad general (GA):** cmdlets preparados para producción que se actualizan mensualmente.</span><span class="sxs-lookup"><span data-stu-id="f33a7-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="f33a7-112">**Versión preliminar pública:** Acceso anticipado a características.</span><span class="sxs-lookup"><span data-stu-id="f33a7-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="f33a7-113">Puede actualizarse con más frecuencia que GA.</span><span class="sxs-lookup"><span data-stu-id="f33a7-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="f33a7-114">Para obtener información detallada sobre las adiciones de características y las mejoras de ambas versiones, lea las [notas de la versión de PowerShell de Teams.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="f33a7-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="f33a7-115">Administrar Teams con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f33a7-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="f33a7-116">Usará los módulos de PowerShell de Teams para administrar teams por completo:</span><span class="sxs-lookup"><span data-stu-id="f33a7-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="f33a7-117">[Módulo De PowerShell de Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)el módulo PowerShell de Teams contiene cmdlets para administrar equipos, chat y canales.</span><span class="sxs-lookup"><span data-stu-id="f33a7-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="f33a7-118">La última [versión pública de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams se integra con Skype Empresarial Online Connector, proporcionando un módulo único para la administración de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="f33a7-118">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="f33a7-119">[Conector de PowerShell de Skype](https://www.microsoft.com/download/details.aspx?id=39366)Empresarial: El conector de PowerShell de Skype Empresarial ahora forma parte del módulo PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="f33a7-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="f33a7-120">Para obtener una guía completa sobre la administración de Teams con estos módulos, consulte [Administrar equipos con PowerShell de Teams.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f33a7-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="f33a7-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f33a7-121">Related topics</span></span>

[<span data-ttu-id="f33a7-122">Instalación de Teams powerShell</span><span class="sxs-lookup"><span data-stu-id="f33a7-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="f33a7-123">Administrar Teams con PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="f33a7-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="f33a7-124">Notas de la versión de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="f33a7-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="f33a7-125">Referencia de cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f33a7-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="f33a7-126">Referencia de cmdlet de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f33a7-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="f33a7-127">Usar los roles de administrador de Microsoft Teams para administrar Teams</span><span class="sxs-lookup"><span data-stu-id="f33a7-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
