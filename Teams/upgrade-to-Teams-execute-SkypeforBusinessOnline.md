---
title: Actualización de Skype para la empresa en línea a equipos - equipos de Microsoft
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para actualizar a los equipos de Skype para profesionales en línea
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: fabcd88a0444a01f950064ade0c49dfef50400e1
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013574"
---
<span data-ttu-id="91793-103">![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")</span><span class="sxs-lookup"><span data-stu-id="91793-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="91793-104">En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización.</span><span class="sxs-lookup"><span data-stu-id="91793-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="91793-105">Antes de continuar, confirme que ha realizado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="91793-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="91793-106">Los participantes en el proyecto de alta</span><span class="sxs-lookup"><span data-stu-id="91793-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="91793-107">Define el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="91793-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="91793-108">Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos</span><span class="sxs-lookup"><span data-stu-id="91793-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="91793-109">Elegido su viaje por la actualización</span><span class="sxs-lookup"><span data-stu-id="91793-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="91793-110">Preparar el entorno</span><span class="sxs-lookup"><span data-stu-id="91793-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="91793-111">Preparar la organización</span><span class="sxs-lookup"><span data-stu-id="91793-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="91793-112">Realiza una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="91793-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="91793-113">Actualización de Skype para la empresa en línea a los equipos</span><span class="sxs-lookup"><span data-stu-id="91793-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="91793-114">Siga las instrucciones de este artículo si totalmente implementado Skype para profesionales en línea y desea actualizar los usuarios de Skype para la empresa a los equipos.</span><span class="sxs-lookup"><span data-stu-id="91793-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="91793-115">Puede actualizar a los usuarios de forma selectiva o en función de la actualización, todo viaje que su organización ha decidido, mediante la asignación de la coexistencia adecuada y el modo de actualización a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="91793-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="91793-116">Asignar el modo de actualización y coexistencia</span><span class="sxs-lookup"><span data-stu-id="91793-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="91793-117">Actualización a los equipos puede realizarse mediante la asignación el modo de TeamsOnly de TeamsUpgradePolicy, que se puede realizar mediante el uso de Microsoft Teams & Skype para el centro de administración de negocio o un Skype para la sesión remota de Windows Powershell de negocio.</span><span class="sxs-lookup"><span data-stu-id="91793-117">Upgrading to Teams can be accomplished by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="91793-118">Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="91793-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="91793-119">Sistema telefónico y los equipos de actualización</span><span class="sxs-lookup"><span data-stu-id="91793-119">Phone System and Teams upgrade</span></span>

<span data-ttu-id="91793-120">Si su Skype para la implementación empresarial Online incluye sistema telefónico con planes de llamada y Microsoft es su proveedor de telefónica conmutada (RTC), actualizar a los usuarios a los equipos automáticamente transición RTC entrante a los equipos de llamada.</span><span class="sxs-lookup"><span data-stu-id="91793-120">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="91793-121">Si su Skype para la implementación empresarial Online incluye sistema telefónico con la edición de conector en la nube, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="91793-121">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>