---
title: Supervisar la movilidad para el rendimiento en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumen: Obtenga información sobre el servicio de movilidad (MCX) y la API Web de comunicaciones unificadas (UCWA) en Skype empresarial Server.'
ms.openlocfilehash: 7b8340d90b5e1fa18c4dfaa7d61f986344ccbb33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279924"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="bc84e-103">Supervisar la movilidad para el rendimiento en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc84e-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="bc84e-104">**Resumen:** Obtenga más información sobre el servicio de movilidad (MCX) y la API Web de comunicaciones unificadas (UCWA) en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bc84e-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="bc84e-105">El servicio de movilidad de Skype empresarial Server (MCX) y la API Web de comunicaciones unificadas (UCWA) aumentan la carga en los servidores front-end y en las agrupaciones front-end.</span><span class="sxs-lookup"><span data-stu-id="bc84e-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="bc84e-106">Dispositivos móviles que mantienen una conexión con el servidor incluso cuando la aplicación móvil está minimizada, como los dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como los dispositivos Apple y Android que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que finalizar la conexión con el servidor cuando se minimice la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="bc84e-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="bc84e-107">A medida que aumenta el uso de la movilidad, es preciso supervisar el rendimiento para determinar cuándo necesita aumentar su capacidad.</span><span class="sxs-lookup"><span data-stu-id="bc84e-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="bc84e-108">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bc84e-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="bc84e-109">Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="bc84e-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="bc84e-110">Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="bc84e-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="bc84e-111">Hay varios límites que afectan al rendimiento de la movilidad:</span><span class="sxs-lookup"><span data-stu-id="bc84e-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="bc84e-112">Memoria disponible</span><span class="sxs-lookup"><span data-stu-id="bc84e-112">Available memory</span></span>
    
- <span data-ttu-id="bc84e-113">Límite de la cola de solicitudes</span><span class="sxs-lookup"><span data-stu-id="bc84e-113">Request queue limit</span></span>
    
- <span data-ttu-id="bc84e-114">Conexiones simultáneas</span><span class="sxs-lookup"><span data-stu-id="bc84e-114">Concurrent connections</span></span>
    
- <span data-ttu-id="bc84e-115">Longitud de la cola de IIS</span><span class="sxs-lookup"><span data-stu-id="bc84e-115">IIS queue length</span></span>
    
<span data-ttu-id="bc84e-p103">Otros límites en los servidores que pueden afectar al rendimiento de la movilidad son un máximo de 12 inicios de sesión simultáneos, autenticaciones, renovaciones y finalizaciones de sesión. Estos máximos no tienen que modificarse para la mayoría de implementaciones.</span><span class="sxs-lookup"><span data-stu-id="bc84e-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="bc84e-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bc84e-118">In this section</span></span>

- [<span data-ttu-id="bc84e-119">Supervisar los límites de capacidad de memoria del servidor en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc84e-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="bc84e-120">Supervisar el servicio de movilidad y el uso de UCWA en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc84e-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="bc84e-121">Configurar el servicio de movilidad para un alto rendimiento en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc84e-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="bc84e-122">Supervisar los archivos de registro de seguimiento de solicitudes de IIS en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc84e-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="bc84e-123">Contadores de rendimiento de movilidad en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bc84e-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

