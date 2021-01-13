---
title: Actualizar la implementación híbrida de Skype Empresarial a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Aprenda a actualizar su organización a Microsoft Teams desde una implementación híbrida de Skype Empresarial.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802350"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="e3549-103">Actualizar desde una implementación híbrida de Skype Empresarial a Teams</span><span class="sxs-lookup"><span data-stu-id="e3549-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="e3549-104">![Fases del viaje de actualización, con énfasis en la fase implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")</span><span class="sxs-lookup"><span data-stu-id="e3549-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e3549-105">Este artículo forma parte de la fase de implementación e implementación del viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="e3549-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e3549-106">Antes de continuar, confirma que has completado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="e3549-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="e3549-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="e3549-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e3549-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="e3549-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="e3549-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="e3549-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="e3549-110">Ha elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="e3549-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e3549-111">Preparado tu entorno</span><span class="sxs-lookup"><span data-stu-id="e3549-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="e3549-112">Ha preparado tu organización</span><span class="sxs-lookup"><span data-stu-id="e3549-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="e3549-113">Se realizó un piloto</span><span class="sxs-lookup"><span data-stu-id="e3549-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="e3549-114">Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y lo ha configurado en una implementación híbrida con su organización de Microsoft 365 u Office 365 y su organización desea actualizar a Teams de forma selectiva (usando varios modos de coexistencia) o todo en él.</span><span class="sxs-lookup"><span data-stu-id="e3549-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="e3549-115">Para ambos viajes de actualización, debe mover los usuarios a Skype Empresarial Online (si aún no están en línea) y asignarles el modo de coexistencia y actualización adecuados.</span><span class="sxs-lookup"><span data-stu-id="e3549-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="e3549-116">Paso 1: Mover usuarios a Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e3549-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="e3549-117">Este paso se aplica a los usuarios que están actualmente homed on-premises.</span><span class="sxs-lookup"><span data-stu-id="e3549-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="e3549-118">Para obtener más información sobre cómo mover estos usuarios a Skype Empresarial Online, vea Mover usuarios de una implementación local a [Skype Empresarial Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="e3549-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="e3549-119">Paso 2: Asignar un modo de coexistencia y actualización</span><span class="sxs-lookup"><span data-stu-id="e3549-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="e3549-120">Después de mover los usuarios a Skype Empresarial Online, puede asignarles el modo de coexistencia adecuado en función del camino de actualización que haya elegido su organización.</span><span class="sxs-lookup"><span data-stu-id="e3549-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="e3549-121">Para obtener más información, vea [Configurar la coexistencia](https://aka.ms/SkypeToTeams-SetCoexistence) y la configuración de actualización y [TeamsUpgradePolicy: administrar la migración y coexistencia.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="e3549-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e3549-122">Con Skype Empresarial Server 2019 y una actualización acumulativa futura de Skype Empresarial Server 2015, podrá realizar los pasos 1 (mover usuarios a Skype Empresarial Online) y paso 2 (actualizar usuarios a Teams) en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="e3549-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="e3549-123">Después de la lanzamiento de Skype Empresarial Server 2019, se le dará más información.</span><span class="sxs-lookup"><span data-stu-id="e3549-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e3549-124">Actualización de Sistema telefónico y Teams</span><span class="sxs-lookup"><span data-stu-id="e3549-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e3549-125">Si va a realizar la transición de su implementación híbrida de Skype Empresarial a Sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica conmutada (RTC) público y, suponiendo que ha completado la porción de números de teléfono, al actualizar los usuarios a Teams se realizarán automáticamente las llamadas RTC de entrada a Teams.</span><span class="sxs-lookup"><span data-stu-id="e3549-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="e3549-126">Si los planes de llamadas no están disponibles o su intención es usar su proveedor de conectividad CON RTC, deberá pasar la implementación de voz empresarial (o una implementación de voz híbrida que usa su implementación local existente o Cloud Connector Edition) a Microsoft Phone System Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="e3549-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="e3549-127">Para actualizar los usuarios a Teams, consulte las [consideraciones adicionales para el enrutamiento directo de sistema telefónico.](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="e3549-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
