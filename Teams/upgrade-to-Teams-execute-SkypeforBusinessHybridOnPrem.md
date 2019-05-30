---
title: 'Actualizar a Teams desde una implementación local o híbrida de Skype Empresarial: Microsoft Teams'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para actualizar a teams desde una implementación híbrida o local de Skype empresarial.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 118bae776f4bb3709d62dea1f384ccaa0707397b
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493982"
---
<span data-ttu-id="29004-103">![Actualizar diagrama de viaje, enfatizar implementación e implementación] (media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e") implementación</span><span class="sxs-lookup"><span data-stu-id="29004-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="29004-104">Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="29004-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="29004-105">Antes de continuar, confirme que ha completado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="29004-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="29004-106">Inventar a los participantes del proyecto</span><span class="sxs-lookup"><span data-stu-id="29004-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="29004-107">Definió el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="29004-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="29004-108">La coexistencia y la interoperabilidad de Skype para empresas y equipos</span><span class="sxs-lookup"><span data-stu-id="29004-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="29004-109">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="29004-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="29004-110">Preparado su entorno</span><span class="sxs-lookup"><span data-stu-id="29004-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="29004-111">Preparado para su organización</span><span class="sxs-lookup"><span data-stu-id="29004-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="29004-112">Ha realizado una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="29004-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="29004-113">Actualizar a teams desde una implementación híbrida o local de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="29004-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="29004-114">Siga las instrucciones de este artículo si ha implementado Skype empresarial o Microsoft Lync local y su organización desea actualizarse a teams de forma selectiva, mediante el uso de varios modos de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="29004-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="29004-115">El primer paso es configurar la conectividad híbrida con el inquilino de Office 365 y, a continuación, trasladar a los usuarios a Skype empresarial online y asignarles el modo de coexistencia y actualización apropiado.</span><span class="sxs-lookup"><span data-stu-id="29004-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="29004-116">Paso 1: implementar conectividad híbrida</span><span class="sxs-lookup"><span data-stu-id="29004-116">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="29004-117">El requisito previo de actualización de los usuarios a teams es implementar la conectividad híbrida.</span><span class="sxs-lookup"><span data-stu-id="29004-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="29004-118">Esto puede implicar la implementación de una nueva conectividad externa para su implementación actual de Skype empresarial o de Lync, o simplemente configurar una relación híbrida con su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="29004-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="29004-119">Para obtener más información, consulte [implementar conectividad híbrida entre Skype empresarial Server y Skype empresarial online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="29004-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="29004-120">Paso 2: mover usuarios a Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="29004-120">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="29004-121">Una vez completada la configuración híbrida, mueva usuarios a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="29004-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="29004-122">Para obtener más información, vea [mover usuarios de local a Skype empresarial online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="29004-122">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="29004-123">Paso 3: asignar un modo de coexistencia y actualización</span><span class="sxs-lookup"><span data-stu-id="29004-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="29004-124">Después de mover los usuarios a Skype empresarial online, puede asignarles el modo de coexistencia adecuado en función del recorrido de actualización que haya elegido su organización.</span><span class="sxs-lookup"><span data-stu-id="29004-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="29004-125">Para obtener más información, vea [configurar la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de la migración y](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistencia.</span><span class="sxs-lookup"><span data-stu-id="29004-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="29004-126">Con Skype empresarial Server 2019 y una actualización acumulativa futura de Skype empresarial Server 2015, podrá realizar el paso 2 (mover usuarios a Skype empresarial online) y el paso 3 (actualizar usuarios a teams) en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="29004-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="29004-127">Se proporcionará más información después de que se publique el servidor 2019 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="29004-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="29004-128">Actualización de equipos y sistemas telefónicos</span><span class="sxs-lookup"><span data-stu-id="29004-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="29004-129">Si va a realizar la transición de su implementación híbrida de Skype empresarial a un sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica pública conmutada (RTC) y se ha completado la portabilidad de los números de teléfono, actualice los usuarios a Teams migrará automáticamente las llamadas RTC entrantes a teams.</span><span class="sxs-lookup"><span data-stu-id="29004-129">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="29004-130">Si los planes de llamadas no están disponibles, debe realizar la transición de la implementación de telefonía IP empresarial en el enrutamiento directo de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="29004-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="29004-131">Para actualizar los usuarios a Teams, consulte las [consideraciones adicionales para el enrutamiento directo de sistema telefónico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="29004-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
