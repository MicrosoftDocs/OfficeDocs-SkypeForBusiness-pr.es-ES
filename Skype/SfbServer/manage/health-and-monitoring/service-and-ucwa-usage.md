---
title: Supervisar el uso de servicio de movilidad y UCWA en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumen: Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.'
ms.openlocfilehash: 780d8fca068a78ec08312551d03dbdb5327df90e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975952"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="8f720-103">Supervisar el uso de servicio de movilidad y UCWA en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8f720-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="8f720-104">**Resumen:** Administrar el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f720-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="8f720-105">Compatibilidad con MCX para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8f720-105">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8f720-106">Los usuarios deben actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="8f720-106">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="8f720-107">De forma continuada, debe supervisar la CPU y memoria que se usa en el Skype para el servicio de movilidad de Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="8f720-107">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="8f720-108">Para supervisar el uso, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f720-108">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="8f720-109">**Para la API web de comunicaciones unificadas (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="8f720-109">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="8f720-110">El proceso de trabajo de **LyncUcwa** en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="8f720-110">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="8f720-111">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="8f720-111">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="8f720-112">Los contadores de rendimiento **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="8f720-112">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="8f720-113">Para la mayoría de las implementaciones, el uso de la CPU de UCWA tendría que estar por debajo del 15 % como promedio.</span><span class="sxs-lookup"><span data-stu-id="8f720-113">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="8f720-114">El uso de memoria debe estar dentro de los límites que se describen en el [Monitor para los límites de capacidad de memoria de servidor en Skype para Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="8f720-114">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="8f720-115">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="8f720-115">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="8f720-116">**LS:WEB - limitación y Authentication\WEB - solicitudes totales en el procesamiento**, que indica el número de solicitudes web en el servidor pendientes.</span><span class="sxs-lookup"><span data-stu-id="8f720-116">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="8f720-117">Cuando este contador alcanza las 10.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.</span><span class="sxs-lookup"><span data-stu-id="8f720-117">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="8f720-118">**ASP. net\requests Queued** (debería ser siempre cero).</span><span class="sxs-lookup"><span data-stu-id="8f720-118">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8f720-119">Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="8f720-119">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="8f720-120">**Para el servicio de movilidad (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="8f720-120">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="8f720-121">Los procesos de trabajo **CSIntMcxAppPool** y **CSExtMcxAppPool** en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="8f720-121">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="8f720-122">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="8f720-122">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="8f720-123">Los contadores de rendimiento **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="8f720-123">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="8f720-124">En la mayoría de las implementaciones, el uso de la CPU por parte del servicio Movilidad tendría que estar por debajo del 15 por ciento de media.</span><span class="sxs-lookup"><span data-stu-id="8f720-124">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="8f720-125">El uso de memoria debe estar dentro de los límites que se describen en el [Monitor para los límites de capacidad de memoria de servidor en Skype para Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="8f720-125">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="8f720-126">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="8f720-126">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="8f720-127">**ASP.NET v2.0.50727\Requests actual**, lo que indica el número de solicitudes web en el servidor pendientes.</span><span class="sxs-lookup"><span data-stu-id="8f720-127">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="8f720-128">Cuando este contador alcanza las 5.000, las solicitudes posteriores provocarán el error “503 - Servicio no disponible”.</span><span class="sxs-lookup"><span data-stu-id="8f720-128">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="8f720-129">**ASP. net\requests Queued** (debería ser siempre cero).</span><span class="sxs-lookup"><span data-stu-id="8f720-129">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8f720-130">Si cumple o excede estos valores, repase y calcule de nuevo la planeación de capacidad para corregir el tamaño de CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="8f720-130">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="8f720-131">Compatibilidad con MCX para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8f720-131">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8f720-132">Los usuarios deben actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="8f720-132">Your users will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8f720-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f720-133">See also</span></span>

[<span data-ttu-id="8f720-134">Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8f720-134">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)