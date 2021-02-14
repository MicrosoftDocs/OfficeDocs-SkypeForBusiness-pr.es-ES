---
title: Supervisar la movilidad para el rendimiento en Skype Empresarial Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumen: obtenga información sobre el servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816840"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="993c0-103">Supervisar la movilidad para el rendimiento en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="993c0-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="993c0-104">**Resumen:** Obtenga información sobre el servicio de movilidad (Mcx) y la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="993c0-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="993c0-105">El servicio de movilidad de Skype Empresarial Server (Mcx) y la API web de comunicaciones unificadas (UCWA) aumentan la carga en los servidores front-end y los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="993c0-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="993c0-106">Los dispositivos móviles que mantienen una conexión con el servidor incluso cuando la aplicación móvil está minimizada, como los dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como los dispositivos Android y Apple que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que finalizan su conexión con el servidor cuando la aplicación móvil está minimizada.</span><span class="sxs-lookup"><span data-stu-id="993c0-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="993c0-107">A medida que aumenta el uso de la movilidad, debe supervisar el rendimiento de la movilidad para determinar cuándo necesita aumentar la capacidad.</span><span class="sxs-lookup"><span data-stu-id="993c0-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="993c0-108">La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="993c0-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="993c0-109">Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="993c0-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="993c0-110">Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.</span><span class="sxs-lookup"><span data-stu-id="993c0-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="993c0-111">Hay varios límites que afectan al rendimiento de la movilidad:</span><span class="sxs-lookup"><span data-stu-id="993c0-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="993c0-112">Memoria disponible</span><span class="sxs-lookup"><span data-stu-id="993c0-112">Available memory</span></span>
    
- <span data-ttu-id="993c0-113">Límite de la cola de solicitudes</span><span class="sxs-lookup"><span data-stu-id="993c0-113">Request queue limit</span></span>
    
- <span data-ttu-id="993c0-114">Conexiones simultáneas</span><span class="sxs-lookup"><span data-stu-id="993c0-114">Concurrent connections</span></span>
    
- <span data-ttu-id="993c0-115">Longitud de la cola de IIS</span><span class="sxs-lookup"><span data-stu-id="993c0-115">IIS queue length</span></span>
    
<span data-ttu-id="993c0-116">Otros límites en los servidores que pueden influir en el rendimiento de la movilidad son un máximo de 12 inicios de sesión simultáneos, autenticaciones, renovaciones de sesión y terminaciones.</span><span class="sxs-lookup"><span data-stu-id="993c0-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="993c0-117">Estos máximos no tienen que modificarse para la mayoría de implementaciones.</span><span class="sxs-lookup"><span data-stu-id="993c0-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="993c0-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="993c0-118">In this section</span></span>

- [<span data-ttu-id="993c0-119">Supervisar los límites de capacidad de memoria del servidor en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="993c0-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="993c0-120">Supervisar el uso del servicio de movilidad y UCWA en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="993c0-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="993c0-121">Configurar el servicio de movilidad para un alto rendimiento en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="993c0-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="993c0-122">Supervisión de archivos de registro de seguimiento de solicitudes IIS en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="993c0-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="993c0-123">Contadores de rendimiento de movilidad en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="993c0-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

