---
title: 'Lync Server 2013: tabla TraceRoute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="92ee8-102">Tabla TraceRoute en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92ee8-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92ee8-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="92ee8-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="92ee8-104">La tabla TraceRoute contiene información de enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="92ee8-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="92ee8-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="92ee8-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92ee8-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="92ee8-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="92ee8-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="92ee8-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92ee8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="92ee8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="92ee8-112">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="92ee8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="92ee8-113">Fecha y hora en que comenzó la llamada.</span><span class="sxs-lookup"><span data-stu-id="92ee8-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92ee8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee8-115">int</span><span class="sxs-lookup"><span data-stu-id="92ee8-115">int</span></span></p></td>
<td><p><span data-ttu-id="92ee8-116">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="92ee8-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="92ee8-117">Identificador único que se usa para distinguir entre varias llamadas que podrían haber comenzado en la misma fecha y al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="92ee8-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92ee8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="92ee8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="92ee8-120">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="92ee8-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="92ee8-121">Representa el tipo de línea de vídeo que se usa en la llamada.</span><span class="sxs-lookup"><span data-stu-id="92ee8-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="92ee8-122">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="92ee8-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="92ee8-123">0: audio</span><span class="sxs-lookup"><span data-stu-id="92ee8-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="92ee8-124">1: vídeo</span><span class="sxs-lookup"><span data-stu-id="92ee8-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="92ee8-125">2-video panorámico</span><span class="sxs-lookup"><span data-stu-id="92ee8-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="92ee8-126">3: uso compartido de aplicaciones y escritorio</span><span class="sxs-lookup"><span data-stu-id="92ee8-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92ee8-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee8-128">bit</span><span class="sxs-lookup"><span data-stu-id="92ee8-128">bit</span></span></p></td>
<td><p><span data-ttu-id="92ee8-129">Primary</span><span class="sxs-lookup"><span data-stu-id="92ee8-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="92ee8-130">Extremo que hizo la llamada.</span><span class="sxs-lookup"><span data-stu-id="92ee8-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92ee8-131"><strong>Únicos</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee8-132">int</span><span class="sxs-lookup"><span data-stu-id="92ee8-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92ee8-133">Salto de red/</span><span class="sxs-lookup"><span data-stu-id="92ee8-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92ee8-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee8-135">int</span><span class="sxs-lookup"><span data-stu-id="92ee8-135">int</span></span></p></td>
<td><p><span data-ttu-id="92ee8-136">Extranjero</span><span class="sxs-lookup"><span data-stu-id="92ee8-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="92ee8-137">Identificador único de la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="92ee8-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="92ee8-138">La información de la dirección IP se almacena en la <a href="lync-server-2013-ipaddress-table.md">tabla direcciónIP de Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="92ee8-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92ee8-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="92ee8-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee8-140">int</span><span class="sxs-lookup"><span data-stu-id="92ee8-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92ee8-141">Tiempo de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="92ee8-141">Roundtrip time.</span></span> <span data-ttu-id="92ee8-142">El tiempo de ida y vuelta mide la cantidad de tiempo que se tarda en llegar un paquete de voz a su destino y, a continuación, se envía una notificación de que se ha recibido.</span><span class="sxs-lookup"><span data-stu-id="92ee8-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

