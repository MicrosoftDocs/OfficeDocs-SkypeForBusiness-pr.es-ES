---
title: 'Lync Server 2013: Conmutación por error de un grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="914f8-102">Conmutación por error de un grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="914f8-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="914f8-103">_**Última modificación del tema:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="914f8-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="914f8-104">Si un único grupo de servidores front-end ha fallado y debe realizarse la conmutación por error, use el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="914f8-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="914f8-105">En este procedimiento, Datacenter1 contiene Pool1 y Pool1 ha fallado.</span><span class="sxs-lookup"><span data-stu-id="914f8-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="914f8-106">Está conmutando por error a Pool2 que se encuentra en Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="914f8-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="914f8-107">La mayor parte del trabajo para la conmutación por error del grupo incluye la conmutación por error del almacén de administración central, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="914f8-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="914f8-108">Esto es importante porque el almacén central de administración debe funcionar cuando se conmuta por error los usuarios del grupo.</span><span class="sxs-lookup"><span data-stu-id="914f8-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="914f8-109">Además, si se produce un error en un grupo de servidores front-end pero el grupo Edge de ese sitio aún se está ejecutando, debe saber si el grupo Edge usa el grupo erróneo como grupo de saltos próximos.</span><span class="sxs-lookup"><span data-stu-id="914f8-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="914f8-110">Si es así, debe cambiar el grupo de límites para usar un grupo de servidores front end diferente antes de la conmutación por error del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="914f8-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="914f8-111">La forma de cambiar la configuración del próximo salto depende de si el borde usará un grupo en el mismo sitio que el grupo de bordes o un sitio diferente.</span><span class="sxs-lookup"><span data-stu-id="914f8-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="914f8-112">**Para establecer que un grupo de servidores Perimetrals use un grupo de próximos saltos en el mismo sitio**</span><span class="sxs-lookup"><span data-stu-id="914f8-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="914f8-113">Abra el generador de topologías, haga clic con el botón secundario en el grupo perimetral que necesita cambiar y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="914f8-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="914f8-114">Haga clic en **próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="914f8-114">Click **Next Hop**.</span></span> <span data-ttu-id="914f8-115">En la lista **grupo de próximos saltos:** , seleccione el grupo que servirá ahora como el grupo de próximos saltos.</span><span class="sxs-lookup"><span data-stu-id="914f8-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="914f8-116">Haga clic en **Aceptar**y, a continuación, publique los cambios.</span><span class="sxs-lookup"><span data-stu-id="914f8-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="914f8-117">**Para establecer que un grupo de servidores Perimetrals use un grupo de próximos saltos en otro sitio**</span><span class="sxs-lookup"><span data-stu-id="914f8-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="914f8-118">Abra una ventana del shell de administración de Lync Server y escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="914f8-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="914f8-119">**Para conmutar por error un grupo en un desastre**</span><span class="sxs-lookup"><span data-stu-id="914f8-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="914f8-120">Busque el grupo que es el host para el servidor de administración central escribiendo el siguiente cmdlet en un servidor front-end en Pool2:</span><span class="sxs-lookup"><span data-stu-id="914f8-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="914f8-121">El resultado de este cmdlet muestra el grupo que hospeda actualmente el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="914f8-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="914f8-122">En el resto de este procedimiento, este grupo se conoce como grupo\_CMS.</span><span class="sxs-lookup"><span data-stu-id="914f8-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="914f8-123">Use el generador de topologías para buscar la versión de Lync Server que se\_ejecuta en el grupo de CMS.</span><span class="sxs-lookup"><span data-stu-id="914f8-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="914f8-124">Si está ejecutando Lync Server 2013, use el siguiente cmdlet para buscar el grupo de copias de seguridad del grupo 1.</span><span class="sxs-lookup"><span data-stu-id="914f8-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="914f8-125">Permitir que\_el grupo de copia de seguridad sea el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="914f8-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="914f8-126">Compruebe el estado del almacén de administración central con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="914f8-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="914f8-127">Este cmdlet debe mostrar que tanto ActiveMasterFQDN como ActiveFileTransferAgents apuntan al FQDN del grupo de\_servidores CMS.</span><span class="sxs-lookup"><span data-stu-id="914f8-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="914f8-128">Si están vacíos, el servidor de administración central no está disponible y debe conmutarlo por error.</span><span class="sxs-lookup"><span data-stu-id="914f8-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="914f8-129">Si el almacén central de administración no está disponible o si el almacén de administración central se estaba ejecutando en Pool1 (es decir, el grupo que falló), debe realizar la conmutación por error del servidor de administración central antes de realizar la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="914f8-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="914f8-130">Si necesita conmutar por error el servidor de administración central alojado en un grupo que ejecuta Lync Server 2013, use el cmdlet en el paso 5 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="914f8-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="914f8-131">Si necesita migrar por error el servidor de administración central alojado en un grupo que ejecuta Lync Server 2010, use el cmdlet en el paso 6 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="914f8-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="914f8-132">Si no necesita realizar la conmutación por error del servidor de administración central, vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="914f8-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="914f8-133">Para conmutar por error el almacén de administración central en un grupo que ejecute Lync Server 2013, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="914f8-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="914f8-134">En primer lugar, compruebe qué servidor back-\_end del grupo de copia de seguridad ejecuta la instancia principal del almacén central de administración; para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="914f8-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="914f8-135">Si el servidor back-end principal del\_grupo de copias de seguridad es el principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="914f8-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="914f8-136">Si el servidor de back-end de\_duplicación de la copia de seguridad es el principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="914f8-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="914f8-137">Valide que la conmutación por error del servidor de administración central se haya completado.</span><span class="sxs-lookup"><span data-stu-id="914f8-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="914f8-138">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="914f8-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="914f8-139">Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents apunten al FQDN del grupo de\_copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="914f8-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="914f8-140">Por último, compruebe el estado de la réplica de todos los servidores front-end escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="914f8-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="914f8-141">Compruebe que todas las réplicas tengan el valor true.</span><span class="sxs-lookup"><span data-stu-id="914f8-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="914f8-142">Vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="914f8-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="914f8-143">Instale el almacén central de administración en el servidor back-end\_del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="914f8-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="914f8-144">En primer lugar, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="914f8-144">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="914f8-145">Ejecute el comando siguiente en uno de los servidores front-end del\_grupo de copia de seguridad para forzar el movimiento del almacén de administración central:</span><span class="sxs-lookup"><span data-stu-id="914f8-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="914f8-146">Valide que el movimiento se haya completado:</span><span class="sxs-lookup"><span data-stu-id="914f8-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="914f8-147">Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents apunten al FQDN del grupo de\_copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="914f8-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="914f8-148">Para comprobar el estado de la réplica de todos los servidores front-end, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="914f8-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="914f8-149">Compruebe que todas las réplicas tengan el valor true.</span><span class="sxs-lookup"><span data-stu-id="914f8-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="914f8-150">Instale el servicio de servidor de administración central en el resto de los servidores Front-\_end del grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="914f8-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="914f8-151">Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto el que usó para forzar el movimiento del almacén de administración central anteriormente en este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="914f8-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="914f8-152">Conmutar por error los usuarios de Pool1 a Pool2 ejecutando el cmdlet siguiente en una ventana del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="914f8-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="914f8-153">Puesto que los pasos que se han realizado en las partes anteriores de este procedimiento para comprobar el estado de la tienda de administración central no son universales, todavía existe la posibilidad de que este cmdlet falle porque el almacén de administración central aún no se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="914f8-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="914f8-154">En este caso, debe corregir el almacén de administración central en función de los mensajes de error que ve y, a continuación, volver a ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="914f8-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="914f8-155">Si ve el siguiente mensaje de error, debe cambiar el grupo de bordes de este sitio para que use una agrupación diferente como el próximo salto antes de que se produzca un error en el grupo.</span><span class="sxs-lookup"><span data-stu-id="914f8-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="914f8-156">Para obtener más información, consulte los procedimientos que se describen al principio de este tema.</span><span class="sxs-lookup"><span data-stu-id="914f8-156">For details, see the procedures at the beginning of this topic.</span></span>
    
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

