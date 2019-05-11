---
title: Actualización de Skype para la empresa en línea para los equipos de Microsoft | Implementar
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902728"
---
<span data-ttu-id="0909e-103">![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")</span><span class="sxs-lookup"><span data-stu-id="0909e-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="0909e-104">En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización.</span><span class="sxs-lookup"><span data-stu-id="0909e-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="0909e-105">Antes de continuar, confirme que ha realizado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="0909e-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="0909e-106">Los participantes en el proyecto de alta</span><span class="sxs-lookup"><span data-stu-id="0909e-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="0909e-107">Define el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="0909e-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="0909e-108">Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos</span><span class="sxs-lookup"><span data-stu-id="0909e-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="0909e-109">Elegido su viaje por la actualización</span><span class="sxs-lookup"><span data-stu-id="0909e-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="0909e-110">Preparar el entorno</span><span class="sxs-lookup"><span data-stu-id="0909e-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="0909e-111">Preparar la organización</span><span class="sxs-lookup"><span data-stu-id="0909e-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="0909e-112">Realiza una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="0909e-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="0909e-113">Actualización de Skype Empresarial Online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0909e-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="0909e-114">Siga las instrucciones de este artículo si totalmente implementado Skype para profesionales en línea y desea actualizar los usuarios de Skype para la empresa a los equipos.</span><span class="sxs-lookup"><span data-stu-id="0909e-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="0909e-115">Puede actualizar a los usuarios de forma selectiva o en función de la actualización, todo viaje que su organización ha decidido, mediante la asignación de la coexistencia adecuada y el modo de actualización a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0909e-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="0909e-116">Asignar el modo de actualización y coexistencia</span><span class="sxs-lookup"><span data-stu-id="0909e-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="0909e-117">Puede actualizar a los usuarios a modo de TeamsOnly mediante la asignación de la instancia de UpgradeToTeams de TeamsUpgradePolicy, que se puede realizar mediante el centro de administración de Microsoft Teams o un Skype para la sesión remota de Windows Powershell de negocio.</span><span class="sxs-lookup"><span data-stu-id="0909e-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="0909e-118">Puede hacerlo de forma individual por usuario, o en todo el inquilino si desea actualización el inquilino todo en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="0909e-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="0909e-119">Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="0909e-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="0909e-120">Actualizar todos los usuarios a los equipos a la vez</span><span class="sxs-lookup"><span data-stu-id="0909e-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="0909e-121">Siga estos pasos para actualizar todos los usuarios a los equipos a la vez.</span><span class="sxs-lookup"><span data-stu-id="0909e-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="0909e-122">Paso 1: Notificar a los usuarios el cambio (opcional)</span><span class="sxs-lookup"><span data-stu-id="0909e-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="0909e-123">En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización** > **actualización de los equipos**.</span><span class="sxs-lookup"><span data-stu-id="0909e-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="0909e-124">En **modo de coexistencia**, cambie el modificador de **Notificar a Skype para que esté disponible una actualización a los equipos de los usuarios empresariales** a **en**.</span><span class="sxs-lookup"><span data-stu-id="0909e-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="0909e-125">Paso 2: Establecer el modo de coexistencia en TeamsOnly para la organización</span><span class="sxs-lookup"><span data-stu-id="0909e-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="0909e-126">En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="0909e-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="0909e-127">Seleccione el modo de **Sólo los equipos** desde la lista desplegable **modo de coexistencia** .</span><span class="sxs-lookup"><span data-stu-id="0909e-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="0909e-128">Actualizar los usuarios por fases</span><span class="sxs-lookup"><span data-stu-id="0909e-128">Upgrade users in stages</span></span>

<span data-ttu-id="0909e-129">Siga estos pasos si desea actualizar gradualmente los usuarios a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="0909e-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="0909e-130">Paso 1: Identificación de grupos de usuarios para la actualización</span><span class="sxs-lookup"><span data-stu-id="0909e-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="0909e-131">A menudo, las organizaciones pueden optar por actualizar sus organizaciones en ondas de éxito de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0909e-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="0909e-132">Desea identificar estos usuarios en primer lugar, por lo que puede buscar fácilmente para ellos en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0909e-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0909e-133">Como alternativa, es posible que desea usar PowerShell para hacerlo de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="0909e-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="0909e-134">Una vez que haya identificado el conjunto de usuarios para una determinada onda de actualización, continúe con los pasos restantes.</span><span class="sxs-lookup"><span data-stu-id="0909e-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="0909e-135">Paso 2: Configurar la notificación para los usuarios en la onda de actualización actual (opcional)</span><span class="sxs-lookup"><span data-stu-id="0909e-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="0909e-136">Si utiliza el centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="0909e-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="0909e-137">En el centro de administración de Microsoft Teams, seleccione **los usuarios**y buscar y selección múltiple de la casilla de verificación para los usuarios hasta 20 que debe actualizarse.</span><span class="sxs-lookup"><span data-stu-id="0909e-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="0909e-138">Seleccione **Editar la configuración** en la esquina superior izquierda de la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="0909e-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="0909e-139">En el panel **Editar configuración** de la derecha, en **los equipos de actualización**, cambiar el modificador de **notificar el Skype para usuarios de empresa** **activado**.</span><span class="sxs-lookup"><span data-stu-id="0909e-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="0909e-140">Nota: Si el valor del modo de coexistencia es "configuración de toda la organización uso", no verá este modificador, por lo que tendrá que primero establecer explícitamente el modo de coexistencia para estos usuarios a todo lo que es el valor predeterminado para el organigrama.</span><span class="sxs-lookup"><span data-stu-id="0909e-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="0909e-141">Como alternativa, es posible que encuentre más fácil habilitar las notificaciones para los grupos de usuarios a la vez mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0909e-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="0909e-142">Paso 3: Establecer el modo de coexistencia para que los usuarios sólo los equipos</span><span class="sxs-lookup"><span data-stu-id="0909e-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="0909e-143">Cuando esté listo para actualizar los usuarios de la onda actual para usar los equipos como su única aplicación, establezca el modo de coexistencia para que los usuarios sólo los equipos.</span><span class="sxs-lookup"><span data-stu-id="0909e-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="0909e-144">Si utiliza el centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="0909e-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="0909e-145">En el centro de administración de Microsoft Teams, seleccione **los usuarios**y, a continuación, seleccione la casilla de verificación hasta 20 usuarios.</span><span class="sxs-lookup"><span data-stu-id="0909e-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="0909e-146">Seleccione **Editar la configuración** en la esquina superior izquierda de la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="0909e-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="0909e-147">En el panel **Editar configuración** de la derecha, en la sección de **actualización de los equipos** , establezca el modo de coexistencia en **Los equipos sólo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0909e-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="0909e-148">Como alternativa, es posible que encuentre más sencillo actualizar grupos de usuarios a la vez mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0909e-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="0909e-149">Paso 4: Repita los pasos del 1 al 3 para sucesivas de usuarios</span><span class="sxs-lookup"><span data-stu-id="0909e-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="0909e-150">Como validar la actualización al modo de sólo los equipos y esté listo para expandir, repita los pasos anteriores para aplicar TeamsOnly a más usuarios.</span><span class="sxs-lookup"><span data-stu-id="0909e-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="0909e-151">Sistema telefónico y los equipos de actualización</span><span class="sxs-lookup"><span data-stu-id="0909e-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="0909e-152">Si su Skype para la implementación empresarial Online incluye sistema telefónico con planes de llamada y Microsoft es su proveedor de telefónica conmutada (RTC), actualizar a los usuarios a los equipos automáticamente transición RTC entrante a los equipos de llamada.</span><span class="sxs-lookup"><span data-stu-id="0909e-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="0909e-153">Si su Skype para la implementación empresarial Online incluye sistema telefónico con la edición de conector en la nube, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="0909e-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
