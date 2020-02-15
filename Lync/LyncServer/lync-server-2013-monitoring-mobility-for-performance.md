---
title: 'Lync Server 2013: supervisión de la movilidad para el rendimiento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 131a6a4dd6fffb3081ff2b1dee58318afd525eaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Supervisión de la movilidad para el rendimiento en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

El servicio de movilidad de Lync Server (MCX) y la API Web de comunicaciones unificadas (UCWA) aumentan la carga en los servidores front-end y los grupos de servidores front-end. Dispositivos móviles que mantienen una conexión al servidor incluso cuando la aplicación móvil está minimizada, como los dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como los dispositivos Android y Apple que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que termine la conexión al servidor cuando se minimice la aplicación móvil. A medida que aumente el uso de la movilidad, deberá supervisar el rendimiento de la movilidad para determinar cuándo debe aumentar la capacidad.

Hay varios límites que afectan al rendimiento de la movilidad:

  - Memoria disponible

  - Límite de la cola de solicitudes

  - Conexiones simultáneas

  - Longitud de la cola de IIS

Otros límites en los servidores que pueden influir en el rendimiento de la movilidad son un máximo de doce inicios de sesión simultáneos, autenticaciones, renovaciones de sesiones y finalizaciones. Estos máximos no tienen que modificarse para la mayoría de implementaciones.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Supervisión de los límites de capacidad de la memoria del servidor en Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Supervisar el uso de UCWA y del servicio de movilidad en Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configurar el servicio de movilidad para alto rendimiento en Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Supervisión de los archivos de registro de seguimiento de solicitudes de IIS en Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Contadores de rendimiento de movilidad en Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

