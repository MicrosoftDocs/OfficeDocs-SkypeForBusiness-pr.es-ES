---
title: Supervisar el uso de UCWA y del servicio de movilidad en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumen: Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server 2015.'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a><span data-ttu-id="95695-103">Supervisar el uso de UCWA y del servicio de movilidad en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="95695-103">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95695-104">**Resumen:** Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95695-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="95695-105">Debe supervisar de forma continua, la CPU y la memoria utilizada por el Skype para servicio de movilidad Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="95695-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="95695-106">Para supervisar el uso, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95695-106">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="95695-107">**Para la API web de comunicaciones unificadas (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="95695-107">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="95695-108">El proceso de trabajo de **LyncUcwa** en el Administrador de servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="95695-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="95695-109">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="95695-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="95695-110">Los contadores de rendimiento **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="95695-110">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="95695-111">Para la mayoría de las implementaciones, el uso de la CPU de UCWA tendría que estar por debajo del 15 % como promedio.</span><span class="sxs-lookup"><span data-stu-id="95695-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="95695-112">Uso de la memoria debe caer dentro de los límites descritos en el [Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server 2015](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="95695-112">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="95695-113">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="95695-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="95695-114">**LS:WEB - límite y Authentication\WEB - Nº Total de peticiones en el procesamiento de**, lo que indica el número de peticiones de web en el servidor pendientes.</span><span class="sxs-lookup"><span data-stu-id="95695-114">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="95695-115">Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.</span><span class="sxs-lookup"><span data-stu-id="95695-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="95695-116">**ASP.NET\Requests en cola** (debe ser siempre cero).</span><span class="sxs-lookup"><span data-stu-id="95695-116">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="95695-117">Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="95695-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="95695-118">**Para el servicio de movilidad (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="95695-118">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="95695-119">Los procesos de trabajo de **CSIntMcxAppPool** y **CSExtMcxAppPool** en el Administrador de servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="95695-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="95695-120">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="95695-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="95695-121">Los contadores de rendimiento **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="95695-121">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="95695-122">En la mayoría de las implementaciones, el uso de la CPU por parte del servicio Movilidad tendría que estar por debajo del 15 por ciento de media.</span><span class="sxs-lookup"><span data-stu-id="95695-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="95695-123">Uso de la memoria debe caer dentro de los límites descritos en el [Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server 2015](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="95695-123">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="95695-124">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="95695-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="95695-125">**V2.0.50727\Requests ASP.NET actual**, lo que indica el número de peticiones de web en el servidor pendientes.</span><span class="sxs-lookup"><span data-stu-id="95695-125">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="95695-126">Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.</span><span class="sxs-lookup"><span data-stu-id="95695-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="95695-127">**ASP.NET\Requests en cola** (debe ser siempre cero).</span><span class="sxs-lookup"><span data-stu-id="95695-127">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="95695-128">Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="95695-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="95695-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="95695-129">See also</span></span>

#### 

[<span data-ttu-id="95695-130">Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="95695-130">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)

