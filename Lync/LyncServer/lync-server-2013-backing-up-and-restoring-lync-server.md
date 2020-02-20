---
title: 'Lync Server 2013: copia de seguridad y restauración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2dd48b7a4357fef2f848210a52313ae334b608b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Copia de seguridad y restauración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En esta sección, encontrará los procedimientos recomendados para realizar copias de seguridad de los datos de Lync Server 2013 y para restaurarlos si tiene un error. Estos procedimientos recomendados se aplican a las siguientes situaciones:

  - Un grupo de servidores de Lync completo de cualquier tipo (servidor front-end, servidor perimetral, servidor de mediación, servidor de chat persistente o director) o un servidor individual de uno de estos grupos de servidores.

  - El servidor de administración central

  - Un servidor Standard Edition

  - Un servidor back-end de Enterprise Edition

  - Un almacén de archivos

  - Una base de datos de archivado, una base de datos de supervisión o una base de datos de chat persistente

En esta sección no se incluye información sobre cómo restaurar un sitio completo o desarrollar un sitio en espera. Para obtener más información sobre cómo desarrollar una solución de recuperación ante desastres con grupos de servidores front-end emparejados, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Este es el método recomendado para la planeación de la recuperación ante desastres.

Si ha implementado grupos de servidores front-end emparejados, si uno de estos grupos da error y se convierte en irrecuperable, puede restaurar este grupo con un nuevo nombre de dominio completo (FQDN) de su grupo emparejado. Para obtener más información sobre los pasos para realizar esta recuperación, consulte [conmutación por error de un grupo de servidores en Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Además, si más adelante desea volver a crear un grupo de servidores con errores e irrecuperables que formaba parte de un par de servidores front-end, puede seguir los pasos que se indican en [realizar una conmutación por error de grupo de servidores front-end ABC en Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

La metodología descrita en este documento incluye consideraciones especiales durante la fase de planeación. Para obtener más información, consulte [establecer un plan de copia de seguridad y restauración para Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Preparación para la copia de seguridad y restauración de Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Copia de seguridad de datos y configuración en Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Restauración de datos y configuración en Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Hojas de cálculo de copia de seguridad y restauración para Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

