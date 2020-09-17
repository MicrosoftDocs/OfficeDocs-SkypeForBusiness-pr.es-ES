---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 887ab004ae913ee2171f1894bd5fc4a44845881f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940748"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="1ea54-103">Implementar la actualización de Skype empresarial a teams &mdash; para administradores de ti</span><span class="sxs-lookup"><span data-stu-id="1ea54-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="1ea54-104">En este artículo se describe cómo implementar la actualización.</span><span class="sxs-lookup"><span data-stu-id="1ea54-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="1ea54-105">Este artículo es el quinto de varios que describen los conceptos de actualización y la implementación para administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="1ea54-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="1ea54-106">Información general</span><span class="sxs-lookup"><span data-stu-id="1ea54-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="1ea54-107">Métodos de actualización</span><span class="sxs-lookup"><span data-stu-id="1ea54-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="1ea54-108">Herramientas para administrar la actualización</span><span class="sxs-lookup"><span data-stu-id="1ea54-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="1ea54-109">Consideraciones adicionales para las organizaciones con Skype empresarial local</span><span class="sxs-lookup"><span data-stu-id="1ea54-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="1ea54-110">**Implementar la actualización** (este artículo)</span><span class="sxs-lookup"><span data-stu-id="1ea54-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="1ea54-111">Consideraciones sobre la red telefónica pública conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="1ea54-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="1ea54-112">Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:</span><span class="sxs-lookup"><span data-stu-id="1ea54-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="1ea54-113">Coexistencia de Teams y Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="1ea54-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="1ea54-114">Modos de coexistencia: referencia</span><span class="sxs-lookup"><span data-stu-id="1ea54-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="1ea54-115">Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia</span><span class="sxs-lookup"><span data-stu-id="1ea54-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="1ea54-116">Opciones de actualización</span><span class="sxs-lookup"><span data-stu-id="1ea54-116">Upgrade options</span></span>

<span data-ttu-id="1ea54-117">En esta sección se describe cómo implementar la actualización mediante una de las siguientes opciones de actualización:</span><span class="sxs-lookup"><span data-stu-id="1ea54-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="1ea54-118">Actualización de capacidades superpuestas (con el modo Islas)</span><span class="sxs-lookup"><span data-stu-id="1ea54-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="1ea54-119">Una actualización de las funciones seleccionadas para una organización que aún no ha empezado a usar Teams</span><span class="sxs-lookup"><span data-stu-id="1ea54-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="1ea54-120">Una actualización de las funciones seleccionadas para una organización que ya usa equipos en el modo islas</span><span class="sxs-lookup"><span data-stu-id="1ea54-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="1ea54-121">Si necesita más información sobre las opciones, asegúrese de que ya ha leído [los métodos de actualización](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="1ea54-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="1ea54-122">Actualización de capacidades superpuestas (con el modo Islas)</span><span class="sxs-lookup"><span data-stu-id="1ea54-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="1ea54-123">Para la opción de actualización capacidades superpuestas:</span><span class="sxs-lookup"><span data-stu-id="1ea54-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="1ea54-124">Considere esta opción si puede realizar una actualización rápida para su organización general.</span><span class="sxs-lookup"><span data-stu-id="1ea54-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="1ea54-125">Puesto que hay riesgo potencial de confusión para los usuarios finales que ejecutan ambos clientes, es mejor si puede minimizar el período de tiempo durante el cual los usuarios deben ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="1ea54-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="1ea54-126">Debe asegurarse de que los usuarios sepan ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="1ea54-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="1ea54-127">Esta opción es el modelo que no está en el equipo y no requiere ninguna acción de administrador para comenzar a usar Teams excepto para asignar la licencia de Microsoft 365 o de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ea54-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="1ea54-128">Si los usuarios ya tienen Skype empresarial online, es posible que ya esté en este modelo.</span><span class="sxs-lookup"><span data-stu-id="1ea54-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="1ea54-129">Puede resultar difícil sacar provecho del modo de funciones superpuestas y pasar a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1ea54-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="1ea54-130">Como los usuarios actualizados solo se comunican a través de Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe estar usando Teams.</span><span class="sxs-lookup"><span data-stu-id="1ea54-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="1ea54-131">Si tiene usuarios que no han empezado a usar Teams, se mostrarán a los mensajes que faltan.</span><span class="sxs-lookup"><span data-stu-id="1ea54-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="1ea54-132">Además, no verán los usuarios de TeamsOnly en línea en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1ea54-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="1ea54-133">Algunas organizaciones eligen realizar una actualización para todos los inquilinos con la directiva global de inquilino para evitar esto, sin embargo, requieren una planeación inicial, así como la espera hasta que todos los usuarios estén listos para su actualización.</span><span class="sxs-lookup"><span data-stu-id="1ea54-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="1ea54-134">Una actualización de las funciones seleccionadas para una organización que aún no ha empezado a usar Teams</span><span class="sxs-lookup"><span data-stu-id="1ea54-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="1ea54-135">Si su organización aún no tiene ningún usuario activo en Teams, el primer paso es establecer la directiva predeterminada para el inquilino para TeamsUpgradePolicy en uno de los modos de Skype empresarial, por ejemplo, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="1ea54-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="1ea54-136">Los usuarios que aún no hayan comenzado a usar Teams no apreciarán ninguna diferencia en el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1ea54-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="1ea54-137">Sin embargo, la configuración de esta directiva en el nivel de espacio empresarial permite empezar a actualizar usuarios al modo TeamsOnly y garantiza que los usuarios actualizados puedan seguir comunicándose con usuarios no actualizados.</span><span class="sxs-lookup"><span data-stu-id="1ea54-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="1ea54-138">Una vez que hayas identificado a los usuarios de la prueba piloto, puedes actualizarlos a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1ea54-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="1ea54-139">Si son locales, usa Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="1ea54-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="1ea54-140">Si están conectados, simplemente asígnelos a TeamsOnly Mode con Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="1ea54-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="1ea54-141">De forma predeterminada, cualquier reunión de Skype empresarial programada por estos usuarios se migrará a teams.</span><span class="sxs-lookup"><span data-stu-id="1ea54-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="1ea54-142">A continuación se muestran los comandos clave:</span><span class="sxs-lookup"><span data-stu-id="1ea54-142">Following are the key commands:</span></span>

1. <span data-ttu-id="1ea54-143">Establezca el valor predeterminado para el inquilino en modo SfbWithTeamsCollab de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1ea54-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="1ea54-144">Actualice los usuarios de la prueba piloto para que TeamsOnly de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1ea54-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="1ea54-145">Para un usuario que está conectado:</span><span class="sxs-lookup"><span data-stu-id="1ea54-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="1ea54-146">Para un usuario que sea local:</span><span class="sxs-lookup"><span data-stu-id="1ea54-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="1ea54-147">Notas</span><span class="sxs-lookup"><span data-stu-id="1ea54-147">Notes</span></span>
 
- <span data-ttu-id="1ea54-148">En lugar de establecer la Directiva de todo el inquilino en SfbWithTeamsCollab, puede establecerla en SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="1ea54-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="1ea54-149">Esto hace que todos los usuarios programen todas las reuniones nuevas en Teams.</span><span class="sxs-lookup"><span data-stu-id="1ea54-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="1ea54-150">`Move-CsUser` es un cmdlet en las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="1ea54-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="1ea54-151">El `MoveToTeams` conmutador requiere Skype empresarial server 2019 o Skype empresarial server 2015 con CU8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="1ea54-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="1ea54-152">Si está usando una versión anterior, puede mover primero el usuario a Skype empresarial online y, a continuación, conceder el modo TeamsOnly a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="1ea54-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="1ea54-153">De forma predeterminada, las reuniones de Skype empresarial se migran a teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="1ea54-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="1ea54-154">El diagrama siguiente muestra las fases conceptuales de actualización de las funciones seleccionadas para una organización sin un uso previo de Teams.</span><span class="sxs-lookup"><span data-stu-id="1ea54-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="1ea54-155">El alto de las barras representa el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1ea54-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="1ea54-156">Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="1ea54-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="1ea54-157">Los usuarios de Skype empresarial se comunican con usuarios de TeamsOnly usando interoperabilidad y viceversa.</span><span class="sxs-lookup"><span data-stu-id="1ea54-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="1ea54-158">Los usuarios en modo islas deben asegurarse de ejecutar ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="1ea54-158">Users in Islands mode must be sure to run both clients.</span></span>

![Diagrama que muestra la selección de funciones de selección sin un uso previo de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="1ea54-160">Una actualización de las funciones seleccionadas para una organización que ya usa equipos en el modo islas</span><span class="sxs-lookup"><span data-stu-id="1ea54-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="1ea54-161">Si algunos usuarios de su organización usan activamente equipos en modo islas, es probable que no desee quitar la funcionalidad de los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="1ea54-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="1ea54-162">Por lo tanto, es necesario un paso adicional antes de cambiar la Directiva de todo el inquilino.</span><span class="sxs-lookup"><span data-stu-id="1ea54-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="1ea54-163">La solución es "abuelo", es decir, los usuarios existentes de equipos activos en modo islas, antes de establecer la política de todos los inquilinos en SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="1ea54-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="1ea54-164">Una vez que lo haya hecho, puede proceder con la implementación como se indica anteriormente, pero tendrá dos grupos de usuarios que se están moviendo a TeamsOnly: los usuarios que estuvieron activos en Teams estarán en modo islas y el resto de usuarios estarán en el modo SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="1ea54-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="1ea54-165">Puede mover estos usuarios progresivamente al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1ea54-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="1ea54-166">Busque usuarios que estén activos en Teams de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1ea54-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="1ea54-167">En el centro de administración de Microsoft 365, en la barra de navegación de la izquierda, vaya a informes y, después, uso.</span><span class="sxs-lookup"><span data-stu-id="1ea54-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="1ea54-168">En la lista desplegable "seleccionar un informe", elija Microsoft Teams y, a continuación, actividad del usuario.</span><span class="sxs-lookup"><span data-stu-id="1ea54-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="1ea54-169">Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams.</span><span class="sxs-lookup"><span data-stu-id="1ea54-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="1ea54-170">Haga clic en exportar, abrir Excel y filtro para mostrar solo los usuarios que están activos en Teams.</span><span class="sxs-lookup"><span data-stu-id="1ea54-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="1ea54-171">Para cada usuario de equipos activos que se encuentra en el paso 1, asigne el modo islas en el PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="1ea54-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="1ea54-172">Esto le permite ir al paso siguiente y se asegura de que no cambie la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="1ea54-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="1ea54-173">Establezca la Directiva de todo el inquilino en SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="1ea54-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="1ea54-174">Actualice los usuarios seleccionados al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1ea54-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="1ea54-175">Puede optar por actualizar los usuarios en el modo islas o SfbWithTeamsCollab, aunque es posible que desee dar prioridad a la actualización de los usuarios en el modo islas en primer lugar para minimizar la posibilidad de confusión que puede producirse cuando los usuarios están en modo islas.</span><span class="sxs-lookup"><span data-stu-id="1ea54-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="1ea54-176">Para usuarios alojados en Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="1ea54-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="1ea54-177">Para los usuarios alojados en Skype empresarial Server local:</span><span class="sxs-lookup"><span data-stu-id="1ea54-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="1ea54-178">El diagrama siguiente muestra las fases conceptuales de una transición de selección de funciones en la que hay usuarios de islas activas al principio.</span><span class="sxs-lookup"><span data-stu-id="1ea54-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="1ea54-179">El alto de las barras representa el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1ea54-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="1ea54-180">Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.</span><span class="sxs-lookup"><span data-stu-id="1ea54-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="1ea54-181">Los usuarios de Skype empresarial se comunican con usuarios de TeamsOnly usando interoperabilidad y viceversa.</span><span class="sxs-lookup"><span data-stu-id="1ea54-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagrama que muestra las funciones de selección actualizar con usuarios activos en modo islas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="1ea54-183">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="1ea54-183">Related links</span></span>

[<span data-ttu-id="1ea54-184">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1ea54-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="1ea54-185">Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="1ea54-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="1ea54-186">Mover usuarios entre la implementación local y la nube</span><span class="sxs-lookup"><span data-stu-id="1ea54-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="1ea54-187">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="1ea54-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="1ea54-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="1ea54-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="1ea54-189">Usar el servicio de migración de reuniones (MMS)</span><span class="sxs-lookup"><span data-stu-id="1ea54-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

