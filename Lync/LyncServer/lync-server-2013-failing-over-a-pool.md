---
title: 'Lync Server 2013: conmutación por error de un grupo'
description: 'Lync Server 2013: conmutación por error de un grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819137c1277c5058f4e5d36ef5dbe71e672e8641
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554986"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="426ba-103">Conmutación por error de un grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="426ba-103">Failing over a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="426ba-104">_**Última modificación del tema:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="426ba-104">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="426ba-p101">Si ha fallado un grupo de servidores front-end y se deben conmutar los errores, utilice el procedimiento siguiente. En este procedimiento, Datacenter1 contiene el Grupo1, y el Grupo1 ha fallado. Está conmutando los errores en el Grupo2 situado en Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="426ba-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="426ba-108">La mayor parte del trabajo de la conmutación por error del grupo de servidores implica la conmutación por error del almacén de administración central, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="426ba-108">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="426ba-109">Esto es importante porque el almacén de administración central debe ser funcional cuando los usuarios del grupo de servidores se conmutan por error.</span><span class="sxs-lookup"><span data-stu-id="426ba-109">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="426ba-p103">Además, si se produce un error en un grupo de servidores front-end pero el servidor perimetral en dicho sitio todavía se está ejecutando, debe saber si el grupo de servidores perimetrales usa el grupo de servidores con error como el grupo de servidores de próximo salto. Si lo hace, debe cambiar el grupo de servidores perimetrales para que use un grupo de servidores de front-end diferente antes de conmutar por error el grupo de servidores front-end con error. La manera en que cambie la configuración del próximo salto depende de si el servidor perimetral usará un grupo de servidores en el mismo sitio que el grupo de servidores perimetrales, o un sitio diferente.</span><span class="sxs-lookup"><span data-stu-id="426ba-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="426ba-113">**Para establecer un grupo de servidores perimetrales para que usen un grupo de servidores de próximo salto en el mismo sitio**</span><span class="sxs-lookup"><span data-stu-id="426ba-113">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="426ba-114">Abra el generador de topologías, haga clic con el botón secundario en el grupo de servidores perimetrales que se debe cambiar y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="426ba-114">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="426ba-p104">Haga clic en **Próximo salto**. En la lista **Grupo de servidores del próximo salto:**, seleccione el grupo de servidores que servirá ahora como el grupo de servidores de próximo salto.</span><span class="sxs-lookup"><span data-stu-id="426ba-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="426ba-117">Haga clic en **Aceptar** y, a continuación, publique los cambios.</span><span class="sxs-lookup"><span data-stu-id="426ba-117">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="426ba-118">**Para establecer un grupo de servidores perimetrales para que usen un grupo de servidores de próximo salto en un sitio diferente**</span><span class="sxs-lookup"><span data-stu-id="426ba-118">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="426ba-119">Abra una ventana del shell de administración de Lync Server y escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="426ba-119">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="426ba-120">**Para conmutar por error un grupo de servidores en un desastre**</span><span class="sxs-lookup"><span data-stu-id="426ba-120">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="426ba-121">Busque qué grupo de servidores es el host del servidor de administración central; para ello, escriba el siguiente cmdlet en un servidor front-end en Grupo2:</span><span class="sxs-lookup"><span data-stu-id="426ba-121">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="426ba-122">Los resultados de este cmdlet muestran el grupo que hospeda actualmente el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="426ba-122">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="426ba-123">En el resto de este procedimiento, este grupo se conoce como \_ Grupo CMS.</span><span class="sxs-lookup"><span data-stu-id="426ba-123">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="426ba-124">Use el generador de topologías para buscar la versión de Lync Server que se ejecuta en el grupo de servidores CMS \_ .</span><span class="sxs-lookup"><span data-stu-id="426ba-124">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="426ba-125">Si ejecuta Lync Server 2013, use el siguiente cmdlet para encontrar el grupo de copia de seguridad del grupo de servidores 1.</span><span class="sxs-lookup"><span data-stu-id="426ba-125">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="426ba-126">Permita que \_ el grupo de copia de seguridad sea el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="426ba-126">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="426ba-127">Compruebe el estado del almacén de administración central con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="426ba-127">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="426ba-128">Este cmdlet debería mostrar que tanto ActiveMasterFQDN como ActiveFileTransferAgents apuntan al FQDN del grupo de CMS \_ .</span><span class="sxs-lookup"><span data-stu-id="426ba-128">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="426ba-129">Si están vacíos, el servidor de administración central no está disponible y se debe producir un error.</span><span class="sxs-lookup"><span data-stu-id="426ba-129">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="426ba-130">Si el almacén de administración central no está disponible o si el almacén de administración central se estaba ejecutando en Grupo1 (es decir, el grupo de servidores que ha fallado), debe realizar una conmutación por error del servidor de administración central antes de realizar la conmutación por error del grupo.</span><span class="sxs-lookup"><span data-stu-id="426ba-130">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="426ba-131">Si necesita realizar una conmutación por error del servidor de administración central que se hospeda en un grupo de servidores que ejecuta Lync Server 2013, use el cmdlet en el paso 5 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="426ba-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="426ba-132">Si necesita realizar una conmutación por error del servidor de administración central que se hospeda en un grupo de servidores que ejecuta Lync Server 2010, use el cmdlet en el paso 6 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="426ba-132">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="426ba-133">Si no necesita realizar la conmutación por error del servidor de administración central, vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="426ba-133">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="426ba-134">Para conmutar por error el almacén de administración central en un grupo de servidores que ejecute Lync Server 2013, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="426ba-134">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="426ba-135">En primer lugar, compruebe el servidor back-end del grupo de copia de seguridad que \_ ejecuta la instancia principal del almacén de administración central; para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="426ba-135">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="426ba-136">Si el servidor back-end principal del grupo de copia de seguridad \_ es el principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="426ba-136">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="426ba-137">Si el servidor back-end reflejado en el grupo de copia de seguridad \_ es el principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="426ba-137">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="426ba-138">Compruebe que se ha completado la conmutación por error del servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="426ba-138">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="426ba-139">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="426ba-139">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="426ba-140">Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents estén señalando al FQDN del grupo de copia de seguridad \_ .</span><span class="sxs-lookup"><span data-stu-id="426ba-140">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="426ba-141">Por último, compruebe el estado de la réplica para todos los servidores front-end; para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="426ba-141">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="426ba-142">Compruebe que todas las réplicas tengan un valor de True.</span><span class="sxs-lookup"><span data-stu-id="426ba-142">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="426ba-143">Vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="426ba-143">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="426ba-144">Instale el almacén de administración central en el servidor back-end del grupo de copia de seguridad \_ .</span><span class="sxs-lookup"><span data-stu-id="426ba-144">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="426ba-145">En primer lugar, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="426ba-145">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="426ba-146">Ejecute el comando siguiente en uno de los servidores front-end del grupo de copia de seguridad \_ para forzar la transferencia del almacén de administración central:</span><span class="sxs-lookup"><span data-stu-id="426ba-146">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="426ba-147">La validación del movimiento se ha completado:</span><span class="sxs-lookup"><span data-stu-id="426ba-147">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="426ba-148">Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents estén señalando al FQDN del grupo de copia de seguridad \_ .</span><span class="sxs-lookup"><span data-stu-id="426ba-148">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="426ba-149">Compruebe el estado de réplica para todos los servidores front-end escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="426ba-149">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="426ba-150">Compruebe que todas las réplicas tengan un valor de True.</span><span class="sxs-lookup"><span data-stu-id="426ba-150">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="426ba-151">Instale el servicio de servidor de administración central en el resto de los servidores front-end del grupo de copia de seguridad \_ .</span><span class="sxs-lookup"><span data-stu-id="426ba-151">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="426ba-152">Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto el que usó para forzar el movimiento del almacén de administración central anteriormente en este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="426ba-152">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="426ba-153">Conmute por error los usuarios de Grupo1 a grupo2 ejecutando el siguiente cmdlet en una ventana del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="426ba-153">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="426ba-154">Debido a que los pasos realizados en las partes anteriores de este procedimiento para comprobar el estado del almacén de administración central no son universales, todavía existe la posibilidad de que se produzca un error en el cmdlet porque el almacén de administración central aún no ha conmutado por error.</span><span class="sxs-lookup"><span data-stu-id="426ba-154">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="426ba-155">En este caso, debe corregir el almacén de administración central en función de los mensajes de error que aparecen y, a continuación, volver a ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="426ba-155">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="426ba-p112">Si ve el siguiente mensaje de error, tiene que cambiar el grupo de servidores perimetrales en este sitio para que use un grupo de servidores diferente al del próximo salto antes de conmutar por error el grupo de servidores. Para obtener detalles, vea los procedimientos al comienzo de este tema.</span><span class="sxs-lookup"><span data-stu-id="426ba-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

