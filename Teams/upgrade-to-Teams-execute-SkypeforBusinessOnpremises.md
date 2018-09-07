---
title: Actualizar desde un Skype para la implementación local de empresa a los equipos - Microsoft Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para la actualización a los equipos de un Skype para profesionales implementación local.
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3703f7fe8e3a81382a6716e9209ef9ade64cee18
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23869520"
---
<span data-ttu-id="11000-103">![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")</span><span class="sxs-lookup"><span data-stu-id="11000-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="11000-104">En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización.</span><span class="sxs-lookup"><span data-stu-id="11000-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="11000-105">Antes de continuar, confirme que ha realizado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="11000-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="11000-106">Los participantes en el proyecto de alta</span><span class="sxs-lookup"><span data-stu-id="11000-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="11000-107">Define el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="11000-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="11000-108">Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos</span><span class="sxs-lookup"><span data-stu-id="11000-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="11000-109">Elegido su viaje por la actualización</span><span class="sxs-lookup"><span data-stu-id="11000-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="11000-110">Preparar el entorno</span><span class="sxs-lookup"><span data-stu-id="11000-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="11000-111">Preparar la organización</span><span class="sxs-lookup"><span data-stu-id="11000-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="11000-112">Realiza una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="11000-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="11000-113">Actualizar desde un Skype para la implementación local de empresa a los equipos</span><span class="sxs-lookup"><span data-stu-id="11000-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="11000-114">Siga las instrucciones de este artículo si ha implementado Skype para la empresa o Microsoft Lync local y su organización desea actualizar a los equipos de forma selectiva: mediante el uso de varios modos de coexistencia, o todo.</span><span class="sxs-lookup"><span data-stu-id="11000-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="11000-115">El primer paso es configurar conectividad híbrida con el inquilino de Office 365 y, a continuación, mover los usuarios a Skype para profesionales en línea y asígneles la coexistencia adecuada y modo de actualización.</span><span class="sxs-lookup"><span data-stu-id="11000-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="11000-116">Paso 1: Implementar conectividad híbrida</span><span class="sxs-lookup"><span data-stu-id="11000-116">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="11000-117">El requisito previo clave para actualizar a los usuarios a los equipos consiste en implementar conectividad híbrida.</span><span class="sxs-lookup"><span data-stu-id="11000-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="11000-118">Esto podría implicar la implementación nueva conectividad externa para su Skype existente para la implementación empresarial o Lync, o simplemente configurar una relación de híbrida con el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="11000-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span>

<span data-ttu-id="11000-119">Para obtener más información, consulte [Deploy la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="11000-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="11000-120">Paso 2: Mover usuarios a Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="11000-120">Step 2: Move users to Skype for Business Online</span></span>

<span data-ttu-id="11000-121">Una vez completada la configuración híbrida, mover usuarios a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="11000-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="11000-122">Para obtener más información, vea [mover usuarios de local a Skype para profesionales en línea](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="11000-122">For more information, see [Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span></span>

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="11000-123">Paso 3: Asignar una coexistencia y modo de actualización</span><span class="sxs-lookup"><span data-stu-id="11000-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="11000-124">Una vez que haya movido a los usuarios a Skype para profesionales en línea, se puede asignar el modo de coexistencia apropiado según el viaje de actualización que ha elegido la organización.</span><span class="sxs-lookup"><span data-stu-id="11000-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="11000-125">Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="11000-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="11000-126">Skype para Business Server 2019 y una futura actualización acumulativa de Skype para Business Server 2015, podrá realizar el paso 2 (migración de usuarios a Skype para profesionales en línea) y el paso 3 (actualización a los equipos de los usuarios) en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="11000-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="11000-127">Obtener más información, se proporcionará después del lanzamiento de Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="11000-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="11000-128">Sistema telefónico y los equipos de actualización</span><span class="sxs-lookup"><span data-stu-id="11000-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="11000-129">Si está migrando su Skype para la implementación local de empresa de telefonía IP empresarial al sistema de teléfono con planes de llamada y Microsoft será su proveedor de telefónica conmutada (RTC) de la red, y suponiendo que haya completado el número de teléfono trasladar: actualización de los usuarios a los equipos pasará automáticamente las llamadas RTC entrantes a los equipos.</span><span class="sxs-lookup"><span data-stu-id="11000-129">If you’re transitioning your Skype for Business on-premises deployment from enterprise voice to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="11000-130">Si al llamar a los planes de no está disponible, debe realizar la transición de su implementación de enterprise voice para enrutamiento directo de Microsoft teléfono del sistema.</span><span class="sxs-lookup"><span data-stu-id="11000-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="11000-131">Para actualizar a los usuarios a los equipos, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="11000-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>