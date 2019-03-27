---
title: Administración de recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información acerca de los procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos en grupos de servidores Front-End emparejados.
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892416"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="bbff2-103">Administración de Skype para recuperación ante desastres de servidor empresarial, alta disponibilidad y servicio de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="bbff2-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="bbff2-104">Esta sección contiene procedimientos para operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos en grupos de servidores Front-End emparejados.</span><span class="sxs-lookup"><span data-stu-id="bbff2-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="bbff2-105">Procedimientos de recuperación ante desastres, conmutación por error y conmutación por recuperación, son manuales.</span><span class="sxs-lookup"><span data-stu-id="bbff2-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="bbff2-106">Si no hay un desastre, el administrador debe invocar manualmente los procedimientos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="bbff2-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="bbff2-107">El mismo se aplica a la conmutación por recuperación una vez reparado el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="bbff2-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="bbff2-108">Los procedimientos de recuperación ante desastres en esta sección suponen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbff2-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="bbff2-109">Tiene una implementación con grupos de servidores Front-End emparejados, que se encuentra en sitios diferentes, tal como se describe en el [Plan de alta disponibilidad y recuperación ante desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="bbff2-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="bbff2-110">El servicio de copia de seguridad se ha ejecutado en estos grupos de servidores emparejados para mantenerlos sincronizados.</span><span class="sxs-lookup"><span data-stu-id="bbff2-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="bbff2-111">Si el almacén de Administración Central está hospedado en cualquier grupo de servidores, está instalado y se está ejecutando en ambos de los grupos de servidores emparejados con uno de esos grupos de servidores que hospedan al maestro activo y el grupo de hospedaje el estado de espera.</span><span class="sxs-lookup"><span data-stu-id="bbff2-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbff2-112">En los siguientes procedimientos, el parámetro *PoolFQDN* hace referencia al FQDN del grupo de servidores que se ve afectada por ante desastres, no el grupo de servidores que afecta a los usuarios se redirigen desde.</span><span class="sxs-lookup"><span data-stu-id="bbff2-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="bbff2-113">Para el mismo conjunto de usuarios afectados, hace referencia al mismo grupo de servidores en los cmdlets de conmutación por error y conmutación por recuperación (es decir, el grupo de servidores que hospedados en primer lugar los usuarios antes de la conmutación por error).</span><span class="sxs-lookup"><span data-stu-id="bbff2-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="bbff2-114">Por ejemplo, supongamos que un caso en el que todos los usuarios alojados en un grupo de servidores P1 se conmuta por error para el grupo de copia de seguridad, P2.</span><span class="sxs-lookup"><span data-stu-id="bbff2-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="bbff2-115">Si el administrador desea mover todos los usuarios que actualmente atendidos por P2 a se pasarán por P1, el administrador debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="bbff2-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="bbff2-116">Fail hacer una copia de todos los usuarios hospedados originalmente en P1 de P2 a P1 mediante el cmdlet de la conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="bbff2-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="bbff2-117">En este caso, el *PoolFQDN* es P1 FQDN.</span><span class="sxs-lookup"><span data-stu-id="bbff2-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="bbff2-118">Conmutar por error todos los usuarios hospedados originalmente en P2 a P1 mediante el cmdlet de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="bbff2-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="bbff2-119">En este caso, el PoolFQDN es P2 FQDN.</span><span class="sxs-lookup"><span data-stu-id="bbff2-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="bbff2-120">Si más adelante, el administrador desea conmutar por recuperación los usuarios de P2 a P2, el PoolFQDN es P2 FQDN.</span><span class="sxs-lookup"><span data-stu-id="bbff2-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="bbff2-121">Tenga en cuenta ese paso 1 anterior debe realizarse antes del paso 2 para conservar la integridad del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="bbff2-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="bbff2-122">Si intenta paso 2 antes del paso 1, se producirá un error en el cmdlet del paso 2.</span><span class="sxs-lookup"><span data-stu-id="bbff2-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="bbff2-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbff2-123">See Also</span></span>

[<span data-ttu-id="bbff2-124">Planificar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="bbff2-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
