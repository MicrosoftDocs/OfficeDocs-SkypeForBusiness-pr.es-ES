---
title: 'Lync Server 2013: supervisión de los límites de capacidad de la memoria del servidor'
description: 'Lync Server 2013: supervisión de los límites de capacidad de la memoria del servidor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6561908af2c8f2f7b5fb9e347cc6247f7ca6642e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562056"
---
# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="990f4-103">Supervisión de los límites de capacidad de la memoria del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="990f4-103">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="990f4-104">_**Última modificación del tema:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="990f4-104">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="990f4-105">La información de este tema que se refiere a la planeación de la capacidad solo se aplica a los clientes móviles de Lync 2010 y al servicio de movilidad (MCX).</span><span class="sxs-lookup"><span data-stu-id="990f4-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="990f4-106">La planeación de capacidad para la API Web de comunicaciones unificadas (UCWA), usada por los clientes móviles de Lync 2013, se proporciona en Lync Server 2013, la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="990f4-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="990f4-107">Hay dos contadores de rendimiento de movilidad que pueden ayudarle a determinar su uso actual y a planear la capacidad del servicio de movilidad de Lync Server 2013 (MCX), así como supervisar el uso de memoria para UCWA.</span><span class="sxs-lookup"><span data-stu-id="990f4-107">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="990f4-108">Para UCWA, la categoría de contador es **LS: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="990f4-108">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="990f4-109">En el caso del servicio de movilidad (MCX), los contadores están bajo la categoría **LS: web-Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="990f4-109">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="990f4-110">Los contadores que se van a supervisar son:</span><span class="sxs-lookup"><span data-stu-id="990f4-110">The counters to monitor are:</span></span>

  - <span data-ttu-id="990f4-111">**Recuento de sesiones actualmente activas con suscripciones de presencia activa**, que es el número actual de extremos registrados a través de UCWA o el servicio de movilidad (MCX) que tienen suscripciones de presencia activas (número de usuarios móviles conectados siempre)</span><span class="sxs-lookup"><span data-stu-id="990f4-111">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="990f4-112">**Recuento de sesiones actualmente activas**, que es el número actual de extremos registrados a través de UCWA o el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="990f4-112">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="990f4-113">Si la diferencia entre el **número de sesiones actualmente activas con suscripciones de presencia activa** y el **recuento de sesiones actualmente activas** es pequeño con el tiempo, significa que la mayoría de los usuarios de dispositivos móviles tienen un dispositivo conectado siempre, como un dispositivo móvil Android o Nokia (solo para MCX).</span><span class="sxs-lookup"><span data-stu-id="990f4-113">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="990f4-114">Los dispositivos de UCWA Always-Connected incluyen los dispositivos Apple y Android que ejecutan clientes móviles de Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="990f4-114">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="990f4-115">Si el **recuento de sesiones actualmente activas** es mucho mayor que el **recuento de sesiones actualmente activas con suscripciones de presencia activa**, esto indica que más usuarios están usando un dispositivo de extremo en segundo plano, como un dispositivo iOS de Apple o Windows Phone en MCX.</span><span class="sxs-lookup"><span data-stu-id="990f4-115">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="990f4-116">(Windows Phone es el único cliente móvil de Lync 2013 que se registrará como this).</span><span class="sxs-lookup"><span data-stu-id="990f4-116">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="990f4-117">Debe establecer un límite en el **recuento de sesiones actualmente activas con suscripciones de presencia activa** y contadores de rendimiento de **recuento de sesiones actualmente** en función del uso previsto, los resultados de la planeación de la capacidad y la supervisión continua del servicio de movilidad y otros contadores de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="990f4-117">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="990f4-118">Los límites que establezca deben permitirle evaluar la capacidad del servidor y generar alertas cuando se supere la capacidad.</span><span class="sxs-lookup"><span data-stu-id="990f4-118">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="990f4-119">Para determinar los límites apropiados, primero debe determinar la cantidad de memoria disponible en el servidor front-end para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="990f4-119">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="990f4-120">Supervise los contadores para determinar cuándo es necesario planear la capacidad extra, de acuerdo con la siguiente fórmula:</span><span class="sxs-lookup"><span data-stu-id="990f4-120">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="990f4-121">Memoria total usada por el servicio de movilidad de MCX (MB) = 164 + (400 + 134)/1024 \* **recuento de sesiones actualmente activas con suscripciones de presencia activa** + 400/1024 (recuento de \* **sesiones actualmente activas** ; **número de sesiones actualmente activas con suscripciones de presencia activa**)</span><span class="sxs-lookup"><span data-stu-id="990f4-121">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="990f4-122">La calculadora de capacidad 2010 de Microsoft Lync Server es una hoja de cálculo que se rellena previamente con todas las fórmulas que permiten a un planificador determinar cuáles serán los requisitos para los servidores, incluidos la CPU, la memoria y el disco duro.</span><span class="sxs-lookup"><span data-stu-id="990f4-122">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="990f4-123">Puede descargar la hoja de cálculo y un documento asociado en: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="990f4-123">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="990f4-124">El servidor front-end necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="990f4-124">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="990f4-125">Puede supervisar la memoria disponible actual en el servidor front-end mediante el contador **memoria \\ Mbytes disponibles** o mediante la ecuación mencionada anteriormente, para planear la cantidad de memoria que espera que use el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="990f4-125">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="990f4-126">Si la cantidad de memoria disponible en el servidor front-end es inferior a 1.500 MB cuando planea el número previsto de usuarios de movilidad, necesita agregar más hardware para admitir el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="990f4-126">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="990f4-127">Para obtener más información, consulte [Monitoring Mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="990f4-127">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="990f4-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="990f4-128">See Also</span></span>


[<span data-ttu-id="990f4-129">Supervisión de la movilidad para el rendimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="990f4-129">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

