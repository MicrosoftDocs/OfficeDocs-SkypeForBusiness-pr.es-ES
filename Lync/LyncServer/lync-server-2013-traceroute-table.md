---
title: 'Lync Server 2013: tabla TraceRoute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691b7576d59511428400d14a3ff21109525dc5a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="d87be-102">Tabla TraceRoute en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d87be-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d87be-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="d87be-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="d87be-104">La tabla TraceRoute contiene información de enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="d87be-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="d87be-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d87be-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d87be-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d87be-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d87be-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d87be-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d87be-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d87be-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d87be-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d87be-112">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d87be-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d87be-113">Fecha y hora en que comenzó la llamada.</span><span class="sxs-lookup"><span data-stu-id="d87be-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d87be-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d87be-115">int</span><span class="sxs-lookup"><span data-stu-id="d87be-115">int</span></span></p></td>
<td><p><span data-ttu-id="d87be-116">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d87be-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d87be-117">Identificador único que se usa para distinguir entre varias llamadas que podrían haber comenzado en la misma fecha y al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d87be-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d87be-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d87be-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="d87be-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d87be-120">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d87be-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d87be-121">Representa el tipo de línea de vídeo que se usa en la llamada.</span><span class="sxs-lookup"><span data-stu-id="d87be-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="d87be-122">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="d87be-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d87be-123">0: audio</span><span class="sxs-lookup"><span data-stu-id="d87be-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="d87be-124">1: vídeo</span><span class="sxs-lookup"><span data-stu-id="d87be-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="d87be-125">2-video panorámico</span><span class="sxs-lookup"><span data-stu-id="d87be-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="d87be-126">3: uso compartido de aplicaciones y escritorio</span><span class="sxs-lookup"><span data-stu-id="d87be-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d87be-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="d87be-128">bit</span><span class="sxs-lookup"><span data-stu-id="d87be-128">bit</span></span></p></td>
<td><p><span data-ttu-id="d87be-129">Primary</span><span class="sxs-lookup"><span data-stu-id="d87be-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="d87be-130">Extremo que hizo la llamada.</span><span class="sxs-lookup"><span data-stu-id="d87be-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d87be-131"><strong>Únicos</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="d87be-132">int</span><span class="sxs-lookup"><span data-stu-id="d87be-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d87be-133">Salto de red/</span><span class="sxs-lookup"><span data-stu-id="d87be-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d87be-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d87be-135">int</span><span class="sxs-lookup"><span data-stu-id="d87be-135">int</span></span></p></td>
<td><p><span data-ttu-id="d87be-136">Extranjero</span><span class="sxs-lookup"><span data-stu-id="d87be-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d87be-137">Identificador único de la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="d87be-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="d87be-138">La información de la dirección IP se almacena en la <a href="lync-server-2013-ipaddress-table.md">tabla direcciónIP de Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d87be-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d87be-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="d87be-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="d87be-140">int</span><span class="sxs-lookup"><span data-stu-id="d87be-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d87be-141">Tiempo de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="d87be-141">Roundtrip time.</span></span> <span data-ttu-id="d87be-142">El tiempo de ida y vuelta mide la cantidad de tiempo que se tarda en llegar un paquete de voz a su destino y, a continuación, se envía una notificación de que se ha recibido.</span><span class="sxs-lookup"><span data-stu-id="d87be-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

