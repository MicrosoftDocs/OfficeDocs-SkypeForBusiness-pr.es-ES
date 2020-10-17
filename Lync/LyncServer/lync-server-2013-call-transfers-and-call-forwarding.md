---
title: 'Lync Server 2013: transferencias de llamadas y desvío de llamadas'
description: 'Lync Server 2013: transferencias de llamadas y desvío de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565256"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="08f49-103">Transferencias de llamadas y desvío de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f49-103">Call transfers and call forwarding in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08f49-104">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="08f49-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="08f49-105">Cuando se trata de un punto final de RTC, el enrutamiento de Location-Based analiza la ubicación del punto de conexión de calle y el extremo al que se transferirá o reenviará la llamada (es decir, el destino de transferencia o reenvío).</span><span class="sxs-lookup"><span data-stu-id="08f49-105">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="08f49-106">El enrutamiento de Location-Based determina si la llamada se debe transferir o reenviar en función de la ubicación de ambos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="08f49-106">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="08f49-107">En la tabla siguiente se muestra el escenario de un usuario de Lync en una llamada con un punto de conexión RTC y el usuario de Lync transfiere la llamada a otro usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="08f49-107">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="08f49-108">En función de la ubicación del sitio de red del extremo del cesionario, el Location-Based el enrutamiento afecta a la ruta de la transferencia o el desvío de la llamada.</span><span class="sxs-lookup"><span data-stu-id="08f49-108">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="08f49-109">Inicio de transferencia o reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="08f49-109">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08f49-110">Usuario que inicia la transferencia o el desvío de la llamada</span><span class="sxs-lookup"><span data-stu-id="08f49-110">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="08f49-111">El extremo de destino está en el mismo sitio de red que el usuario que inicia la transferencia de llamadas o el reenvío</span><span class="sxs-lookup"><span data-stu-id="08f49-111">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="08f49-112">El extremo de destino está en un sitio de red diferente a medida que el usuario inicia la transferencia de llamadas o reenvía</span><span class="sxs-lookup"><span data-stu-id="08f49-112">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="08f49-113">El extremo de destino está en un sitio de red desconocido o un sitio de red no habilitado para el enrutamiento Location-Based</span><span class="sxs-lookup"><span data-stu-id="08f49-113">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08f49-114">Usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="08f49-114">Lync user</span></span></p></td>
<td><p><span data-ttu-id="08f49-115">Se permite la transferencia o el desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="08f49-115">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="08f49-116">No se permite el desvío o la transferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="08f49-116">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="08f49-117">No se permite el desvío o la transferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="08f49-117">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="08f49-118">Por ejemplo: un usuario de Lync en una llamada con un punto de conexión RTC transfiere la llamada a otro usuario de Lync que se encuentra en el mismo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="08f49-118">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="08f49-119">En este caso, se permite la transferencia de llamadas.</span><span class="sxs-lookup"><span data-stu-id="08f49-119">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="08f49-120">En la tabla siguiente se muestra el escenario de un usuario de Lync en una llamada con otro usuario de Lync y uno de los usuarios transfiere la llamada a un extremo de RTC.</span><span class="sxs-lookup"><span data-stu-id="08f49-120">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="08f49-121">En función de la ubicación del usuario al que se transfiere la llamada, la tabla detalla cómo el enrutamiento de Location-Based afecta a la llamada.</span><span class="sxs-lookup"><span data-stu-id="08f49-121">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="08f49-122">Transferencia de llamadas o reenviar a extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="08f49-122">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08f49-123">Destino de extremo de transferencia/reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="08f49-123">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="08f49-124">Usuarios de Lync en el mismo sitio de red</span><span class="sxs-lookup"><span data-stu-id="08f49-124">Lync users in same network site</span></span></th>
<th><span data-ttu-id="08f49-125">Usuarios de Lync en sitios de red diferentes</span><span class="sxs-lookup"><span data-stu-id="08f49-125">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="08f49-126">Uno o ambos usuarios de Lync en un sitio de red o sitio de red desconocido no están habilitados para el enrutamiento Location-Based</span><span class="sxs-lookup"><span data-stu-id="08f49-126">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08f49-127">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="08f49-127">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="08f49-128">La Directiva de enrutamiento de voz del sitio del usuario transferido permite desviar o transferir las llamadas permitidas.</span><span class="sxs-lookup"><span data-stu-id="08f49-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="08f49-129">La Directiva de enrutamiento de voz del sitio del usuario transferido permite desviar o transferir las llamadas permitidas.</span><span class="sxs-lookup"><span data-stu-id="08f49-129">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="08f49-130">La Directiva de voz del usuario transferido permite desviar o transferir las llamadas solo a través de troncos no habilitados para Location-Based enrutamiento</span><span class="sxs-lookup"><span data-stu-id="08f49-130">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="08f49-131">Por ejemplo: un usuario de Lync en una llamada con otro usuario de Lync que se encuentra en el mismo sitio de red transfiere la llamada a un punto de conexión de RTC y se permite la transferencia de llamadas.</span><span class="sxs-lookup"><span data-stu-id="08f49-131">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="08f49-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08f49-132">See Also</span></span>


[<span data-ttu-id="08f49-133">Escenarios para Location-Based el enrutamiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f49-133">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

