---
title: Actualizar la implementación híbrida de Skype empresarial a Microsoft Teams | RTC
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Consideraciones para actualizar a teams desde una implementación híbrida de Skype empresarial.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7729cd65ff5d58d348229c4ec5ec6182f06aa5de
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235913"
---
<span data-ttu-id="3c4b6-103">![Etapas del viaje de actualización, con énfasis en la fase de implementación e] implementación (media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e") implementación</span><span class="sxs-lookup"><span data-stu-id="3c4b6-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3c4b6-104">Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="3c4b6-105">Antes de continuar, confirme que ha completado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="3c4b6-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="3c4b6-106">Inventar a los participantes del proyecto</span><span class="sxs-lookup"><span data-stu-id="3c4b6-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3c4b6-107">Definió el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="3c4b6-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="3c4b6-108">La coexistencia y la interoperabilidad de Skype para empresas y equipos</span><span class="sxs-lookup"><span data-stu-id="3c4b6-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="3c4b6-109">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="3c4b6-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3c4b6-110">Preparado su entorno</span><span class="sxs-lookup"><span data-stu-id="3c4b6-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="3c4b6-111">Preparado para su organización</span><span class="sxs-lookup"><span data-stu-id="3c4b6-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="3c4b6-112">Ha realizado una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="3c4b6-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="3c4b6-113">Actualizar a teams desde una implementación híbrida de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="3c4b6-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="3c4b6-114">Siga las instrucciones de este artículo si ha implementado Skype empresarial o Microsoft Lync local y lo ha configurado en una implementación híbrida con su inquilino de Office 365, y su organización quiere actualizar a teams de forma selectiva; para ello, use varias modos de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="3c4b6-115">Para realizar cualquiera de las actualizaciones, necesita mover los usuarios a Skype empresarial online (si no están conectados) y, a continuación, asignarles el modo de coexistencia y actualización apropiado.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="3c4b6-116">Paso 1: mover usuarios a Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="3c4b6-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="3c4b6-117">Este paso se aplica a los usuarios que actualmente están alojados en local.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="3c4b6-118">Para obtener más información sobre cómo mover estos usuarios a Skype empresarial online, consulte [mover usuarios de local a Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="3c4b6-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="3c4b6-119">Paso 2: asignar un modo de coexistencia y actualización</span><span class="sxs-lookup"><span data-stu-id="3c4b6-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="3c4b6-120">Después de mover los usuarios a Skype empresarial online, puede asignarles el modo de coexistencia adecuado en función del recorrido de actualización que haya elegido su organización.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="3c4b6-121">Para obtener más información, vea [configurar la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de la migración y](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistencia.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="3c4b6-122">Con Skype empresarial Server 2019 y una actualización acumulativa futura de Skype empresarial Server 2015, podrá realizar el paso 1 (mover usuarios a Skype empresarial online) y el paso 2 (actualizar usuarios a teams) en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="3c4b6-123">Se proporcionará más información después de que se publique el servidor 2019 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="3c4b6-124">Actualización de equipos y sistemas telefónicos</span><span class="sxs-lookup"><span data-stu-id="3c4b6-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="3c4b6-125">Si va a realizar la transición de su implementación híbrida de Skype empresarial a un sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica pública conmutada (RTC) y se ha completado la portabilidad de los números de teléfono, actualice los usuarios a Teams migrará automáticamente las llamadas RTC entrantes a teams.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="3c4b6-126">Si los planes de llamadas no están disponibles o pretende usar su proveedor de conectividad con RTC existente, debe realizar una transición de la implementación de telefonía IP empresarial, o de la implementación de voz híbrida que usa su implementación local existente o de la versión de conector de nube, para Enrutamiento directo de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="3c4b6-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="3c4b6-127">Para actualizar los usuarios a Teams, consulte las [consideraciones adicionales para el enrutamiento directo de sistema telefónico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3c4b6-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
