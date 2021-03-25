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
description: Una vez que los usuarios se mueven a grupos de servidores de Skype Empresarial Server 2019, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto del grupo de respuesta desde la implementación heredada al grupo de Skype Empresarial Server 2019. Después de migrar los grupos de respuesta heredados, la aplicación grupo de respuesta controla las llamadas a los grupos de respuesta en el grupo de Skype Empresarial Server 2019. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.
ms.openlocfilehash: bf4087440fb112cb1af906e1a0915531eea08456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113276"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="6d1b8-106">Migrar los grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="6d1b8-106">Migrate response groups</span></span>

<span data-ttu-id="6d1b8-107">Una vez que los usuarios se mueven a grupos de servidores de Skype Empresarial Server 2019, puede migrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="6d1b8-108">La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto del grupo de respuesta desde la implementación heredada al grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6d1b8-109">Después de migrar los grupos de respuesta heredados, la aplicación grupo de respuesta controla las llamadas a los grupos de respuesta en el grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6d1b8-110">El grupo heredado ya no maneja las llamadas a los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d1b8-111">Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de Skype Empresarial Server 2019, se recomienda mover primero a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="6d1b8-112">En concreto, los usuarios que son agentes de grupo de respuesta no tendrán funcionalidad completa de nuevas características hasta que se trasladen al grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="6d1b8-113">Antes de migrar grupos de respuesta, debe haber implementado un grupo de Skype Empresarial Server 2019 que incluya la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="6d1b8-114">La aplicación grupo de respuesta se instala y se activa de forma predeterminada al implementar Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="6d1b8-115">Puede asegurarse de que la aplicación grupo de respuesta está instalada ejecutando el cmdlet **Get-CsService -ApplicationServer.**</span><span class="sxs-lookup"><span data-stu-id="6d1b8-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6d1b8-116">Puede crear nuevos grupos de respuesta de Skype Empresarial Server 2019 en el grupo de Skype Empresarial Server 2019 antes de migrar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="6d1b8-117">Para migrar grupos de respuesta de un grupo heredado al Skype Empresarial Server 2019, ejecute el cmdlet **Move-CsRgsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="6d1b8-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6d1b8-118">El cmdlet de migración grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="6d1b8-119">No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="6d1b8-120">Después de migrar los grupos de respuesta, debe usar los cmdlets del Panel de control de Skype Empresarial Server o shell de administración de Skype Empresarial Server para comprobar que todos los grupos de agentes, colas y flujos de trabajo se movieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="6d1b8-121">Al migrar grupos de respuesta, no se quitan los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="6d1b8-122">Al administrar grupos de respuesta después de la migración mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server, puede ver tanto los grupos de respuesta heredados como los grupos de respuesta de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="6d1b8-123">Solo debe aplicar actualizaciones a los grupos de respuesta de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="6d1b8-124">Los grupos de respuesta heredados solo se conservan con fines de reversión.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="6d1b8-125">Una vez completada la migración y creados los nuevos grupos de respuesta, el Panel de control de Skype Empresarial Server y el Shell de administración de Skype Empresarial Server mostrarán las versiones heredadas y Skype Empresarial Server 2019 de cada grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="6d1b8-126">No use el Panel de control de Skype Empresarial Server ni el Shell de administración de Skype Empresarial Server para quitar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="6d1b8-127">Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="6d1b8-128">Los grupos de respuesta heredados se quitarán al retirar el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6d1b8-129">Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="6d1b8-130">También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="6d1b8-131">Si se debe quitar un grupo de respuesta heredado, puede restaurar los grupos de respuesta de la copia de seguridad para que los grupos de respuesta de Skype Empresarial Server 2019 vuelvan a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="6d1b8-132">Skype Empresarial Server 2019 presenta una nueva característica de grupo de respuesta denominada **Tipo de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="6d1b8-133">El **tipo de flujo de trabajo** puede ser **administrado** o **no administrado**.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="6d1b8-134">Todos los grupos de respuesta son migrados con el **tipo de flujo de trabajo** configurado en **No administrado** y con la lista del Administrador vacía.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="6d1b8-135">Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="6d1b8-136">Si embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="6d1b8-137">El siguiente procedimiento para migrar configuraciones de grupo de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de servidores de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="6d1b8-138">Si tiene previsto consolidar o dividir grupos de servidores durante la migración y la implementación, debe planear qué grupo heredado asigna a qué grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="6d1b8-139">Para migrar configuraciones de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6d1b8-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="6d1b8-140">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="6d1b8-141">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de **Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6d1b8-142">Ejecute: </span><span class="sxs-lookup"><span data-stu-id="6d1b8-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="6d1b8-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6d1b8-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="6d1b8-144">Después de migrar grupos de respuesta y agentes al grupo de Skype Empresarial Server 2019, la dirección URL que los agentes usan  para iniciar sesión y cerrar sesión es una dirección URL de Skype Empresarial Server 2019 y está disponible en el menú Herramientas.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="6d1b8-145">Recuerde a los agentes que actualicen las referencias, como los marcadores, a la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6d1b8-146">Para comprobar la migración del grupo de respuesta mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6d1b8-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6d1b8-147">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="6d1b8-148">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="6d1b8-149">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, vea [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span><span class="sxs-lookup"><span data-stu-id="6d1b8-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="6d1b8-150">En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="6d1b8-151">En la **pestaña Flujo** de trabajo, compruebe que todos los flujos de trabajo del entorno heredado están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="6d1b8-152">Haga clic **en la pestaña** Cola y compruebe que todas las colas del entorno heredado se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="6d1b8-153">Haga clic **en la pestaña** Grupo y compruebe que todos los grupos de agentes del entorno heredado están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6d1b8-154">Para comprobar la migración del grupo de respuesta mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6d1b8-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6d1b8-155">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="6d1b8-156">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de **Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="6d1b8-157">Para obtener más información sobre los siguientes cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6d1b8-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="6d1b8-158">Ejecute: </span><span class="sxs-lookup"><span data-stu-id="6d1b8-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="6d1b8-159">Compruebe que todos los grupos de agentes del entorno heredado estén incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="6d1b8-160">Ejecute: </span><span class="sxs-lookup"><span data-stu-id="6d1b8-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="6d1b8-161">Compruebe que todas las colas del entorno heredado están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="6d1b8-162">Ejecute: </span><span class="sxs-lookup"><span data-stu-id="6d1b8-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="6d1b8-163">Compruebe que todos los flujos de trabajo del entorno heredado están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="6d1b8-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
