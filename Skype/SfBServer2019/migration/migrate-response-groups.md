---
title: Migrar grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de que los usuarios se mueven a Skype para grupos de negocio Server 2019, puede migrar los grupos de respuesta. Respuesta migrar grupos incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover los objetos de contacto del grupo de respuesta de la implementación heredada a la Skype para el grupo de servidores de Business Server 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta son resueltos por la aplicación de grupo de respuesta en el Skype para el grupo de servidores de Business Server 2019. Las llamadas a grupos de respuesta ya no se controlan mediante el grupo heredado.
ms.openlocfilehash: 17ba19be3b574436f3a175457264654d8c28ebd0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231654"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="6fd2e-106">Migrar grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="6fd2e-106">Migrate response groups</span></span>

<span data-ttu-id="6fd2e-107">Después de que los usuarios se mueven a Skype para grupos de negocio Server 2019, puede migrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="6fd2e-108">Respuesta migrar grupos incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover los objetos de contacto del grupo de respuesta de la implementación heredada a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6fd2e-109">Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta son resueltos por la aplicación de grupo de respuesta en el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6fd2e-110">Las llamadas a grupos de respuesta ya no se controlan mediante el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6fd2e-111">Aunque puede migrar grupos de respuesta antes de mover todos los usuarios a la Skype para Business Server 2019 grupo de servidores, se recomienda que mueva todos los usuarios en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="6fd2e-112">En particular, los usuarios que sean los agentes del grupo de respuesta no tendrán una funcionalidad completa de las nuevas características hasta que se mueven a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="6fd2e-113">Antes de migrar grupos de respuesta, debe haber implementado un Skype para Business Server 2019 del grupo que incluye la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="6fd2e-114">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="6fd2e-115">Asegúrese de que está instalada la aplicación de grupo de respuesta ejecutando el cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="6fd2e-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6fd2e-116">Puede crear nuevas Skype Business Server 2019 grupos de respuesta en el Skype para el grupo de servidores de Business Server 2019 antes de migrar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="6fd2e-117">Para migrar grupos de respuesta de un grupo de servidores heredado a la Skype para Business Server 2019, ejecute el cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6fd2e-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6fd2e-118">El cmdlet de migración de grupo de respuesta mueve a la configuración de grupo de respuesta para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="6fd2e-119">No puede seleccionar grupos específicos, colas o flujos de trabajo para migrar.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="6fd2e-120">Después de migrar los grupos de respuesta, debe usar Skype para el Panel de Control de servidor empresarial o Skype para los cmdlets del Shell de administración de servidor empresarial para comprobar que todos los grupos de agentes, colas y flujos de trabajo se hayan migrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="6fd2e-121">Cuando se migran grupos de respuesta, no se quitan los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="6fd2e-122">Al administrar grupos de respuesta después de la migración mediante el uso de ambos Skype para el Panel de Control de servidor empresarial o Skype de consola de administración de servidor empresarial, puede ver los grupos de respuesta heredados y la Skype Business Server 2019 grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="6fd2e-123">Se deben aplicar las actualizaciones sólo a la Skype Business Server 2019 grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="6fd2e-124">Los grupos de respuesta heredados se conservan únicamente con fines de reversión.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="6fd2e-125">Después de la migración se ha completado y se han creado los nuevos grupos de respuesta, el Skype para el Panel de Control de servidor empresarial y la Skype para Shell de administración de Business Server mostrará el heredado y Skype para Business Server 2019 versiones de cada respuesta grupo.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="6fd2e-126">No use Skype para Panel de Control de servidor empresarial o Skype para Business Server Management Shell para quitar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="6fd2e-127">Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="6fd2e-128">Los grupos de respuesta heredados se quitan cuando se dé de baja el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6fd2e-129">Se recomienda que no quite los datos de la implementación anterior hasta que se dé de baja el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="6fd2e-130">Además, se recomienda exportar grupos de respuesta inmediatamente después de migrar.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="6fd2e-131">Si debe obtener quitar un grupo de respuesta heredados, a continuación, puede restaurar los grupos de respuesta desde la copia de seguridad para obtener Skype para volver a ejecutar los grupos de respuesta Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="6fd2e-132">Skype para Business Server 2019 presenta una nueva característica de grupo de respuesta denominada **Tipo de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="6fd2e-133">**Tipo de flujo de trabajo** puede ser **administrado** o **no administrado**.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="6fd2e-134">Todos los grupos de respuesta se migran con el **Tipo de flujo de trabajo** establecido como **no administrados** y con una lista vacía en Administrador.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="6fd2e-135">Cuando se ejecuta el cmdlet **Move-CsRgsConfiguration** , los grupos de agentes, colas, flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="6fd2e-136">Sin embargo, si es necesario revertir al grupo de servidores heredado, necesario ejecutar el cmdlet **Move-CsApplicationEndpoint** para mover objetos de contacto de vuelta al grupo de servidores heredado.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="6fd2e-137">El siguiente procedimiento para migrar las configuraciones de grupo de respuesta se da por supuesto que tiene una relación de uno a uno entre los grupos heredados y la Skype para grupos de negocio Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="6fd2e-138">Si tiene previsto consolidar o dividir los grupos de servidores durante la migración y la implementación, debe plan qué grupo heredado que se asigna a qué Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="6fd2e-139">Para migrar las configuraciones de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6fd2e-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="6fd2e-140">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga permisos y derechos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="6fd2e-141">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6fd2e-142">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="6fd2e-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="6fd2e-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fd2e-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="6fd2e-144">Después de migrar los grupos de respuesta y los agentes a la Skype para el grupo de servidores de Business Server 2019, la dirección URL que los agentes que se utilizan para iniciar y cerrar la sesión es un Skype para Business Server 2019 URL y está disponible en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="6fd2e-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="6fd2e-145">Recuerde a los agentes para actualizar las referencias, como marcadores, a la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6fd2e-146">Para comprobar la migración de grupo de respuesta mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="6fd2e-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6fd2e-147">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o, como mínimo, es un miembro del rol CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="6fd2e-148">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="6fd2e-149">Para obtener información detallada sobre los distintos métodos que puede usar para iniciar Skype para el Panel de Control de servidor empresarial, vea [Open Skype para las herramientas administrativas de Business Server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="6fd2e-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="6fd2e-150">En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="6fd2e-151">En la ficha **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno heredado se encuentran en la lista.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="6fd2e-152">Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno heredado se encuentran en la lista.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="6fd2e-153">Haga clic en la ficha de **grupo** y compruebe que todos los grupos de agentes del entorno heredado se encuentran en la lista.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6fd2e-154">Para comprobar la migración de grupo de respuesta mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="6fd2e-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6fd2e-155">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o, como mínimo, es un miembro del rol CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="6fd2e-156">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="6fd2e-157">Para obtener información detallada sobre los siguientes cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6fd2e-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="6fd2e-158">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="6fd2e-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="6fd2e-159">Compruebe que todos los grupos de agentes del entorno heredado se encuentran en la lista.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="6fd2e-160">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="6fd2e-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="6fd2e-161">Compruebe que todas las colas del entorno heredado se encuentran en la lista.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="6fd2e-162">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="6fd2e-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="6fd2e-163">Compruebe que todos los flujos de trabajo del entorno heredado se encuentran en la lista.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

