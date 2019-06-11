---
title: 'Lync Server 2013: supervisión de la movilidad para el rendimiento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b6cbdefcb7c78f68fe8838109dea3be5b8203d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="5b31d-102">Supervisión de la movilidad para el rendimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b31d-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b31d-103">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="5b31d-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="5b31d-104">El servicio de movilidad de Lync Server (MCX) y la API Web de comunicaciones unificadas (UCWA) aumentan la carga en los servidores front-end y en las agrupaciones front-end.</span><span class="sxs-lookup"><span data-stu-id="5b31d-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="5b31d-105">Dispositivos móviles que mantienen una conexión con el servidor incluso cuando la aplicación móvil está minimizada, como los dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como los dispositivos Apple y Android que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que finalizar la conexión con el servidor cuando se minimice la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="5b31d-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="5b31d-106">A medida que aumenta el uso de la movilidad, es preciso supervisar el rendimiento para determinar cuándo necesita aumentar su capacidad.</span><span class="sxs-lookup"><span data-stu-id="5b31d-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="5b31d-107">Hay varios límites que afectan al rendimiento de la movilidad:</span><span class="sxs-lookup"><span data-stu-id="5b31d-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="5b31d-108">Memoria disponible</span><span class="sxs-lookup"><span data-stu-id="5b31d-108">Available memory</span></span>

  - <span data-ttu-id="5b31d-109">Límite de la cola de solicitudes</span><span class="sxs-lookup"><span data-stu-id="5b31d-109">Request queue limit</span></span>

  - <span data-ttu-id="5b31d-110">Conexiones simultáneas</span><span class="sxs-lookup"><span data-stu-id="5b31d-110">Concurrent connections</span></span>

  - <span data-ttu-id="5b31d-111">Longitud de la cola de IIS</span><span class="sxs-lookup"><span data-stu-id="5b31d-111">IIS queue length</span></span>

<span data-ttu-id="5b31d-112">Otros límites en los servidores que pueden influir en el rendimiento de la movilidad son un máximo de doce inicios de sesión simultáneos, autenticaciones, renovaciones de sesión y finalizaciones.</span><span class="sxs-lookup"><span data-stu-id="5b31d-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="5b31d-113">Estos máximos no tienen que modificarse para la mayoría de implementaciones.</span><span class="sxs-lookup"><span data-stu-id="5b31d-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b31d-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5b31d-114">In This Section</span></span>

  - [<span data-ttu-id="5b31d-115">Supervisión de los límites de capacidad de memoria del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b31d-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="5b31d-116">Supervisar el uso del servicio de movilidad y de UCWA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b31d-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="5b31d-117">Configurar el servicio de movilidad para un alto rendimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b31d-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="5b31d-118">Supervisar los archivos de registro de seguimiento de solicitudes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b31d-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="5b31d-119">Contadores de rendimiento de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b31d-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

