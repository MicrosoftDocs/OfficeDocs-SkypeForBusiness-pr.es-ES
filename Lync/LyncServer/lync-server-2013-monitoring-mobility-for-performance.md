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
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Supervisión de la movilidad para el rendimiento en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

El servicio de movilidad de Lync Server (MCX) y la API Web de comunicaciones unificadas (UCWA) aumentan la carga en los servidores front-end y en las agrupaciones front-end. Dispositivos móviles que mantienen una conexión con el servidor incluso cuando la aplicación móvil está minimizada, como los dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como los dispositivos Apple y Android que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que finalizar la conexión con el servidor cuando se minimice la aplicación móvil. A medida que aumenta el uso de la movilidad, es preciso supervisar el rendimiento para determinar cuándo necesita aumentar su capacidad.

Hay varios límites que afectan al rendimiento de la movilidad:

  - Memoria disponible

  - Límite de la cola de solicitudes

  - Conexiones simultáneas

  - Longitud de la cola de IIS

Otros límites en los servidores que pueden influir en el rendimiento de la movilidad son un máximo de doce inicios de sesión simultáneos, autenticaciones, renovaciones de sesión y finalizaciones. Estos máximos no tienen que modificarse para la mayoría de implementaciones.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Supervisión de los límites de capacidad de memoria del servidor en Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Supervisar el uso del servicio de movilidad y de UCWA en Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configurar el servicio de movilidad para un alto rendimiento en Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Supervisar los archivos de registro de seguimiento de solicitudes en Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Contadores de rendimiento de movilidad en Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

