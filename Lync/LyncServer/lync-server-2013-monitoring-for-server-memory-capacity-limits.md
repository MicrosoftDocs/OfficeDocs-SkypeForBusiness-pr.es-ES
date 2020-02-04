---
title: 'Lync Server 2013: supervisión de los límites de capacidad de memoria del servidor'
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
ms.openlocfilehash: e5c9746240335b1c66606da24edf6ffa2a0e7bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="2d444-102">Supervisión de los límites de capacidad de memoria del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d444-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d444-103">_**Última modificación del tema:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="2d444-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="2d444-104">La información de este tema que se refiere a la planificación de capacidad solo se aplica a los clientes móviles de Lync 2010 y al servicio de movilidad (MCX).</span><span class="sxs-lookup"><span data-stu-id="2d444-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="2d444-105">La planificación de capacidad de la API Web de comunicaciones unificadas (UCWA), usada por los clientes móviles de Lync 2013, se proporciona en Lync Server 2013, la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="2d444-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="2d444-106">Dos contadores de rendimiento de movilidad pueden ayudarle a determinar su uso actual y a ayudarle a planear la capacidad del servicio de movilidad de Lync Server 2013 (MCX), así como a supervisar el uso de memoria para UCWA.</span><span class="sxs-lookup"><span data-stu-id="2d444-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="2d444-107">Para UCWA, la categoría de contador es **LS:WEB - UCWA**.</span><span class="sxs-lookup"><span data-stu-id="2d444-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="2d444-108">En el caso de Mobility Service (Mcx), los contadores pertenecen a la categoría **LS:WEB - Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="2d444-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="2d444-109">Los contadores que se supervisan son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d444-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="2d444-110">**Número de sesiones actualmente activas con suscripciones de presencia activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service (Mcx) que tienen suscripciones de presencia activas (número de usuarios móviles conectados siempre)</span><span class="sxs-lookup"><span data-stu-id="2d444-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="2d444-111">**Número de sesiones actualmente activas**, que es el número actual de extremos registrados a través de UCWA o Mobility Service</span><span class="sxs-lookup"><span data-stu-id="2d444-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="2d444-112">Si la diferencia entre **Número de sesiones actualmente activas con suscripciones de presencia activas** y **Número de sesiones actualmente activas** es pequeña con el transcurso del tiempo, significa que la mayoría de los usuarios de dispositivos móviles tiene un dispositivo conectado siempre, como un dispositivo móvil Android o Nokia (solo para Mcx).</span><span class="sxs-lookup"><span data-stu-id="2d444-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="2d444-113">UCWA los dispositivos siempre conectados incluyen Apple y Android que ejecutan clientes móviles de Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="2d444-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="2d444-114">Si **Número de sesiones actualmente activas** es muy superior a **Número de sesiones actualmente activas con suscripciones de presencia activas**, quiere decir que hay más usuarios que usan un dispositivo de extremo en segundo plano, como un dispositivo Apple iOS o Windows Phone con Mcx.</span><span class="sxs-lookup"><span data-stu-id="2d444-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="2d444-115">(Windows Phone es el único cliente móvil de Lync 2013 que se registrará como this).</span><span class="sxs-lookup"><span data-stu-id="2d444-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="2d444-116">Debe establecer un límite en el **recuento de sesiones activas actualmente con suscripciones de presencia activas** y contadores de rendimiento de **recuento de sesiones actualmente activos** según el uso previsto, los resultados de la planificación de capacidad y la supervisión continua de los contadores de servicio de movilidad y otros servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2d444-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="2d444-117">Los límites que establezca necesitan permitirle evaluar la capacidad del servidor y generar alertas cuando dicha capacidad se exceda.</span><span class="sxs-lookup"><span data-stu-id="2d444-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="2d444-118">Para determinar los límites adecuados, primero debe determinar cuánta memoria está disponible en el servidor front-end para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="2d444-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="2d444-119">Supervise los contadores para determinar cuándo hay que planear la capacidad adicional según la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d444-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="2d444-120">Memoria total usada por el servicio de movilidad de MCX (MB) = 164 + (400 + 134) \* /1024 **recuento de sesiones activas con suscripciones de presencia activas** + 400/1024 \* (recuento de**sesiones actualmente** activas; **recuento de sesiones activas actualmente con suscripciones de presencia activas**)</span><span class="sxs-lookup"><span data-stu-id="2d444-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d444-121">La calculadora de capacidad 2010 de Microsoft Lync Server es una hoja de cálculo que se rellenó con todas las fórmulas que permiten a un planeador determinar cuáles serán los requisitos para los servidores, como la CPU, la memoria y el disco duro.</span><span class="sxs-lookup"><span data-stu-id="2d444-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="2d444-122">Puede descargar la hoja de cálculo y un documento asociado en:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="2d444-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="2d444-123">El servidor front-end necesita suficiente memoria disponible para admitir el servicio de movilidad en situaciones de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="2d444-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="2d444-124">Puede supervisar la memoria disponible actual en el servidor front-end mediante el contador **memoria\\Mbytes disponibles** , o mediante la ecuación mencionada anteriormente, para planear la cantidad de memoria que espera que use el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="2d444-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="2d444-125">Si la cantidad de memoria disponible en el servidor front-end es inferior a 1.500 MB cuando se planea la cantidad de usuarios de movilidad esperada, necesita agregar más hardware para admitir el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="2d444-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="2d444-126">Para obtener más información, vea [supervisión de la movilidad para el rendimiento en Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="2d444-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2d444-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d444-127">See Also</span></span>


[<span data-ttu-id="2d444-128">Supervisión de la movilidad para el rendimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d444-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

