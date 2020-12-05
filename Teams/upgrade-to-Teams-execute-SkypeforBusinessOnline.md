---
title: Actualizar de Skype empresarial online a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación de Skype empresarial online.
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
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578263"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="9d81e-103">Actualización de Skype Empresarial Online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d81e-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="9d81e-104">![Actualizar diagrama de viaje, enfatizar implementación e implementación](media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación")</span><span class="sxs-lookup"><span data-stu-id="9d81e-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="9d81e-105">Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización.</span><span class="sxs-lookup"><span data-stu-id="9d81e-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="9d81e-106">Antes de continuar, confirme que ha completado las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="9d81e-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="9d81e-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="9d81e-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="9d81e-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="9d81e-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="9d81e-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="9d81e-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="9d81e-110">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="9d81e-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="9d81e-111">Preparado su entorno</span><span class="sxs-lookup"><span data-stu-id="9d81e-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="9d81e-112">Preparado para su organización</span><span class="sxs-lookup"><span data-stu-id="9d81e-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="9d81e-113">Ha realizado una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="9d81e-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="9d81e-114">Siga las instrucciones de este artículo si ha implementado totalmente Skype empresarial online y desea actualizar los usuarios de Skype empresarial a teams.</span><span class="sxs-lookup"><span data-stu-id="9d81e-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="9d81e-115">Puede actualizar los usuarios de forma selectiva o todos en función del recorrido de actualización que su organización haya elegido, asignando el modo de coexistencia y actualización adecuado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9d81e-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d81e-116">Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte.</span><span class="sxs-lookup"><span data-stu-id="9d81e-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="9d81e-117">Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d81e-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="9d81e-118">Recuerde que una actualización correcta alinea la disposición de los usuarios y técnicos, así que asegúrese de aprovechar las instrucciones de este documento a medida que navega por Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d81e-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="9d81e-119">Asignar el modo de coexistencia y actualización</span><span class="sxs-lookup"><span data-stu-id="9d81e-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="9d81e-120">Puede actualizar los usuarios al modo de TeamsOnly asignando la instancia de UpgradeToTeams de TeamsUpgradePolicy, que se puede realizar mediante el centro de administración de Microsoft Teams o una sesión de Windows PowerShell remota de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="9d81e-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="9d81e-121">Puede hacer esto para cada usuario o a escala de inquilino si quiere actualizar todo el inquilino en un solo paso de tiempo.</span><span class="sxs-lookup"><span data-stu-id="9d81e-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="9d81e-122">Para obtener más información, vea [configurar la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de la migración y la coexistencia](upgrade-to-teams-on-prem-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9d81e-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="9d81e-123">Actualizar todos los usuarios a teams a la vez</span><span class="sxs-lookup"><span data-stu-id="9d81e-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="9d81e-124">Siga estos pasos para actualizar todos los usuarios a teams a la vez.</span><span class="sxs-lookup"><span data-stu-id="9d81e-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="9d81e-125">Paso 1: notificar a los usuarios el cambio (opcional)</span><span class="sxs-lookup"><span data-stu-id="9d81e-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="9d81e-126">En el centro de administración de Microsoft Teams, seleccione la actualización de la configuración de equipos de la **organización**  >  **Teams upgrade**.</span><span class="sxs-lookup"><span data-stu-id="9d81e-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="9d81e-127">En **modo de coexistencia**, cambie la opción **notificar a los usuarios de Skype empresarial que hay disponible una actualización a teams** **.**</span><span class="sxs-lookup"><span data-stu-id="9d81e-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="9d81e-128">Paso 2: establecer el modo de coexistencia en TeamsOnly para la organización</span><span class="sxs-lookup"><span data-stu-id="9d81e-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="9d81e-129">En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="9d81e-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="9d81e-130">Seleccione el modo **solo de Teams** en la lista desplegable **modo de coexistencia** .</span><span class="sxs-lookup"><span data-stu-id="9d81e-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="9d81e-131">Actualizar usuarios por etapas</span><span class="sxs-lookup"><span data-stu-id="9d81e-131">Upgrade users in stages</span></span>

<span data-ttu-id="9d81e-132">Siga estos pasos si desea actualizar gradualmente los usuarios a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9d81e-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="9d81e-133">Paso 1: identificar los grupos de usuarios para la actualización</span><span class="sxs-lookup"><span data-stu-id="9d81e-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="9d81e-134">A menudo, las organizaciones pueden optar por actualizar sus organizaciones con las ondas de éxito de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9d81e-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="9d81e-135">Es posible que desee identificar estos usuarios en primer lugar para que pueda buscarlos fácilmente en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d81e-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9d81e-136">Como alternativa, es posible que desee usar PowerShell para hacerlo de manera más eficaz.</span><span class="sxs-lookup"><span data-stu-id="9d81e-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="9d81e-137">Una vez que haya identificado el conjunto de usuarios para una onda de actualización determinada, continúe con los pasos restantes.</span><span class="sxs-lookup"><span data-stu-id="9d81e-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="9d81e-138">Paso 2: establecer una notificación para los usuarios de la onda de actualización actual (opcional)</span><span class="sxs-lookup"><span data-stu-id="9d81e-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="9d81e-139">Si usa el centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="9d81e-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="9d81e-140">En el centro de administración de Microsoft Teams, seleccione **usuarios**, busque y seleccione la casilla múltiple para un máximo de 20 usuarios que deberían actualizarse.</span><span class="sxs-lookup"><span data-stu-id="9d81e-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="9d81e-141">Seleccione **Editar configuración** en la esquina superior izquierda del ListView.</span><span class="sxs-lookup"><span data-stu-id="9d81e-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="9d81e-142">En el panel **Editar configuración** de la derecha, en la sección **actualizar de Teams**, cambie **notificar al usuario de Skype empresarial** a **activado**.</span><span class="sxs-lookup"><span data-stu-id="9d81e-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="9d81e-143">Nota: Si el valor de modo de coexistencia es "usar la configuración de toda la organización", no verá este modificador, por lo que tendrá que establecer explícitamente el modo de coexistencia de estos usuarios en el valor predeterminado de la organización.</span><span class="sxs-lookup"><span data-stu-id="9d81e-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="9d81e-144">Como alternativa, es posible que le resulte más fácil habilitar las notificaciones para grupos de usuarios a la vez mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d81e-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="9d81e-145">Paso 3: establecer el modo de coexistencia para los usuarios solo para equipos</span><span class="sxs-lookup"><span data-stu-id="9d81e-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="9d81e-146">Cuando esté listo para actualizar los usuarios de la onda actual para que use Teams como única aplicación, establezca el modo de coexistencia para los usuarios solo en Teams.</span><span class="sxs-lookup"><span data-stu-id="9d81e-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="9d81e-147">Si usa el centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="9d81e-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="9d81e-148">En el centro de administración de Microsoft Teams, seleccione **usuarios** y, a continuación, seleccione la casilla de verificación para un máximo de 20 usuarios.</span><span class="sxs-lookup"><span data-stu-id="9d81e-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="9d81e-149">Seleccione **Editar configuración** en la esquina superior izquierda del ListView.</span><span class="sxs-lookup"><span data-stu-id="9d81e-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="9d81e-150">En el panel **Editar configuración** de la derecha, en la sección **actualización de equipos** , establezca el modo de coexistencia en **Teams solo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9d81e-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="9d81e-151">Como alternativa, es posible que le resulte más fácil actualizar grupos de usuarios a la vez mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d81e-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="9d81e-152">Paso 4: Repita los pasos 1-3 para las ondas sucesivas de los usuarios</span><span class="sxs-lookup"><span data-stu-id="9d81e-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="9d81e-153">Mientras valida la actualización al modo solo para equipos y está listo para expandir, repita los pasos anteriores para aplicar TeamsOnly a más usuarios.</span><span class="sxs-lookup"><span data-stu-id="9d81e-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="9d81e-154">Opciones de conectividad RTC y sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="9d81e-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="9d81e-155">El sistema telefónico con Teams es compatible cuando el usuario está en modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9d81e-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="9d81e-156">(Si el usuario está en modo islas, el sistema telefónico solo es compatible con Skype empresarial).</span><span class="sxs-lookup"><span data-stu-id="9d81e-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="9d81e-157">Opciones de conectividad RTC</span><span class="sxs-lookup"><span data-stu-id="9d81e-157">PSTN connectivity options</span></span>

<span data-ttu-id="9d81e-158">Al considerar las opciones de conectividad de la red de telefonía pública conmutada (RTC), hay dos situaciones posibles en las que se pasa de Skype empresarial online al modo TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="9d81e-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="9d81e-159">Un usuario de Skype empresarial online con un plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d81e-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="9d81e-160">Después de la actualización, este usuario seguirá teniendo un plan de llamadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d81e-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="9d81e-161">Este es el escenario más simple que requiere solo un par de pasos.</span><span class="sxs-lookup"><span data-stu-id="9d81e-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="9d81e-162">Para obtener más información, consulte [de Skype empresarial online con los planes de llamadas de Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="9d81e-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="9d81e-163">Un usuario de Skype empresarial online con funcionalidad de voz local a través de Skype empresarial local o Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="9d81e-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="9d81e-164">La actualización del usuario a teams debe coordinarse con la migración del usuario al enrutamiento directo para garantizar que el usuario de TeamsOnly tiene la funcionalidad de RTC.</span><span class="sxs-lookup"><span data-stu-id="9d81e-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="9d81e-165">Para obtener más información, consulte [Skype empresarial online con voz local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span><span class="sxs-lookup"><span data-stu-id="9d81e-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>


