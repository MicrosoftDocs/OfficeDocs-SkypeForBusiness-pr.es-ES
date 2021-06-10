---
title: Información general sobre cómo implementar la actualización a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Determine la ruta de actualización óptima para Microsoft Teams en función de su implementación Skype Empresarial actual.
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
ms.openlocfilehash: 1774b8bebc1330e69a611e64d4f0a8e01f05febb
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282377"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="5856d-103">Información general sobre cómo implementar la actualización</span><span class="sxs-lookup"><span data-stu-id="5856d-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="5856d-104">![Fases del viaje de actualización, con énfasis en la fase implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")</span><span class="sxs-lookup"><span data-stu-id="5856d-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="5856d-105">Este artículo forma parte de la fase implementación e implementación del viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="5856d-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="5856d-106">Actividades de planificación de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5856d-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5856d-107">Antes de continuar con la implementación de actualización, confirme que ha leído el contenido de planeación a partir de [Planear](upgrade-plan-journey.md) la actualización para asegurarse de que ha completado todas las actividades de planeación de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="5856d-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="5856d-108">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="5856d-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5856d-109">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="5856d-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="5856d-110">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="5856d-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="5856d-111">Elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="5856d-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="5856d-112">Planear un piloto de usuario</span><span class="sxs-lookup"><span data-stu-id="5856d-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="5856d-113">Preparado el entorno</span><span class="sxs-lookup"><span data-stu-id="5856d-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="5856d-114">Preparar la organización</span><span class="sxs-lookup"><span data-stu-id="5856d-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="5856d-115">Elegir el punto de inicio de la actualización</span><span class="sxs-lookup"><span data-stu-id="5856d-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="5856d-116">Los pasos que realice para realizar la actualización a Teams depende de la implementación actual de Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="5856d-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="5856d-117">En función de su entorno actual, elija el punto de partida:</span><span class="sxs-lookup"><span data-stu-id="5856d-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="5856d-118">**Si va a actualizar de Skype Empresarial Online a Teams**, siga los pasos de Actualizar de Skype Empresarial Online a [Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span><span class="sxs-lookup"><span data-stu-id="5856d-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="5856d-119">**Si va a** actualizar desde un entorno local de Skype Empresarial, deberá realizar algunos pasos adicionales para configurar la conectividad entre los entornos locales y en línea antes de mover a los usuarios a Teams.</span><span class="sxs-lookup"><span data-stu-id="5856d-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="5856d-120">Para obtener más información, vea [Actualizar Skype Empresarial local a Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="5856d-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]