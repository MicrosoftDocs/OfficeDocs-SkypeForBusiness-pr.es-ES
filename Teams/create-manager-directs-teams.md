---
title: Crear equipos de administración de personas en Microsoft Teams
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Aprenda a usar un script de PowerShell para crear un equipo para cada jefe con sus directos como miembros del equipo.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796222"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="ba595-103">Crear equipos de administración de personas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba595-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="ba595-104">Al implementar Microsoft Teams, en lugar de iniciar una "pizarra en blanco" (sin equipos ni canales), le recomendamos encarecidamente que configure un marco de trabajo base de Teams y canales.</span><span class="sxs-lookup"><span data-stu-id="ba595-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="ba595-105">Esto ayuda a evitar la "proliferación de equipos", en la que los usuarios crean numerosos equipos cuando deberían crear canales en los equipos existentes.</span><span class="sxs-lookup"><span data-stu-id="ba595-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="ba595-106">Para ayudarle a comenzar a usar una estructura de equipos y canales bien diseñada, hemos creado un script de PowerShell que crea un equipo para cada uno de sus administradores de contactos de primera y segunda línea, con los informes directos de cada Gerente como miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="ba595-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="ba595-107">Este es un script "puntual" (no actualiza los equipos ni los canales de forma automática cuando se agregan o quitan usuarios de una organización).</span><span class="sxs-lookup"><span data-stu-id="ba595-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="ba595-108">Pero es una herramienta valiosa que puede usar para imponer algún pedido en la estructura de su equipo desde el principio.</span><span class="sxs-lookup"><span data-stu-id="ba595-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="ba595-109">Este script lee su Azure AD, obtiene una lista de administradores y sus subordinados directos.</span><span class="sxs-lookup"><span data-stu-id="ba595-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="ba595-110">Usa esta lista para crear un equipo por administrador de personas.</span><span class="sxs-lookup"><span data-stu-id="ba595-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="ba595-111">Cómo usar el script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba595-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="ba595-112">Para empezar, ejecute los [administradores de exportación y sus secuencias de comandos de Direct](scripts/powershell-script-create-teams-from-managers-export-managers.md) (lo cual supone que ya ha ejecutado los módulos [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) y [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ba595-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="ba595-113">Los *administradores de exportaciones y sus* scripts directos crean un archivo delimitado por tabulaciones (ExportedManagerDirects. txt) que enumera a todos los administradores con sus subordinados directos.</span><span class="sxs-lookup"><span data-stu-id="ba595-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="ba595-114">A continuación, ejecute el [script de Teams crear nuevo jefe de contactos](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ba595-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="ba595-115">Este script se lee en el archivo ExportedManagerDirects. txt y crea un equipo para cada jefe, con los informes directos de ese administrador como miembros.</span><span class="sxs-lookup"><span data-stu-id="ba595-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="ba595-116">Si algún administrador o directo no está habilitado para Teams, el script lo omite y no crea un equipo.</span><span class="sxs-lookup"><span data-stu-id="ba595-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="ba595-117">(Revise el informe y vuelva a ejecutar el script una vez que haya activado Teams para cualquiera que lo necesite.</span><span class="sxs-lookup"><span data-stu-id="ba595-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="ba595-118">La secuencia de comandos no creará un segundo equipo para cualquier administrador para el que ya haya creado un equipo.</span><span class="sxs-lookup"><span data-stu-id="ba595-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="ba595-119">Para cada equipo, el script crea un canal general y "solo para el entretenimiento".</span><span class="sxs-lookup"><span data-stu-id="ba595-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="ba595-120">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="ba595-120">Best practices</span></span>

- <span data-ttu-id="ba595-121">Pídale al administrador de cada persona que agregue el sitio web de comunicaciones de crisis de su organización como una ficha al canal general de cada equipo.</span><span class="sxs-lookup"><span data-stu-id="ba595-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="ba595-122">Consulta la nueva aplicación de comunicaciones de crisis leyendo la publicación del blog del 8 de marzo de 2020: [coordina las comunicaciones de crisis con Microsoft Teams + plataforma de energía](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span><span class="sxs-lookup"><span data-stu-id="ba595-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba595-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ba595-123">Related topics</span></span>

[<span data-ttu-id="ba595-124">Procedimientos recomendados para organizar equipos</span><span class="sxs-lookup"><span data-stu-id="ba595-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="ba595-125">Crear un equipo que abarque toda la organización en Teams</span><span class="sxs-lookup"><span data-stu-id="ba595-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
