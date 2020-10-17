---
title: Migrar los grupos de respuesta
description: Migrar grupos de respuesta.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19da4d39b6f11931bffb5a6e422c2826e7351d69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570326"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="0ab41-103">Migrar los grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="0ab41-103">Migrate response groups</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab41-104">_**Última modificación del tema:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="0ab41-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="0ab41-105">Una vez que los usuarios se han movido a grupos de servidores de Lync Server 2013, puede migrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0ab41-105">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="0ab41-106">Migrar grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ab41-106">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="0ab41-107">Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación grupo de respuesta en el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ab41-107">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="0ab41-108">El grupo heredado ya no maneja las llamadas a los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0ab41-108">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ab41-109">Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Lync Server 2013, le recomendamos que mueva todos los usuarios en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="0ab41-109">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="0ab41-110">En concreto, los usuarios que son agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ab41-110">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="0ab41-111">Antes de migrar los grupos de respuesta, debe haber implementado un grupo de servidores de 2013 de Lync Server que incluya la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0ab41-111">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="0ab41-112">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="0ab41-112">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0ab41-113">Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService – ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="0ab41-113">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ab41-114">Puede crear nuevos grupos de respuesta 2013 de Lync Server en el grupo de Lync Server 2013 antes de migrar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="0ab41-114">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="0ab41-115">Para migrar grupos de respuesta de un grupo heredado a la versión 2013 de Lync Server, ejecute el cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0ab41-115">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0ab41-116">El cmdlet de migración del grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="0ab41-116">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="0ab41-117">No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración.</span><span class="sxs-lookup"><span data-stu-id="0ab41-117">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="0ab41-118">Después de migrar los grupos de respuesta, debe usar el panel de control de Lync Server o los cmdlets del shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se movieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="0ab41-118">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="0ab41-119">Al migrar grupos de respuesta, los grupos de respuesta de Lync Server 2010 no se quitan.</span><span class="sxs-lookup"><span data-stu-id="0ab41-119">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="0ab41-120">Cuando administre grupos de respuesta después de la migración mediante el panel de control de Lync Server o el shell de administración de Lync Server, puede ver los grupos de respuesta de Lync Server 2010 y de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ab41-120">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="0ab41-121">Solo debe aplicar actualizaciones a los grupos de respuesta 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ab41-121">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="0ab41-122">Los grupos de respuesta de Lync Server 2010 solo se conservan por motivos de reversión.</span><span class="sxs-lookup"><span data-stu-id="0ab41-122">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0ab41-123">Una vez que se haya completado la migración y se hayan creado los nuevos grupos de respuesta, el panel de control de Lync Server y el shell de administración de Lync Server mostrarán las versiones de Lync Server 2010 y Lync Server 2013 de cada grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0ab41-123">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="0ab41-124">No use el panel de control de Lync Server o el shell de administración de Lync Server para quitar los grupos de respuesta 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ab41-124">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="0ab41-125">Si quita una, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="0ab41-125">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="0ab41-126">Los grupos de respuesta de Lync Server 2010 se quitarán cuando retire el grupo de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0ab41-126">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0ab41-127">Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="0ab41-127">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="0ab41-128">También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración.</span><span class="sxs-lookup"><span data-stu-id="0ab41-128">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="0ab41-129">Si se debe quitar un grupo de respuesta 2010 de Lync Server, puede restaurar los grupos de respuesta a partir de la copia de seguridad para que los grupos de respuesta de Lync Server 2013 vuelvan a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="0ab41-129">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="0ab41-130">Lync Server 2013 presenta una nueva característica de grupo de respuesta llamada **tipo de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="0ab41-130">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="0ab41-131">El **tipo de flujo de trabajo** puede ser **administrado** o **no administrado**.</span><span class="sxs-lookup"><span data-stu-id="0ab41-131">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="0ab41-132">Todos los grupos de respuesta son migrados con el **tipo de flujo de trabajo** configurado en **No administrado** y con la lista del Administrador vacía.</span><span class="sxs-lookup"><span data-stu-id="0ab41-132">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="0ab41-133">Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión.</span><span class="sxs-lookup"><span data-stu-id="0ab41-133">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="0ab41-134">Si embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="0ab41-134">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="0ab41-135">El siguiente procedimiento para migrar configuraciones de grupo de respuesta presupone que tiene una relación de uno a uno entre los grupos de servidores heredados y los grupos de servidores de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ab41-135">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="0ab41-136">Si tiene previsto consolidar o dividir grupos durante la migración y la implementación, debe planear el grupo de servidores heredado asignado a cada grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ab41-136">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="0ab41-137">Para migrar configuraciones de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="0ab41-137">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="0ab41-138">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="0ab41-138">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="0ab41-139">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0ab41-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0ab41-140">Realizar</span><span class="sxs-lookup"><span data-stu-id="0ab41-140">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="0ab41-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0ab41-141">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="0ab41-142">Después de migrar los grupos de respuesta y los agentes al grupo de servidores de Lync Server 2013, la dirección URL que los agentes usan para iniciar y cerrar sesión es una dirección URL de Lync Server 2013 y está disponible en el menú **herramientas** .</span><span class="sxs-lookup"><span data-stu-id="0ab41-142">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="0ab41-143">Recuerde a los agentes que actualicen las referencias, como los marcadores, a la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0ab41-143">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="0ab41-144">Para comprobar la migración del grupo de respuesta mediante el Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="0ab41-144">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0ab41-145">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0ab41-145">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="0ab41-146">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ab41-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0ab41-147">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0ab41-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0ab41-148">En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="0ab41-148">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="0ab41-149">En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ab41-149">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="0ab41-150">Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno de Lync Server 2010 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ab41-150">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="0ab41-151">Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Lync Server 2010 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ab41-151">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="0ab41-152">Para comprobar la migración del grupo de respuesta mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="0ab41-152">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="0ab41-153">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0ab41-153">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="0ab41-154">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0ab41-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="0ab41-155">Para obtener más información sobre los siguientes cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="0ab41-155">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="0ab41-156">Realizar</span><span class="sxs-lookup"><span data-stu-id="0ab41-156">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="0ab41-157">Compruebe que todos los grupos de agentes del entorno de Lync Server 2010 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ab41-157">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="0ab41-158">Realizar</span><span class="sxs-lookup"><span data-stu-id="0ab41-158">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="0ab41-159">Compruebe que todas las colas del entorno de Lync Server 2010 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ab41-159">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="0ab41-160">Realizar</span><span class="sxs-lookup"><span data-stu-id="0ab41-160">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="0ab41-161">Compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ab41-161">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

