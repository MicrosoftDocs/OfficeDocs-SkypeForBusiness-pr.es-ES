---
title: Supervisar el uso de servicio de movilidad y UCWA en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumen: Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.'
ms.openlocfilehash: ddbb8ee4915c64781d059f8495c7e0bd46e57fc6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887135"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="13160-103">Supervisar el uso de servicio de movilidad y UCWA en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="13160-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="13160-104">**Resumen:** Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="13160-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="13160-105">Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="13160-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="13160-106">Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos.</span><span class="sxs-lookup"><span data-stu-id="13160-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="13160-107">Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="13160-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="13160-108">De forma continuada, debe supervisar la CPU y memoria que se usa en el Skype para el servicio de movilidad de Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="13160-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="13160-109">Para supervisar el uso, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="13160-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="13160-110">**Para la API web de comunicaciones unificadas (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="13160-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="13160-111">El proceso de trabajo de **LyncUcwa** en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="13160-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="13160-112">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="13160-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="13160-113">Los contadores de rendimiento **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="13160-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="13160-114">Para la mayoría de las implementaciones, el uso de la CPU de UCWA tendría que estar por debajo del 15 % como promedio.</span><span class="sxs-lookup"><span data-stu-id="13160-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="13160-115">El uso de memoria debe estar dentro de los límites que se describen en el [Monitor para los límites de capacidad de memoria de servidor en Skype para Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="13160-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="13160-116">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="13160-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="13160-117">**LS:WEB - limitación y Authentication\WEB - solicitudes totales en el procesamiento**, que indica el número de solicitudes web en el servidor pendientes.</span><span class="sxs-lookup"><span data-stu-id="13160-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="13160-118">Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.</span><span class="sxs-lookup"><span data-stu-id="13160-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="13160-119">**ASP.NET\Requests Queued** (siempre tendría que ser cero).</span><span class="sxs-lookup"><span data-stu-id="13160-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="13160-120">Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="13160-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="13160-121">**Para el servicio de movilidad (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="13160-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="13160-122">Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="13160-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="13160-123">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="13160-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="13160-124">Los contadores de rendimiento **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="13160-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="13160-125">En la mayoría de las implementaciones, el uso de la CPU por parte del servicio Movilidad tendría que estar por debajo del 15 por ciento de media.</span><span class="sxs-lookup"><span data-stu-id="13160-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="13160-126">El uso de memoria debe estar dentro de los límites que se describen en el [Monitor para los límites de capacidad de memoria de servidor en Skype para Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="13160-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="13160-127">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="13160-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="13160-128">**ASP.NET v2.0.50727\Requests Current**, que indica el número de solicitudes web pendientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="13160-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="13160-129">Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.</span><span class="sxs-lookup"><span data-stu-id="13160-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="13160-130">**ASP.NET\Requests Queued** (siempre tendría que ser cero).</span><span class="sxs-lookup"><span data-stu-id="13160-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="13160-131">Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="13160-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="13160-132">Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="13160-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="13160-133">Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos.</span><span class="sxs-lookup"><span data-stu-id="13160-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="13160-134">Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="13160-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="13160-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="13160-135">See also</span></span>

[<span data-ttu-id="13160-136">Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="13160-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
