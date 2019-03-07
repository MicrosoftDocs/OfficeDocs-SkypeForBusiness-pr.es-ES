---
title: Actualización de Skype para la empresa en línea para los equipos de Microsoft | Implementar
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para actualizar a los equipos de Skype para profesionales en línea
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82577b8e8102baca9ea9681bb94d4a0c73f8b01e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465159"
---
<span data-ttu-id="51844-103">![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")</span><span class="sxs-lookup"><span data-stu-id="51844-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="51844-104">En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización.</span><span class="sxs-lookup"><span data-stu-id="51844-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="51844-105">Antes de continuar, confirme que ha realizado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="51844-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="51844-106">Los participantes en el proyecto de alta</span><span class="sxs-lookup"><span data-stu-id="51844-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="51844-107">Define el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="51844-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="51844-108">Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos</span><span class="sxs-lookup"><span data-stu-id="51844-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="51844-109">Elegido su viaje por la actualización</span><span class="sxs-lookup"><span data-stu-id="51844-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="51844-110">Preparar el entorno</span><span class="sxs-lookup"><span data-stu-id="51844-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="51844-111">Preparar la organización</span><span class="sxs-lookup"><span data-stu-id="51844-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="51844-112">Realiza una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="51844-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="51844-113">Actualización de Skype para la empresa en línea a los equipos</span><span class="sxs-lookup"><span data-stu-id="51844-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="51844-114">Siga las instrucciones de este artículo si totalmente implementado Skype para profesionales en línea y desea actualizar los usuarios de Skype para la empresa a los equipos.</span><span class="sxs-lookup"><span data-stu-id="51844-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="51844-115">Puede actualizar a los usuarios de forma selectiva o en función de la actualización, todo viaje que su organización ha decidido, mediante la asignación de la coexistencia adecuada y el modo de actualización a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="51844-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="51844-116">Asignar el modo de actualización y coexistencia</span><span class="sxs-lookup"><span data-stu-id="51844-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="51844-117">Los usuarios de los equipos que se pueden actualizar asignando el modo de TeamsOnly de TeamsUpgradePolicy, que se puede realizar mediante el centro de administración de Microsoft Teams o un Skype para la sesión remota de Windows Powershell de negocio.</span><span class="sxs-lookup"><span data-stu-id="51844-117">You can upgrade your users by Teams by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="51844-118">Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="51844-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="51844-119">Actualizar todos los usuarios a los equipos a la vez</span><span class="sxs-lookup"><span data-stu-id="51844-119">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="51844-120">Siga estos pasos para actualizar todos los usuarios a los equipos a la vez.</span><span class="sxs-lookup"><span data-stu-id="51844-120">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change"></a><span data-ttu-id="51844-121">Paso 1: Notificar a los usuarios del cambio</span><span class="sxs-lookup"><span data-stu-id="51844-121">Step 1: Notify the users of the change</span></span>

1. <span data-ttu-id="51844-122">En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización** > **actualización de los equipos**.</span><span class="sxs-lookup"><span data-stu-id="51844-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="51844-123">En **modo de coexistencia**, cambie el modificador de **Notificar a Skype para que esté disponible una actualización a los equipos de los usuarios empresariales** a **en**.</span><span class="sxs-lookup"><span data-stu-id="51844-123">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a><span data-ttu-id="51844-124">Paso 2: Establecer el modo de coexistencia para los usuarios</span><span class="sxs-lookup"><span data-stu-id="51844-124">Step 2: Set the coexistence mode for the users</span></span>

1. <span data-ttu-id="51844-125">En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="51844-125">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="51844-126">Seleccione el modo de **Sólo los equipos** desde la lista desplegable **modo de coexistencia** .</span><span class="sxs-lookup"><span data-stu-id="51844-126">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="51844-127">Actualizar los usuarios por fases</span><span class="sxs-lookup"><span data-stu-id="51844-127">Upgrade users in stages</span></span>

<span data-ttu-id="51844-128">Siga estos pasos si desea actualizar gradualmente los usuarios a los equipos.</span><span class="sxs-lookup"><span data-stu-id="51844-128">Follow these steps if you want to gradually upgrade your users to Teams.</span></span>

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a><span data-ttu-id="51844-129">Paso 1: Crear a sus las cohortes de usuario para la actualización</span><span class="sxs-lookup"><span data-stu-id="51844-129">Step 1: Create your user cohorts for the upgrade</span></span>

<span data-ttu-id="51844-130">Las cohortes de usuario son grupos de usuarios que se moverán al modo de sólo los equipos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="51844-130">User cohorts are groups of users who will be moved to Teams Only mode at the same time.</span></span>

<span data-ttu-id="51844-131">Para crear a sus las cohortes de usuario (Agregar vínculo a la página de selección de usuario)</span><span class="sxs-lookup"><span data-stu-id="51844-131">To create your user cohorts (Add link to user selection page)</span></span>

### <a name="step-2-set-the-user-mode-to-islands"></a><span data-ttu-id="51844-132">Paso 2: Establecer el modo de usuario a islas</span><span class="sxs-lookup"><span data-stu-id="51844-132">Step 2: Set the user mode to Islands</span></span>

1. <span data-ttu-id="51844-133">En el centro de administración de Microsoft Teams, seleccione **los usuarios**y, a continuación, seleccione un grupo de edad del usuario.</span><span class="sxs-lookup"><span data-stu-id="51844-133">In the Microsoft Teams admin center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="51844-134">Junto a la **actualización de los equipos**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51844-134">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="51844-135">En el panel de **Actualización de los equipos** , en **modo de coexistencia**, seleccione **Islas** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="51844-135">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Islands** from the drop-down list.</span></span>

### <a name="step-3-set-notification-for-the-user-optional"></a><span data-ttu-id="51844-136">Paso 3: Configurar la notificación para el usuario (opcional)</span><span class="sxs-lookup"><span data-stu-id="51844-136">Step 3: Set notification for the user (optional)</span></span>

1. <span data-ttu-id="51844-137">En el centro de administración de Microsoft Teams, seleccione **los usuarios**y seleccione un grupo de edad del usuario.</span><span class="sxs-lookup"><span data-stu-id="51844-137">In the Microsoft Teams admin center, select **Users**, and select a user cohort.</span></span>
2. <span data-ttu-id="51844-138">Junto a la **actualización de los equipos**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51844-138">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="51844-139">En el panel de **Actualización de los equipos** , en **modo de coexistencia**, cambie modificador **Notificar la Skype para usuarios de empresa** a **en**.</span><span class="sxs-lookup"><span data-stu-id="51844-139">In the **Teams Upgrade** pane, under **Coexistence mode**, change **Notify the Skype for Business user** switch to **On**.</span></span>

### <a name="step-4-set-the-user-mode-to-teams-only"></a><span data-ttu-id="51844-140">Paso 4: Establecer el modo de usuario en los equipos sólo</span><span class="sxs-lookup"><span data-stu-id="51844-140">Step 4: Set the user mode to Teams Only</span></span>

<span data-ttu-id="51844-141">Cuando esté listo para actualizar los usuarios para usar los equipos como su única aplicación, establezca el modo de coexistencia para que el usuario sólo los equipos.</span><span class="sxs-lookup"><span data-stu-id="51844-141">When you are ready to upgrade the users to use Teams as their only application, set the Coexistence mode for the user to Teams Only.</span></span>

1. <span data-ttu-id="51844-142">En el centro de administración de Microsoft Teams, seleccione **los usuarios**y, a continuación, seleccione un grupo de edad del usuario.</span><span class="sxs-lookup"><span data-stu-id="51844-142">In the Microsoft Teams admin center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="51844-143">Junto a la **actualización de los equipos**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51844-143">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="51844-144">En el panel de **Actualización de los equipos** , en **modo de coexistencia**, seleccione **Sólo los equipos** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="51844-144">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Teams Only** from the drop-down list.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="51844-145">Sistema telefónico y los equipos de actualización</span><span class="sxs-lookup"><span data-stu-id="51844-145">Phone System and Teams upgrade</span></span>

<span data-ttu-id="51844-146">Si su Skype para la implementación empresarial Online incluye sistema telefónico con planes de llamada y Microsoft es su proveedor de telefónica conmutada (RTC), actualizar a los usuarios a los equipos automáticamente transición RTC entrante a los equipos de llamada.</span><span class="sxs-lookup"><span data-stu-id="51844-146">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="51844-147">Si su Skype para la implementación empresarial Online incluye sistema telefónico con la edición de conector en la nube, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="51844-147">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>