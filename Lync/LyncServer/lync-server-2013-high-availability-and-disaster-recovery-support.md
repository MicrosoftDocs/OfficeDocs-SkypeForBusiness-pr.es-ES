---
title: "Compatibilidad entre la alta disponibilidad y la recuperación ante desastres"
TOCTitle: Compatibilidad entre la alta disponibilidad y la recuperación ante desastres
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48275130
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad entre la alta disponibilidad y la recuperación ante desastres en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-25_

Lync Server 2013 proporciona alta disponibilidad por redundancia de servidores a través de grupos. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto se aplica a servidores front-end, servidores perimetrales, servidores de mediación y directores. Para más información sobre los roles de servidor, vea [Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 también proporciona medidas de recuperación ante desastres habilitando la vinculación del grupo. Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada. Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.

Lync Server 2013 también admite alta disponibilidad del servidor back-end. Es una topología opcional en la que implementa servidores back-end para un grupo front-end y configura la creación de reflejo de SQL Server sincrónica para todas las bases de datos del Lync que se ejecutan en los servidores back-end.

Para información sobre la vinculación de pares y la creación de reflejo del servidor back-end, vea [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Vea también

#### Conceptos

[Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md)  
[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

