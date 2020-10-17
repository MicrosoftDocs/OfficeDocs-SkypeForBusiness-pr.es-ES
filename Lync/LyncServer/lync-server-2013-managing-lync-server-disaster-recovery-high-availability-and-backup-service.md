---
title: Administración de la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad de Lync Server
description: Administración de la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad de Lync Server.
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
ms.openlocfilehash: 3e440c8c72ab5e66d27a86dfce963368dff804bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569416"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="8da12-103">Administración del servicio de copia de seguridad, alta disponibilidad y recuperación ante desastres de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-103">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8da12-104">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="8da12-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="8da12-105">En esta sección se incluyen procedimientos para operaciones de recuperación ante desastres, así como para el mantenimiento del Servicio de copia de seguridad, el cual sincroniza los datos entre grupos de servidores front-end asociados.</span><span class="sxs-lookup"><span data-stu-id="8da12-105">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="8da12-p101">Los procedimientos de recuperación ante desastres, tanto de conmutación por error, como por recuperación, son manuales. Si se produce un desastre, el administrador deberá invocar manualmente los procedimientos de conmutación por error. Y lo mismo ocurre con la conmutación por recuperación después de la reparación del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8da12-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="8da12-109">Para los procedimientos de recuperación ante desastres expuestos a continuación, se supone que:</span><span class="sxs-lookup"><span data-stu-id="8da12-109">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="8da12-110">Tiene una implementación con grupos de servidores front-end emparejados, ubicados en diferentes sitios, tal como se describe en [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8da12-110">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="8da12-111">El Servicio de copia de seguridad se ha estado ejecutando en estos grupos emparejados para mantenerlos sincronizados.</span><span class="sxs-lookup"><span data-stu-id="8da12-111">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="8da12-112">Si el almacén de administración central está hospedado en cualquier grupo de servidores, se instala y se ejecuta en los dos grupos emparejados, con uno de esos grupos de servidores que hospedan el maestro activo y el otro grupo que hospeda el modo de espera.</span><span class="sxs-lookup"><span data-stu-id="8da12-112">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8da12-p103">En los procedimientos siguientes, el parámetro <EM>PoolFQDN</EM> hace referencia al FQDN del grupo afectado por el desastre y no al grupo desde el cual se redirige a los usuarios afectados. Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo tanto en los cmdlets de conmutación por error, como de conmutación por recuperación (es decir, el grupo de servidores que hospedó en primer lugar a los usuarios antes de la conmutación por error).</span><span class="sxs-lookup"><span data-stu-id="8da12-p103">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="8da12-p104">Por ejemplo, supongamos que se hizo de la conmutación por error de todos los usuarios hospedados en el grupo P1 al grupo de servidores de reserva, el P2. Si el administrador quiere mover a todos los usuarios que actualmente están siendo atendidos por P2 a P1, el administrador deberá dar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8da12-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="8da12-p105">Conmutar por recuperación a todos los usuarios hospedados inicialmente en P1 de P2 a P1 usando el cmdlet de conmutación por recuperación. En este caso, el <EM>PoolFQDN</EM> es el FQDN de P1.</span><span class="sxs-lookup"><span data-stu-id="8da12-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="8da12-p106">Conmutar por error a todos los usuarios hospedados inicialmente en P2 a P1 usando el cmdlet de conmutación por error. En este caso, el <EM>PoolFQDN</EM> es el FQDN de P2.</span><span class="sxs-lookup"><span data-stu-id="8da12-p106">Fail over all the users originally homed on P2 to P1 using the failover cmdlet. In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="8da12-121">Si después el administrador desea llevar a cabo la conmutación por recuperación de los usuarios de P2 de vuelta a P2, el <EM>PoolFQDN</EM> será el FQDN de P2.</span><span class="sxs-lookup"><span data-stu-id="8da12-121">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="8da12-122">Observe que el paso 1 anterior se debe llevar a cabo antes que el paso 2 para mantener la integridad del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8da12-122">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="8da12-123">Si intenta realizar el paso 2 antes que el paso 1, el cmdlet del paso 2 no se completará correctamente.</span><span class="sxs-lookup"><span data-stu-id="8da12-123">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8da12-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8da12-124">In This Section</span></span>

  - [<span data-ttu-id="8da12-125">Configuración y supervisión del servicio de copia de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-125">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="8da12-126">Conmutación por error de un grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-126">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="8da12-127">Conmutación por recuperación de un grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-127">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="8da12-128">Conmutación por error de una base de datos reflejada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-128">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="8da12-129">Conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-129">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="8da12-130">Conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-130">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="8da12-131">Conmutación por recuperación del grupo de servidores perimetrales usado para la Federación de Lync Server o la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-131">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="8da12-132">Cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-132">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="8da12-133">Restauración de contenidos de Conferencia mediante el servicio de copia de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-133">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8da12-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8da12-134">See Also</span></span>


[<span data-ttu-id="8da12-135">Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da12-135">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

