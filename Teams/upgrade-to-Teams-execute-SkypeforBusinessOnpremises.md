---
title: Actualizar Skype empresarial local a Microsoft Teams | Implementar | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Consideraciones para actualizar a teams desde una implementación local de Skype empresarial.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 971accd5211c0d8f861ff03db115933f3c75b570
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "37925401"
---
<span data-ttu-id="05a0a-103">![Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación](media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación")</span><span class="sxs-lookup"><span data-stu-id="05a0a-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="05a0a-104">Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="05a0a-104">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="05a0a-105">Antes de continuar, confirme que ha completado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="05a0a-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="05a0a-106">Inventar a los participantes del proyecto</span><span class="sxs-lookup"><span data-stu-id="05a0a-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="05a0a-107">Definió el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="05a0a-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="05a0a-108">La coexistencia y la interoperabilidad de Skype para empresas y equipos</span><span class="sxs-lookup"><span data-stu-id="05a0a-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="05a0a-109">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="05a0a-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="05a0a-110">Preparado su entorno</span><span class="sxs-lookup"><span data-stu-id="05a0a-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="05a0a-111">Preparado para su organización</span><span class="sxs-lookup"><span data-stu-id="05a0a-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="05a0a-112">Ha realizado una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="05a0a-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="05a0a-113">Actualizar desde una implementación local de Skype empresarial a teams</span><span class="sxs-lookup"><span data-stu-id="05a0a-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="05a0a-114">Siga las instrucciones de este artículo si ha implementado Skype empresarial o Microsoft Lync local y su organización quiere actualizar a Microsoft Teams de forma selectiva, mediante el uso de varios modos de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="05a0a-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="05a0a-115">Paso 1: implementar conectividad híbrida</span><span class="sxs-lookup"><span data-stu-id="05a0a-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="05a0a-116">El requisito previo de actualización de los usuarios a teams es implementar la conectividad híbrida.</span><span class="sxs-lookup"><span data-stu-id="05a0a-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="05a0a-117">Para obtener más información, consulte [implementar conectividad híbrida entre Skype empresarial Server y Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) .</span><span class="sxs-lookup"><span data-stu-id="05a0a-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="05a0a-118">Paso 2: implementar el viaje de actualización elegido para su organización</span><span class="sxs-lookup"><span data-stu-id="05a0a-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="05a0a-119">Una vez completada la configuración híbrida, puede planear mover los usuarios a Office 365.</span><span class="sxs-lookup"><span data-stu-id="05a0a-119">After you’ve completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="05a0a-120">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="05a0a-120">For more information, see:</span></span>

- <span data-ttu-id="05a0a-121">[TeamsUpgradePolicy: administración de la migración y la coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="05a0a-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="05a0a-122">[Mover usuarios de local a Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="05a0a-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="05a0a-123">Actualización de equipos y sistemas telefónicos</span><span class="sxs-lookup"><span data-stu-id="05a0a-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="05a0a-124">La transición de sistemas telefónicos locales a equipos le permitirá aprovechar las ventajas del enrutamiento directo de sistema telefónico ("enrutamiento directo") o los planes de llamadas proporcionadas por Microsoft para Office 365.</span><span class="sxs-lookup"><span data-stu-id="05a0a-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing (“Direct Routing”) or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="05a0a-125">Si no usa planes de llamadas en Office 365, necesitará realizar la transición de la implementación de telefonía IP empresarial al enrutamiento de sistema telefónico directo como parte de la actualización a teams.</span><span class="sxs-lookup"><span data-stu-id="05a0a-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="05a0a-126">Para obtener más información, consulte [consideraciones adicionales para el enrutamiento directo de un sistema telefónico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="05a0a-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="05a0a-127">Si tiene pensado usar planes de llamadas en Office 365, consulte nuestra guía para [transferir los números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="05a0a-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>