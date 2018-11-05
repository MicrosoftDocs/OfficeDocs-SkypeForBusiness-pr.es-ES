---
title: "Recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad"
TOCTitle: Administrar la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad en Lync Server 2013
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49889817
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-12_

En esta sección se incluyen procedimientos para operaciones de recuperación ante desastres, así como para el mantenimiento del Servicio de copia de seguridad, el cual sincroniza los datos entre grupos de servidores front-end asociados.

Los procedimientos de recuperación ante desastres, tanto de conmutación por error, como por recuperación, son manuales. Si se produce un desastre, el administrador deberá invocar manualmente los procedimientos de conmutación por error. Y lo mismo ocurre con la conmutación por recuperación después de la reparación del grupo de servidores.

Para los procedimientos de recuperación ante desastres expuestos a continuación, se supone que:

  - Tiene una implementación con grupos de servidores front-end emparejados, localizados en centros diferentes, como se describe en [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). El Servicio de copia de seguridad se ha estado ejecutando en estos grupos emparejados para mantenerlos sincronizados.

  - Si el Almacén de administración central está hospedado en uno de los grupos de servidores, está instalado y en ejecución en los dos grupos de servidores emparejados. En uno de los grupos de servidores se hospeda el maestro activo y, en el otro, el maestro en espera.

> [!IMPORTANT]  
> En los procedimientos siguientes, el parámetro <em>PoolFQDN</em> hace referencia al FQDN del grupo afectado por el desastre y no al grupo desde el cual se redirige a los usuarios afectados. Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo tanto en los cmdlets de conmutación por error, como de conmutación por recuperación (es decir, el grupo de servidores que hospedó en primer lugar a los usuarios antes de la conmutación por error).<br />
> Por ejemplo, supongamos que se hizo de la conmutación por error de todos los usuarios hospedados en el grupo P1 al grupo de servidores de reserva, el P2. Si el administrador quiere mover a todos los usuarios que actualmente están siendo atendidos por P2 a P1, el administrador deberá dar los siguientes pasos:
> <ol>
> <li><p>Conmutar por recuperación a todos los usuarios hospedados inicialmente en P1 de P2 a P1 usando el cmdlet de conmutación por recuperación. En este caso, el <em>PoolFQDN</em> es el FQDN de P1.</p></li>
> <li><p>Conmutar por error a todos los usuarios hospedados inicialmente en P2 a P1 usando el cmdlet de conmutación por error. En este caso, el <em>PoolFQDN</em> es el FQDN de P2.</p></li>
> <li><p>Si después el administrador desea llevar a cabo la conmutación por recuperación de los usuarios de P2 de vuelta a P2, el <em>PoolFQDN</em> será el FQDN de P2.</p></li>
> </ol>
> Observe que el paso 1 anterior se debe llevar a cabo antes que el paso 2 para mantener la integridad del grupo de servidores. Si intenta realizar el paso 2 antes que el paso 1, el cmdlet del paso 2 no se completará correctamente.


## En esta sección

  - [Configurar y supervisar el servicio de copia de seguridad en Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Conmutación por error de un grupo en Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Conmutación por recuperación de grupo en Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Conmutación por error de una base de datos reflejada en Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP en Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Restauración de contenidos de conferencia mediante el servicio de copias de seguridad en Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

## Vea también

#### Conceptos

[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

