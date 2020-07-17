---
title: Actualizar a Microsoft Teams | Guía básica de equipos de Skype para empresas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Determine la ruta de actualización óptima a Microsoft Teams en función de su implementación actual de Skype empresarial.
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
ms.openlocfilehash: 4a0e8ca9356704d471320e4474f48270375aea2d
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868497"
---
# <a name="overview"></a><span data-ttu-id="bd455-103">Información general</span><span class="sxs-lookup"><span data-stu-id="bd455-103">Overview</span></span>

<span data-ttu-id="bd455-104">![Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación](media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación")</span><span class="sxs-lookup"><span data-stu-id="bd455-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="bd455-105">Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="bd455-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="bd455-106">Requisitos previos de planificación</span><span class="sxs-lookup"><span data-stu-id="bd455-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd455-107">Antes de continuar con la implementación de la actualización, confirme que ha leído el contenido de la planificación empezando por [planificar la actualización](upgrade-plan-journey.md) para asegurarse de que ha completado todas las actividades de planeación de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="bd455-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="bd455-108">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="bd455-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="bd455-109">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="bd455-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="bd455-110">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="bd455-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="bd455-111">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="bd455-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="bd455-112">Planear una prueba piloto de usuario</span><span class="sxs-lookup"><span data-stu-id="bd455-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="bd455-113">Preparado su entorno</span><span class="sxs-lookup"><span data-stu-id="bd455-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="bd455-114">Preparado para su organización</span><span class="sxs-lookup"><span data-stu-id="bd455-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="bd455-115">Elegir el punto de inicio de la actualización</span><span class="sxs-lookup"><span data-stu-id="bd455-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="bd455-116">Los pasos que debe seguir para realizar la actualización a teams dependen de la implementación actual de Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="bd455-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="bd455-117">En función de su entorno actual, elija el punto de partida:</span><span class="sxs-lookup"><span data-stu-id="bd455-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="bd455-118">**Si va a actualizar de Skype empresarial online a teams**, siga los pasos de [actualización de Skype empresarial online a teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span><span class="sxs-lookup"><span data-stu-id="bd455-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="bd455-119">**Si va a actualizar desde un entorno local de Skype empresarial**, tendrá que realizar algunos pasos adicionales para configurar la conectividad entre los entornos locales y en línea antes de mover los usuarios a teams.</span><span class="sxs-lookup"><span data-stu-id="bd455-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="bd455-120">Para obtener más información, consulte [actualizar a teams local de Skype empresarial](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="bd455-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
