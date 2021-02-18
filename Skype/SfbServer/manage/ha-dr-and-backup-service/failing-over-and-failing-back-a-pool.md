---
title: Conmutar por error y conmutar por recuperación un grupo
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 547a71f44fa81f9ba12a1c661465c7b8604b3fa1
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278680"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="f1e94-103">Con error y con error de un grupo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f1e94-103">Failing over and failing back a pool in Skype for Business Server</span></span>

<span data-ttu-id="f1e94-104">Use los siguientes procedimientos si un único grupo de servidores de Front-End ha fallado y necesita ser con errores, o si el grupo que experimentó el desastre vuelve a estar en línea y necesita restaurar la implementación a un estado de trabajo normal.</span><span class="sxs-lookup"><span data-stu-id="f1e94-104">Use the following procedures if a single Front-End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="f1e94-105">Learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front-End pool.</span><span class="sxs-lookup"><span data-stu-id="f1e94-105">Learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front-End pool.</span></span>

- [<span data-ttu-id="f1e94-106">Conmutación por error de un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f1e94-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="f1e94-107">Conmutación por recuperación de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="f1e94-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="f1e94-108">Conmutación por error del grupo de servidores perimetrales usado para la federación de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f1e94-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="f1e94-109">Conmutación por error del grupo de servidores perimetrales usado para la federación XMPP en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f1e94-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="f1e94-110">Conmutación por recuperación del grupo de servidores perimetrales usado para la federación de Skype Empresarial Server o la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="f1e94-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="f1e94-111">Cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f1e94-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="f1e94-112">Conmutación por error de un Front-End de servidores</span><span class="sxs-lookup"><span data-stu-id="f1e94-112">Fail over a Front-End pool</span></span>

<span data-ttu-id="f1e94-113">Datacenter1 contiene Pool1 y Pool1 ha fallado.</span><span class="sxs-lookup"><span data-stu-id="f1e94-113">Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="f1e94-114">Está con errores en el Grupo2 ubicado en Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="f1e94-114">You're failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="f1e94-115">La mayor parte del trabajo para la conmutación por error del grupo implica la conmutación por error del almacén de administración central, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f1e94-115">Most of the work for the pool failover involves failing over the Central Management store, if it's required.</span></span> <span data-ttu-id="f1e94-116">El almacén de administración central debe funcionar cuando se haya con errores de los usuarios del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f1e94-116">The Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="f1e94-117">Si se produce un Front-End de servidores perimetrales, pero el grupo de servidores perimetrales de ese sitio aún se está ejecutando, debe saber si el grupo de servidores perimetrales usa el grupo de servidores con errores como grupo de servidores del próximo salto.</span><span class="sxs-lookup"><span data-stu-id="f1e94-117">If a Front-End pool fails, but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="f1e94-118">Si es así, debe cambiar el grupo de servidores perimetrales para que use un grupo de servidores de Front-End diferente antes de la con error Front-End grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f1e94-118">If it does, you must change the Edge pool to use a different Front-End pool before failing over the failed Front-End pool.</span></span> <span data-ttu-id="f1e94-119">La manera en que cambie la configuración del próximo salto depende de si el servidor perimetral usará un grupo de servidores en el mismo sitio que el grupo de servidores perimetrales, o un sitio diferente.</span><span class="sxs-lookup"><span data-stu-id="f1e94-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="f1e94-120">**Para establecer un grupo de servidores perimetrales para que use un grupo de servidores del próximo salto en el mismo sitio**</span><span class="sxs-lookup"><span data-stu-id="f1e94-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1. <span data-ttu-id="f1e94-121">Abra el Generador de topologías, haga clic con el botón secundario en el grupo de servidores perimetrales que debe cambiarse y seleccione **Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="f1e94-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and select **Edit Properties**.</span></span>

2. <span data-ttu-id="f1e94-122">Seleccione **Próximo salto.**</span><span class="sxs-lookup"><span data-stu-id="f1e94-122">Select **Next Hop**.</span></span> <span data-ttu-id="f1e94-123">En la **lista Grupo de servidores del** próximo salto: seleccione el grupo que ahora servirá como grupo de servidores del próximo salto.</span><span class="sxs-lookup"><span data-stu-id="f1e94-123">From the **Next hop pool:** list, select the pool that will now serve as the next hop pool.</span></span>

3. <span data-ttu-id="f1e94-124">Seleccione **Aceptar** y, a continuación, publique los cambios.</span><span class="sxs-lookup"><span data-stu-id="f1e94-124">Select **OK**, and then publish the changes.</span></span>

<span data-ttu-id="f1e94-125">**Para establecer un grupo de servidores perimetrales para usar un grupo de servidores del próximo salto en un sitio diferente**</span><span class="sxs-lookup"><span data-stu-id="f1e94-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1. <span data-ttu-id="f1e94-126">Abra una ventana del Shell de administración de Skype Empresarial Server y escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f1e94-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>

        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="f1e94-127">**Para conmutar por error un grupo de servidores en un desastre**</span><span class="sxs-lookup"><span data-stu-id="f1e94-127">**To fail over a pool in a disaster**</span></span>

1. <span data-ttu-id="f1e94-128">Para buscar el grupo de servidores host para el servidor de administración central, escriba el siguiente cmdlet en un servidor Front-End en el grupo2:</span><span class="sxs-lookup"><span data-stu-id="f1e94-128">Find the host pool for the Central Management Server by typing the following cmdlet on a Front-End server in Pool2:</span></span>

        Invoke-CsManagementServerFailover -Whatif

    <span data-ttu-id="f1e94-129">Los resultados de este cmdlet muestran qué grupo hospeda actualmente el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="f1e94-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="f1e94-130">En el resto de este procedimiento, este grupo se conoce como grupo de \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="f1e94-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2. <span data-ttu-id="f1e94-131">Use topology Builder para encontrar la versión de Skype Empresarial Server que se ejecuta en el grupo de \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="f1e94-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="f1e94-132">Si está ejecutando Skype Empresarial Server, use el siguiente cmdlet para encontrar el grupo de copia de seguridad del grupo 1.</span><span class="sxs-lookup"><span data-stu-id="f1e94-132">If it's running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>

        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>

    <span data-ttu-id="f1e94-133">Permitir que el \_ grupo de copia de seguridad sea el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1e94-133">Let Backup\_Pool be the backup pool.</span></span>

3. <span data-ttu-id="f1e94-134">Compruebe el estado del almacén de administración central con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f1e94-134">Check the status of the Central Management store with the following cmdlet:</span></span>

        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 

    <span data-ttu-id="f1e94-135">Este cmdlet debe mostrar que ActiveMasterFQDN y ActiveFileTransferAgents apuntan al FQDN del grupo de \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="f1e94-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="f1e94-136">Si están vacíos, el servidor de administración central no está disponible y debe conmutar por error.</span><span class="sxs-lookup"><span data-stu-id="f1e94-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="f1e94-137">Si el almacén de administración central no está disponible o si el almacén de administración central se estaba ejecutando en el Grupo1 (es decir, el grupo que ha fallado), debe conmutar por error el servidor de administración central antes de conmutar por error el grupo.</span><span class="sxs-lookup"><span data-stu-id="f1e94-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="f1e94-138">Si necesita conmutar por error el servidor de administración central hospedado en un grupo que ejecuta Skype Empresarial Server, use el cmdlet en el paso 5 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f1e94-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="f1e94-139">Si no necesita conmutar por error el servidor de administración central, vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f1e94-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="f1e94-140">Para conmutar por error el almacén de administración central en un grupo que ejecuta Skype Empresarial Server, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1e94-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>

      - <span data-ttu-id="f1e94-141">En primer lugar, compruebe qué Back-End en el grupo de servidores de copia de seguridad ejecuta la instancia principal del almacén de administración \_ central escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1e94-141">First, check which Back-End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>

            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="f1e94-142">Si el servidor Back-End principal del grupo de copia de \_ seguridad es la entidad de seguridad, escriba:</span><span class="sxs-lookup"><span data-stu-id="f1e94-142">If the primary Back-End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="f1e94-143">Si el servidor reflejado Back-End en el grupo de copia de \_ seguridad es la entidad de seguridad, escriba:</span><span class="sxs-lookup"><span data-stu-id="f1e94-143">If the mirror Back-End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="f1e94-144">Valide que la conmutación por error del servidor de administración central se haya completado.</span><span class="sxs-lookup"><span data-stu-id="f1e94-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="f1e94-145">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f1e94-145">Type the following command:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="f1e94-146">Compruebe que ActiveMasterFQDN y ActiveFileTransferAgents apuntan al FQDN del grupo de servidores de copia de \_ seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1e94-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f1e94-147">Por último, compruebe el estado de la réplica de todos Front-End server escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1e94-147">Finally, check the replica status for all Front-End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="f1e94-148">Compruebe que todas las réplicas tengan un valor de True.</span><span class="sxs-lookup"><span data-stu-id="f1e94-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="f1e94-149">Vaya al paso 7 de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f1e94-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="f1e94-150">Instale el almacén de administración central en el servidor back-end del grupo de copia de \_ seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1e94-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f1e94-151">En primer lugar, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f1e94-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="f1e94-152">Ejecute el siguiente comando en uno de los servidores front-end del grupo de servidores de copia de seguridad para forzar el \_ movimiento del almacén de administración central:</span><span class="sxs-lookup"><span data-stu-id="f1e94-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="f1e94-153">La validación del movimiento se ha completado:</span><span class="sxs-lookup"><span data-stu-id="f1e94-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="f1e94-154">Compruebe que ActiveMasterFQDN y ActiveFileTransferAgents apuntan al FQDN del grupo de servidores de copia de \_ seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1e94-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f1e94-155">Compruebe el estado de réplica para todos los servidores front-end escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1e94-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="f1e94-156">Compruebe que todas las réplicas tengan un valor de True.</span><span class="sxs-lookup"><span data-stu-id="f1e94-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="f1e94-157">Instale el servicio del servidor de administración central en el resto de los servidores front-end del grupo de servidores de \_ copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1e94-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="f1e94-158">Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto el que usó al forzar el movimiento del almacén de administración central anteriormente en este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="f1e94-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="f1e94-159">Conmutación por error de los usuarios del Grupo1 al Grupo2 ejecutando el siguiente cmdlet en una ventana del Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f1e94-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="f1e94-160">Dado que los pasos que se han realizado en las partes anteriores de este procedimiento para comprobar el estado del almacén de administración central no son universales, todavía existe la posibilidad de que este cmdlet falle porque el almacén de administración central aún no ha conmutado por error por completo.</span><span class="sxs-lookup"><span data-stu-id="f1e94-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="f1e94-161">En este caso, debe corregir el almacén de administración central en función de los mensajes de error que ve y, a continuación, volver a ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1e94-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="f1e94-p113">Si ve el siguiente mensaje de error, tiene que cambiar el grupo de servidores perimetrales en este sitio para que use un grupo de servidores diferente al del próximo salto antes de conmutar por error el grupo de servidores. Para obtener detalles, vea los procedimientos al comienzo de este tema.</span><span class="sxs-lookup"><span data-stu-id="f1e94-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="f1e94-164">Conmutación por recuperación de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="f1e94-164">Fail back a pool</span></span>

<span data-ttu-id="f1e94-165">Una vez que el grupo que experimentó el desastre está de nuevo en línea (es decir, el Grupo1 en este ejemplo), siga los pasos siguientes para restaurar su implementación al estado de funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="f1e94-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="f1e94-166">El proceso de conmutación por recuperación tarda varios minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="f1e94-166">The failback process takes several minute to complete.</span></span> <span data-ttu-id="f1e94-167">Como referencia, se espera que tarde hasta 60 minutos para un grupo de 20 000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="f1e94-167">For reference, it's expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="f1e94-168">Realice la recuperación de los usuarios que estaban hospedados originalmente en el Grupo1 y se han conmutado por error al Grupo2 escribiendo el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f1e94-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="f1e94-169">No es necesario realizar otros.</span><span class="sxs-lookup"><span data-stu-id="f1e94-169">No other steps are necessary.</span></span> <span data-ttu-id="f1e94-170">Si ha fallado el servidor de administración central, puede dejarlo en el grupo2.</span><span class="sxs-lookup"><span data-stu-id="f1e94-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="f1e94-171">Conmutación por error del grupo de servidores perimetrales usado para la federación de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f1e94-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="f1e94-172">Si el grupo de servidores perimetrales en el que tiene configurada la federación de Skype Empresarial Server no funciona, debe cambiar la federación para que use un grupo de servidores perimetrales diferente para que funcione la federación.</span><span class="sxs-lookup"><span data-stu-id="f1e94-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="f1e94-173">En un servidor front-end, abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="f1e94-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="f1e94-174">Expanda **grupos de servidores** perimetrales y, a continuación, haga clic con el botón secundario en el servidor perimetral o grupo de servidores perimetrales configurado actualmente para la federación.</span><span class="sxs-lookup"><span data-stu-id="f1e94-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="f1e94-175">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="f1e94-176">En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f1e94-177">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-177">Select **OK**.</span></span>

3.  <span data-ttu-id="f1e94-178">Expanda **grupos de servidores** perimetrales y, a continuación, haga clic con el botón secundario en el servidor perimetral o grupo de servidores perimetrales que ahora desea usar para la federación.</span><span class="sxs-lookup"><span data-stu-id="f1e94-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="f1e94-179">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="f1e94-180">En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f1e94-181">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-181">Select **OK**.</span></span>

5.  <span data-ttu-id="f1e94-182">Seleccione **Acción**, seleccione **Topología,** **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-182">Select **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="f1e94-183">Cuando se le pida **que publique la topología,** seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f1e94-183">When prompted on **Publish the topology**, select **Next**.</span></span> <span data-ttu-id="f1e94-184">Cuando finalice la publicación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-184">When the Publish is finished, select **Finish**.</span></span>

6.  <span data-ttu-id="f1e94-185">En el servidor perimetral, abra el Asistente para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f1e94-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="f1e94-186">Seleccione **Instalar o actualizar el sistema de Skype Empresarial Server** y, a continuación, seleccione Instalar o quitar componentes de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="f1e94-186">Select **Install or Update Skype for Business Server System**, and then select **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="f1e94-187">Seleccione **Ejecutar de nuevo.**</span><span class="sxs-lookup"><span data-stu-id="f1e94-187">Select **Run Again**.</span></span>

7.  <span data-ttu-id="f1e94-188">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-188">Select **Next**.</span></span> <span data-ttu-id="f1e94-189">La pantalla de resumen mostrará las acciones a medida que se ejecuten.</span><span class="sxs-lookup"><span data-stu-id="f1e94-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="f1e94-190">Una vez que haya terminado la implementación, seleccione **Ver registro** para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="f1e94-190">Once the deployment is done, select **View Log** to view available log files.</span></span> <span data-ttu-id="f1e94-191">Seleccione **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="f1e94-191">Select **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="f1e94-192">Si el sitio que contiene el grupo de servidores perimetrales con errores contiene servidores front-end que aún se están ejecutando, debe actualizar el servicio de conferencia web y el servicio de conferencia A/V en estos grupos de servidores de Front-End para usar un grupo de servidores perimetrales en un sitio remoto que aún se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f1e94-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front-End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="f1e94-193">Conmutación por error del grupo de servidores perimetrales usado para la federación XMPP en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f1e94-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="f1e94-p123">En su organización, hay un grupo perimetral designada como el grupo para la federación XMPP. Si este grupo se desactiva, debe conmutar por error la federación XMPP para que use otro grupo perimetral antes de que la federación XMPP pueda volver a trabajar.</span><span class="sxs-lookup"><span data-stu-id="f1e94-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="f1e94-196">Al instalar primero los grupos perimetrales y habilitar la federación XMPP, puede simplificar el proceso de recuperación ante desastres estableciendo registros SRV de DNS externos para todos los grupos perimetrales para la federación XMPP, en lugar de solo uno.</span><span class="sxs-lookup"><span data-stu-id="f1e94-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="f1e94-197">Cada uno de estos registros SRV debe tener establecida una prioridad diferente.</span><span class="sxs-lookup"><span data-stu-id="f1e94-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="f1e94-198">Todo el tráfico de la federación XMPP atraviesa el grupo con el registro SRV con la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="f1e94-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="f1e94-199">En el siguiente procedimiento, EdgePool1 es el grupo de servidores, que originalmente hospedaba la federación XMPP, y EdgePool2 es el grupo que ahora hospedará la federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="f1e94-199">In the following procedure, EdgePool1 is the pool, which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="f1e94-200">Para conmutar por error el grupo de servidores perimetrales usado para la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="f1e94-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="f1e94-201">Si aún no tiene implementado otro grupo de servidores perimetrales (además del que está actualmente sin instalar), implemente ese grupo.</span><span class="sxs-lookup"><span data-stu-id="f1e94-201">If you don’t already have another Edge pool deployed (besides the one that is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="f1e94-202">En cada servidor perimetral del nuevo grupo perimetral que alojará ahora la federación XMPP (EdgePool2), ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f1e94-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="f1e94-203">Ejecute el siguiente cmdlet para cambiar la ruta de la federación XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="f1e94-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="f1e94-204">En este ejemplo, Site2 es el sitio que contiene el grupo perimetral que alojará ahora la federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral del grupo.</span><span class="sxs-lookup"><span data-stu-id="f1e94-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="f1e94-205">En el servidor DNS externo, cambie el registro de DNS A de la federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f1e94-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="f1e94-p125">Si aún no tiene un registro SRV de DNS para la federación XMPP que resuelva al grupo perimetral que alojará ahora la federación de XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="f1e94-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="f1e94-208">Compruebe que el grupo perimetral que alojará ahora la federación XMPP tiene abierto el puerto 5269 externamente.</span><span class="sxs-lookup"><span data-stu-id="f1e94-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="f1e94-209">Inicie los servicios en todos los servidores perimetrales del grupo perimetral que alojará ahora la federación XMPP:</span><span class="sxs-lookup"><span data-stu-id="f1e94-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="f1e94-210">Conmutación por recuperación del grupo de servidores perimetrales usado para la federación de Skype Empresarial Server o la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="f1e94-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="f1e94-211">Después de que un grupo de servidores perimetrales con errores que usaba para hospedar la federación se haya conectado de nuevo, use este procedimiento para conmutar por recuperación la ruta de federación de Skype Empresarial Server o la ruta de federación XMPP para volver a usar este grupo de servidores perimetrales restaurado.</span><span class="sxs-lookup"><span data-stu-id="f1e94-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="f1e94-212">En el grupo de servidores perimetrales que vuelve a estar disponible, inicie los servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="f1e94-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="f1e94-213">Si desea conmutar por recuperación la ruta de federación de Skype Empresarial Server para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1e94-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="f1e94-214">En un servidor front-end, abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="f1e94-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="f1e94-215">Expanda **grupos de servidores perimetrales** y, a continuación, haga clic con el botón secundario en el servidor perimetral o grupo de servidores perimetrales configurado actualmente para la federación.</span><span class="sxs-lookup"><span data-stu-id="f1e94-215">Expand **Edge pools**, then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="f1e94-216">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="f1e94-217">En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f1e94-218">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-218">Select **OK**.</span></span>
    
      - <span data-ttu-id="f1e94-219">Expanda **grupos de servidores perimetrales** y, a continuación, haga clic con el botón secundario en el servidor perimetral original o en el grupo de servidores perimetrales que vuelva a usar para la federación.</span><span class="sxs-lookup"><span data-stu-id="f1e94-219">Expand **Edge pools**, then right-click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="f1e94-220">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="f1e94-221">En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f1e94-222">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-222">Select **OK**.</span></span>
    
      - <span data-ttu-id="f1e94-223">Seleccione **Acción**, seleccione **Topología,** **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-223">Select **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="f1e94-224">Cuando se le pida **que publique la topología,** seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f1e94-224">When prompted on **Publish the topology**, select **Next**.</span></span> <span data-ttu-id="f1e94-225">Cuando finalice la publicación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-225">When the Publish is finished, select **Finish**.</span></span>
    
      - <span data-ttu-id="f1e94-226">En el servidor perimetral, abra el Asistente para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f1e94-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="f1e94-227">Select **Install or Update Skype for Business Server System**, then select Setup or Remove Skype for Business Server **Components**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-227">Select **Install or Update Skype for Business Server System**, then select **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="f1e94-228">Seleccione **Ejecutar de nuevo.**</span><span class="sxs-lookup"><span data-stu-id="f1e94-228">Select **Run Again**.</span></span>
    
      - <span data-ttu-id="f1e94-229">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-229">Select **Next**.</span></span> <span data-ttu-id="f1e94-230">La pantalla de resumen mostrará las acciones a medida que se ejecuten.</span><span class="sxs-lookup"><span data-stu-id="f1e94-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="f1e94-231">Una vez que haya terminado la implementación, seleccione **Ver registro** para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="f1e94-231">Once the deployment is done, select **View Log** to view available log files.</span></span> <span data-ttu-id="f1e94-232">Seleccione **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="f1e94-232">Select **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="f1e94-233">Si quiere conmutar por recuperación la ruta de la federación XMPP para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1e94-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="f1e94-234">Ejecute el cmdlet siguiente para volver a apuntar la ruta de la federación XMPP al grupo de servidores perimetrales que ahora hospedarán la federación XMPP (en este ejemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="f1e94-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="f1e94-235">En este ejemplo, Site1 es el sitio que contiene el grupo de servidores perimetrales que ahora contendrá la ruta de la federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral de ese grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f1e94-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="f1e94-p133">Si todavía no tiene un registro DNS SRV para la federación XMPP que se resuelva en el grupo de servidores perimetrales que ahora hospedará la federación XMPP, agréguelo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="f1e94-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="f1e94-238">En el servidor DNS externo, cambie el registro DNS A para la federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f1e94-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="f1e94-239">Compruebe que el grupo de servidores perimetrales que ahora hospedará la federación XMPP tiene el puerto 5269 abierto externamente.</span><span class="sxs-lookup"><span data-stu-id="f1e94-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="f1e94-240">Si los grupos de servidores front-end siguieron ejecutándose en el sitio que contiene el grupo de servidores perimetrales que tuvo el error y que se ha restaurado, actualice el servicio de conferencia web y el servicio de conferencia A/V en estos grupos de servidores front-end para que vuelvan a usar los grupos de servidores perimetrales en su sitio local.</span><span class="sxs-lookup"><span data-stu-id="f1e94-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="f1e94-241">Si el grupo de servidores front-end del mismo sitio que el grupo de servidores perimetrales también tuvo errores, ahora puede usar Invoke–CsPoolFailback para conmutar por recuperación el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f1e94-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="f1e94-242">Cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f1e94-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="f1e94-243">Si se produce un error en un grupo perimetral pero el grupo de front-end del mismo sitio sigue en ejecución, deberá establecer el grupo de servidores front-end para que use un grupo perimetral de otro sitio hasta que se restablezca el grupo perimetral en el que se ha producido el error.</span><span class="sxs-lookup"><span data-stu-id="f1e94-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="f1e94-244">En el Generador de topologías, navegue hasta el nombre del grupo de servidores front-end que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="f1e94-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="f1e94-245">Haga clic con el botón secundario en el grupo de servidores y, a continuación, **seleccione Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="f1e94-245">Right-click the pool, and then select **Edit Properties**.</span></span>

3.  <span data-ttu-id="f1e94-246">En la sección **Asociaciones**, en **Asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f1e94-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="f1e94-247">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1e94-247">Select **OK**.</span></span>
