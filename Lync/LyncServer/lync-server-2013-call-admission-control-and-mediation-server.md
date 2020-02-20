---
title: 'Lync Server 2013: control de admisión de llamadas y servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c93bdfc1133bea7d6e6c39358663c18016e0622
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="6af8f-102">Control de admisión de llamadas y servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af8f-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6af8f-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6af8f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6af8f-104">El servicio de control de admisión de llamadas (CAC), que apareció por primera vez en Lync Server 2010, administra el establecimiento de sesiones en tiempo real, en función del ancho de banda disponible, para evitar la mala calidad de la experiencia (QoE) para los usuarios de redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="6af8f-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="6af8f-105">Para admitir esta capacidad, el servidor de mediación, que proporciona la señalización y la conversión de medios entre la infraestructura de telefonía IP empresarial y una puerta de enlace o un proveedor de enlace troncal SIP, es responsable de la administración de ancho de banda para sus dos interacciones en el Lync. Lado del servidor y en el lado del puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="6af8f-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="6af8f-106">En el servicio de control de admisión de llamadas, la entidad que finaliza una llamada controla la reserva del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="6af8f-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="6af8f-107">Los pares de puertas de enlace (puerta de enlace RTC, IP-PBX, SBC) con los que interactúa el servidor de mediación en el lado de la puerta de enlace no admiten Lync Server 2013 Call Admission Control.</span><span class="sxs-lookup"><span data-stu-id="6af8f-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="6af8f-108">Por lo tanto, el servidor de mediación debe controlar las interacciones de ancho de banda en nombre de su puerta de enlace del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="6af8f-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="6af8f-109">Siempre que sea posible, el servidor de mediación reservará el ancho de banda por adelantado.</span><span class="sxs-lookup"><span data-stu-id="6af8f-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="6af8f-110">Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada realizada a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada.</span><span class="sxs-lookup"><span data-stu-id="6af8f-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="6af8f-111">Este funcionamiento puede provocar la sobresuscripción del ancho de banda, pero es la única forma de evitar las llamadas falsas.</span><span class="sxs-lookup"><span data-stu-id="6af8f-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="6af8f-112">El desvío de medios y la reserva del ancho de banda se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="6af8f-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="6af8f-113">Si se usa desvío de medios en una llamada, no se aplicará el control de admisión de llamadas en esa llamada.</span><span class="sxs-lookup"><span data-stu-id="6af8f-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="6af8f-114">En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="6af8f-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="6af8f-115">Si se usa el control de admisión de llamadas para una llamada concreta que implica el servidor de mediación, esa llamada no puede emplear la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="6af8f-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="6af8f-116">Para obtener más información sobre la omisión de medios o el control de admisión de llamadas, consulte [Planning for Media bypass in Lync server 2013](lync-server-2013-planning-for-media-bypass.md) o [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="6af8f-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

