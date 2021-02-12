---
title: Información general sobre cómo implementar la actualización a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Determine la ruta de actualización óptima a Microsoft Teams en función de su implementación actual de Skype Empresarial.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578363"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="00656-103">Información general sobre la implementación de la actualización</span><span class="sxs-lookup"><span data-stu-id="00656-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="00656-104">![Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación")</span><span class="sxs-lookup"><span data-stu-id="00656-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="00656-105">Este artículo forma parte de la fase de implementación e implementación del viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="00656-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="00656-106">Actividades de planeación de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="00656-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00656-107">Antes de continuar con la implementación de la actualización, confirme que ha leído el contenido de planificación empezando con [Planear](upgrade-plan-journey.md) la actualización para asegurarse de que ha completado todos los requisitos previos de las actividades de planeación.</span><span class="sxs-lookup"><span data-stu-id="00656-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="00656-108">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="00656-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="00656-109">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="00656-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="00656-110">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="00656-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="00656-111">Ha elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="00656-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="00656-112">Piloto de usuario planeado</span><span class="sxs-lookup"><span data-stu-id="00656-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="00656-113">Preparado tu entorno</span><span class="sxs-lookup"><span data-stu-id="00656-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="00656-114">Ha preparado tu organización</span><span class="sxs-lookup"><span data-stu-id="00656-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="00656-115">Elegir el punto de partida de la actualización</span><span class="sxs-lookup"><span data-stu-id="00656-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="00656-116">Los pasos que debe seguir para realizar la actualización a Teams dependen de la implementación actual de Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="00656-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="00656-117">En función de su entorno actual, elija su punto de partida:</span><span class="sxs-lookup"><span data-stu-id="00656-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="00656-118">**Si va a actualizar de Skype Empresarial Online a Teams,** siga los pasos indicados en la actualización de [Skype Empresarial Online a Teams.](https://aka.ms/SkypeToTeams-UpgradeOnline)</span><span class="sxs-lookup"><span data-stu-id="00656-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="00656-119">**Si** va a actualizar desde un entorno local de Skype Empresarial, deberá realizar algunos pasos adicionales para configurar la conectividad entre su entorno local y en línea antes de mover los usuarios a Teams.</span><span class="sxs-lookup"><span data-stu-id="00656-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="00656-120">Para obtener más información, [consulte Actualizar Skype Empresarial local a Teams.](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="00656-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
