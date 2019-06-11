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

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="c5264-102">Supervisar el uso del servicio de movilidad y de UCWA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5264-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5264-103">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="c5264-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="c5264-104">De manera continua, debe supervisar la CPU y la memoria que usa el servicio de movilidad de Lync Server (MCX) y la API Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="c5264-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="c5264-105">Para supervisar el uso, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5264-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="c5264-106">**Para la API web de comunicaciones unificadas (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="c5264-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="c5264-107">El proceso de trabajo **LyncUcwa** en el administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c5264-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="c5264-108">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="c5264-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="c5264-109">Los contadores de rendimiento **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="c5264-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="c5264-110">Para la mayoría de las implementaciones, el uso de la CPU de UCWA tendría que estar por debajo del 15 % como promedio.</span><span class="sxs-lookup"><span data-stu-id="c5264-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="c5264-111">El uso de memoria debe estar dentro de los límites descritos en [supervisión de los límites de capacidad de memoria del servidor en Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c5264-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="c5264-112">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="c5264-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="c5264-113">**LS: Web: Web de limitación y\\autenticación: total de solicitudes en procesamiento**, que indica el número de solicitudes web pendientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c5264-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="c5264-114">Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.</span><span class="sxs-lookup"><span data-stu-id="c5264-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="c5264-115">**Solicitudes\\de ASP.net en cola** (debe ser siempre cero).</span><span class="sxs-lookup"><span data-stu-id="c5264-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5264-116">Si cumple o supera estos valores, debe volver a visitar y calcular su plan de capacidad para la determinación correcta de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="c5264-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="c5264-117">**Para el servicio de movilidad (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="c5264-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="c5264-118">Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en el administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c5264-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="c5264-119">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="c5264-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="c5264-120">Los contadores de rendimiento **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="c5264-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="c5264-121">En la mayoría de las implementaciones, el uso de la CPU por parte del servicio Movilidad tendría que estar por debajo del 15 por ciento de media.</span><span class="sxs-lookup"><span data-stu-id="c5264-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="c5264-122">El uso de memoria debe estar dentro de los límites descritos en [supervisión de los límites de capacidad de memoria del servidor en Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c5264-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="c5264-123">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="c5264-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="c5264-124">**ASP.net v 2.0.50727\\solicita Current**, que indica el número de solicitudes web pendientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c5264-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="c5264-125">Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.</span><span class="sxs-lookup"><span data-stu-id="c5264-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="c5264-126">**Solicitudes\\de ASP.net en cola** (debe ser siempre cero).</span><span class="sxs-lookup"><span data-stu-id="c5264-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5264-127">Si cumple o supera estos valores, debe volver a revisar y recalcular su plan de capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="c5264-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5264-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5264-128">See Also</span></span>


[<span data-ttu-id="c5264-129">Supervisión de los límites de capacidad de memoria del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5264-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

