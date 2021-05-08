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
ms.openlocfilehash: d01dc44b626cc2c09a92dabff7649a5e9fddc3c6
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282507"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="2e52d-103">Estrategias de actualización para administradores de TI</span><span class="sxs-lookup"><span data-stu-id="2e52d-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="2e52d-104">![Fases del viaje de actualización, con énfasis en la fase implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")</span><span class="sxs-lookup"><span data-stu-id="2e52d-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="2e52d-105">Este artículo es para administradores de TI que desean implementar su actualización para Teams desde Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="2e52d-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="2e52d-106">Antes de implementar la actualización, se recomiendan los siguientes artículos que describen conceptos de actualización importantes y comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="2e52d-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="2e52d-107">Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="2e52d-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="2e52d-108">Modos de coexistencia: referencia</span><span class="sxs-lookup"><span data-stu-id="2e52d-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="2e52d-109">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="2e52d-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="2e52d-110">Opciones de actualización</span><span class="sxs-lookup"><span data-stu-id="2e52d-110">Upgrade options</span></span>

<span data-ttu-id="2e52d-111">En esta sección se describe cómo implementar la actualización mediante una de las siguientes opciones de actualización:</span><span class="sxs-lookup"><span data-stu-id="2e52d-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="2e52d-112">Actualización de capacidades superpuestas (con el modo Islas)</span><span class="sxs-lookup"><span data-stu-id="2e52d-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="2e52d-113">Una actualización de capacidades de selección para una organización que aún no ha empezado a usar Teams</span><span class="sxs-lookup"><span data-stu-id="2e52d-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="2e52d-114">Una actualización de capacidades de selección para una organización que ya usa Teams en modo Islas</span><span class="sxs-lookup"><span data-stu-id="2e52d-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="2e52d-115">Si necesita más información sobre las opciones, asegúrese de que ya ha leído Elegir el viaje de actualización de Skype Empresarial [a Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2e52d-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="2e52d-116">Actualización de capacidades superpuestas (con el modo Islas)</span><span class="sxs-lookup"><span data-stu-id="2e52d-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="2e52d-117">Para la opción de actualización de funcionalidades superpuestas:</span><span class="sxs-lookup"><span data-stu-id="2e52d-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="2e52d-118">Considere esta opción si puede realizar una actualización rápida para su organización general.</span><span class="sxs-lookup"><span data-stu-id="2e52d-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="2e52d-119">Dado que existe un riesgo potencial de confusión para los usuarios finales al ejecutar ambos clientes, es mejor si puede minimizar el período de tiempo durante el cual los usuarios deben ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="2e52d-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="2e52d-120">Debe asegurarse de que los usuarios sepan ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="2e52d-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="2e52d-121">Esta opción es el modelo sin usar y no requiere acción de administrador para empezar con Teams excepto para asignar la licencia Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e52d-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="2e52d-122">Si los usuarios ya tienen Skype Empresarial online, es posible que ya esté en este modelo.</span><span class="sxs-lookup"><span data-stu-id="2e52d-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="2e52d-123">Puede ser difícil salir del modo de capacidades superpuestas y pasar a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2e52d-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="2e52d-124">Como los usuarios actualizados solo se comunican Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe usar Teams.</span><span class="sxs-lookup"><span data-stu-id="2e52d-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="2e52d-125">Si tiene usuarios que no han empezado a usar Teams, se mostrarán a los mensajes que faltan.</span><span class="sxs-lookup"><span data-stu-id="2e52d-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="2e52d-126">Además, no verán los usuarios de TeamsOnly en línea en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="2e52d-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="2e52d-127">Algunas organizaciones eligen realizar una actualización para todo el espacio empresarial con la directiva global Inquilino para evitar esto, pero eso requiere una planificación inicial, así como esperar hasta que todos los usuarios estén listos para actualizarse.</span><span class="sxs-lookup"><span data-stu-id="2e52d-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="2e52d-128">Una actualización de capacidades de selección para una organización que aún no ha empezado a usar Teams</span><span class="sxs-lookup"><span data-stu-id="2e52d-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="2e52d-129">Si su organización todavía no tiene usuarios activos en Teams, el primer paso es establecer la directiva predeterminada para todo el espacio empresarial para TeamsUpgradePolicy en uno de los modos Skype Empresarial, por ejemplo, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="2e52d-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="2e52d-130">Los usuarios que aún no han empezado a usar Teams no notan ninguna diferencia en el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="2e52d-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="2e52d-131">Sin embargo, establecer esta directiva en el nivel de inquilino permite empezar a actualizar usuarios al modo TeamsOnly y garantiza que los usuarios actualizados puedan comunicarse con usuarios no actualizados.</span><span class="sxs-lookup"><span data-stu-id="2e52d-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="2e52d-132">Una vez que haya identificado los usuarios piloto, puede actualizarlos a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2e52d-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="2e52d-133">Si son locales, use Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="2e52d-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="2e52d-134">Si están en línea, simplemente asígneles el modo TeamsOnly mediante Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="2e52d-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="2e52d-135">De forma predeterminada, Skype Empresarial reuniones programadas por estos usuarios se migrarán a Teams.</span><span class="sxs-lookup"><span data-stu-id="2e52d-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="2e52d-136">Estos son los comandos de clave:</span><span class="sxs-lookup"><span data-stu-id="2e52d-136">Following are the key commands:</span></span>

1. <span data-ttu-id="2e52d-137">Establezca el valor predeterminado para todo el espacio empresarial en el modo SfbWithTeamsCollab de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2e52d-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="2e52d-138">Actualice los usuarios piloto a TeamsOnly de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2e52d-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="2e52d-139">Para un usuario que esté en línea:</span><span class="sxs-lookup"><span data-stu-id="2e52d-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="2e52d-140">Para un usuario local:</span><span class="sxs-lookup"><span data-stu-id="2e52d-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="2e52d-141">Notas</span><span class="sxs-lookup"><span data-stu-id="2e52d-141">Notes</span></span>
 
- <span data-ttu-id="2e52d-142">En lugar de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab, puede establecerla en SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="2e52d-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="2e52d-143">Esto hace que todos los usuarios programe todas las reuniones nuevas en Teams.</span><span class="sxs-lookup"><span data-stu-id="2e52d-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="2e52d-144">`Move-CsUser` es un cmdlet en las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="2e52d-144">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="2e52d-145">El `MoveToTeams` modificador requiere Skype Empresarial Server 2019 o Skype Empresarial Server 2015 con CU8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2e52d-145">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="2e52d-146">Si usa una versión anterior, primero puede mover el usuario a Skype Empresarial Online y, después, conceder el modo TeamsOnly a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="2e52d-146">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="2e52d-147">De forma predeterminada, Skype Empresarial reuniones se migran a Teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="2e52d-147">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="2e52d-148">En el siguiente diagrama se muestran las fases conceptuales de la actualización de capacidades de selección para una organización sin el uso previo de Teams.</span><span class="sxs-lookup"><span data-stu-id="2e52d-148">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="2e52d-149">El alto de las barras representa el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2e52d-149">The height of the bars represents number of users.</span></span> <span data-ttu-id="2e52d-150">Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="2e52d-150">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="2e52d-151">Skype Empresarial se comunican con los usuarios de TeamsOnly mediante interoperabilidad y viceversa.</span><span class="sxs-lookup"><span data-stu-id="2e52d-151">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="2e52d-152">Los usuarios en modo Islas deben asegurarse de ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="2e52d-152">Users in Islands mode must be sure to run both clients.</span></span>

![Diagrama que muestra la actualización de capacidades de selección sin el uso previo de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="2e52d-154">Una actualización de capacidades de selección para una organización que ya usa Teams en modo Islas</span><span class="sxs-lookup"><span data-stu-id="2e52d-154">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="2e52d-155">Si algunos usuarios de su organización usan activamente Teams modo Islas, es probable que no quiera quitar la funcionalidad de los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="2e52d-155">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="2e52d-156">Por lo tanto, es necesario realizar un paso adicional antes de cambiar la directiva de todo el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="2e52d-156">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="2e52d-157">La solución es "abuelito" de estos usuarios activos existentes Teams en modo Islas, antes de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="2e52d-157">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="2e52d-158">Una vez hecho esto, puede continuar con la implementación como se ha indicado anteriormente, pero tendrá dos grupos de usuarios que se mueven a TeamsOnly: los usuarios que estaban activos en Teams estarán en modo Islas y el resto de los usuarios estarán en modo SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="2e52d-158">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="2e52d-159">Puede mover progresivamente estos usuarios al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2e52d-159">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="2e52d-160">Busque usuarios que estén activos en Teams como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="2e52d-160">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="2e52d-161">Desde el Microsoft 365 de administración, en el panel de navegación izquierdo, vaya a Informes y, a continuación, Uso.</span><span class="sxs-lookup"><span data-stu-id="2e52d-161">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="2e52d-162">En el menú desplegable "Seleccionar un informe", elija Microsoft Teams y, a continuación, Actividad del usuario.</span><span class="sxs-lookup"><span data-stu-id="2e52d-162">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="2e52d-163">Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams.</span><span class="sxs-lookup"><span data-stu-id="2e52d-163">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="2e52d-164">Haga clic en Exportar, abra Excel y filtre para mostrar solo los usuarios que están activos en Teams.</span><span class="sxs-lookup"><span data-stu-id="2e52d-164">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="2e52d-165">Para cada usuario Teams activo que se encuentra en el paso 1, asígneles el modo Islas en PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="2e52d-165">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="2e52d-166">Esto le permite ir al paso siguiente y garantiza que no cambie la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="2e52d-166">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="2e52d-167">Establezca la directiva para todo el espacio empresarial en SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="2e52d-167">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="2e52d-168">Actualizar usuarios seleccionados al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="2e52d-168">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="2e52d-169">Puede elegir actualizar los usuarios en modo Islas o en modo SfbWithTeamsCollab, aunque es posible que desee priorizar la actualización de los usuarios en el modo Islas primero para minimizar el potencial de confusión que puede surgir cuando los usuarios están en modo Islas.</span><span class="sxs-lookup"><span data-stu-id="2e52d-169">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="2e52d-170">Para los usuarios que se alo Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="2e52d-170">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="2e52d-171">Para los usuarios que se alo Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="2e52d-171">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="2e52d-172">El siguiente diagrama muestra las fases conceptuales de una transición de capacidades de selección en la que hay usuarios activos de islas al principio.</span><span class="sxs-lookup"><span data-stu-id="2e52d-172">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="2e52d-173">El alto de las barras representa el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2e52d-173">The height of the bars represents the number of users.</span></span> <span data-ttu-id="2e52d-174">Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="2e52d-174">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="2e52d-175">Skype Empresarial usuarios se comunican con los usuarios de TeamsOnly mediante la interoperabilidad y viceversa.</span><span class="sxs-lookup"><span data-stu-id="2e52d-175">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagrama que muestra la actualización de capacidades de selección con usuarios activos en modo Islas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="2e52d-177">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="2e52d-177">Related links</span></span>

[<span data-ttu-id="2e52d-178">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="2e52d-178">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="2e52d-179">Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="2e52d-179">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="2e52d-180">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="2e52d-180">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="2e52d-181">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="2e52d-181">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="2e52d-182">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="2e52d-182">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="2e52d-183">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="2e52d-183">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)