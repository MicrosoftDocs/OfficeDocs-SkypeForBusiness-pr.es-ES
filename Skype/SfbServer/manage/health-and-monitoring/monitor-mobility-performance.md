---
title: Supervisar la movilidad para el rendimiento en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumen: Conozca el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="e53ac-103">Supervisar la movilidad para el rendimiento en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e53ac-103">Monitor mobility for performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e53ac-104">**Resumen:** Conozca el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e53ac-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e53ac-105">El Skype para servicio de movilidad Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA) aumentan la carga de grupos de servidores frontales y Front-End.</span><span class="sxs-lookup"><span data-stu-id="e53ac-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="e53ac-106">Los dispositivos móviles que mantienen una conexión con el servidor, incluso cuando se minimiza la aplicación móvil, como los dispositivos Android y Nokia ejecutan Lync 2010 Mobile, así como los dispositivos Android y Apple con Lync Mobile de 2013, imponen una carga mayor que los dispositivos que terminar su conexión con el servidor cuando se minimiza la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="e53ac-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="e53ac-107">A medida que aumenta el uso de la movilidad, es preciso supervisar el rendimiento para determinar cuándo necesita aumentar su capacidad.</span><span class="sxs-lookup"><span data-stu-id="e53ac-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>
  
<span data-ttu-id="e53ac-108">Hay varios límites que afectan al rendimiento de la movilidad:</span><span class="sxs-lookup"><span data-stu-id="e53ac-108">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="e53ac-109">Memoria disponible</span><span class="sxs-lookup"><span data-stu-id="e53ac-109">Available memory</span></span>
    
- <span data-ttu-id="e53ac-110">Límite de la cola de solicitudes</span><span class="sxs-lookup"><span data-stu-id="e53ac-110">Request queue limit</span></span>
    
- <span data-ttu-id="e53ac-111">Conexiones simultáneas</span><span class="sxs-lookup"><span data-stu-id="e53ac-111">Concurrent connections</span></span>
    
- <span data-ttu-id="e53ac-112">Longitud de la cola de IIS</span><span class="sxs-lookup"><span data-stu-id="e53ac-112">IIS queue length</span></span>
    
<span data-ttu-id="e53ac-p102">Otros límites en los servidores que pueden afectar al rendimiento de la movilidad son un máximo de 12 inicios de sesión simultáneos, autenticaciones, renovaciones y finalizaciones de sesión. Estos máximos no tienen que modificarse para la mayoría de implementaciones.</span><span class="sxs-lookup"><span data-stu-id="e53ac-p102">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e53ac-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e53ac-115">In this section</span></span>

- [<span data-ttu-id="e53ac-116">Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e53ac-116">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="e53ac-117">Supervisar el uso de servicios de movilidad y UCWA en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e53ac-117">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="e53ac-118">Configurar el servicio de movilidad de alto rendimiento de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e53ac-118">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>](configure-service.md)
    
- [<span data-ttu-id="e53ac-119">Archivos de registro de seguimiento de Skype de peticiones de IIS supervisión para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e53ac-119">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="e53ac-120">Contadores de rendimiento de movilidad en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e53ac-120">Mobility performance counters in Skype for Business Server 2015</span></span>](performance-counters.md)
    

