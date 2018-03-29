---
title: Implementación de grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Puede decidir usar grupos de servidores front-end para proporcionar protección de recuperación ante desastres emparejados, pero hacerlo no es un requisito.
ms.openlocfilehash: e13694c364908cfef70edafc1e7eb0484c5fe1bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server-2015"></a><span data-ttu-id="dd4bc-103">Implementación de grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="dd4bc-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dd4bc-104">Puede decidir usar grupos de servidores front-end para proporcionar protección de recuperación ante desastres emparejados, pero hacerlo no es un requisito.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="dd4bc-105">Puede implementar fácilmente la topología de recuperación ante desastres de grupos emparejados de Front-End mediante el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="dd4bc-106">Para implementar un par de grupos de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="dd4bc-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="dd4bc-107">Si los grupos son nuevos y aún no está definido, utilice el generador de topología para crear los grupos.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="dd4bc-108">Generador de topología, haga clic en uno de los dos grupos y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="dd4bc-109">Haga clic en **Resistencia** en el panel izquierdo y, a continuación, seleccione **Grupo de servidores de copia de seguridad asociado** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="dd4bc-p101">En el cuadro de debajo de **Grupo de servidores de copia de seguridad asociado**, seleccione el grupo que desea emparejar con este grupo. Solo los grupos existentes que aún no están emparejados con otro grupo estarán disponibles para su selección.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="dd4bc-112">Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="dd4bc-113">Cuando vea los detalles de este grupo, el grupo asociado aparecerá en el panel derecho debajo de **Resistencia**. </span><span class="sxs-lookup"><span data-stu-id="dd4bc-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="dd4bc-114">Utilice el generador de topología para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="dd4bc-p102">Si los dos grupos aún no se han implementado, impleméntelos ahora y se completará la configuración. Puede omitir los dos últimos pasos de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="dd4bc-117">Sin embargo, si ya se implementaron los grupos antes de definir la relación emparejada, debe completar los dos pasos finales siguientes.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="dd4bc-118">En cada servidor front-end de ambos grupos, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd4bc-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="dd4bc-119">Esto configura otros servicios necesarios para que el emparejamiento de copia de seguridad funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="dd4bc-120">Desde un Skype para la línea de comandos de Shell de administración de servidor de Business, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd4bc-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="dd4bc-121">Haga que los datos de conferencia y usuarios de ambos grupos de servidores se sincronicen entre sí, con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="dd4bc-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
   ```
   Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
   ```

   ```
   Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
   ```

   <span data-ttu-id="dd4bc-p103">La sincronización de datos podría llevar unos minutos. Puede utilizar los siguientes cmdlets para ver el estado. Asegúrese de que el estado de ambas direcciones sea parejo</span><span class="sxs-lookup"><span data-stu-id="dd4bc-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
   ```
   Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
   ```

   ```
   Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
   ```

> [!NOTE]
> <span data-ttu-id="dd4bc-125">La opción **automático failover y failback de voz** y los intervalos de tiempo asociado en el generador de topología sólo se aplican a las características de resistencia de voz que se introdujeron en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="dd4bc-126">La selección de esta opción no implica que la conmutación por error de grupos de servidores tratada en este documento sea automática.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="dd4bc-127">La conmutación por error y la conmutación por recuperación de los grupos de servidores siempre requieren que un administrador invoque manualmente los cmdlets de conmutación por error y de conmutación por recuperación, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="dd4bc-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd4bc-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd4bc-128">See also</span></span>

#### 

[<span data-ttu-id="dd4bc-129">Frontal de recuperación de desastres de grupo final en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dd4bc-129">Front End pool disaster recovery in Skype for Business Server 2015</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)

