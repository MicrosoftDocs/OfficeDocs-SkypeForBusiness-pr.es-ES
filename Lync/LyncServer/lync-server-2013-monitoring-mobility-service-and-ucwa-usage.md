---
title: 'Lync Server 2013: supervisar el servicio de movilidad y el uso de UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Supervisar el uso del servicio de movilidad y de UCWA en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

De manera continua, debe supervisar la CPU y la memoria que usa el servicio de movilidad de Lync Server (MCX) y la API Web de comunicaciones unificadas (UCWA). Para supervisar el uso, haga lo siguiente:

**Para la API web de comunicaciones unificadas (UCWA):**

  - El proceso de trabajo **LyncUcwa** en el administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).

  - Los contadores de rendimiento **CPU** y **Procesador**.

Para la mayoría de las implementaciones, el uso de la CPU de UCWA tendría que estar por debajo del 15 % como promedio. El uso de memoria debe estar dentro de los límites descritos en [supervisión de los límites de capacidad de memoria del servidor en Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:

  - **LS: Web: Web de limitación y\\autenticación: total de solicitudes en procesamiento**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.

  - **Solicitudes\\de ASP.net en cola** (debe ser siempre cero).

<div>


> [!NOTE]  
> Si cumple o supera estos valores, debe volver a visitar y calcular su plan de capacidad para la determinación correcta de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios Web.



</div>

**Para el servicio de movilidad (Mcx):**

  - Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en el administrador de Internet Information Services (IIS). En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).

  - Los contadores de rendimiento **CPU** y **Procesador**.

En la mayoría de las implementaciones, el uso de la CPU por parte del servicio Movilidad tendría que estar por debajo del 15 por ciento de media. El uso de memoria debe estar dentro de los límites descritos en [supervisión de los límites de capacidad de memoria del servidor en Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:

  - **ASP.net v 2.0.50727\\solicita Current**, que indica el número de solicitudes web pendientes en el servidor. Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.

  - **Solicitudes\\de ASP.net en cola** (debe ser siempre cero).

<div>


> [!NOTE]  
> Si cumple o supera estos valores, debe volver a revisar y recalcular su plan de capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios Web.



</div>

<div>

## <a name="see-also"></a>Vea también


[Supervisión de los límites de capacidad de memoria del servidor en Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

