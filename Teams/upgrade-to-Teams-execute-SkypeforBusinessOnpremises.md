---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo realizar la transición de su organización a Microsoft Teams desde una implementación local de Skype Empresarial.
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820950"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="a372b-103">Actualizar desde una implementación local de Skype Empresarial a Teams</span><span class="sxs-lookup"><span data-stu-id="a372b-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="a372b-104">![Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación")</span><span class="sxs-lookup"><span data-stu-id="a372b-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="a372b-105">Este artículo forma parte de la fase de implementación e implementación del viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="a372b-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="a372b-106">Antes de continuar, confirma que has completado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="a372b-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="a372b-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="a372b-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="a372b-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="a372b-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="a372b-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="a372b-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="a372b-110">Ha elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="a372b-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="a372b-111">Preparado tu entorno</span><span class="sxs-lookup"><span data-stu-id="a372b-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="a372b-112">Ha preparado tu organización</span><span class="sxs-lookup"><span data-stu-id="a372b-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="a372b-113">Se realizó un piloto</span><span class="sxs-lookup"><span data-stu-id="a372b-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="a372b-114">Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y su organización desea actualizar a Microsoft Teams ya sea de forma selectiva (usando varios modos de coexistencia) o todo en todo el contenido.</span><span class="sxs-lookup"><span data-stu-id="a372b-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="a372b-115">Paso 1: Implementar conectividad híbrida</span><span class="sxs-lookup"><span data-stu-id="a372b-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="a372b-116">El requisito previo clave para actualizar los usuarios a Teams es implementar la conectividad híbrida.</span><span class="sxs-lookup"><span data-stu-id="a372b-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="a372b-117">Para obtener más información, vea [Implementar conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="a372b-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="a372b-118">Paso 2: Implementar el camino de actualización elegido para su organización</span><span class="sxs-lookup"><span data-stu-id="a372b-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="a372b-119">Después de completar la configuración híbrida, puede planear mover los usuarios a Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="a372b-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="a372b-120">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="a372b-120">For more information, see:</span></span>

- <span data-ttu-id="a372b-121">[TeamsUpgradePolicy: administrar la migración y coexistencia.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="a372b-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="a372b-122">[Mueva usuarios locales a Skype Empresarial Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="a372b-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="a372b-123">Actualización de Sistema telefónico y Teams</span><span class="sxs-lookup"><span data-stu-id="a372b-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="a372b-124">La transición de sistemas telefónicos locales a Teams le permitirá aprovechar las ventajas del enrutamiento directo de sistema telefónico ("enrutamiento directo") o de los planes de llamadas proporcionados por Microsoft para Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="a372b-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="a372b-125">Si no usa planes de llamadas, deberá realizar la transición de la implementación de voz empresarial al enrutamiento directo de Sistema telefónico como parte de la actualización a Teams.</span><span class="sxs-lookup"><span data-stu-id="a372b-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="a372b-126">Para obtener más información, vea [consideraciones adicionales para el enrutamiento directo de sistema telefónico.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="a372b-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="a372b-127">Si está pensando en usar planes de llamadas, consulte nuestras instrucciones para [transferir sus números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="a372b-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>