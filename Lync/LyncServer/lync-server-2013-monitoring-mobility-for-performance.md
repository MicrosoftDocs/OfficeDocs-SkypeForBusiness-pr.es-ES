---
title: 'Lync Server 2013: supervisión de la movilidad para el rendimiento'
description: 'Lync Server 2013: supervisión de la movilidad para el rendimiento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562906"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="e828b-103">Supervisión de la movilidad para el rendimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e828b-103">Monitoring mobility for performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e828b-104">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="e828b-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="e828b-105">El servicio de movilidad de Lync Server (MCX) y la API Web de comunicaciones unificadas (UCWA) aumentan la carga en los servidores front-end y los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e828b-105">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="e828b-106">Dispositivos móviles que mantienen una conexión al servidor, incluso cuando la aplicación móvil está minimizada, como los dispositivos Android y Nokia que ejecutan Lync 2010 Mobile, así como los dispositivos Android y Apple que ejecutan Lync 2013 Mobile, imponen una carga mayor que los dispositivos que terminan su conexión al servidor cuando se minimiza la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="e828b-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="e828b-107">A medida que aumente el uso de la movilidad, deberá supervisar el rendimiento de la movilidad para determinar cuándo debe aumentar la capacidad.</span><span class="sxs-lookup"><span data-stu-id="e828b-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="e828b-108">Hay varios límites que afectan al rendimiento de la movilidad:</span><span class="sxs-lookup"><span data-stu-id="e828b-108">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="e828b-109">Memoria disponible</span><span class="sxs-lookup"><span data-stu-id="e828b-109">Available memory</span></span>

  - <span data-ttu-id="e828b-110">Límite de la cola de solicitudes</span><span class="sxs-lookup"><span data-stu-id="e828b-110">Request queue limit</span></span>

  - <span data-ttu-id="e828b-111">Conexiones simultáneas</span><span class="sxs-lookup"><span data-stu-id="e828b-111">Concurrent connections</span></span>

  - <span data-ttu-id="e828b-112">Longitud de la cola de IIS</span><span class="sxs-lookup"><span data-stu-id="e828b-112">IIS queue length</span></span>

<span data-ttu-id="e828b-113">Otros límites en los servidores que pueden influir en el rendimiento de la movilidad son un máximo de doce inicios de sesión simultáneos, autenticaciones, renovaciones de sesiones y finalizaciones.</span><span class="sxs-lookup"><span data-stu-id="e828b-113">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="e828b-114">Estos máximos no tienen que modificarse para la mayoría de implementaciones.</span><span class="sxs-lookup"><span data-stu-id="e828b-114">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e828b-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e828b-115">In This Section</span></span>

  - [<span data-ttu-id="e828b-116">Supervisión de los límites de capacidad de la memoria del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e828b-116">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="e828b-117">Supervisar el uso de UCWA y del servicio de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e828b-117">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="e828b-118">Configurar el servicio de movilidad para alto rendimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e828b-118">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="e828b-119">Supervisión de los archivos de registro de seguimiento de solicitudes de IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e828b-119">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="e828b-120">Contadores de rendimiento de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e828b-120">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

