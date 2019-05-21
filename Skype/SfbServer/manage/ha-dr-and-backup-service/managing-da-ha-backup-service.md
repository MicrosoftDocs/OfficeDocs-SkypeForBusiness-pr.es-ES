---
title: Administración de recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga más información sobre procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos de las agrupaciones frontales emparejadas.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303901"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="ecaaa-103">Administración de la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ecaaa-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="ecaaa-104">Esta sección contiene procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos de las agrupaciones frontales emparejadas.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="ecaaa-105">Los procedimientos de recuperación ante desastres, tanto de failover como failback, son manuales.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="ecaaa-106">Si se produce un desastre, el administrador debe invocar manualmente los procedimientos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="ecaaa-107">Lo mismo se aplica a la conmutación por recuperación después de reparar el grupo.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="ecaaa-108">Los procedimientos de recuperación de desastres de esta sección suponen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ecaaa-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="ecaaa-109">Tiene una implementación con las agrupaciones frontales emparejadas, que se encuentran en diferentes sitios, como se describe en [planear la alta disponibilidad y la recuperación ante desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ecaaa-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="ecaaa-110">El servicio de copia de seguridad se ha ejecutado en estas agrupaciones emparejadas para mantenerlas sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="ecaaa-111">Si el almacén central de administración se encuentra en cualquiera de las dos agrupaciones, se instalará y se ejecutará en ambos pools emparejados, con uno de esos grupos que alojen el maestro activo y el otro grupo que aloje al modo de espera.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ecaaa-112">En los procedimientos siguientes, el parámetro *PoolFQDN* se refiere al FQDN del grupo de servidores que se ve afectado por el desastre, no al grupo desde el que se redirige a los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="ecaaa-113">Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo en cmdlets de conmutación por error y de conmutación por error (es decir, el grupo que ha alojado primero los usuarios antes de la conmutación por error).</span><span class="sxs-lookup"><span data-stu-id="ecaaa-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="ecaaa-114">Por ejemplo, supongamos que se produjo un error en todos los usuarios alojados en un grupo P1 en el grupo de copia de seguridad, P2.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="ecaaa-115">Si el administrador desea mover todos los usuarios que actualmente son atendidas por P2, el administrador debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ecaaa-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="ecaaa-116">Realice la conmutación por recuperación de todos los usuarios originalmente alojados en P1 desde P2 a P1 con el cmdlet de conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="ecaaa-117">En este caso, el *PoolFQDN* es P1's FQDN.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="ecaaa-118">Conmute por error a todos los usuarios que se hayan alojado originalmente en P2 a P1 mediante el cmdlet de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="ecaaa-119">En este caso, el PoolFQDN es P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="ecaaa-120">Si, posteriormente, el administrador desea volver a realizar la conmutación por error de esos usuarios P2 a P2, la PoolFQDN es P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="ecaaa-121">Tenga en cuenta que el paso 1 anterior debe realizarse antes del paso 2 para preservar la integridad del grupo.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="ecaaa-122">Si intenta paso 2 antes del paso 1, se producirá un error en el cmdlet paso 2.</span><span class="sxs-lookup"><span data-stu-id="ecaaa-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="ecaaa-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecaaa-123">See Also</span></span>

[<span data-ttu-id="ecaaa-124">Planificar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="ecaaa-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
