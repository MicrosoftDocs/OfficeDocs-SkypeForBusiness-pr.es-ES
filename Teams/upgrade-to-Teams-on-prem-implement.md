---
title: 'Actualizar a Teams desde una implementación local de Skype Empresarial: Microsoft Teams'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533607"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="a516e-103">Implementar la actualización de Skype Empresarial a Teams &mdash; para administradores de TI</span><span class="sxs-lookup"><span data-stu-id="a516e-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="a516e-104">En este artículo se describe cómo implementar la actualización.</span><span class="sxs-lookup"><span data-stu-id="a516e-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="a516e-105">Este artículo es el quinto de varios que describen los conceptos de actualización y la implementación para los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="a516e-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="a516e-106">Información general</span><span class="sxs-lookup"><span data-stu-id="a516e-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="a516e-107">Métodos de actualización</span><span class="sxs-lookup"><span data-stu-id="a516e-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="a516e-108">Herramientas para administrar la actualización</span><span class="sxs-lookup"><span data-stu-id="a516e-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="a516e-109">Consideraciones adicionales para las organizaciones con Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="a516e-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="a516e-110">**Implementar la actualización** (en este artículo)</span><span class="sxs-lookup"><span data-stu-id="a516e-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="a516e-111">Consideraciones de la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="a516e-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="a516e-112">Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="a516e-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="a516e-113">Coexistencia de Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a516e-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="a516e-114">Modos de coexistencia - Referencia</span><span class="sxs-lookup"><span data-stu-id="a516e-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="a516e-115">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="a516e-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="a516e-116">Opciones de actualización</span><span class="sxs-lookup"><span data-stu-id="a516e-116">Upgrade options</span></span>

<span data-ttu-id="a516e-117">En esta sección se describe cómo implementar la actualización mediante una de las siguientes opciones de actualización:</span><span class="sxs-lookup"><span data-stu-id="a516e-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="a516e-118">Actualización de funciones superpuestas (con el modo Islas)</span><span class="sxs-lookup"><span data-stu-id="a516e-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="a516e-119">Una actualización de funcionalidades específicas para una organización que aún no ha empezado a usar Teams</span><span class="sxs-lookup"><span data-stu-id="a516e-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="a516e-120">Actualización de capacidades de selección para una organización que ya usa Teams en modo Islas</span><span class="sxs-lookup"><span data-stu-id="a516e-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="a516e-121">Si necesita más información sobre las opciones, asegúrese de que ya ha leído los métodos [de actualización.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="a516e-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="a516e-122">Actualización de funciones superpuestas (con el modo Islas)</span><span class="sxs-lookup"><span data-stu-id="a516e-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="a516e-123">Para la opción de actualización de funcionalidades superpuestas:</span><span class="sxs-lookup"><span data-stu-id="a516e-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="a516e-124">Considere esta opción si puede realizar una actualización rápida para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="a516e-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="a516e-125">Puesto que existe un riesgo potencial de confusión para los usuarios finales que ejecutan ambos clientes, es mejor que pueda minimizar el período de tiempo durante el cual los usuarios deben ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="a516e-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="a516e-126">Debe asegurarse de que los usuarios sepan ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="a516e-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="a516e-127">Esta opción es el modelo de configuración rápida y no requiere una acción del administrador para empezar a usar Teams, excepto para asignar la licencia de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="a516e-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="a516e-128">Si sus usuarios ya tienen Skype Empresarial Online, es posible que ya esté en este modelo.</span><span class="sxs-lookup"><span data-stu-id="a516e-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="a516e-129">Puede ser difícil salir del modo de funcionalidad superpuesta y pasar a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a516e-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="a516e-130">Como los usuarios actualizados solo se comunican a través de Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe usar Teams.</span><span class="sxs-lookup"><span data-stu-id="a516e-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="a516e-131">Si tiene usuarios que no han empezado a usar Teams, se exponen a mensajes que faltan.</span><span class="sxs-lookup"><span data-stu-id="a516e-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="a516e-132">Además, no verán los usuarios de TeamsOnly en línea en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a516e-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="a516e-133">Algunas organizaciones eligen realizar una actualización para todo el inquilino mediante la directiva global de inquilinos para evitar esto, sin embargo, eso requiere una planificación inicial, así como esperar hasta que todos los usuarios estén listos para la actualización.</span><span class="sxs-lookup"><span data-stu-id="a516e-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="a516e-134">Actualización de funcionalidades específicas para una organización que aún no ha empezado a usar Teams</span><span class="sxs-lookup"><span data-stu-id="a516e-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="a516e-135">Si su organización aún no tiene ningún usuario activo en Teams, el primer paso es establecer la directiva predeterminada para todo el espacio empresarial para TeamsUpgradePolicy en uno de los modos de Skype Empresarial, por ejemplo, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="a516e-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="a516e-136">Los usuarios que aún no han empezado a usar Teams no observarán ninguna diferencia en el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a516e-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="a516e-137">Sin embargo, al establecer esta directiva en el nivel de inquilino, es posible iniciar la actualización de los usuarios al modo TeamsOnly, y garantiza que los usuarios actualizados puedan comunicarse con usuarios no actualizados.</span><span class="sxs-lookup"><span data-stu-id="a516e-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="a516e-138">Una vez que haya identificado los usuarios piloto, puede actualizarlos a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a516e-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="a516e-139">Si son locales, use Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="a516e-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="a516e-140">Si están en línea, simplemente asígneles el modo TeamsOnly mediante Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="a516e-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="a516e-141">De forma predeterminada, todas las reuniones de Skype Empresarial programadas por estos usuarios se migrarán a Teams.</span><span class="sxs-lookup"><span data-stu-id="a516e-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="a516e-142">Estos son los comandos de clave:</span><span class="sxs-lookup"><span data-stu-id="a516e-142">Following are the key commands:</span></span>

1. <span data-ttu-id="a516e-143">Establezca el valor predeterminado para todo el espacio empresarial en el modo SfbWithTeamsCollab como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="a516e-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="a516e-144">Actualice los usuarios piloto a TeamsOnly de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a516e-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="a516e-145">Para un usuario que está conectado:</span><span class="sxs-lookup"><span data-stu-id="a516e-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="a516e-146">Para un usuario local:</span><span class="sxs-lookup"><span data-stu-id="a516e-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="a516e-147">Notas</span><span class="sxs-lookup"><span data-stu-id="a516e-147">Notes</span></span>
 
- <span data-ttu-id="a516e-148">En lugar de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab, puede establecerla en SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="a516e-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="a516e-149">Esto hace que todos los usuarios programe todas las reuniones nuevas en Teams.</span><span class="sxs-lookup"><span data-stu-id="a516e-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="a516e-150">`Move-CsUser` es un cmdlet en las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="a516e-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="a516e-151">El `MoveToTeams` cambio requiere Skype Empresarial Server 2019 o Skype Empresarial Server 2015 con CU8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a516e-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="a516e-152">Si usa una versión anterior, primero puede mover el usuario a Skype Empresarial Online y, a continuación, otorgar el modo TeamsOnly a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="a516e-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="a516e-153">De forma predeterminada, las reuniones de Skype Empresarial se migran a Teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="a516e-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="a516e-154">El siguiente diagrama muestra las fases conceptuales de actualización de capacidades de selección para una organización sin uso previo de Teams.</span><span class="sxs-lookup"><span data-stu-id="a516e-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="a516e-155">El alto de las barras representa el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a516e-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="a516e-156">Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="a516e-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="a516e-157">Los usuarios de Skype Empresarial se comunican con los usuarios de TeamsOnly mediante interoperabilidad y viceversa.</span><span class="sxs-lookup"><span data-stu-id="a516e-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="a516e-158">Los usuarios en el modo de islas deben asegurarse de ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="a516e-158">Users in Islands mode must be sure to run both clients.</span></span>

![Diagrama que muestra la actualización de funcionalidades específicas sin uso previo de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="a516e-160">Actualización de capacidades de selección para una organización que ya usa Teams en modo Islas</span><span class="sxs-lookup"><span data-stu-id="a516e-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="a516e-161">Si algunos usuarios de su organización usan activamente Teams en modo islas, es probable que no desee quitar la funcionalidad de los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="a516e-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="a516e-162">Por lo tanto, es necesario realizar un paso adicional antes de cambiar la directiva de todo el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="a516e-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="a516e-163">La solución es "amplio" para estos usuarios activos de Teams existentes en el modo islas, antes de establecer la directiva de todo el espacio empresarial en SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="a516e-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="a516e-164">Una vez que haya hecho esto, puede continuar con la implementación como se ha mencionado anteriormente, sin embargo, tendrá dos grupos de usuarios que se trasladarán a TeamsOnly: los usuarios que estaban activos en Teams estarán en modo Islas y los usuarios restantes estarán en modo SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="a516e-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="a516e-165">Puede mover progresivamente estos usuarios al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a516e-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="a516e-166">Busque usuarios que estén activos en Teams de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a516e-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="a516e-167">En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, vaya a Informes y, a continuación, Uso.</span><span class="sxs-lookup"><span data-stu-id="a516e-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="a516e-168">En el menú desplegable "Seleccionar un informe", elija Microsoft Teams y, después, Actividad del usuario.</span><span class="sxs-lookup"><span data-stu-id="a516e-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="a516e-169">Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams.</span><span class="sxs-lookup"><span data-stu-id="a516e-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="a516e-170">Haga clic en Exportar, abra Excel y filtre para mostrar solo los usuarios que están activos en Teams.</span><span class="sxs-lookup"><span data-stu-id="a516e-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="a516e-171">Para cada usuario activo de Teams que se encontró en el paso 1, asígneles el modo Islas en powerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="a516e-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="a516e-172">Esto le permite ir al siguiente paso y garantiza que no cambie la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="a516e-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="a516e-173">Establezca la directiva de todo el espacio empresarial en SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="a516e-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="a516e-174">Actualice los usuarios seleccionados al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a516e-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="a516e-175">Puede elegir actualizar los usuarios en modo Islas o en modo SfbWithTeamsCollab, aunque es posible que desee priorizar la actualización de los usuarios en modo islas en primer lugar para minimizar el potencial de confusión que puede surgir cuando los usuarios están en modo Islas.</span><span class="sxs-lookup"><span data-stu-id="a516e-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="a516e-176">Para usuarios que están en Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="a516e-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="a516e-177">Para usuarios que se aloban en Skype Empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="a516e-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="a516e-178">El siguiente diagrama muestra las fases conceptuales de una transición de capacidades selectas en la que hay usuarios activos de las Islas al principio.</span><span class="sxs-lookup"><span data-stu-id="a516e-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="a516e-179">El alto de las barras representa el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a516e-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="a516e-180">Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="a516e-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="a516e-181">Los usuarios de Skype Empresarial se comunican con los usuarios de TeamsOnly mediante interoperabilidad y viceversa.</span><span class="sxs-lookup"><span data-stu-id="a516e-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagrama que muestra la actualización de capacidades de selección con usuarios activos en el modo Islas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="a516e-183">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="a516e-183">Related links</span></span>

[<span data-ttu-id="a516e-184">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a516e-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="a516e-185">Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="a516e-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="a516e-186">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="a516e-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="a516e-187">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="a516e-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="a516e-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="a516e-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="a516e-189">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="a516e-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

