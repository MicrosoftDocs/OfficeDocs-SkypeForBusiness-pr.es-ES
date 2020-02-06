---
title: Conmutar por error y conmutar por recuperación un grupo
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: d5409441336ef2af8bbe9c6a39530584a167ec05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818211"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="b4072-103">Conmutación por error y reversión de un grupo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b4072-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="b4072-104">Use los procedimientos siguientes si un único grupo de servidores front-end ha fallado y necesita conmutar por error, o el grupo que experimentó el desastre está de nuevo en línea y necesita restaurar la implementación a un estado de funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="b4072-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="b4072-105">También puede obtener información sobre la conmutación por error y la conmutación por error del grupo perimetral usado para la Federación de Skype empresarial o la Federación XMPP, o cambiar el grupo perimetral asociado a un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="b4072-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="b4072-106">Conmutación por error de un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="b4072-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="b4072-107">Devolver un grupo por error</span><span class="sxs-lookup"><span data-stu-id="b4072-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="b4072-108">Conmutación por error del grupo perimetral usado para la Federación de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b4072-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="b4072-109">Conmutación por error del grupo perimetral usado para la Federación de XMPP en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b4072-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="b4072-110">Conmutación por error del grupo perimetral usado para la Federación de Skype empresarial Server o con la Federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="b4072-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="b4072-111">Cambiar el grupo perimetral asociado a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="b4072-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="b4072-112">Conmutación por error de un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="b4072-112">Fail over a Front End pool</span></span>

<span data-ttu-id="b4072-113">En este procedimiento, Datacenter1 contiene Pool1 y Pool1 ha fallado.</span><span class="sxs-lookup"><span data-stu-id="b4072-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="b4072-114">Está conmutando por error a Pool2 que se encuentra en Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="b4072-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="b4072-115">La mayor parte del trabajo para la conmutación por error del grupo incluye la conmutación por error del almacén de administración central, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b4072-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="b4072-116">Esto es importante porque el almacén central de administración debe funcionar cuando se conmuta por error los usuarios del grupo.</span><span class="sxs-lookup"><span data-stu-id="b4072-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="b4072-117">Además, si se produce un error en un grupo de servidores front-end pero el grupo Edge de ese sitio aún se está ejecutando, debe saber si el grupo Edge usa el grupo erróneo como grupo de saltos próximos.</span><span class="sxs-lookup"><span data-stu-id="b4072-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="b4072-118">Si es así, debe cambiar el grupo de límites para usar un grupo de servidores front end diferente antes de la conmutación por error del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="b4072-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="b4072-119">La forma de cambiar la configuración del próximo salto depende de si el borde usará un grupo en el mismo sitio que el grupo de bordes o un sitio diferente.</span><span class="sxs-lookup"><span data-stu-id="b4072-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="b4072-120">**Para establecer que un grupo de servidores Perimetrals use un grupo de próximos saltos en el mismo sitio**</span><span class="sxs-lookup"><span data-stu-id="b4072-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="b4072-121">Abra el generador de topologías, haga clic con el botón secundario en el grupo perimetral que necesita cambiar y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b4072-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="b4072-122">Haga clic en **próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="b4072-122">Click **Next Hop**.</span></span> <span data-ttu-id="b4072-123">En la lista **grupo de próximos saltos:** , seleccione el grupo que servirá ahora como el grupo de próximos saltos.</span><span class="sxs-lookup"><span data-stu-id="b4072-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="b4072-124">Haga clic en **Aceptar**y, a continuación, publique los cambios.</span><span class="sxs-lookup"><span data-stu-id="b4072-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="b4072-125">**Para establecer que un grupo de servidores Perimetrals use un grupo de próximos saltos en otro sitio**</span><span class="sxs-lookup"><span data-stu-id="b4072-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="b4072-126">Abra una ventana del shell de administración de Skype empresarial Server y escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b4072-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="b4072-127">**Para conmutar por error un grupo en un desastre**</span><span class="sxs-lookup"><span data-stu-id="b4072-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="b4072-128">Busque el grupo que es el host para el servidor de administración central escribiendo el siguiente cmdlet en un servidor front-end en Pool2:</span><span class="sxs-lookup"><span data-stu-id="b4072-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="b4072-129">El resultado de este cmdlet muestra el grupo que hospeda actualmente el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="b4072-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="b4072-130">En el resto de este procedimiento, este grupo se conoce como grupo\_CMS.</span><span class="sxs-lookup"><span data-stu-id="b4072-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="b4072-131">Use el generador de topologías para buscar la versión de Skype empresarial Server que se ejecuta\_en el grupo de CMS.</span><span class="sxs-lookup"><span data-stu-id="b4072-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="b4072-132">Si está ejecutando Skype empresarial Server, use el siguiente cmdlet para buscar el grupo de copias de seguridad del grupo 1.</span><span class="sxs-lookup"><span data-stu-id="b4072-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="b4072-133">Permitir que\_el grupo de copia de seguridad sea el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b4072-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="b4072-134">Compruebe el estado del almacén de administración central con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b4072-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="b4072-135">Este cmdlet debe mostrar que tanto ActiveMasterFQDN como ActiveFileTransferAgents apuntan al FQDN del grupo de\_servidores CMS.</span><span class="sxs-lookup"><span data-stu-id="b4072-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="b4072-136">Si están vacíos, el servidor de administración central no está disponible y debe conmutarlo por error.</span><span class="sxs-lookup"><span data-stu-id="b4072-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="b4072-137">Si el almacén central de administración no está disponible o si el almacén de administración central se estaba ejecutando en Pool1 (es decir, el grupo que falló), debe realizar la conmutación por error del servidor de administración central antes de realizar la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b4072-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="b4072-138">Si necesita migrar por error el servidor de administración central que se ha hospedado en un grupo de servidores que ejecutan Skype empresarial Server, use el cmdlet del paso 5 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b4072-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="b4072-139">Si no necesita realizar la conmutación por error del servidor de administración central, vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b4072-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="b4072-140">Para conmutar por error el almacén de administración central en un grupo que ejecute Skype empresarial Server, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4072-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="b4072-141">En primer lugar, compruebe qué servidor back-\_end del grupo de copia de seguridad ejecuta la instancia principal del almacén central de administración; para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4072-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="b4072-142">Si el servidor back-end principal del\_grupo de copias de seguridad es el principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="b4072-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="b4072-143">Si el servidor de back-end de\_duplicación de la copia de seguridad es el principal, escriba:</span><span class="sxs-lookup"><span data-stu-id="b4072-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="b4072-144">Valide que la conmutación por error del servidor de administración central se haya completado.</span><span class="sxs-lookup"><span data-stu-id="b4072-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="b4072-145">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4072-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="b4072-146">Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents apunten al FQDN del grupo de\_copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b4072-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="b4072-147">Por último, compruebe el estado de la réplica de todos los servidores front-end escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4072-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="b4072-148">Compruebe que todas las réplicas tengan el valor true.</span><span class="sxs-lookup"><span data-stu-id="b4072-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="b4072-149">Vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b4072-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="b4072-150">Instale el almacén central de administración en el servidor back-end\_del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b4072-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="b4072-151">En primer lugar, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b4072-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="b4072-152">Ejecute el comando siguiente en uno de los servidores front-end del\_grupo de copia de seguridad para forzar el movimiento del almacén de administración central:</span><span class="sxs-lookup"><span data-stu-id="b4072-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="b4072-153">Valide que el movimiento se haya completado:</span><span class="sxs-lookup"><span data-stu-id="b4072-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="b4072-154">Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents apunten al FQDN del grupo de\_copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b4072-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="b4072-155">Para comprobar el estado de la réplica de todos los servidores front-end, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4072-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="b4072-156">Compruebe que todas las réplicas tengan el valor true.</span><span class="sxs-lookup"><span data-stu-id="b4072-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="b4072-157">Instale el servicio de servidor de administración central en el resto de los servidores Front-\_end del grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b4072-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="b4072-158">Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto el que usó para forzar el movimiento del almacén de administración central anteriormente en este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b4072-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="b4072-159">Realice la conmutación por error a los usuarios de Pool1 a Pool2 ejecutando el cmdlet siguiente en una ventana del shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="b4072-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="b4072-160">Puesto que los pasos que se han realizado en las partes anteriores de este procedimiento para comprobar el estado de la tienda de administración central no son universales, todavía existe la posibilidad de que este cmdlet falle porque el almacén de administración central aún no se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4072-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="b4072-161">En este caso, debe corregir el almacén de administración central en función de los mensajes de error que ve y, a continuación, volver a ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b4072-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="b4072-162">Si ve el siguiente mensaje de error, debe cambiar el grupo de bordes de este sitio para que use una agrupación diferente como el próximo salto antes de que se produzca un error en el grupo.</span><span class="sxs-lookup"><span data-stu-id="b4072-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="b4072-163">Para obtener más información, consulte los procedimientos que se describen al principio de este tema.</span><span class="sxs-lookup"><span data-stu-id="b4072-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="b4072-164">Devolver un grupo por error</span><span class="sxs-lookup"><span data-stu-id="b4072-164">Fail back a pool</span></span>

<span data-ttu-id="b4072-165">Después de que el grupo que experimentó el desastre vuelva a estar conectado (es decir, Pool1 en este ejemplo), siga estos pasos para restaurar la implementación a su estado de funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="b4072-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="b4072-166">Tenga en cuenta que el proceso de recuperación tras error tarda varios minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="b4072-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="b4072-167">Como referencia, se espera que tarde 60 minutos como máximo para un grupo de 20 000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="b4072-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="b4072-168">Conmutar por error a los usuarios que originalmente se encontraban en Pool1 y se ha producido un error en Pool2 escribiendo el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b4072-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="b4072-169">No es necesario realizar ningún otro paso.</span><span class="sxs-lookup"><span data-stu-id="b4072-169">No other steps are necessary.</span></span> <span data-ttu-id="b4072-170">Si se ha producido un error en el servidor de administración central, puede dejarlo en Pool2.</span><span class="sxs-lookup"><span data-stu-id="b4072-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="b4072-171">Conmutación por error del grupo perimetral usado para la Federación de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b4072-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="b4072-172">Si el grupo perimetral en el que tiene la Federación de Skype empresarial Server está desactivada, debe cambiar la Federación para usar un grupo de borde diferente para que la Federación funcione.</span><span class="sxs-lookup"><span data-stu-id="b4072-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="b4072-173">En un servidor front-end, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="b4072-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="b4072-174">Expanda **agrupaciones perimetrales**y, a continuación, haga clic con el botón derecho en el servidor perimetral o en el grupo de servidores perimetrales actualmente configurados para la Federación.</span><span class="sxs-lookup"><span data-stu-id="b4072-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="b4072-175">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b4072-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="b4072-176">En **Editar propiedades** , en **General**, desactive **Habilitar Federación para este grupo perimetral (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="b4072-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="b4072-177">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-177">Click **OK**.</span></span>

3.  <span data-ttu-id="b4072-178">Expanda **agrupaciones perimetrales**y, a continuación, haga clic con el botón derecho en el grupo de servidores perimetrales o perimetrales que desea usar para la Federación.</span><span class="sxs-lookup"><span data-stu-id="b4072-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="b4072-179">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b4072-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="b4072-180">En **propiedades de edición** , en **General**, seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="b4072-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="b4072-181">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-181">Click **OK**.</span></span>

5.  <span data-ttu-id="b4072-182">Haga clic en **acción**, seleccione **topología**, seleccione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="b4072-183">Cuando se le solicite al **publicar la topología**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b4072-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="b4072-184">Una vez finalizada la publicación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="b4072-185">En el servidor perimetral, abra el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b4072-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="b4072-186">Haga clic en **instalar o actualizar el sistema de Skype empresarial Server**y, a continuación, haga clic en **configurar o quitar los componentes de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="b4072-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="b4072-187">**Vuelva a**hacer clic en ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b4072-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="b4072-188">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b4072-188">Click **Next**.</span></span> <span data-ttu-id="b4072-189">La pantalla resumen mostrará las acciones a medida que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="b4072-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="b4072-190">Una vez que haya finalizado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4072-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="b4072-191">Haga clic en **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="b4072-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="b4072-192">Si el sitio que contiene el grupo perimetral con error contiene servidores front-end que aún se están ejecutando, debe actualizar el servicio de conferencias web y el servicio de conferencia A/V en estos grupos front-end para usar un grupo perimetral en un sitio remoto que aún se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="b4072-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="b4072-193">Conmutación por error del grupo perimetral usado para la Federación de XMPP en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b4072-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="b4072-194">En su organización, hay un grupo perimetral designado como grupo para usar en la Federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="b4072-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="b4072-195">Si este grupo deja de funcionar, debe conmutar por error la Federación XMPP para usar un grupo de servidores perimetrales diferente antes de que la Federación XMPP pueda volver a funcionar.</span><span class="sxs-lookup"><span data-stu-id="b4072-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="b4072-196">La primera vez que instala agrupaciones de límites y habilita la Federación de XMPP, puede simplificar el proceso de recuperación ante desastres configurando registros SRV de DNS para todos los grupos de borde para la Federación de XMPP, en lugar de solo uno.</span><span class="sxs-lookup"><span data-stu-id="b4072-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="b4072-197">Cada uno de estos registros SRV debe tener un conjunto de prioridades diferente.</span><span class="sxs-lookup"><span data-stu-id="b4072-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="b4072-198">Todo el tráfico de Federación XMPP pasa por el grupo con el registro SRV con la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="b4072-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="b4072-199">En el procedimiento siguiente, EdgePool1 es el grupo que originalmente contenía la Federación de XMPP y EdgePool2 es el grupo que ahora hospedará la Federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="b4072-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="b4072-200">Para conmutar por error el grupo perimetral usado para la Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="b4072-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="b4072-201">Si aún no tiene otra agrupación perimetral implementada (aparte de la que actualmente está desactivada), implemente ese grupo.</span><span class="sxs-lookup"><span data-stu-id="b4072-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="b4072-202">En cada servidor perimetral en el nuevo grupo de límites que ahora hospede la Federación XMPP (EdgePool2), ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b4072-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="b4072-203">Ejecute el cmdlet siguiente para redirigir la ruta de Federación de XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="b4072-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="b4072-204">En este ejemplo, Site2 es el sitio que contiene el grupo Edge que ahora hospedará la ruta de Federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="b4072-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="b4072-205">En el servidor DNS externo, cambie el registro A de DNS para la Federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b4072-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="b4072-206">Si todavía no tiene un registro SRV de DNS para la Federación de XMPP, que se resuelve en el grupo Edge que ahora hospedará la Federación XMPP, debe agregarlo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b4072-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="b4072-207">Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="b4072-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="b4072-208">Verifique que el grupo de servidores perimetrales que ahora hospeda la Federación XMPP tenga el puerto 5269 abierto externamente.</span><span class="sxs-lookup"><span data-stu-id="b4072-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="b4072-209">Inicie los servicios en todos los servidores perimetrales del grupo perimetral que ahora hospedarán la Federación de XMPP:</span><span class="sxs-lookup"><span data-stu-id="b4072-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="b4072-210">Conmutación por error del grupo perimetral usado para la Federación de Skype empresarial Server o con la Federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="b4072-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="b4072-211">Después de que se haya vuelto a conectar un grupo perimetral que usó para hospedar la Federación, use este procedimiento para recuperar la ruta de Federación de Skype empresarial Server y/o la ruta de Federación de XMPP para volver a usar este grupo de Edge restaurado.</span><span class="sxs-lookup"><span data-stu-id="b4072-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="b4072-212">En el grupo Edge que ya está disponible de nuevo, inicie los servicios de Edge.</span><span class="sxs-lookup"><span data-stu-id="b4072-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="b4072-213">Si desea recuperar la conmutación por recuperación de la ruta de Federación de Skype empresarial Server para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4072-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b4072-214">En un servidor front-end, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="b4072-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="b4072-215">Expanda **agrupaciones perimetrales**y haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales actualmente configurados para la Federación.</span><span class="sxs-lookup"><span data-stu-id="b4072-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="b4072-216">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b4072-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b4072-217">En **Editar propiedades** , en **General**, desactive **Habilitar Federación para este grupo perimetral (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="b4072-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="b4072-218">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="b4072-219">Expanda **agrupaciones perimetrales**y, a continuación, haga clic con el botón secundario en el servidor perimetral original o en el grupo de servidores perimetrales que desea usar de nuevo para la Federación.</span><span class="sxs-lookup"><span data-stu-id="b4072-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="b4072-220">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b4072-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b4072-221">En **propiedades de edición** , en **General**, seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="b4072-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="b4072-222">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="b4072-223">Haga clic en **acción**, seleccione **topología**, seleccione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="b4072-224">Cuando se le solicite al **publicar la topología**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b4072-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="b4072-225">Una vez finalizada la publicación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="b4072-226">En el servidor perimetral, abra el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b4072-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="b4072-227">Haga clic en **instalar o actualizar el sistema de Skype empresarial Server**y, a continuación, haga clic en **configurar o quitar los componentes de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="b4072-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="b4072-228">**Vuelva a**hacer clic en ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b4072-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="b4072-229">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b4072-229">Click **Next**.</span></span> <span data-ttu-id="b4072-230">La pantalla resumen mostrará las acciones a medida que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="b4072-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="b4072-231">Una vez que haya finalizado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4072-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="b4072-232">Haga clic en **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="b4072-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="b4072-233">Si desea recuperar la conmutación por recuperación de la ruta de Federación de XMPP para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4072-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b4072-234">Ejecute el siguiente cmdlet para redirigir la ruta de Federación de XMPP al conjunto de servidores perimetrales que ahora hospedan la Federación XMPP (en este ejemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="b4072-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="b4072-235">En este ejemplo, Sitio1 es el sitio que contiene el grupo Edge que ahora hospedará la ruta de Federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="b4072-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="b4072-236">Si todavía no tiene un registro SRV de DNS para la Federación de XMPP, que se resuelve en el grupo Edge que ahora hospedará la Federación XMPP, debe agregarlo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b4072-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="b4072-237">Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="b4072-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="b4072-238">En el servidor DNS externo, cambie el registro A de DNS para la Federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b4072-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="b4072-239">Verifique que el grupo de servidores perimetrales que ahora hospeda la Federación XMPP tenga el puerto 5269 abierto externamente.</span><span class="sxs-lookup"><span data-stu-id="b4072-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="b4072-240">Si las agrupaciones front-end permanecieron ejecutándose en el sitio que contiene el grupo perimetral que falló y se han restaurado, debe actualizar el servicio de conferencias web y el servicio de conferencia A/V en estos grupos de aplicaciones para el usuario de nuevo para usar los grupos perimetrales en su sitio local.</span><span class="sxs-lookup"><span data-stu-id="b4072-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="b4072-241">Si el grupo de servidores front-end en el mismo sitio que el grupo perimetral con errores también ha fallado, ahora puede usar Invoke-CsPoolFailback para recuperar el repositorio front-end.</span><span class="sxs-lookup"><span data-stu-id="b4072-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="b4072-242">Cambiar el grupo perimetral asociado a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="b4072-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="b4072-243">Si un grupo de servidores perimetrales deja de funcionar pero el grupo de servidores front-end en el mismo sitio aún se está ejecutando, tendrá que configurar el grupo de servidores front-end para que use un grupo de límites en un sitio diferente hasta que se restaure el grupo perimetral con error.</span><span class="sxs-lookup"><span data-stu-id="b4072-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="b4072-244">En el generador de topología, vaya al nombre del grupo de servidores front-end que necesita cambiar.</span><span class="sxs-lookup"><span data-stu-id="b4072-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="b4072-245">Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b4072-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="b4072-246">En la sección **asociaciones** , en **asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="b4072-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="b4072-247">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b4072-247">Click **OK**.</span></span>
