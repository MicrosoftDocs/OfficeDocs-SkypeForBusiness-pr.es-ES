---
title: Migrar grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de mover los usuarios a los grupos de servidores de Skype empresarial 2019, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover los objetos de contacto del grupo de respuesta de la implementación heredada al grupo de servidores de Skype empresarial 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación de grupo de respuesta en el grupo de servidores de Skype empresarial 2019. Las llamadas a grupos de respuesta ya no son controladas por el grupo heredado.
ms.openlocfilehash: 9e7605daf92646e5bb53626eeed2371888bf9cb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813468"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="25882-106">Migrar grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="25882-106">Migrate response groups</span></span>

<span data-ttu-id="25882-107">Después de mover los usuarios a los grupos de servidores de Skype empresarial 2019, puede migrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="25882-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="25882-108">La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover los objetos de contacto del grupo de respuesta de la implementación heredada al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="25882-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="25882-109">Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación de grupo de respuesta en el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="25882-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="25882-110">Las llamadas a grupos de respuesta ya no son controladas por el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="25882-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="25882-111">Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Skype empresarial 2019, le recomendamos que mueva todos los usuarios en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="25882-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="25882-112">En particular, los usuarios que sean agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="25882-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="25882-113">Antes de migrar grupos de respuesta, debe haber implementado un grupo de servidores de Skype empresarial 2019 que incluya la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="25882-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="25882-114">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="25882-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="25882-115">Para asegurarse de que la aplicación de grupo de respuesta se instala, ejecute el cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="25882-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="25882-116">Puede crear nuevos grupos de respuesta de Skype empresarial 2019 en el grupo de Skype empresarial 2019 antes de migrar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="25882-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="25882-117">Para migrar grupos de respuesta de un grupo heredado a la 2019 de Skype empresarial Server, ejecute el cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="25882-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="25882-118">El cmdlet de migración de grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="25882-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="25882-119">No puede seleccionar grupos, colas o flujos de trabajo específicos para migrar.</span><span class="sxs-lookup"><span data-stu-id="25882-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="25882-120">Después de migrar los grupos de respuesta, debe usar el panel de control de Skype empresarial Server o los cmdlets del shell de administración de Skype empresarial para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se han movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="25882-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="25882-121">Al migrar grupos de respuesta, los grupos de respuesta heredados no se quitan.</span><span class="sxs-lookup"><span data-stu-id="25882-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="25882-122">Al administrar grupos de respuesta después de la migración mediante el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial, puede ver los grupos de respuesta heredados y los grupos de respuesta de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="25882-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="25882-123">Solo debe aplicar actualizaciones a los grupos de respuesta 2019 de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="25882-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="25882-124">Los grupos de respuesta heredados solo se conservan con fines de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="25882-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="25882-125">Una vez que se haya completado la migración y se hayan creado los nuevos grupos de respuesta, el panel de control de Skype empresarial Server y el shell de administración de Skype empresarial Server mostrarán las versiones del servidor de Skype heredado y de Skype empresarial 2019 de cada respuesta mesa.</span><span class="sxs-lookup"><span data-stu-id="25882-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="25882-126">No use el panel de control de Skype empresarial Server ni el shell de administración de Skype empresarial para quitar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="25882-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="25882-127">Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="25882-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="25882-128">Los grupos de respuesta heredados se quitarán al retirar el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="25882-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="25882-129">Le recomendamos que no elimine ningún dato de la implementación anterior hasta que no represente el grupo.</span><span class="sxs-lookup"><span data-stu-id="25882-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="25882-130">Además, le recomendamos encarecidamente que exporte los grupos de respuesta inmediatamente después de la migración.</span><span class="sxs-lookup"><span data-stu-id="25882-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="25882-131">Si un grupo de respuesta heredado debe quitarse, puede restaurar los grupos de respuesta de la copia de seguridad para que los grupos de respuesta de Skype empresarial Server 2019 vuelvan a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="25882-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="25882-132">Skype empresarial Server 2019 presenta una nueva característica de grupo de respuesta llamada **tipo de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="25882-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="25882-133">El **tipo de flujo de trabajo** se puede administrar o **no administrar**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="25882-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="25882-134">Todos los grupos de respuesta se migran con el **tipo de flujo de trabajo** establecido en **no administrado** y con una lista vacía de administrador.</span><span class="sxs-lookup"><span data-stu-id="25882-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="25882-135">Al ejecutar el cmdlet **Move-CsRgsConfiguration** , los grupos de agentes, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para fines de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="25882-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="25882-136">Sin embargo, si necesita volver al grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para mover los objetos de contacto de nuevo al grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="25882-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="25882-137">El siguiente procedimiento para migrar la configuración de un grupo de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de 2019 de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="25882-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="25882-138">Si tiene previsto consolidar o dividir las agrupaciones durante la migración y la implementación, debe planear los mapas de agrupaciones heredados en los que el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="25882-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="25882-139">Para migrar las configuraciones de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="25882-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="25882-140">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="25882-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="25882-141">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="25882-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="25882-142">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="25882-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="25882-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="25882-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="25882-144">Después de migrar grupos de respuesta y agentes al grupo de servidores de Skype empresarial 2019, la dirección URL que los agentes usan para iniciar y cerrar sesión es una URL de Skype empresarial Server 2019 y está disponible en el menú **herramientas** .</span><span class="sxs-lookup"><span data-stu-id="25882-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="25882-145">Recuerde a los agentes que actualicen cualquier referencia, como marcadores, a la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="25882-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="25882-146">Para comprobar la migración de grupos de respuesta con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="25882-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="25882-147">Inicie sesión en el equipo con una cuenta que sea miembro de RTCUniversalReadOnlyAdmins grupo o que sea, al menos, miembro de la función CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="25882-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="25882-148">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="25882-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="25882-149">Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [abrir las herramientas administrativas 2019 de Skype empresarial Server](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span><span class="sxs-lookup"><span data-stu-id="25882-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="25882-150">En el panel de navegación izquierdo, haga clic en **grupos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="25882-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="25882-151">En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo de su entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="25882-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="25882-152">Haga clic en la pestaña **cola** y compruebe que todas las colas de su entorno heredado estén incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="25882-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="25882-153">Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes de su entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="25882-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="25882-154">Para comprobar la migración de grupos de respuesta con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="25882-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="25882-155">Inicie sesión en el equipo con una cuenta que sea miembro de RTCUniversalReadOnlyAdmins grupo o que sea, al menos, miembro de la función CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="25882-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="25882-156">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="25882-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="25882-157">Para obtener más información sobre los siguientes cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="25882-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="25882-158">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="25882-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="25882-159">Verifique que todos los grupos de agentes de su entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="25882-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="25882-160">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="25882-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="25882-161">Verifique que todas las colas de su entorno heredado estén incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="25882-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="25882-162">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="25882-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="25882-163">Verifique que todos los flujos de trabajo de su entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="25882-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

