---
title: Crear equipos de administradores de personas en Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Obtenga información sobre cómo usar un script de PowerShell para crear un equipo para cada administrador con sus directos como miembros del equipo.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094416"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="6249c-103">Crear equipos de administradores de personas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6249c-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="6249c-104">Al ejecutar Microsoft Teams, en lugar de iniciar con una "pizarra en blanco" (sin equipos ni canales), le recomendamos encarecidamente que configure un marco base de equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="6249c-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="6249c-105">Esto ayuda a evitar la "expansión del equipo", donde los usuarios crean numerosos equipos cuando deben crear canales en equipos existentes.</span><span class="sxs-lookup"><span data-stu-id="6249c-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="6249c-106">Para ayudarle a empezar con una estructura de equipos y canales bien diseñada, hemos creado un script de PowerShell que crea un equipo para cada uno de los administradores de personas de primera y segunda línea, con los informes directos de cada administrador como miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="6249c-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="6249c-107">Se trata de un script "a tiempo" (no actualiza los equipos o canales automáticamente cuando se agregan o quitan personas de una organización).</span><span class="sxs-lookup"><span data-stu-id="6249c-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="6249c-108">Pero es una herramienta valiosa que puede usar para imponer algún orden en su estructura Teams desde el principio.</span><span class="sxs-lookup"><span data-stu-id="6249c-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="6249c-109">Este script lee Azure AD, obtiene una lista de administradores y sus informes directos.</span><span class="sxs-lookup"><span data-stu-id="6249c-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="6249c-110">Usa esta lista para crear un equipo por cada administrador de personas.</span><span class="sxs-lookup"><span data-stu-id="6249c-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="6249c-111">Cómo usar el script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="6249c-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="6249c-112">Empiece ejecutando los administradores de exportación y su script de directs (lo que supone que ya ha ejecutado los [módulos](scripts/powershell-script-create-teams-from-managers-export-managers.md) [de PowerShell Conectar-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) [y Conectar-MicrosoftTeams).](/powershell/module/teams/connect-microsoftteams?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="6249c-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="6249c-113">El *script Exportar administradores y* sus directos crea un archivo delimitado por tabulaciones (ExportedManagerDirects.txt) que enumera todos los administradores con sus informes directos.</span><span class="sxs-lookup"><span data-stu-id="6249c-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="6249c-114">A continuación, ejecute el script [Crear nuevos equipos de administrador de personas.](scripts/powershell-script-create-teams-from-managers-new-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6249c-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="6249c-115">Este script se lee en el ExportedManagerDirects.txt y crea un equipo para cada administrador, con los informes directos de ese administrador como miembros.</span><span class="sxs-lookup"><span data-stu-id="6249c-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="6249c-116">Si algún administrador o directo no está habilitado para Teams, el script los omite y no crea un equipo.</span><span class="sxs-lookup"><span data-stu-id="6249c-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="6249c-117">(Revise el informe y vuelva a ejecutar el script después de haber activado Teams para cualquier persona que lo necesite.</span><span class="sxs-lookup"><span data-stu-id="6249c-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="6249c-118">El script no creará un segundo equipo para ningún administrador para el que ya haya creado un equipo).</span><span class="sxs-lookup"><span data-stu-id="6249c-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="6249c-119">Para cada equipo, el script crea un canal General y "Solo por diversión".</span><span class="sxs-lookup"><span data-stu-id="6249c-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="6249c-120">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="6249c-120">Best practices</span></span>

- <span data-ttu-id="6249c-121">Pida a cada administrador de personas que agregue el sitio web de comunicaciones por crisis de su organización como pestaña al canal General de cada equipo.</span><span class="sxs-lookup"><span data-stu-id="6249c-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="6249c-122">Consulte la nueva aplicación Crisis Communications leyendo esta entrada de blog del 8 de marzo de 2020: Coordinar las comunicaciones de [crisis con Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)</span><span class="sxs-lookup"><span data-stu-id="6249c-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6249c-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6249c-123">Related topics</span></span>

[<span data-ttu-id="6249c-124">Procedimientos recomendados para organizar equipos</span><span class="sxs-lookup"><span data-stu-id="6249c-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="6249c-125">Crear un equipo que abarque toda la organización en Teams</span><span class="sxs-lookup"><span data-stu-id="6249c-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)