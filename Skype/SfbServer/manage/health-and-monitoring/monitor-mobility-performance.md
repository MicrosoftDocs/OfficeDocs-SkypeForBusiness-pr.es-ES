---
title: Movilidad de Monitor de rendimiento en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumen: Obtenga información sobre el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.'
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990640"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="32944-103">Movilidad de Monitor de rendimiento en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="32944-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="32944-104">**Resumen:** Información sobre el servicio de movilidad (Mcx) y la Web de comunicaciones unificadas (UCWA) de la API de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="32944-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="32944-105">El Skype para el servicio de movilidad de Business Server (Mcx) y la API de Web de comunicaciones unificadas (UCWA) aumentan la carga de los grupos de servidores Front-End y servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="32944-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="32944-106">Dispositivos móviles que mantienen una conexión con el servidor incluso cuando se minimiza la aplicación móvil, como dispositivos Android y Nokia ejecuta Lync 2010 Mobile, así como los dispositivos Android y Apple que ejecutan Lync Mobile de 2013, imponen una carga mayor que los dispositivos que finalizar su conexión con el servidor cuando se minimiza la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="32944-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="32944-107">A medida que aumenta el uso de la movilidad, es preciso supervisar el rendimiento para determinar cuándo necesita aumentar su capacidad.</span><span class="sxs-lookup"><span data-stu-id="32944-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="32944-108">Compatibilidad con MCX para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="32944-108">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="32944-109">Los usuarios deben actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="32944-109">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="32944-110">Hay varios límites que afectan al rendimiento de la movilidad:</span><span class="sxs-lookup"><span data-stu-id="32944-110">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="32944-111">Memoria disponible</span><span class="sxs-lookup"><span data-stu-id="32944-111">Available memory</span></span>
    
- <span data-ttu-id="32944-112">Límite de la cola de solicitudes</span><span class="sxs-lookup"><span data-stu-id="32944-112">Request queue limit</span></span>
    
- <span data-ttu-id="32944-113">Conexiones simultáneas</span><span class="sxs-lookup"><span data-stu-id="32944-113">Concurrent connections</span></span>
    
- <span data-ttu-id="32944-114">Longitud de la cola de IIS</span><span class="sxs-lookup"><span data-stu-id="32944-114">IIS queue length</span></span>
    
<span data-ttu-id="32944-p103">Otros límites en los servidores que pueden afectar al rendimiento de la movilidad son un máximo de 12 inicios de sesión simultáneos, autenticaciones, renovaciones y finalizaciones de sesión. Estos máximos no tienen que modificarse para la mayoría de implementaciones.</span><span class="sxs-lookup"><span data-stu-id="32944-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="32944-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="32944-117">In this section</span></span>

- [<span data-ttu-id="32944-118">Monitor de los límites de capacidad de memoria de servidor en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="32944-118">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="32944-119">Supervisar el uso de servicio de movilidad y UCWA en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="32944-119">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="32944-120">Configurar el servicio de movilidad para alto rendimiento en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="32944-120">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="32944-121">Supervisión de solicitudes de IIS el seguimiento de los archivos de registro en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="32944-121">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="32944-122">Contadores de rendimiento de movilidad en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="32944-122">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

