---
title: Actualización de Skype para su implementación híbrida empresarial en Microsoft Teams | RTC
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para la actualización a los equipos de un Skype para implementación híbrida de negocio.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: c78c5b519997c125dc1902021acabe664ea03047
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349578"
---
<span data-ttu-id="fae37-103">![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")</span><span class="sxs-lookup"><span data-stu-id="fae37-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="fae37-104">En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización.</span><span class="sxs-lookup"><span data-stu-id="fae37-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="fae37-105">Antes de continuar, confirme que ha realizado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="fae37-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="fae37-106">Los participantes en el proyecto de alta</span><span class="sxs-lookup"><span data-stu-id="fae37-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="fae37-107">Define el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="fae37-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="fae37-108">Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos</span><span class="sxs-lookup"><span data-stu-id="fae37-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="fae37-109">Elegido su viaje por la actualización</span><span class="sxs-lookup"><span data-stu-id="fae37-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="fae37-110">Preparar el entorno</span><span class="sxs-lookup"><span data-stu-id="fae37-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="fae37-111">Preparar la organización</span><span class="sxs-lookup"><span data-stu-id="fae37-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="fae37-112">Realiza una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="fae37-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="fae37-113">Actualizar desde un Skype para implementación híbrida de negocio a los equipos</span><span class="sxs-lookup"><span data-stu-id="fae37-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="fae37-114">Siga las instrucciones de este artículo si ha implementado Skype para la empresa o Microsoft Lync local configurado en una implementación híbrida con el inquilino de Office 365 y su organización desea actualizar a los equipos de forma selectiva: mediante el uso de varios modos de coexistencia, o todo.</span><span class="sxs-lookup"><span data-stu-id="fae37-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="fae37-115">Para cualquier viaje de actualización, debe mover los usuarios a Skype para profesionales en línea (si ya no están alojados en línea) y a continuación, asignar la coexistencia adecuada y el modo de actualización.</span><span class="sxs-lookup"><span data-stu-id="fae37-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="fae37-116">Paso 1: Mover usuarios a Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="fae37-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="fae37-117">En este paso se aplica a los usuarios que están actualmente asignados local.</span><span class="sxs-lookup"><span data-stu-id="fae37-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="fae37-118">Para obtener más información sobre cómo mover estos usuarios a Skype para profesionales en línea, consulte [mover usuarios de local - a Skype para profesionales en línea](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="fae37-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="fae37-119">Paso 2: Asignar una coexistencia y modo de actualización</span><span class="sxs-lookup"><span data-stu-id="fae37-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="fae37-120">Una vez que haya movido a los usuarios a Skype para profesionales en línea, se puede asignar el modo de coexistencia apropiado según el viaje de actualización que ha elegido la organización.</span><span class="sxs-lookup"><span data-stu-id="fae37-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="fae37-121">Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="fae37-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="fae37-122">Skype para Business Server 2019 y una futura actualización acumulativa de Skype para Business Server 2015, podrá realizar el paso 1 (mover los usuarios a Skype para profesionales en línea) y el paso 2 (actualización a los equipos de los usuarios) en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="fae37-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="fae37-123">Obtener más información, se proporcionará después del lanzamiento de Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fae37-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="fae37-124">Sistema telefónico y los equipos de actualización</span><span class="sxs-lookup"><span data-stu-id="fae37-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="fae37-125">Si está migrando su Skype para implementación híbrida de negocio al sistema de teléfono con planes de llamada y Microsoft será su proveedor de telefónica conmutada (RTC) de la red, y suponiendo que haya completado el número de teléfono trasladar — actualizar a los usuarios a Los equipos automáticamente va a realizar la transición de RTC entrante a los equipos de llamada.</span><span class="sxs-lookup"><span data-stu-id="fae37-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="fae37-126">Si al llamar a los planes de no está disponible o piensa usar el proveedor de conectividad RTC existente, es necesario realizar la transición de su implementación de enterprise voice: implementación de voz híbrida que usa la existente local o en la implementación o en la nube conector Edition — a Enrutamiento directo de sistema telefónico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fae37-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="fae37-127">Para actualizar a los usuarios a los equipos, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="fae37-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
