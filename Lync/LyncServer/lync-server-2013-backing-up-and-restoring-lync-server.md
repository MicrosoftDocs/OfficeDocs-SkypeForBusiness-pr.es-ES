---
title: Copia de seguridad y restauración de Lync Server 2013
TOCTitle: Copia de seguridad y restauración de Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202160(v=OCS.15)
ms:contentKeyID: 52061588
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Copia de seguridad y restauración de Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

En esta sección, encontrará los procedimientos recomendados para realizar la copia de seguridad de los datos de Lync Server 2013 y para restaurarlos en el caso de un error. Estos procedimientos recomendados se aplican a las siguientes situaciones:

  - Un grupo de Lync Server completo de cualquier tipo (Servidor front-end, Servidor perimetral, Servidor de mediación, Servidor de chat persistente o Director) o un servidor individual de uno de estos grupos.

  - El Servidor de administración central

  - Un servidor Standard Edition

  - Un Servidor back-end de Enterprise Edition

  - Un Almacén de archivos

  - Una Base de datos de archivado, una Base de datos de supervisión o una base de datos de chat persistente

Esta sección no incluye información sobre cómo restaurar un sitio completo o desarrollar un sitio en espera. Para obtener información detallada sobre cómo desarrollar una solución de recuperación ante desastres con grupos de servidores front-end emparejados, consulte [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Este es el método recomendado para planear una recuperación ante desastres.

Si ha implementado grupos de servidores front-end emparejados y se produce un error irrecuperable en uno de estos grupos, puede restaurarlo con un nuevo nombre de dominio completo (FQDN) desde su grupo emparejado. Para obtener detalles sobre los pasos de esta recuperación, consulte [Conmutación por error de un grupo en Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Además, si más tarde desea volver a crear un grupo en el que se ha producido un error irrecuperable y que formaba parte de un par de servidores front-end, puede usar los pasos descritos en [Ejecutar una conmutación por error de grupo de servidores front-end ABC](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

La metodología descrita en este documento incluye consideraciones especiales durante la fase de planeación. Para obtener detalles, consulte [Definir un plan de copia de seguridad y restauración](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

## En esta sección

  - [Preparar la copia de seguridad y restauración de Lync Server](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Copia de seguridad de los datos y la configuración](lync-server-2013-backing-up-data-and-settings.md)

  - [Restaurar los datos y la configuración](lync-server-2013-restoring-data-and-settings.md)

  - [Hojas de cálculo de copia de seguridad y restauración](lync-server-2013-backup-and-restoration-worksheets.md)

