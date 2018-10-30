---
title: 'Lync Server 2013: Planear la combinación de grupos de servidores front-end'
TOCTitle: Planear la combinación de grupos de servidores front-end
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48276706
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planear la combinación de grupos de servidores front-end en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-28_

Para conseguir la máxima capacidad de recuperación ante desastres en Lync Server 2013, implemente parejas de grupos de servidores front-end en dos sitios geográficamente dispersos. Cada sitio contiene un grupo de servidores front-end emparejado con otro grupo correspondiente en el otro sitio. Ambos sitios están activos y el servicio de copia de seguridad de Lync Server proporciona una replicación de datos en tiempo real para mantener sincronizados los grupos de servidores. El servicio de copia de seguridad es una nueva característica de Lync Server 2013, diseñada para apoyar la solución de recuperación ante desastres. Se instala en un grupo de servidores front-end cuando se empareja el grupo de servidores con otro grupo de servidores front-end.

Si el grupo de servidores de un sitio falla, puede realizar una conmutación por error de los usuarios de dicho grupo de servidores al grupo de servidores del otro sitio, que proporcionará servicios a todos los servidores de ambos grupos. Para la planificación de capacidad, cada grupo de servidores debe estar diseñado para gestionar las cargas de trabajo de todos los usuarios de ambos grupos en caso de desastre.

## En esta sección

  - [Opciones compatibles de emparejamiento de grupos de servidores y procedimientos recomendados para Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Relaciones del registrador de copia de seguridad en Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Tiempo de recuperación para la conmutación por error y por recuperación del grupo de servidores en Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Conmutación por error del almacén de administración central en Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Seguridad de datos en el emparejamiento de grupos de servidores front-end en Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

