---
title: Información general de Microsoft Teams PowerShell
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
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943993"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="1c605-103">Información general de Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c605-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="1c605-104">Microsoft Teams PowerShell es un conjunto de cmdlets para administrar equipos directamente desde la línea de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c605-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="1c605-105">Desarrollado en .NET Standard, Teams PowerShell funciona en PowerShell 5,1 en Windows, PowerShell 6. x y versiones posteriores en todas las plataformas, incluido el shell de Azure.</span><span class="sxs-lookup"><span data-stu-id="1c605-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="1c605-106">Antes de empezar a usar PowerShell, tendrá que [instalarlo](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="1c605-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="1c605-107">Hay problemas conocidos con PowerShell 7 y Teams.</span><span class="sxs-lookup"><span data-stu-id="1c605-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="1c605-108">Le recomendamos que use el 5,1 de PowerShell hasta que se resuelvan los problemas.</span><span class="sxs-lookup"><span data-stu-id="1c605-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="1c605-109">Ediciones</span><span class="sxs-lookup"><span data-stu-id="1c605-109">Releases</span></span>


<span data-ttu-id="1c605-110">Teams PowerShell está disponible en la [Galería de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) en dos tipos de versiones.</span><span class="sxs-lookup"><span data-stu-id="1c605-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="1c605-111">**Disponibilidad general (GA)**: cmdlets listos para producción, actualizados mensualmente.</span><span class="sxs-lookup"><span data-stu-id="1c605-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="1c605-112">**Versión preliminar pública**: acceso anticipado a las características.</span><span class="sxs-lookup"><span data-stu-id="1c605-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="1c605-113">Puede actualizarse con más frecuencia que la GA.</span><span class="sxs-lookup"><span data-stu-id="1c605-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="1c605-114">Para obtener información detallada sobre las adiciones y mejoras de características de las versiones, lea las notas de la [versión de Teams PowerShell](teams-powershell-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="1c605-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="1c605-115">Administrar equipos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c605-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="1c605-116">Puede usar estos dos módulos de PowerShell para administrar completamente los equipos:</span><span class="sxs-lookup"><span data-stu-id="1c605-116">You'll use both of these PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="1c605-117">[Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): el módulo de PowerShell de Teams contiene cmdlets para administrar equipos, chats y canales.</span><span class="sxs-lookup"><span data-stu-id="1c605-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

- <span data-ttu-id="1c605-118">[Módulo de PowerShell de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=39366): el módulo de PowerShell de Skype empresarial contiene los cmdlets para administrar reuniones, el sistema telefónico y las características de las directivas.</span><span class="sxs-lookup"><span data-stu-id="1c605-118">[Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage meetings, phone system, and policies features.</span></span>

<span data-ttu-id="1c605-119">Para obtener una guía completa de la administración de equipos con estos módulos, consulte [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1c605-119">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1c605-120">La versión más reciente de la [versión preliminar pública de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada en el conector de Skype empresarial online, que ofrece un único módulo para la administración de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="1c605-120">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1c605-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1c605-121">Related topics</span></span>

[<span data-ttu-id="1c605-122">Instalar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c605-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="1c605-123">Administración de equipos con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c605-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="1c605-124">Notas de la versión de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c605-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="1c605-125">Referencia del cmdlet de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c605-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="1c605-126">Referencia de cmdlet de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="1c605-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="1c605-127">Usar los roles de administrador de Microsoft Teams para administrar Teams</span><span class="sxs-lookup"><span data-stu-id="1c605-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
