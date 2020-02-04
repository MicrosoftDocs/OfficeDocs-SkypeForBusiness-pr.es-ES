---
title: Migrar grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="d8e78-102">Migrar grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="d8e78-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8e78-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d8e78-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d8e78-104">Una vez que los usuarios se mueven a los grupos de Lync Server 2013, puede migrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d8e78-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="d8e78-105">La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo y archivos de audio, y mover los objetos de contacto del grupo de respuesta de la implementación heredada al grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e78-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d8e78-106">Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación de grupo de respuesta en el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e78-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="d8e78-107">Las llamadas a grupos de respuesta ya no son controladas por el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="d8e78-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8e78-108">Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Lync Server 2013, le recomendamos que mueva todos los usuarios en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="d8e78-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="d8e78-109">En particular, los usuarios que sean agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e78-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="d8e78-110">Antes de migrar grupos de respuesta, debe haber implementado un grupo de 2013 de Lync Server que incluya la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d8e78-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="d8e78-111">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8e78-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="d8e78-112">Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService-ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="d8e78-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8e78-113">Puede crear nuevos grupos de respuesta de Lync Server 2013 en el grupo de servidores de Lync 2013 antes de migrar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="d8e78-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="d8e78-114">Para migrar grupos de respuesta de un grupo heredado a Lync Server 2013, ejecute el cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d8e78-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="d8e78-115">Antes de poder ejecutar **Move-CsRgsConfiguration**, primero debe instalar el paquete interfaces de compatibilidad con versiones anteriores del instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="d8e78-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="d8e78-116">Instale esta aplicación ejecutando OCSWMIBC. msi.</span><span class="sxs-lookup"><span data-stu-id="d8e78-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="d8e78-117">Puede encontrar OCSWMIBC. msi en los medios de instalación de la carpeta SETUP.</span><span class="sxs-lookup"><span data-stu-id="d8e78-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8e78-118">El cmdlet de migración de grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="d8e78-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="d8e78-119">No puede seleccionar grupos, colas o flujos de trabajo específicos para migrar.</span><span class="sxs-lookup"><span data-stu-id="d8e78-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="d8e78-120">Después de migrar los grupos de respuesta, debe actualizar la dirección URL que usan los agentes formales para iniciar y cerrar sesión en sus grupos de respuesta, y usar el panel de control de Lync Server o los cmdlets del shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se movieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8e78-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d8e78-121">Al migrar grupos de respuesta, los grupos de respuesta de Office Communications Server 2007 R2 no se quitan.</span><span class="sxs-lookup"><span data-stu-id="d8e78-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="d8e78-122">No quite los grupos de respuesta de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d8e78-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="d8e78-123">Si quita un grupo de respuesta de Office Communications Server 2007 R2, los grupos de respuesta de Lync Server 2013 dejarán de funcionar.</span><span class="sxs-lookup"><span data-stu-id="d8e78-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8e78-124">Le recomendamos que no elimine ningún dato de la implementación anterior hasta que no represente el grupo.</span><span class="sxs-lookup"><span data-stu-id="d8e78-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="d8e78-125">Además, le recomendamos encarecidamente que exporte los grupos de respuesta inmediatamente después de la migración.</span><span class="sxs-lookup"><span data-stu-id="d8e78-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="d8e78-126">Si se elimina un grupo de respuesta de Office Communications Server 2007 R2, puede restaurar los grupos de respuesta desde la copia de seguridad para obtener los grupos de respuesta de Lync Server 2013 que se ejecutan de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d8e78-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="d8e78-127">Al ejecutar el cmdlet **Move-CsRgsConfiguration** , los grupos de agentes, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para fines de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="d8e78-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="d8e78-128">Sin embargo, si necesita volver al grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para mover los objetos de contacto de nuevo al grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="d8e78-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8e78-129">Le recomendamos que no elimine ningún dato del grupo de respuesta del grupo heredado hasta que se desbloquee el grupo.</span><span class="sxs-lookup"><span data-stu-id="d8e78-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="d8e78-130">El procedimiento siguiente para migrar las configuraciones de grupos de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8e78-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="d8e78-131">Si tiene previsto consolidar o dividir las agrupaciones durante la migración y la implementación, debe planear los mapas de agrupaciones heredados en los que el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e78-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="d8e78-132">Para migrar las configuraciones de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="d8e78-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="d8e78-133">Busque OCSWMIBC. msi en la carpeta SETUP del disco de instalación e instálelo.</span><span class="sxs-lookup"><span data-stu-id="d8e78-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="d8e78-134">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d8e78-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="d8e78-135">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8e78-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="d8e78-136">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="d8e78-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="d8e78-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d8e78-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="d8e78-138">Si ha implementado la pestaña grupo de respuesta para Microsoft Office Communicator 2007 R2 en el entorno de Office Communications Server 2007 R2, quite la pestaña del archivo Tabs. XML de Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d8e78-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8e78-139">Agentes formales usó la ficha grupo de respuesta para iniciar sesión en sus grupos de respuesta antes de que puedan recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="d8e78-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="d8e78-140">Si ha implementado la pestaña grupo de respuesta, eligió la ubicación del archivo Tabs. XML de Office Communicator 2007 R2 al implementarlo.</span><span class="sxs-lookup"><span data-stu-id="d8e78-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="d8e78-141">Proporcionar a los usuarios la dirección URL actualizada para que los agentes tengan que iniciar y cerrar sesión en sus grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d8e78-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8e78-142">La dirección URL es https://webpoolFQDN/RgsClients/Tab.aspxnormalmente, donde webpoolFQDN es el nombre de dominio completo (FQDN) del grupo de servidores web que está asociado al grupo que acaba de migrar a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8e78-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8e78-143">Este paso no es necesario después de que los usuarios actualicen a Lync 2013 porque la dirección URL está disponible en el menú <STRONG>herramientas</STRONG> de Lync.</span><span class="sxs-lookup"><span data-stu-id="d8e78-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="d8e78-144">Para comprobar la migración de grupos de respuesta mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d8e78-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d8e78-145">Abra el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8e78-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="d8e78-146">En el panel de navegación izquierdo, haga clic en **grupos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="d8e78-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="d8e78-147">En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="d8e78-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="d8e78-148">Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno de Office Communications Server 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="d8e78-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="d8e78-149">Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="d8e78-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="d8e78-150">Para comprobar la migración de grupos de respuesta mediante cmdlets</span><span class="sxs-lookup"><span data-stu-id="d8e78-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="d8e78-151">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8e78-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="d8e78-152">Para obtener más información sobre los siguientes cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d8e78-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="d8e78-153">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="d8e78-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="d8e78-154">Compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="d8e78-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="d8e78-155">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="d8e78-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="d8e78-156">Compruebe que todas las colas del entorno de Office Communications Server 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="d8e78-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="d8e78-157">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="d8e78-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="d8e78-158">Compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="d8e78-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

