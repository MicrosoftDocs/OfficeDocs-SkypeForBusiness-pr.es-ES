---
title: Administración de la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad de Lync Server
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
ms.openlocfilehash: 83e0446bbc0b39f553ac9a2bcba0af9ceacc421f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Administración del servicio de copia de seguridad, alta disponibilidad y recuperación ante desastres de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-12_

En esta sección se incluyen procedimientos para operaciones de recuperación ante desastres, así como para el mantenimiento del Servicio de copia de seguridad, el cual sincroniza los datos entre grupos de servidores front-end asociados.

Los procedimientos de recuperación ante desastres, tanto de conmutación por error, como por recuperación, son manuales. Si se produce un desastre, el administrador deberá invocar manualmente los procedimientos de conmutación por error. Y lo mismo ocurre con la conmutación por recuperación después de la reparación del grupo de servidores.

Para los procedimientos de recuperación ante desastres expuestos a continuación, se supone que:

  - Tiene una implementación con grupos de servidores front-end emparejados, ubicados en diferentes sitios, tal como se describe en [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). El Servicio de copia de seguridad se ha estado ejecutando en estos grupos emparejados para mantenerlos sincronizados.

  - Si el almacén de administración central está hospedado en cualquier grupo de servidores, se instala y se ejecuta en los dos grupos emparejados, con uno de esos grupos de servidores que hospedan el maestro activo y el otro grupo que hospeda el modo de espera.

<div>


> [!IMPORTANT]
> En los procedimientos siguientes, el parámetro <EM>PoolFQDN</EM> hace referencia al FQDN del grupo afectado por el desastre y no al grupo desde el cual se redirige a los usuarios afectados. Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo tanto en los cmdlets de conmutación por error, como de conmutación por recuperación (es decir, el grupo de servidores que hospedó en primer lugar a los usuarios antes de la conmutación por error).<BR>Por ejemplo, supongamos que se hizo de la conmutación por error de todos los usuarios hospedados en el grupo P1 al grupo de servidores de reserva, el P2. Si el administrador quiere mover a todos los usuarios que actualmente están siendo atendidos por P2 a P1, el administrador deberá dar los siguientes pasos: 
> <OL>
> <LI>
> <P>Conmutar por recuperación a todos los usuarios hospedados inicialmente en P1 de P2 a P1 usando el cmdlet de conmutación por recuperación. En este caso, el <EM>PoolFQDN</EM> es el FQDN de P1.</P>
> <LI>
> <P>Conmutar por error a todos los usuarios hospedados inicialmente en P2 a P1 usando el cmdlet de conmutación por error. En este caso, el <EM>PoolFQDN</EM> es el FQDN de P2.</P>
> <LI>
> <P>Si después el administrador desea llevar a cabo la conmutación por recuperación de los usuarios de P2 de vuelta a P2, el <EM>PoolFQDN</EM> será el FQDN de P2.</P></LI></OL>Observe que el paso 1 anterior se debe llevar a cabo antes que el paso 2 para mantener la integridad del grupo de servidores. Si intenta realizar el paso 2 antes que el paso 1, el cmdlet del paso 2 no se completará correctamente.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración y supervisión del servicio de copia de seguridad en Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Conmutación por error de un grupo de servidores en Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Conmutación por recuperación de un grupo de servidores en Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Conmutación por error de una base de datos reflejada en Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Conmutación por recuperación del grupo de servidores perimetrales usado para la Federación de Lync Server o la Federación XMPP en Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Restauración de contenidos de Conferencia mediante el servicio de copia de seguridad en Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

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

