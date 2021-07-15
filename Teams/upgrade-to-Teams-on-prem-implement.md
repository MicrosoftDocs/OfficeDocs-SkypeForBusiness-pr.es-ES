---
title: Estrategias de actualización para administradores de TI
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: El artículo es para administradores de TI y describe estrategias para implementar su actualización de Skype Empresarial a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f11d14bc7bf302a864afe3062ef8f2bb8eccd7da
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437647"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="9dd47-103">Estrategias de actualización para administradores de TI</span><span class="sxs-lookup"><span data-stu-id="9dd47-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="9dd47-104">![Fases del viaje de actualización, con énfasis en la fase implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")</span><span class="sxs-lookup"><span data-stu-id="9dd47-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="9dd47-105">Este artículo es para administradores de TI que desean implementar su actualización para Teams desde Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="9dd47-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="9dd47-106">Antes de implementar la actualización, se recomiendan los siguientes artículos que describen conceptos de actualización importantes y comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="9dd47-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="9dd47-107">Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9dd47-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="9dd47-108">Modos de coexistencia: referencia</span><span class="sxs-lookup"><span data-stu-id="9dd47-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="9dd47-109">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="9dd47-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="9dd47-110">Opciones de actualización</span><span class="sxs-lookup"><span data-stu-id="9dd47-110">Upgrade options</span></span>

<span data-ttu-id="9dd47-111">En esta sección se describe cómo implementar la actualización mediante una de las siguientes opciones de actualización:</span><span class="sxs-lookup"><span data-stu-id="9dd47-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="9dd47-112">Actualización de capacidades superpuestas (con el modo Islas)</span><span class="sxs-lookup"><span data-stu-id="9dd47-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="9dd47-113">Una actualización de capacidades de selección para una organización que aún no ha empezado a usar Teams</span><span class="sxs-lookup"><span data-stu-id="9dd47-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="9dd47-114">Una actualización de capacidades de selección para una organización que ya usa Teams en modo Islas</span><span class="sxs-lookup"><span data-stu-id="9dd47-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="9dd47-115">Si necesita más información sobre las opciones, asegúrese de que ya ha leído Elegir el viaje de actualización de Skype Empresarial [a Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9dd47-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="9dd47-116">Actualización de capacidades superpuestas (con el modo Islas)</span><span class="sxs-lookup"><span data-stu-id="9dd47-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="9dd47-117">Para la opción de actualización de funcionalidades superpuestas:</span><span class="sxs-lookup"><span data-stu-id="9dd47-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="9dd47-118">Considere esta opción si puede realizar una actualización rápida para su organización general.</span><span class="sxs-lookup"><span data-stu-id="9dd47-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="9dd47-119">Dado que existe un riesgo potencial de confusión para los usuarios finales al ejecutar ambos clientes, es mejor si puede minimizar el período de tiempo durante el cual los usuarios deben ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="9dd47-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="9dd47-120">Debe asegurarse de que los usuarios sepan ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="9dd47-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="9dd47-121">Esta opción es el modelo sin usar y no requiere acción de administrador para empezar con Teams excepto para asignar la licencia Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="9dd47-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="9dd47-122">Si los usuarios ya tienen Skype Empresarial online, es posible que ya esté en este modelo.</span><span class="sxs-lookup"><span data-stu-id="9dd47-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="9dd47-123">Puede ser difícil salir del modo de capacidades superpuestas y pasar a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9dd47-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="9dd47-124">Como los usuarios actualizados solo se comunican Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe usar Teams.</span><span class="sxs-lookup"><span data-stu-id="9dd47-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="9dd47-125">Si tiene usuarios que no han empezado a usar Teams, se mostrarán a los mensajes que faltan.</span><span class="sxs-lookup"><span data-stu-id="9dd47-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="9dd47-126">Además, no verán los usuarios de TeamsOnly en línea en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="9dd47-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="9dd47-127">Algunas organizaciones eligen realizar una actualización para todo el espacio empresarial con la directiva global Inquilino para evitar esto, pero eso requiere una planificación inicial, así como esperar hasta que todos los usuarios estén listos para actualizarse.</span><span class="sxs-lookup"><span data-stu-id="9dd47-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="9dd47-128">Una actualización de capacidades de selección para una organización que aún no ha empezado a usar Teams</span><span class="sxs-lookup"><span data-stu-id="9dd47-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="9dd47-129">Si su organización todavía no tiene usuarios activos en Teams, el primer paso es establecer la directiva predeterminada para todo el espacio empresarial para TeamsUpgradePolicy en uno de los modos Skype Empresarial, por ejemplo, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="9dd47-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="9dd47-130">Los usuarios que aún no han empezado a usar Teams no notan ninguna diferencia en el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9dd47-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="9dd47-131">Sin embargo, establecer esta directiva en el nivel de inquilino permite empezar a actualizar usuarios al modo TeamsOnly y garantiza que los usuarios actualizados puedan comunicarse con usuarios no actualizados.</span><span class="sxs-lookup"><span data-stu-id="9dd47-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="9dd47-132">Una vez que haya identificado los usuarios piloto, puede actualizarlos a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9dd47-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="9dd47-133">Si son locales, use Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="9dd47-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="9dd47-134">Si están en línea, simplemente asígneles el modo TeamsOnly mediante Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="9dd47-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="9dd47-135">De forma predeterminada, Skype Empresarial reuniones programadas por estos usuarios se migrarán a Teams.</span><span class="sxs-lookup"><span data-stu-id="9dd47-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="9dd47-136">Estos son los comandos de clave:</span><span class="sxs-lookup"><span data-stu-id="9dd47-136">Following are the key commands:</span></span>

1. <span data-ttu-id="9dd47-137">Establezca el valor predeterminado para todo el espacio empresarial en el modo SfbWithTeamsCollab de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9dd47-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="9dd47-138">Actualice los usuarios piloto a TeamsOnly de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9dd47-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="9dd47-139">Para un usuario que esté en línea:</span><span class="sxs-lookup"><span data-stu-id="9dd47-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="9dd47-140">Para un usuario local:</span><span class="sxs-lookup"><span data-stu-id="9dd47-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="9dd47-141">Notas</span><span class="sxs-lookup"><span data-stu-id="9dd47-141">Notes</span></span>
 
- <span data-ttu-id="9dd47-142">En lugar de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab, puede establecerla en SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="9dd47-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="9dd47-143">Esto hace que todos los usuarios programe todas las reuniones nuevas en Teams.</span><span class="sxs-lookup"><span data-stu-id="9dd47-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="9dd47-144">De forma predeterminada, Skype Empresarial reuniones se migran a Teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="9dd47-144">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="9dd47-145">En preparación para la próxima retirada de Skype Empresarial Online, Microsoft ha simplificado la forma en que las organizaciones se mueven a Teams.</span><span class="sxs-lookup"><span data-stu-id="9dd47-145">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="9dd47-146">Ya no es necesario especificar el cambio para mover los usuarios directamente desde el entorno `-MoveToTeams` `Move-CsUser` local directamente a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9dd47-146">It is no longer required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises directly to TeamsOnly.</span></span> <span data-ttu-id="9dd47-147">Anteriormente, si no se especificaba este modificador, los usuarios pasaron de estar en casa en Skype Empresarial Server local Skype Empresarial Online y su modo no se cambió.</span><span class="sxs-lookup"><span data-stu-id="9dd47-147">Previously, if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="9dd47-148">Ahora, al mover un usuario de local a la nube con , los usuarios se asignan automáticamente al modo TeamsOnly y sus reuniones desde locales se convierten automáticamente en reuniones de Teams, igual que si el modificador se especifica `Move-CsUser` `-MoveToTeams switch had been specified` realmente.</span><span class="sxs-lookup"><span data-stu-id="9dd47-148">Now when moving a user from on-premises to the cloud with `Move-CsUser`, users are automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="9dd47-149">Este comportamiento está disponible en todas las versiones de Skype Para Empresas Server y Lync Server 2013 (que nunca tuvieron soporte para `-MoveToTeams` ).</span><span class="sxs-lookup"><span data-stu-id="9dd47-149">This behavior is available on all versions of Skype For Business Server and Lync Server 2013 (which never had support for `-MoveToTeams`).</span></span>

<span data-ttu-id="9dd47-150">En el siguiente diagrama se muestran las fases conceptuales de la actualización de capacidades de selección para una organización sin el uso previo de Teams.</span><span class="sxs-lookup"><span data-stu-id="9dd47-150">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="9dd47-151">El alto de las barras representa el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="9dd47-151">The height of the bars represents number of users.</span></span> <span data-ttu-id="9dd47-152">Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="9dd47-152">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="9dd47-153">Skype Empresarial se comunican con los usuarios de TeamsOnly mediante interoperabilidad y viceversa.</span><span class="sxs-lookup"><span data-stu-id="9dd47-153">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="9dd47-154">Los usuarios en modo Islas deben asegurarse de ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="9dd47-154">Users in Islands mode must be sure to run both clients.</span></span>

![Diagrama que muestra la actualización de capacidades de selección sin el uso previo de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="9dd47-156">Una actualización de capacidades de selección para una organización que ya usa Teams en modo Islas</span><span class="sxs-lookup"><span data-stu-id="9dd47-156">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="9dd47-157">Si algunos usuarios de su organización usan activamente Teams modo Islas, es probable que no quiera quitar la funcionalidad de los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="9dd47-157">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="9dd47-158">Por lo tanto, es necesario realizar un paso adicional antes de cambiar la directiva de todo el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="9dd47-158">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="9dd47-159">La solución es "abuelito" de estos usuarios activos existentes Teams en modo Islas, antes de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="9dd47-159">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="9dd47-160">Una vez hecho esto, puede continuar con la implementación como se ha indicado anteriormente, pero tendrá dos grupos de usuarios que se mueven a TeamsOnly: los usuarios que estaban activos en Teams estarán en modo Islas y el resto de los usuarios estarán en modo SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="9dd47-160">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="9dd47-161">Puede mover progresivamente estos usuarios al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9dd47-161">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="9dd47-162">Busque usuarios que estén activos en Teams como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="9dd47-162">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="9dd47-163">En la Centro de administración de Microsoft 365, en el panel de navegación izquierdo, vaya a Informes y, a continuación, Uso.</span><span class="sxs-lookup"><span data-stu-id="9dd47-163">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="9dd47-164">En el menú desplegable "Seleccionar un informe", elija Microsoft Teams y, a continuación, Actividad del usuario.</span><span class="sxs-lookup"><span data-stu-id="9dd47-164">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="9dd47-165">Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams.</span><span class="sxs-lookup"><span data-stu-id="9dd47-165">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="9dd47-166">Haga clic en Exportar, abra Excel y filtre para mostrar solo los usuarios que están activos en Teams.</span><span class="sxs-lookup"><span data-stu-id="9dd47-166">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="9dd47-167">Para cada usuario Teams activo que se encuentra en el paso 1, asígneles el modo Islas en PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="9dd47-167">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="9dd47-168">Esto le permite ir al paso siguiente y garantiza que no cambie la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="9dd47-168">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="9dd47-169">Establezca la directiva para todo el espacio empresarial en SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="9dd47-169">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="9dd47-170">Actualizar usuarios seleccionados al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9dd47-170">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="9dd47-171">Puede elegir actualizar los usuarios en modo Islas o en modo SfbWithTeamsCollab, aunque es posible que desee priorizar la actualización de los usuarios en el modo Islas primero para minimizar el potencial de confusión que puede surgir cuando los usuarios están en modo Islas.</span><span class="sxs-lookup"><span data-stu-id="9dd47-171">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="9dd47-172">Para los usuarios que se alo Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="9dd47-172">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="9dd47-173">Para los usuarios que se alo Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="9dd47-173">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="9dd47-174">El siguiente diagrama muestra las fases conceptuales de una transición de capacidades de selección en la que hay usuarios activos de islas al principio.</span><span class="sxs-lookup"><span data-stu-id="9dd47-174">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="9dd47-175">El alto de las barras representa el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="9dd47-175">The height of the bars represents the number of users.</span></span> <span data-ttu-id="9dd47-176">Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="9dd47-176">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="9dd47-177">Skype Empresarial usuarios se comunican con los usuarios de TeamsOnly mediante la interoperabilidad y viceversa.</span><span class="sxs-lookup"><span data-stu-id="9dd47-177">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagrama que muestra la actualización de capacidades de selección con usuarios activos en modo Islas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="9dd47-179">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="9dd47-179">Related links</span></span>

[<span data-ttu-id="9dd47-180">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9dd47-180">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="9dd47-181">Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="9dd47-181">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="9dd47-182">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="9dd47-182">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="9dd47-183">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="9dd47-183">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="9dd47-184">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="9dd47-184">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="9dd47-185">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="9dd47-185">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
