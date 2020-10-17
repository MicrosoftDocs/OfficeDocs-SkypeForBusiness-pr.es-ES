---
title: 'Lync Server 2013: supervisar el uso de UCWA y del servicio de movilidad'
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
ms.openlocfilehash: 2248bbd2eea4bb9204a98b5c5805ef196cbf2015
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531803"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="b59b1-102">Supervisar el uso de UCWA y del servicio de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b59b1-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b59b1-103">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b59b1-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="b59b1-104">De manera continua, debe supervisar la CPU y la memoria que usa el servicio de movilidad de Lync Server (MCX) y la API Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="b59b1-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="b59b1-105">Para supervisar el uso, puede usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b59b1-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="b59b1-106">**Para la API Web de comunicaciones unificadas (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="b59b1-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="b59b1-107">El proceso de trabajo **LyncUcwa** en el administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b59b1-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b59b1-108">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="b59b1-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="b59b1-109">Los contadores de rendimiento de **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="b59b1-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="b59b1-110">Para la mayoría de las implementaciones, el uso de la CPU de UCWA debe ser inferior al 15 por ciento en promedio.</span><span class="sxs-lookup"><span data-stu-id="b59b1-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="b59b1-111">El uso de la memoria debe estar dentro de los límites descritos en [supervisión de los límites de capacidad de la memoria del servidor en Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="b59b1-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="b59b1-112">Además de los contadores de uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento como ayuda para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="b59b1-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="b59b1-113">**LS: Web – autenticación \\ y limitación WEB: número total de solicitudes en procesamiento**, que indica el número de solicitudes web pendientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b59b1-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b59b1-114">Cuando este contador alcanza 10.000, se producirá un error en las solicitudes posteriores, con el mensaje de error "503-servicio no disponible".</span><span class="sxs-lookup"><span data-stu-id="b59b1-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="b59b1-115">**ASP.net \\ Solicitudes en cola** (siempre debe ser cero).</span><span class="sxs-lookup"><span data-stu-id="b59b1-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b59b1-116">Si cumple o supera estos valores, debe volver a consultar y calcular la planeación de la capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="b59b1-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="b59b1-117">**Para el servicio de movilidad (MCX):**</span><span class="sxs-lookup"><span data-stu-id="b59b1-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="b59b1-118">Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en el administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b59b1-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b59b1-119">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="b59b1-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="b59b1-120">Los contadores de rendimiento de **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="b59b1-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="b59b1-121">Para la mayoría de las implementaciones, el uso de CPU del servicio de movilidad debe ser inferior al 15 por ciento, como promedio.</span><span class="sxs-lookup"><span data-stu-id="b59b1-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="b59b1-122">El uso de la memoria debe estar dentro de los límites descritos en [supervisión de los límites de capacidad de la memoria del servidor en Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="b59b1-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="b59b1-123">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="b59b1-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="b59b1-124">**ASP.net v 2.0.50727 \\ Solicita Current**, que indica el número de solicitudes web pendientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b59b1-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b59b1-125">Cuando este contador alcanza 5.000, se producirá un error en las solicitudes posteriores con el mensaje de error "503-servicio no disponible".</span><span class="sxs-lookup"><span data-stu-id="b59b1-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="b59b1-126">**ASP.net \\ Solicitudes en cola** (siempre debe ser cero).</span><span class="sxs-lookup"><span data-stu-id="b59b1-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b59b1-127">Si cumple o supera estos valores, debe volver a revisar y calcular la planeación de la capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="b59b1-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b59b1-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b59b1-128">See Also</span></span>


[<span data-ttu-id="b59b1-129">Supervisión de los límites de capacidad de la memoria del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b59b1-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

