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

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Administrar la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-12_

Esta sección contiene procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad que sincroniza los datos de las agrupaciones frontales emparejadas.

Los procedimientos de recuperación ante desastres, tanto de failover como failback, son manuales. Si se produce un desastre, el administrador debe invocar manualmente los procedimientos de conmutación por error. Lo mismo se aplica a la conmutación por recuperación después de reparar el grupo.

Los procedimientos de recuperación de desastres en el resto de esta sección suponen lo siguiente:

  - Tiene una implementación con las agrupaciones frontales emparejadas, que se encuentran en diferentes sitios, como se describe en [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). El servicio de copia de seguridad se ha ejecutado en estas agrupaciones emparejadas para mantenerlas sincronizadas.

  - Si el almacén central de administración se encuentra en cualquiera de las dos agrupaciones, se instalará y se ejecutará en ambos pools emparejados, con uno de esos grupos que alojen el maestro activo y el otro grupo que aloje al modo de espera.

<div>


> [!IMPORTANT]
> En los procedimientos siguientes, el parámetro <EM>PoolFQDN</EM> se refiere al FQDN del grupo de servidores que se ve afectado por el desastre, no al grupo desde el que se redirige a los usuarios afectados. Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo en cmdlets de conmutación por error y de conmutación por error (es decir, el grupo que ha alojado primero los usuarios antes de la conmutación por error).<BR>Por ejemplo, supongamos que se produjo un error en todos los usuarios alojados en un grupo P1 en el grupo de copia de seguridad, P2. Si el administrador desea mover todos los usuarios que actualmente son atendidas por P2, el administrador debe realizar los siguientes pasos: 
> <OL>
> <LI>
> <P>Realice la conmutación por recuperación de todos los usuarios originalmente alojados en P1 desde P2 a P1 con el cmdlet de conmutación por recuperación. En este caso, el <EM>PoolFQDN</EM> es P1's FQDN.</P>
> <LI>
> <P>Conmute por error a todos los usuarios que se hayan alojado originalmente en P2 a P1 mediante el cmdlet de conmutación por error. En este caso, el <EM>PoolFQDN</EM> es P2's FQDN.</P>
> <LI>
> <P>Si, posteriormente, el administrador desea volver a realizar la conmutación por error de esos usuarios P2 a P2, la <EM>PoolFQDN</EM> es P2's FQDN.</P></LI></OL>Tenga en cuenta que el paso 1 anterior debe realizarse antes del paso 2 para preservar la integridad del grupo. Si intenta paso 2 antes del paso 1, se producirá un error en el cmdlet paso 2.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar y supervisar el servicio de copia de seguridad en Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Conmutación por error de un grupo en Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Conmutación por recuperación de grupo en Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Conmutación por error de una base de datos reflejada en Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP en Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Restauración de contenidos de conferencia mediante el servicio de copias de seguridad en Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

