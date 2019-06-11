---
title: 'Lync Server 2013: copia de seguridad y restauración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0cf9f9baabd095e54373c31acd4f4522974a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Copia de seguridad y restauración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En esta sección, encontrarás los procedimientos recomendados para realizar copias de seguridad de los datos de Lync Server 2013 y de restaurarlos si tienes un error. Estas prácticas recomendadas se aplican a las siguientes situaciones:

  - Un grupo de servidores de Lync completo de cualquier tipo (servidor front-end, servidor perimetral, servidor de mediación, servidor de chat persistente o director) o un servidor individual de uno de estos grupos.

  - El servidor de administración central

  - Un servidor Standard Edition

  - Un servidor de back-end Enterprise Edition

  - Un almacén de archivos

  - Una base de datos de archivado, una base de datos de supervisión o una base de datos de chat persistente

Esta sección no incluye información sobre cómo restaurar todo un sitio o para desarrollar un sitio en espera. Para obtener información sobre cómo desarrollar una solución de recuperación ante desastres con grupos front-end emparejados, vea [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Este es el método recomendado para planear la recuperación de desastres.

Si ha implementado agrupaciones front-end emparejadas, si uno de estos grupos tiene errores y se vuelve irrecuperable, puede restaurar este grupo con un nuevo nombre de dominio completo (FQDN) de su grupo emparejado. Para obtener más información sobre los pasos necesarios para realizar esta recuperación, consulte [conmutación por error de un grupo en Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Además, si posteriormente desea volver a crear un grupo con errores e irrecuperables que formaba parte de un par front-end, puede seguir los pasos que se indican en [realizar una conmutación por error de la agrupación de front-end ABC en Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

La metodología descrita en este documento implica consideraciones especiales durante la fase de planificación. Para obtener más información, consulte [establecer un plan de copia de seguridad y restauración para Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Prepararse para la copia de seguridad y restauración de Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Copia de seguridad de datos y configuración en Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Restauración de datos y configuración en Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Copias de seguridad y restauración de hojas de cálculo para Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

