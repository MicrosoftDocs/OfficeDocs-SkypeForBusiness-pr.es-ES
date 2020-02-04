---
title: Administración de recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="651ee-102">Administrar la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="651ee-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="651ee-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="651ee-104">Esta sección contiene procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad que sincroniza los datos de las agrupaciones frontales emparejadas.</span><span class="sxs-lookup"><span data-stu-id="651ee-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="651ee-105">Los procedimientos de recuperación ante desastres, tanto de failover como failback, son manuales.</span><span class="sxs-lookup"><span data-stu-id="651ee-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="651ee-106">Si se produce un desastre, el administrador debe invocar manualmente los procedimientos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="651ee-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="651ee-107">Lo mismo se aplica a la conmutación por recuperación después de reparar el grupo.</span><span class="sxs-lookup"><span data-stu-id="651ee-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="651ee-108">Los procedimientos de recuperación de desastres en el resto de esta sección suponen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="651ee-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="651ee-109">Tiene una implementación con las agrupaciones frontales emparejadas, que se encuentran en diferentes sitios, como se describe en [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="651ee-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="651ee-110">El servicio de copia de seguridad se ha ejecutado en estas agrupaciones emparejadas para mantenerlas sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="651ee-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="651ee-111">Si el almacén central de administración se encuentra en cualquiera de las dos agrupaciones, se instalará y se ejecutará en ambos pools emparejados, con uno de esos grupos que alojen el maestro activo y el otro grupo que aloje al modo de espera.</span><span class="sxs-lookup"><span data-stu-id="651ee-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="651ee-112">En los procedimientos siguientes, el parámetro <EM>PoolFQDN</EM> se refiere al FQDN del grupo de servidores que se ve afectado por el desastre, no al grupo desde el que se redirige a los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="651ee-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="651ee-113">Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo en cmdlets de conmutación por error y de conmutación por error (es decir, el grupo que ha alojado primero los usuarios antes de la conmutación por error).</span><span class="sxs-lookup"><span data-stu-id="651ee-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="651ee-114">Por ejemplo, supongamos que se produjo un error en todos los usuarios alojados en un grupo P1 en el grupo de copia de seguridad, P2.</span><span class="sxs-lookup"><span data-stu-id="651ee-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="651ee-115">Si el administrador desea mover todos los usuarios que actualmente son atendidas por P2, el administrador debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="651ee-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="651ee-116">Realice la conmutación por recuperación de todos los usuarios originalmente alojados en P1 desde P2 a P1 con el cmdlet de conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="651ee-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="651ee-117">En este caso, el <EM>PoolFQDN</EM> es P1's FQDN.</span><span class="sxs-lookup"><span data-stu-id="651ee-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="651ee-118">Conmute por error a todos los usuarios que se hayan alojado originalmente en P2 a P1 mediante el cmdlet de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="651ee-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="651ee-119">En este caso, el <EM>PoolFQDN</EM> es P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="651ee-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="651ee-120">Si, posteriormente, el administrador desea volver a realizar la conmutación por error de esos usuarios P2 a P2, la <EM>PoolFQDN</EM> es P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="651ee-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="651ee-121">Tenga en cuenta que el paso 1 anterior debe realizarse antes del paso 2 para preservar la integridad del grupo.</span><span class="sxs-lookup"><span data-stu-id="651ee-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="651ee-122">Si intenta paso 2 antes del paso 1, se producirá un error en el cmdlet paso 2.</span><span class="sxs-lookup"><span data-stu-id="651ee-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="651ee-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="651ee-123">In This Section</span></span>

  - [<span data-ttu-id="651ee-124">Configurar y supervisar el servicio de copia de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="651ee-125">Conmutación por error de un grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="651ee-126">Conmutación por recuperación de grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="651ee-127">Conmutación por error de una base de datos reflejada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="651ee-128">Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="651ee-129">Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="651ee-130">Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="651ee-131">Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="651ee-132">Restauración de contenidos de conferencia mediante el servicio de copias de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="651ee-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="651ee-133">See Also</span></span>


[<span data-ttu-id="651ee-134">Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="651ee-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

