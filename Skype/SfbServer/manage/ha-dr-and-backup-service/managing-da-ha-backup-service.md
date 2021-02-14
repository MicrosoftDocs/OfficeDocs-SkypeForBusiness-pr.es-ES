---
title: Administración de recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad
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
description: Obtenga información sobre los procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos en grupos de servidores front-end emparejados.
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817160"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="3aaf9-103">Administración de la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3aaf9-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="3aaf9-104">Esta sección contiene procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos en grupos de servidores front-end emparejados.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="3aaf9-p101">Los procedimientos de recuperación ante desastres, tanto de conmutación por error, como por recuperación, son manuales. Si se produce un desastre, el administrador deberá invocar manualmente los procedimientos de conmutación por error. Y lo mismo ocurre con la conmutación por recuperación después de la reparación del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="3aaf9-108">Los procedimientos de recuperación ante desastres de esta sección suponen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3aaf9-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="3aaf9-109">Tiene una implementación con grupos de servidores front-end emparejados, ubicados en sitios diferentes, como se describe en Planeación de alta disponibilidad [y recuperación ante desastres.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="3aaf9-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="3aaf9-110">El Servicio de copia de seguridad se ha estado ejecutando en estos grupos emparejados para mantenerlos sincronizados.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="3aaf9-111">Si el almacén de administración central está hospedado en cualquiera de los grupos, se instala y se ejecuta en ambos grupos emparejados, con uno de esos grupos que hospeda el maestro activo y el otro grupo de servidores que hospeda el modo de espera.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3aaf9-p103">En los procedimientos siguientes, el parámetro *PoolFQDN* hace referencia al FQDN del grupo afectado por el desastre y no al grupo desde el cual se redirige a los usuarios afectados. Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo tanto en los cmdlets de conmutación por error, como de conmutación por recuperación (es decir, el grupo de servidores que hospedó en primer lugar a los usuarios antes de la conmutación por error).</span><span class="sxs-lookup"><span data-stu-id="3aaf9-p103">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="3aaf9-p104">Por ejemplo, supongamos que se hizo de la conmutación por error de todos los usuarios hospedados en el grupo P1 al grupo de servidores de reserva, el P2. Si el administrador quiere mover a todos los usuarios que actualmente están siendo atendidos por P2 a P1, el administrador deberá dar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="3aaf9-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="3aaf9-p105">Conmutar por recuperación a todos los usuarios hospedados inicialmente en P1 de P2 a P1 usando el cmdlet de conmutación por recuperación. En este caso, el *PoolFQDN* es el FQDN de P1.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="3aaf9-118">Conmutar por error a todos los usuarios hospedados inicialmente en P2 a P1 usando el cmdlet de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="3aaf9-119">En este caso, el PoolFQDN es el FQDN de P2.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="3aaf9-120">Si después el administrador desea llevar a cabo la conmutación por recuperación de los usuarios de P2 de vuelta a P2, el PoolFQDN será el FQDN de P2.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="3aaf9-p107">Observe que el paso 1 anterior se debe llevar a cabo antes que el paso 2 para mantener la integridad del grupo de servidores. Si intenta realizar el paso 2 antes que el paso 1, el cmdlet del paso 2 no se completará correctamente.</span><span class="sxs-lookup"><span data-stu-id="3aaf9-p107">Note that step 1 above must be performed before step 2 to preserve pool integrity. If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="3aaf9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3aaf9-123">See Also</span></span>

[<span data-ttu-id="3aaf9-124">Planeación de alta disponibilidad y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="3aaf9-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
