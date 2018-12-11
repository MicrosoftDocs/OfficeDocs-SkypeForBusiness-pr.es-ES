---
title: Con errores más y a falta de vuelta a un grupo de servidores
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 23b70817ba75f3a0a6e73cc42a9df9026e17b2d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223510"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="4191f-103">Con errores más y a falta de vuelta un grupo de servidores en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4191f-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="4191f-104">Use los procedimientos siguientes si ha generado un error en un único grupo de servidores Front-End y las necesidades de conmutación por error, o el grupo que experimentó el desastre es nuevo en línea y necesita restaurar su implementación al estado de funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="4191f-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="4191f-105">También Obtenga información sobre cómo conmutar por error y conmutar por recuperación del grupo perimetral usado para Skype para la federación de negocio o la federación XMPP o cambiar el grupo de servidores perimetrales asociado con un grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="4191f-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="4191f-106">Conmutar por error un grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="4191f-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="4191f-107">Conmutar por un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="4191f-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="4191f-108">Conmutar por error el grupo de servidores perimetrales para Skype para la federación de Business Server</span><span class="sxs-lookup"><span data-stu-id="4191f-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="4191f-109">Conmutar por error el grupo de servidores perimetrales para la federación XMPP en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4191f-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="4191f-110">Conmutar por recuperación del grupo perimetral usado para Skype para la federación de Business Server o la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="4191f-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="4191f-111">Cambiar el grupo de servidores perimetrales asociado con un grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="4191f-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="4191f-112">Conmutar por error un grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="4191f-112">Fail over a Front End pool</span></span>

<span data-ttu-id="4191f-113">En este procedimiento, Datacenter1 contiene grupo1 y grupo1 ha generado un error.</span><span class="sxs-lookup"><span data-stu-id="4191f-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="4191f-114">Se conmuta a grupo2 que se encuentra en Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="4191f-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="4191f-115">La mayoría del trabajo para el grupo de servidores de conmutación por error implica la conmutación en el almacén de Administración Central, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4191f-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="4191f-116">Esto es importante porque el almacén de Administración Central debe ser funcional cuando los usuarios del grupo de servidores se conmutan por error.</span><span class="sxs-lookup"><span data-stu-id="4191f-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="4191f-117">Además, si se produce un error en un grupo de servidores Front-End, pero todavía se está ejecutando el grupo de servidores perimetrales en ese sitio, es necesario saber si el grupo de servidores perimetrales utiliza el grupo de servidores con error como un grupo del próximo salto.</span><span class="sxs-lookup"><span data-stu-id="4191f-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="4191f-118">Si es así, debe cambiar el grupo de servidores perimetrales para utilizar un grupo de servidores Front-End diferente antes de dar error sobre el grupo de servidores Front-End con errores.</span><span class="sxs-lookup"><span data-stu-id="4191f-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="4191f-119">Cómo cambiar la configuración de salto siguiente depende de si el borde usará un grupo de servidores en el mismo sitio que el grupo de servidores perimetrales, o en un sitio diferente.</span><span class="sxs-lookup"><span data-stu-id="4191f-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="4191f-120">**Para establecer un grupo de servidores perimetrales para usar un grupo del próximo salto en el mismo sitio**</span><span class="sxs-lookup"><span data-stu-id="4191f-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="4191f-121">Abra el generador, haga clic en el grupo de servidores perimetrales que debe cambiarse y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4191f-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="4191f-122">Haga clic en **próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="4191f-122">Click **Next Hop**.</span></span> <span data-ttu-id="4191f-123">Desde el **del próximo salto del grupo:** de lista, seleccione el grupo que ahora servirá como el próximo salto.</span><span class="sxs-lookup"><span data-stu-id="4191f-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="4191f-124">Haga clic en **Aceptar**y, a continuación, publique los cambios.</span><span class="sxs-lookup"><span data-stu-id="4191f-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="4191f-125">**Para establecer un grupo de servidores perimetrales para usar un grupo del próximo salto en un sitio diferente**</span><span class="sxs-lookup"><span data-stu-id="4191f-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="4191f-126">Abra un Skype para la ventana de Shell de administración de servidor empresarial y escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4191f-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="4191f-127">**Para conmutar por error un grupo de servidores en un desastre**</span><span class="sxs-lookup"><span data-stu-id="4191f-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="4191f-128">Busque qué grupo es el host para el servidor de Administración Central escribiendo el siguiente cmdlet en un servidor Front-End en el grupo2:</span><span class="sxs-lookup"><span data-stu-id="4191f-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="4191f-129">Los resultados de esta presentación de cmdlet qué grupo actualmente hospeda el servidor de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="4191f-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="4191f-130">En el resto de este procedimiento, este grupo de servidores se conoce como CMS\_grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="4191f-131">Usar el generador de topología para buscar la versión de Skype para Business Server que se ejecutan en el CMS\_grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="4191f-132">Si se está ejecutando Skype para Business Server, use el siguiente cmdlet para buscar el grupo de copia de seguridad del grupo de servidores 1.</span><span class="sxs-lookup"><span data-stu-id="4191f-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="4191f-133">Permitir que la copia de seguridad\_grupo de ser el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4191f-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="4191f-134">Compruebe el estado del almacén de Administración Central con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4191f-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="4191f-135">Este cmdlet se debe mostrar que ActiveMasterFQDN y activefiletransferagents apunten señalen al FQDN de CMS\_grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="4191f-136">Si están vacíos, el servidor de Administración Central no está disponible y deberá conmutar.</span><span class="sxs-lookup"><span data-stu-id="4191f-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="4191f-137">Si el almacén de Administración Central no está disponible o si el almacén de Administración Central se estaba ejecutando en el grupo1 (es decir, el grupo de servidores que ha generado un error), deberá conmutar el servidor de Administración Central antes de dar error el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="4191f-138">Si necesita conmutar por error el servidor de Administración Central que se hospedan en un grupo de servidores que ejecuta Skype para Business Server, use el cmdlet en el paso 5 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4191f-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="4191f-139">Si no es necesario conmutar por error el servidor de Administración Central, vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4191f-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="4191f-140">Para conmutar por error el almacén de Administración Central en un grupo de servidores que ejecuta Skype para Business Server, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4191f-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="4191f-141">En primer lugar, compruebe qué servidor Back-End en copia de seguridad\_grupo de servidores ejecuta la instancia de entidad de seguridad del almacén de Administración Central, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4191f-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="4191f-142">Si el principal servidor Back-End en copia de seguridad\_grupo de servidores es el tipo de entidad de seguridad,:</span><span class="sxs-lookup"><span data-stu-id="4191f-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="4191f-143">Si el servidor Back-End en copia de seguridad de reflejo\_grupo de servidores es el tipo de entidad de seguridad,:</span><span class="sxs-lookup"><span data-stu-id="4191f-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="4191f-144">Validar que el servidor de Administración Central de conmutación por error está completa.</span><span class="sxs-lookup"><span data-stu-id="4191f-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="4191f-145">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4191f-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="4191f-146">Compruebe que el nombre de dominio completo de copia de seguridad se ActiveMasterFQDN y activefiletransferagents apunten\_grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="4191f-147">Por último, compruebe el estado de réplica para todos los servidores Front-End escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4191f-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="4191f-148">Compruebe que todas las réplicas tengan un valor de True.</span><span class="sxs-lookup"><span data-stu-id="4191f-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="4191f-149">Vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4191f-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="4191f-150">Instalar el almacén de Administración Central en el Back End Server de copia de seguridad\_grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="4191f-151">En primer lugar, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4191f-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="4191f-152">Ejecute el comando siguiente en uno de los Front-End los servidores de copia de seguridad\_grupo de servidores para forzar el desplazamiento del almacén de Administración Central:</span><span class="sxs-lookup"><span data-stu-id="4191f-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="4191f-153">Validar el movimiento es completado:</span><span class="sxs-lookup"><span data-stu-id="4191f-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="4191f-154">Compruebe que el nombre de dominio completo de copia de seguridad se ActiveMasterFQDN y activefiletransferagents apunten\_grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="4191f-155">Compruebe el estado de réplica para todos los servidores Front-End escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4191f-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="4191f-156">Compruebe que todas las réplicas tengan un valor de True.</span><span class="sxs-lookup"><span data-stu-id="4191f-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="4191f-157">Instalar el servicio de servidor de Administración Central en el resto de los servidores Front-End en copia de seguridad\_grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="4191f-158">Para ello, ejecute el comando siguiente en todos los servidores Front-End, excepto el utilizado para forzar la Administración Central se mueva almacén anteriormente en este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="4191f-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="4191f-159">Conmutación por error los usuarios del Grupo1 al grupo2 ejecutando el siguiente cmdlet en un Skype para la ventana de Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="4191f-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="4191f-160">Debido a que los pasos realizados en los elementos anteriores de este procedimiento para comprobar el estado del almacén de Administración Central no son universales, sigue siendo una oportunidad de que este cmdlet se producirá un error debido a que el almacén de Administración Central no se aún totalmente conmuta por error.</span><span class="sxs-lookup"><span data-stu-id="4191f-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="4191f-161">En este caso, debe corregir el almacén de Administración Central en función de los mensajes de error que aparecen y, a continuación, vuelva a ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4191f-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="4191f-162">Si ve el mensaje de error siguiente, debe cambiar el grupo de servidores perimetrales en este sitio para utilizar un grupo de servidores diferente como su próximo salto antes de dar error sobre el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4191f-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="4191f-163">Para obtener información detallada, vea los procedimientos al principio de este tema.</span><span class="sxs-lookup"><span data-stu-id="4191f-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="4191f-164">Conmutar por un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="4191f-164">Fail back a pool</span></span>

<span data-ttu-id="4191f-165">Después de que el grupo que experimentó el desastre es nuevo en línea (es decir, el grupo1 en este ejemplo), siga estos pasos para restaurar su implementación al estado de funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="4191f-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="4191f-166">Tenga en cuenta que el proceso de la conmutación por recuperación tarda varios minutos para llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="4191f-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="4191f-167">Como referencia, se espera que tarde 60 minutos como máximo para un grupo de 20 000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="4191f-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="4191f-168">Conmutar por recuperación los usuarios que estaban hospedados originalmente en el grupo1 y han sido conmuta por error al grupo2 escribiendo el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4191f-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="4191f-169">No hay otros pasos son necesarios.</span><span class="sxs-lookup"><span data-stu-id="4191f-169">No other steps are necessary.</span></span> <span data-ttu-id="4191f-170">Si no se pudo a través del servidor de Administración Central, puede dejar en el grupo2.</span><span class="sxs-lookup"><span data-stu-id="4191f-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="4191f-171">Conmutar por error el grupo de servidores perimetrales para Skype para la federación de Business Server</span><span class="sxs-lookup"><span data-stu-id="4191f-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="4191f-172">Si el grupo de servidores perimetrales donde tenga Skype para configurado la federación de Business Server deja de funcionar, debe cambiar la federación para usar un grupo de servidores perimetrales diferente para la federación para que funcione.</span><span class="sxs-lookup"><span data-stu-id="4191f-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="4191f-173">En un servidor Front-End, abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="4191f-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="4191f-174">Expanda **grupos de servidores perimetrales**y, a continuación, haga clic en el servidor perimetral o grupo de servidores perimetrales que actualmente está configurado para la federación.</span><span class="sxs-lookup"><span data-stu-id="4191f-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="4191f-175">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4191f-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="4191f-176">En **Editar propiedades** en **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4191f-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="4191f-177">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-177">Click **OK**.</span></span>

3.  <span data-ttu-id="4191f-178">Expanda **grupos de servidores perimetrales**y, a continuación, haga clic en el servidor perimetral o grupo de servidores perimetrales que ahora desea usar para la federación.</span><span class="sxs-lookup"><span data-stu-id="4191f-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="4191f-179">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4191f-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="4191f-180">En **Editar propiedades** en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4191f-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="4191f-181">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-181">Click **OK**.</span></span>

5.  <span data-ttu-id="4191f-182">Haga clic en **acción**, seleccione la **topología**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="4191f-183">Cuando se le solicite en **publicar la topología**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4191f-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="4191f-184">Cuando finalice la publicación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="4191f-185">En el servidor perimetral, abra el Skype para el Asistente para la implementación de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4191f-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="4191f-186">Haga clic en **instalar o actualización de Skype para Business Server System**y, a continuación, haga clic en **el programa de instalación o quitar Skype para los componentes de servidor empresariales**.</span><span class="sxs-lookup"><span data-stu-id="4191f-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="4191f-187">Haga clic en **volver a ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="4191f-188">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4191f-188">Click **Next**.</span></span> <span data-ttu-id="4191f-189">La pantalla de resumen mostrará acciones cuando se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="4191f-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="4191f-190">Una vez que se realiza la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="4191f-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="4191f-191">Haga clic en **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="4191f-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="4191f-192">Si el sitio que contiene el grupo de servidores perimetrales con errores contiene servidores Front-End que todavía se está ejecutando, debe actualizar el servicio de conferencia Web y A / servicio de conferencia A/v en estos grupos de servidores Front-End para usar un grupo de servidores perimetrales en un control remoto de sitios es decir ejecución fija.</span><span class="sxs-lookup"><span data-stu-id="4191f-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="4191f-193">Conmutar por error el grupo de servidores perimetrales para la federación XMPP en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4191f-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="4191f-194">En la organización, hay un grupo de servidores perimetrales designado como el grupo de servidores que se usará para la federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="4191f-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="4191f-195">Si este grupo de servidores deja de funcionar, deberá conmutar federación XMPP para usar un grupo de servidores perimetrales diferente antes de la federación XMPP puede trabajar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="4191f-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="4191f-196">Cuando en primer lugar instalar grupos de servidores perimetrales y habilitar la federación XMPP, puede simplificar el proceso de recuperación ante desastres mediante la configuración de registros SRV de DNS externos para todos los grupos de servidores perimetrales para la federación XMPP, en lugar de sólo uno.</span><span class="sxs-lookup"><span data-stu-id="4191f-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="4191f-197">Cada uno de estos registros SRV debe tener una prioridad diferente para establecer.</span><span class="sxs-lookup"><span data-stu-id="4191f-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="4191f-198">Todo el tráfico de federación XMPP circula a través del grupo de servidores con el registro SRV con la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="4191f-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="4191f-199">En el procedimiento siguiente, EdgePool1 es el grupo que originalmente la federación XMPP y EdgePool2 es el grupo que alojará ahora la federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="4191f-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="4191f-200">Para conmutar por error el grupo de servidores perimetrales para la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="4191f-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="4191f-201">Si ya no dispone de otro grupo de servidores perimetrales implementado (además de la que actualmente está inactivo), implemente ese grupo.</span><span class="sxs-lookup"><span data-stu-id="4191f-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="4191f-202">En cada servidor perimetral en el nuevo grupo de servidores perimetrales que alojará ahora la federación XMPP (EdgePool2), ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4191f-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="4191f-203">Ejecute el siguiente cmdlet para cambiar la ruta de federación XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="4191f-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="4191f-204">En este ejemplo, Site2 es el sitio que contiene el grupo de servidores perimetrales que alojará ahora la ruta de federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="4191f-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="4191f-205">En el servidor DNS externo, cambie el registro A DNS para la federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4191f-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="4191f-206">Si aún no tiene un registro SRV de DNS para la federación XMPP que se resuelve en el grupo de servidores perimetrales que alojará ahora la federación XMPP, debe agregarlo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4191f-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="4191f-207">Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="4191f-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="4191f-208">Compruebe que el grupo de servidores perimetrales que alojará ahora la federación XMPP tiene abierto el puerto 5269 externamente.</span><span class="sxs-lookup"><span data-stu-id="4191f-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="4191f-209">Iniciar los servicios en todos los servidores perimetrales en el grupo de servidores perimetrales que alojará ahora la federación XMPP:</span><span class="sxs-lookup"><span data-stu-id="4191f-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="4191f-210">Conmutar por recuperación del grupo perimetral usado para Skype para la federación de Business Server o la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="4191f-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="4191f-211">Después de un borde con errores grupo de servidores que usa para la federación de host ha sido puesta en línea, use este procedimiento para conmutar por recuperación la Skype para la ruta de federación Business Server o la ruta de federación XMPP para volver a usar este grupo de servidores perimetrales restaurado.</span><span class="sxs-lookup"><span data-stu-id="4191f-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="4191f-212">En el grupo de servidores perimetrales que ahora esté disponible de nuevo, inicie los Servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="4191f-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="4191f-213">Si desea conmutar por recuperación la Skype para ruta de federación Business Server para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4191f-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="4191f-214">En un servidor Front-End, abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="4191f-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="4191f-215">Expanda **grupos de servidores perimetrales**, a continuación, haga clic en el servidor perimetral o grupo de servidores perimetrales que actualmente está configurado para la federación.</span><span class="sxs-lookup"><span data-stu-id="4191f-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="4191f-216">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4191f-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="4191f-217">En **Editar propiedades** en **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4191f-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="4191f-218">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="4191f-219">Expanda **grupos de servidores perimetrales**, a continuación, haga clic en el servidor perimetral original o el grupo de servidores perimetrales que desea volver a usar para la federación.</span><span class="sxs-lookup"><span data-stu-id="4191f-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="4191f-220">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4191f-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="4191f-221">En **Editar propiedades** en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4191f-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="4191f-222">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="4191f-223">Haga clic en **acción**, seleccione la **topología**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="4191f-224">Cuando se le solicite en **publicar la topología**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4191f-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="4191f-225">Cuando finalice la publicación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="4191f-226">En el servidor perimetral, abra el Skype para el Asistente para la implementación de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4191f-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="4191f-227">Haga clic en **instalar o actualización de Skype para Business Server System**y, a continuación, haga clic en **el programa de instalación o quitar Skype para los componentes de servidor empresariales**.</span><span class="sxs-lookup"><span data-stu-id="4191f-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="4191f-228">Haga clic en **volver a ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="4191f-229">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4191f-229">Click **Next**.</span></span> <span data-ttu-id="4191f-230">La pantalla de resumen mostrará acciones cuando se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="4191f-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="4191f-231">Una vez que se realiza la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="4191f-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="4191f-232">Haga clic en **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="4191f-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="4191f-233">Si desea conmutar por recuperación la ruta de federación XMPP para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4191f-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="4191f-234">Ejecute el siguiente cmdlet para cambiar la ruta de federación XMPP para el grupo de servidores perimetrales que alojará ahora la federación XMPP (en este ejemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="4191f-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="4191f-235">En este ejemplo, sitio1 es el sitio que contiene el grupo de servidores perimetrales que alojará ahora la ruta de federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="4191f-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="4191f-236">Si aún no tiene un registro SRV de DNS para la federación XMPP que se resuelve en el grupo de servidores perimetrales que alojará ahora la federación XMPP, debe agregarlo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4191f-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="4191f-237">Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="4191f-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="4191f-238">En el servidor DNS externo, cambie el registro A DNS para la federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4191f-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="4191f-239">Compruebe que el grupo de servidores perimetrales que alojará ahora la federación XMPP tiene abierto el puerto 5269 externamente.</span><span class="sxs-lookup"><span data-stu-id="4191f-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="4191f-240">Si los grupos de servidores Front-End se mantuvo que se está ejecutando en el sitio que contiene el grupo de servidores perimetrales que errores y se ha restaurado, deberá actualizar el servicio de conferencia Web y A grupos de servicio de conferencia A/v en estos Front-End para volver a usar los grupos de servidores perimetrales en su sitio local.</span><span class="sxs-lookup"><span data-stu-id="4191f-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="4191f-241">Si el grupo de servidores Front-End en el mismo sitio que el grupo de servidores perimetrales con errores también falla, ahora puede usar Invoke – CsPoolFailback para conmutar por recuperación del grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="4191f-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="4191f-242">Cambiar el grupo de servidores perimetrales asociado con un grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="4191f-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="4191f-243">Si un grupo de servidores perimetrales deja de funcionar, pero todavía se está ejecutando el grupo de servidores Front-End en el mismo sitio, debe establecer el grupo de servidores Front-End para usar un grupo de servidores perimetrales en un sitio diferente hasta que se restaura el grupo de servidores perimetrales con errores.</span><span class="sxs-lookup"><span data-stu-id="4191f-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="4191f-244">En el generador, desplácese hasta el nombre del grupo de servidores Front-End que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="4191f-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="4191f-245">Haga clic en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4191f-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4191f-246">En la sección **asociaciones** , en **Asociar grupo de servidores perimetrales (para componentes multimedia)**, utilice el cuadro desplegable para seleccionar el grupo de servidores perimetrales que desea asociar este grupo de servidores Front-End con.</span><span class="sxs-lookup"><span data-stu-id="4191f-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="4191f-247">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4191f-247">Click **OK**.</span></span>