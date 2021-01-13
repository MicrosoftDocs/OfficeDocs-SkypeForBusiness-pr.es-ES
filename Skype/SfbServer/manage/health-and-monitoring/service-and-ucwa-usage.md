---
title: Supervisar el uso del servicio de movilidad y UCWA en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumen: administre el servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814250"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="e5042-103">Supervisar el uso del servicio de movilidad y UCWA en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e5042-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="e5042-104">**Resumen:** Administrar el servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e5042-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="e5042-105">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5042-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e5042-106">Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="e5042-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e5042-107">Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="e5042-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="e5042-108">De forma continua, debe supervisar la CPU y la memoria que usan el servicio de movilidad de Skype Empresarial Server (Mcx) y la API web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="e5042-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="e5042-109">Para supervisar el uso, puede usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5042-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="e5042-110">**Para la API web de comunicaciones unificadas (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="e5042-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="e5042-111">Proceso **de trabajo de LyncUcwa** en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="e5042-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="e5042-112">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="e5042-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="e5042-113">Los contadores de rendimiento de **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="e5042-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="e5042-114">Para la mayoría de las implementaciones, el uso de CPU de UCWA debe ser inferior al 15 por ciento de media.</span><span class="sxs-lookup"><span data-stu-id="e5042-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="e5042-115">El uso de memoria debe estar dentro de los límites descritos en Monitor para los límites de capacidad de memoria del [servidor en Skype Empresarial Server.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="e5042-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="e5042-116">Además de los contadores de uso de cpu y memoria, puede usar los siguientes contadores de rendimiento para ayudar a determinar cuándo un servidor está sobrecargado con solicitudes:</span><span class="sxs-lookup"><span data-stu-id="e5042-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="e5042-117">**LS:WEB: limitación y autenticación\WEB:** solicitudes totales en procesamiento, que indica el número de solicitudes web pendientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e5042-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="e5042-118">Cuando este contador alcanza las 10.000, se producirá un error en las solicitudes posteriores, con el mensaje de error "503 - Servicio no disponible".</span><span class="sxs-lookup"><span data-stu-id="e5042-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="e5042-119">**ASP.NET\Requests Queued** (debería ser siempre cero)</span><span class="sxs-lookup"><span data-stu-id="e5042-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e5042-120">Si cumple o supera estos valores, debe revisar y volver a calcular la planeación de capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="e5042-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="e5042-121">**Para el servicio de movilidad (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="e5042-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="e5042-122">Los **procesos de trabajo CSIntMcxAppPool** y **CSExtMcxAppPool** en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="e5042-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="e5042-123">En el panel **Procesos de trabajo**, mire las columnas **% de CPU** y **Bytes privados (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="e5042-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="e5042-124">Los contadores de rendimiento de **CPU** y **Procesador**.</span><span class="sxs-lookup"><span data-stu-id="e5042-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="e5042-125">Para la mayoría de las implementaciones, el uso de CPU del servicio de movilidad debe ser inferior al 15 por ciento, como promedio.</span><span class="sxs-lookup"><span data-stu-id="e5042-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="e5042-126">El uso de memoria debe estar dentro de los límites descritos en Monitor para los límites de capacidad de memoria del [servidor en Skype Empresarial Server.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="e5042-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="e5042-127">Además de los contadores del uso de la CPU y de la memoria, puede usar los siguientes contadores de rendimiento de ASP.NET para determinar cuándo un servidor está sobrecargado de solicitudes:</span><span class="sxs-lookup"><span data-stu-id="e5042-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="e5042-128">**ASP.NET v2.0.50727\Requests Current**, que indica el número de solicitudes web pendientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e5042-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="e5042-129">Cuando este contador alcanza las 5.000, se producirá un error en las solicitudes posteriores con el mensaje de error "503 - Servicio no disponible".</span><span class="sxs-lookup"><span data-stu-id="e5042-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="e5042-130">**ASP.NET\Requests Queued** (debería ser siempre cero)</span><span class="sxs-lookup"><span data-stu-id="e5042-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e5042-131">Si cumple o supera estos valores, debe revisar y volver a compilar la planeación de capacidad para el tamaño correcto de la CPU, el número de núcleos y la memoria de los equipos que hospedan los servicios web.</span><span class="sxs-lookup"><span data-stu-id="e5042-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="e5042-132">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5042-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e5042-133">Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="e5042-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e5042-134">Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="e5042-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e5042-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5042-135">See also</span></span>

[<span data-ttu-id="e5042-136">Supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e5042-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
