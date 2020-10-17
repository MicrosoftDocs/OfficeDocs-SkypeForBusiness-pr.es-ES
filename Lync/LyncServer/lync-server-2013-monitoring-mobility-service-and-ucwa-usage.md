---
title: 'Lync Server 2013: supervisar el uso de UCWA y del servicio de movilidad'
description: 'Lync Server 2013: supervisar el uso de UCWA y del servicio de movilidad.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6575941faf904e46cd1f66d7226a16c88e8cbaa3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548116"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Supervisar el uso de UCWA y del servicio de movilidad en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

De manera continua, debe supervisar la CPU y la memoria que usa el servicio de movilidad de Lync Server (MCX) y la API Web de comunicaciones unificadas (UCWA). Para supervisar el uso, puede usar lo siguiente:

**Para la API Web de comunicaciones unificadas (UCWA):**

  - El proceso de trabajo **LyncUcwa** en el administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).

  - Los contadores de rendimiento de **CPU** y **Procesador**.

Para la mayoría de las implementaciones, el uso de la CPU de UCWA debe ser inferior al 15 por ciento en promedio. El uso de la memoria debe estar dentro de los límites descritos en [supervisión de los límites de capacidad de la memoria del servidor en Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Además de los contadores de uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento como ayuda para determinar cuándo un servidor está sobrecargado de solicitudes:

  - **LS: Web – autenticación \\ y limitación WEB: número total de solicitudes en procesamiento**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza 10.000, se producirá un error en las solicitudes posteriores, con el mensaje de error "503-servicio no disponible".

  - **ASP.net \\ Solicitudes en cola** (siempre debe ser cero).

<div>


> [!NOTE]  
> Si cumple o supera estos valores, debe volver a consultar y calcular la planeación de la capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios Web.



</div>

**Para el servicio de movilidad (MCX):**

  - Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en el administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).

  - Los contadores de rendimiento de **CPU** y **Procesador**.

Para la mayoría de las implementaciones, el uso de CPU del servicio de movilidad debe ser inferior al 15 por ciento, como promedio. El uso de la memoria debe estar dentro de los límites descritos en [supervisión de los límites de capacidad de la memoria del servidor en Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:

  - **ASP.net v 2.0.50727 \\ Solicita Current**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza 5.000, se producirá un error en las solicitudes posteriores con el mensaje de error "503-servicio no disponible".

  - **ASP.net \\ Solicitudes en cola** (siempre debe ser cero).

<div>


> [!NOTE]  
> Si cumple o supera estos valores, debe volver a revisar y calcular la planeación de la capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios Web.



</div>

<div>

## <a name="see-also"></a>Consulte también


[Supervisión de los límites de capacidad de la memoria del servidor en Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

