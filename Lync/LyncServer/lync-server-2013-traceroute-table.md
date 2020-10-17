---
title: 'Lync Server 2013: tabla TraceRoute'
description: 'Lync Server 2013: tabla TraceRoute.'
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
ms.openlocfilehash: 8af33e572065fbab1eaaaef684997e7f95edaed9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549066"
---
# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="51de5-103">TraceRoute tabla en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51de5-103">TraceRoute table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51de5-104">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="51de5-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="51de5-105">La tabla TraceRoute contiene información de enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="51de5-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="51de5-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51de5-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51de5-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="51de5-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="51de5-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="51de5-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51de5-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51de5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="51de5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="51de5-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="51de5-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="51de5-114">Fecha y hora en que empezó la llamada.</span><span class="sxs-lookup"><span data-stu-id="51de5-114">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51de5-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51de5-116">entero</span><span class="sxs-lookup"><span data-stu-id="51de5-116">int</span></span></p></td>
<td><p><span data-ttu-id="51de5-117">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="51de5-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="51de5-118">Identificador único que se usa para diferenciar varias llamadas que pueden haber empezado el mismo día a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="51de5-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51de5-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="51de5-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="51de5-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51de5-121">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="51de5-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="51de5-p102">Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="51de5-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="51de5-124">0: audio</span><span class="sxs-lookup"><span data-stu-id="51de5-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="51de5-125">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="51de5-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="51de5-126">2 – Vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="51de5-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="51de5-127">3 – uso compartido de aplicaciones y escritorios</span><span class="sxs-lookup"><span data-stu-id="51de5-127">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51de5-128"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-128"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="51de5-129">bit</span><span class="sxs-lookup"><span data-stu-id="51de5-129">bit</span></span></p></td>
<td><p><span data-ttu-id="51de5-130">Principal</span><span class="sxs-lookup"><span data-stu-id="51de5-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="51de5-131">Extremo que ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="51de5-131">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51de5-132"><strong>Únicos</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-132"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="51de5-133">entero</span><span class="sxs-lookup"><span data-stu-id="51de5-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="51de5-134">Salto de red.</span><span class="sxs-lookup"><span data-stu-id="51de5-134">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51de5-135"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-135"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="51de5-136">entero</span><span class="sxs-lookup"><span data-stu-id="51de5-136">int</span></span></p></td>
<td><p><span data-ttu-id="51de5-137">Externa</span><span class="sxs-lookup"><span data-stu-id="51de5-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51de5-138">Identificador único de la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="51de5-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="51de5-139">La información de la dirección IP se almacena en la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="51de5-139">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51de5-140"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="51de5-140"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="51de5-141">entero</span><span class="sxs-lookup"><span data-stu-id="51de5-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="51de5-p104">Tiempo de ida y vuelta. El tiempo de ida y vuelta mide el tiempo que tarda el paquete de voz en llegar a su destino y devolver una notificación que informe de que se ha recibido.</span><span class="sxs-lookup"><span data-stu-id="51de5-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

