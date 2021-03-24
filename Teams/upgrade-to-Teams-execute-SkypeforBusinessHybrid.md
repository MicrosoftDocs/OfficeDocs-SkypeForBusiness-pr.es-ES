---
title: Actualizar la implementación híbrida de Skype Empresarial a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación híbrida de Skype Empresarial.
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104026"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="aa00b-103">Actualizar de una implementación híbrida de Skype Empresarial a Teams</span><span class="sxs-lookup"><span data-stu-id="aa00b-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="aa00b-104">![Fases del viaje de actualización, con énfasis en la fase implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")</span><span class="sxs-lookup"><span data-stu-id="aa00b-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="aa00b-105">Este artículo forma parte de la fase de implementación e implementación del viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="aa00b-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="aa00b-106">Antes de continuar, confirme que ha completado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="aa00b-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="aa00b-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="aa00b-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="aa00b-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="aa00b-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="aa00b-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="aa00b-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="aa00b-110">Elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="aa00b-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="aa00b-111">Preparado el entorno</span><span class="sxs-lookup"><span data-stu-id="aa00b-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="aa00b-112">Preparar la organización</span><span class="sxs-lookup"><span data-stu-id="aa00b-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="aa00b-113">Llevó a cabo un piloto</span><span class="sxs-lookup"><span data-stu-id="aa00b-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="aa00b-114">Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y lo ha configurado en una implementación híbrida con su organización de Microsoft 365 u Office 365, y su organización quiere actualizar a Teams de forma selectiva (mediante varios modos de coexistencia) o todo en.</span><span class="sxs-lookup"><span data-stu-id="aa00b-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="aa00b-115">Para cualquier viaje de actualización, debe mover a los usuarios a Skype Empresarial Online (si aún no están en línea) y, a continuación, asignarles el modo de coexistencia y actualización adecuados.</span><span class="sxs-lookup"><span data-stu-id="aa00b-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="aa00b-116">Paso 1: Mover usuarios a Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aa00b-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="aa00b-117">Este paso se aplica a los usuarios que se encuentran actualmente en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="aa00b-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="aa00b-118">Para obtener más información sobre cómo mover estos usuarios a Skype Empresarial Online, vea Mover usuarios de local [a Skype Empresarial Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="aa00b-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="aa00b-119">Paso 2: Asignar un modo de coexistencia y actualización</span><span class="sxs-lookup"><span data-stu-id="aa00b-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="aa00b-120">Después de mover a los usuarios a Skype Empresarial Online, puede asignarles el modo de coexistencia adecuado en función del viaje de actualización que haya elegido su organización.</span><span class="sxs-lookup"><span data-stu-id="aa00b-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="aa00b-121">Para obtener más información, vea [Establecer la configuración de](./setting-your-coexistence-and-upgrade-settings.md) coexistencia y actualización y [TeamsUpgradePolicy: administrar la migración y la coexistencia.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="aa00b-121">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aa00b-122">Con Skype Empresarial Server 2019 y una actualización acumulativa futura de Skype Empresarial Server 2015, podrá realizar el paso 1 (mover usuarios a Skype Empresarial Online) y el paso 2 (actualizar usuarios a Teams) en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="aa00b-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="aa00b-123">Después de publicar Skype Empresarial Server 2019, se proporciona más información.</span><span class="sxs-lookup"><span data-stu-id="aa00b-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="aa00b-124">Actualización de Sistema telefónico y Teams</span><span class="sxs-lookup"><span data-stu-id="aa00b-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="aa00b-125">Si está cambiando su implementación híbrida de Skype Empresarial a Sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica conmutada (RTC) público y, suponiendo que haya completado la porción de número de teléfono, actualizar los usuarios a Teams pasará automáticamente las llamadas RTC entrantes a Teams.</span><span class="sxs-lookup"><span data-stu-id="aa00b-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="aa00b-126">Si los planes de llamadas no están disponibles o tiene la intención de usar su proveedor de conectividad RTC existente, debe cambiar la implementación de voz empresarial (o la implementación de voz híbrida que usa su implementación local existente o Cloud Connector Edition) a Enrutamiento directo de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="aa00b-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="aa00b-127">Para actualizar los usuarios a Teams, vea las [consideraciones adicionales](./direct-routing-landing-page.md)para enrutamiento directo del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="aa00b-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span>