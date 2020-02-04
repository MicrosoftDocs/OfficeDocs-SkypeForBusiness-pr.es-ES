---
title: 'Lync Server 2013: Transferencia y desvío de llamadas'
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
ms.openlocfilehash: 512deaf8af03f112e35443c25e46685c42a2f2e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="8c5b3-102">Transferencia y desvío de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5b3-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c5b3-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="8c5b3-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="8c5b3-104">Cuando se trata de un punto final de RTC, el enrutamiento basado en la ubicación analiza la ubicación del extremo de la calle y el punto final al que se transferirá o desviará la llamada (es decir, el destino de transferencia/reenvío).</span><span class="sxs-lookup"><span data-stu-id="8c5b3-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="8c5b3-105">El enrutamiento basado en la ubicación determina si la llamada se debe transferir o desviar dependiendo de la ubicación de ambos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="8c5b3-106">En la tabla siguiente se muestra el escenario de un usuario de Lync en una llamada con un punto final de RTC, y el usuario de Lync transfiere la llamada a otro usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="8c5b3-107">En función de la ubicación del sitio de red del extremo del cesionario, el enrutamiento basado en la ubicación afecta al enrutamiento de la transferencia de la llamada o hacia adelante.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="8c5b3-108">Inicio de la transferencia o el desvío de la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c5b3-109">Usuario que inicia la transferencia o el desvío de la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="8c5b3-110">El extremo de destino está en el mismo sitio de red que el usuario que inicia la transferencia o el desvío de la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="8c5b3-111">El extremo de destino está en un sitio de red diferente del sitio del usuario que inicia la transferencia o el desvío de la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="8c5b3-112">El extremo de destino está en un sitio de red desconocido o el sitio de red no está habilitado para el enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="8c5b3-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c5b3-113">Usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="8c5b3-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="8c5b3-114">Se permite el desvío o la transferencia de la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="8c5b3-115">No se permite el desvío ni la transferencia de la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="8c5b3-116">No se permite el desvío ni la transferencia de la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="8c5b3-117">Por ejemplo: un usuario de Lync en una llamada con un punto final de la RTC transfiere la llamada a otro usuario de Lync que se encuentra en el mismo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="8c5b3-118">En este caso, se permite la transferencia de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="8c5b3-119">En la tabla siguiente se muestra el escenario de un usuario de Lync en una llamada con otro usuario de Lync, y uno de los usuarios transfiere la llamada a un punto final de la RTC.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="8c5b3-120">La tabla recoge los detalles de cómo el enrutamiento basado en ubicación afecta a la llamada en función de la ubicación del usuario al que se transfiere la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="8c5b3-121">Transferencia o desvío de la llamada al extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="8c5b3-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c5b3-122">Destino del extremo de la transferencia o el desvío de la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="8c5b3-123">Usuarios de Lync en el mismo sitio de red</span><span class="sxs-lookup"><span data-stu-id="8c5b3-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="8c5b3-124">Usuarios de Lync en diferentes sitios de red</span><span class="sxs-lookup"><span data-stu-id="8c5b3-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="8c5b3-125">Uno o ambos usuarios de Lync en un sitio de red o sitio de red desconocidos no están habilitados para el enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="8c5b3-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c5b3-126">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="8c5b3-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="8c5b3-127">Desvío o transferencia de llamada permitido por la directiva de enrutamiento de voz del sitio del usuario al que se transfiere la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="8c5b3-128">Desvío o transferencia de llamada permitido por la directiva de enrutamiento de voz del sitio del usuario al que se transfiere la llamada</span><span class="sxs-lookup"><span data-stu-id="8c5b3-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="8c5b3-129">Desvío o transferencia de llamada permitido por la directiva de voz del usuario al que se transfiere la llamada únicamente a través de troncos no habilitados para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="8c5b3-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="8c5b3-130">Por ejemplo: un usuario de Lync en una llamada con otro usuario de Lync que se encuentra en el mismo sitio de red transfiere la llamada a un punto final de RTC y se permite la transferencia de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8c5b3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c5b3-131">See Also</span></span>


[<span data-ttu-id="8c5b3-132">Escenarios para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5b3-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

