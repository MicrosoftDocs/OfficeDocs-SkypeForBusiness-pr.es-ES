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
ms.openlocfilehash: 057253527615164b4b8b22a1fa13e7ea48778ee1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="56eb8-102">TraceRoute tabla en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56eb8-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56eb8-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="56eb8-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="56eb8-104">La tabla TraceRoute contiene información de enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="56eb8-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="56eb8-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="56eb8-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56eb8-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="56eb8-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="56eb8-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="56eb8-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56eb8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="56eb8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="56eb8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="56eb8-112">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="56eb8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="56eb8-113">Fecha y hora en que empezó la llamada.</span><span class="sxs-lookup"><span data-stu-id="56eb8-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56eb8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="56eb8-115">int</span><span class="sxs-lookup"><span data-stu-id="56eb8-115">int</span></span></p></td>
<td><p><span data-ttu-id="56eb8-116">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="56eb8-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="56eb8-117">Identificador único que se usa para diferenciar varias llamadas que pueden haber empezado el mismo día a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="56eb8-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56eb8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="56eb8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="56eb8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="56eb8-120">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="56eb8-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="56eb8-p102">Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="56eb8-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="56eb8-123">0: audio</span><span class="sxs-lookup"><span data-stu-id="56eb8-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="56eb8-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="56eb8-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="56eb8-125">2 – Vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="56eb8-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="56eb8-126">3 – uso compartido de aplicaciones y escritorios</span><span class="sxs-lookup"><span data-stu-id="56eb8-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56eb8-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="56eb8-128">bit</span><span class="sxs-lookup"><span data-stu-id="56eb8-128">bit</span></span></p></td>
<td><p><span data-ttu-id="56eb8-129">Principal</span><span class="sxs-lookup"><span data-stu-id="56eb8-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="56eb8-130">Extremo que ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="56eb8-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56eb8-131"><strong>Únicos</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="56eb8-132">int</span><span class="sxs-lookup"><span data-stu-id="56eb8-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56eb8-133">Salto de red.</span><span class="sxs-lookup"><span data-stu-id="56eb8-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56eb8-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="56eb8-135">int</span><span class="sxs-lookup"><span data-stu-id="56eb8-135">int</span></span></p></td>
<td><p><span data-ttu-id="56eb8-136">Externa</span><span class="sxs-lookup"><span data-stu-id="56eb8-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="56eb8-137">Identificador único de la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="56eb8-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="56eb8-138">La información de la dirección IP se almacena en la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="56eb8-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56eb8-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="56eb8-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="56eb8-140">int</span><span class="sxs-lookup"><span data-stu-id="56eb8-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56eb8-p104">Tiempo de ida y vuelta. El tiempo de ida y vuelta mide el tiempo que tarda el paquete de voz en llegar a su destino y devolver una notificación que informe de que se ha recibido.</span><span class="sxs-lookup"><span data-stu-id="56eb8-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

