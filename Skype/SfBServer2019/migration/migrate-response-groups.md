---
title: Migrar los grupos de respuesta
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de mover los usuarios a los grupos de Skype Empresarial Server 2019, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de Skype Empresarial Server 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación Grupo de respuesta en el grupo de Skype Empresarial Server 2019. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752682"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="99531-106">Migrar los grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="99531-106">Migrate response groups</span></span>

<span data-ttu-id="99531-107">Después de mover los usuarios a los grupos de Skype Empresarial Server 2019, puede migrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="99531-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="99531-108">La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="99531-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="99531-109">Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación Grupo de respuesta en el grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="99531-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="99531-110">El grupo heredado ya no maneja las llamadas a los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="99531-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99531-111">Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de Skype Empresarial Server 2019, se recomienda mover primero todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="99531-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="99531-112">En particular, los usuarios que son agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se trasladen al grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="99531-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="99531-113">Antes de migrar grupos de respuesta, debe haber implementado un grupo de Skype Empresarial Server 2019 que incluya la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="99531-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="99531-114">La aplicación Grupo de respuesta se instala y activa de forma predeterminada al implementar Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="99531-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="99531-115">Puede asegurarse de que la aplicación Grupo de respuesta está instalada ejecutando el cmdlet **Get-CsService -ApplicationServer.**</span><span class="sxs-lookup"><span data-stu-id="99531-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="99531-116">Puede crear nuevos grupos de respuesta de Skype Empresarial Server 2019 en el grupo de Skype Empresarial Server 2019 antes de migrar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="99531-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="99531-117">Para migrar grupos de respuesta de un grupo heredado a Skype Empresarial Server 2019, ejecute el cmdlet **Move-CsRgsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="99531-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="99531-118">El cmdlet de migración de grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="99531-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="99531-119">No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración.</span><span class="sxs-lookup"><span data-stu-id="99531-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="99531-120">Después de migrar los grupos de respuesta, debe usar el Panel de control de Skype Empresarial Server o los cmdlets del Shell de administración de Skype Empresarial Server para comprobar que todos los grupos de agentes, colas y flujos de trabajo se movieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="99531-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="99531-121">Al migrar grupos de respuesta, no se quitan los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="99531-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="99531-122">Cuando administra grupos de respuesta después de la migración mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server, puede ver tanto los grupos de respuesta heredados como los grupos de respuesta de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="99531-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="99531-123">Solo debe aplicar actualizaciones a los grupos de respuesta de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="99531-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="99531-124">Los grupos de respuesta heredados se conservan solo con fines de reversión.</span><span class="sxs-lookup"><span data-stu-id="99531-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="99531-125">Una vez completada la migración y creados los nuevos grupos de respuesta, el Panel de control de Skype Empresarial Server y el Shell de administración de Skype Empresarial Server mostrarán las versiones heredadas y de Skype Empresarial Server 2019 de cada grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="99531-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="99531-126">No use el Panel de control de Skype Empresarial Server ni el Shell de administración de Skype Empresarial Server para quitar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="99531-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="99531-127">Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="99531-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="99531-128">Los grupos de respuesta heredados se quitarán al retirar el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="99531-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="99531-129">Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="99531-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="99531-130">También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración.</span><span class="sxs-lookup"><span data-stu-id="99531-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="99531-131">Si se debe quitar un grupo de respuesta heredado, puede restaurar los grupos de respuesta de la copia de seguridad para que los grupos de respuesta de Skype Empresarial Server 2019 vuelvan a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="99531-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="99531-132">Skype Empresarial Server 2019 presenta una nueva característica de grupo de respuesta denominada **Tipo de flujo de trabajo.**</span><span class="sxs-lookup"><span data-stu-id="99531-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="99531-133">El **tipo de flujo de trabajo** puede ser **administrado** o **no administrado**.</span><span class="sxs-lookup"><span data-stu-id="99531-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="99531-134">Todos los grupos de respuesta son migrados con el **tipo de flujo de trabajo** configurado en **No administrado** y con la lista del Administrador vacía.</span><span class="sxs-lookup"><span data-stu-id="99531-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="99531-135">Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión.</span><span class="sxs-lookup"><span data-stu-id="99531-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="99531-136">Si embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="99531-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="99531-137">El siguiente procedimiento para migrar configuraciones de grupo de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="99531-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="99531-138">Si planea consolidar o dividir grupos durante la migración y la implementación, debe planear qué grupo heredado se asigna a qué grupo de servidores de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="99531-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="99531-139">Para migrar configuraciones de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="99531-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="99531-140">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="99531-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="99531-141">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="99531-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="99531-142">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="99531-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="99531-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="99531-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="99531-144">Después de migrar los grupos de respuesta y los agentes al grupo de Skype Empresarial Server 2019, la dirección URL que usan  los agentes para iniciar y cerrar sesión es una dirección URL de Skype Empresarial Server 2019 y está disponible en el menú Herramientas.</span><span class="sxs-lookup"><span data-stu-id="99531-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="99531-145">Recuerde a los agentes que actualicen las referencias, como los marcadores, a la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="99531-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="99531-146">Para comprobar la migración del grupo de respuesta mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="99531-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="99531-147">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="99531-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="99531-148">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="99531-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="99531-149">Para obtener más información sobre los distintos métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, consulte Herramientas administrativas de Skype Empresarial [Server 2019.](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)</span><span class="sxs-lookup"><span data-stu-id="99531-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="99531-150">En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="99531-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="99531-151">En la **pestaña Flujo de** trabajo, compruebe que todos los flujos de trabajo del entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="99531-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="99531-152">Haga clic **en la** pestaña Cola y compruebe que todas las colas del entorno heredado estén incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="99531-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="99531-153">Haga clic **en la pestaña** Grupo y compruebe que todos los grupos de agentes del entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="99531-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="99531-154">Para comprobar la migración del grupo de respuesta mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="99531-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="99531-155">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="99531-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="99531-156">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="99531-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="99531-157">Para obtener más información sobre los siguientes cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="99531-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="99531-158">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="99531-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="99531-159">Compruebe que todos los grupos de agentes del entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="99531-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="99531-160">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="99531-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="99531-161">Compruebe que todas las colas del entorno heredado estén incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="99531-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="99531-162">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="99531-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="99531-163">Compruebe que todos los flujos de trabajo del entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="99531-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

