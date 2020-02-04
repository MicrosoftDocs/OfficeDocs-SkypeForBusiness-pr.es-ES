---
title: Migrar grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="de699-102">Migrar grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="de699-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de699-103">_**Última modificación del tema:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="de699-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="de699-104">Una vez que los usuarios se mueven a los grupos de Lync Server 2013, puede migrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="de699-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="de699-105">La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contactos de grupo de respuesta de la implementación heredada al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de699-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="de699-106">Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación de grupo de respuesta en el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de699-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="de699-107">Las llamadas a grupos de respuesta ya no son controladas por el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="de699-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de699-108">Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Lync Server 2013, le recomendamos que mueva todos los usuarios en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="de699-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="de699-109">En particular, los usuarios que sean agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de699-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="de699-110">Antes de migrar grupos de respuesta, debe haber implementado un grupo de 2013 de Lync Server que incluya la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="de699-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="de699-111">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="de699-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="de699-112">Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="de699-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de699-113">Puede crear nuevos grupos de respuesta de Lync Server 2013 en el grupo de servidores de Lync 2013 antes de migrar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="de699-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="de699-114">Para migrar grupos de respuesta de un grupo heredado a Lync Server 2013, ejecute el cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="de699-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="de699-115">El cmdlet de migración de grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="de699-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="de699-116">No puede seleccionar grupos, colas o flujos de trabajo específicos para migrar.</span><span class="sxs-lookup"><span data-stu-id="de699-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="de699-117">Después de migrar los grupos de respuesta, debe usar el panel de control de Lync Server o los cmdlets del shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se han movido correctamente.</span><span class="sxs-lookup"><span data-stu-id="de699-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="de699-118">Al migrar grupos de respuesta, los grupos de respuesta 2010 de Lync Server no se quitan.</span><span class="sxs-lookup"><span data-stu-id="de699-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="de699-119">Al administrar grupos de respuesta después de la migración mediante el panel de control de Lync Server o el shell de administración de Lync Server, puede ver los grupos de respuesta 2010 de Lync Server y los grupos de respuesta de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de699-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="de699-120">Solo debe aplicar actualizaciones a los grupos de respuesta 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de699-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="de699-121">Los grupos de respuesta de Lync Server 2010 se conservan solo por motivos de reversión.</span><span class="sxs-lookup"><span data-stu-id="de699-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="de699-122">Una vez completada la migración y creados los nuevos grupos de respuesta, el panel de control de Lync Server y el shell de administración de Lync Server mostrarán las versiones de Lync Server 2010 y Lync Server 2013 de cada grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="de699-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="de699-123">No use el panel de control de Lync Server ni el shell de administración de Lync Server para quitar los grupos de respuesta 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de699-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="de699-124">Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="de699-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="de699-125">Los grupos de respuesta de Lync Server 2010 se quitarán al retirar el grupo de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="de699-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="de699-126">Le recomendamos que no elimine ningún dato de la implementación anterior hasta que no represente el grupo.</span><span class="sxs-lookup"><span data-stu-id="de699-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="de699-127">Además, le recomendamos encarecidamente que exporte los grupos de respuesta inmediatamente después de la migración.</span><span class="sxs-lookup"><span data-stu-id="de699-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="de699-128">Si se debe quitar un grupo de respuesta 2010 de Lync Server, puede restaurar los grupos de respuesta desde la copia de seguridad para obtener los grupos de respuesta de Lync Server 2013 de nuevo.</span><span class="sxs-lookup"><span data-stu-id="de699-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="de699-129">Lync Server 2013 incorpora una nueva característica de grupo de respuesta denominada **tipo de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="de699-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="de699-130">El **tipo de flujo de trabajo** se puede administrar o **no administrar**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="de699-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="de699-131">Todos los grupos de respuesta se migran con el **tipo de flujo de trabajo** establecido en **no administrado** y con una lista vacía de administrador.</span><span class="sxs-lookup"><span data-stu-id="de699-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="de699-132">Al ejecutar el cmdlet **Move-CsRgsConfiguration** , los grupos de agentes, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para fines de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="de699-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="de699-133">Sin embargo, si necesita volver al grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para mover los objetos de contacto de nuevo al grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="de699-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="de699-134">El siguiente procedimiento para migrar la configuración de un grupo de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de699-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="de699-135">Si tiene previsto consolidar o dividir las agrupaciones durante la migración y la implementación, debe planear los mapas de agrupaciones heredados en los que el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de699-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="de699-136">Para migrar las configuraciones de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="de699-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="de699-137">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="de699-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="de699-138">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="de699-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="de699-139">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="de699-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="de699-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="de699-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="de699-141">Después de migrar grupos de respuesta y agentes al grupo de servidores de Lync Server 2013, la dirección URL que los agentes usan para iniciar y cerrar sesión es una dirección URL de Lync Server 2013 y está disponible en el menú **herramientas** .</span><span class="sxs-lookup"><span data-stu-id="de699-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="de699-142">Recuerde a los agentes que actualicen cualquier referencia, como marcadores, a la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="de699-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="de699-143">Para comprobar la migración de grupos de respuesta mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="de699-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="de699-144">Inicie sesión en el equipo con una cuenta que sea miembro de RTCUniversalReadOnlyAdmins grupo o que sea, al menos, miembro de la función CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="de699-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="de699-145">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de699-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="de699-146">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="de699-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="de699-147">En el panel de navegación izquierdo, haga clic en **grupos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="de699-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="de699-148">En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="de699-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="de699-149">Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno de Lync Server 2010 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="de699-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="de699-150">Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Lync Server 2010 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="de699-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="de699-151">Para comprobar la migración de grupos de respuesta mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="de699-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="de699-152">Inicie sesión en el equipo con una cuenta que sea miembro de RTCUniversalReadOnlyAdmins grupo o que sea, al menos, miembro de la función CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="de699-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="de699-153">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="de699-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="de699-154">Para obtener más información sobre los siguientes cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="de699-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="de699-155">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="de699-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="de699-156">Compruebe que todos los grupos de agentes del entorno de Lync Server 2010 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="de699-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="de699-157">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="de699-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="de699-158">Compruebe que todas las colas del entorno de Lync Server 2010 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="de699-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="de699-159">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="de699-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="de699-160">Compruebe que todos los flujos de trabajo del entorno de Lync Server 2010 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="de699-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

