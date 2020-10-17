---
title: 'Lync Server 2013: tabla VideoClientEvent'
description: 'Lync Server 2013: tabla VideoClientEvent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae73ac2548e838241febe60a2d31f80983b01de5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568496"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="5ed2c-103">Tabla VideoClientEvent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ed2c-103">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ed2c-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5ed2c-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5ed2c-105">Cada registro contiene un evento de cliente para un punto de conexión en una videollamada.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="5ed2c-106">Normalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ed2c-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5ed2c-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5ed2c-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5ed2c-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ed2c-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ed2c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5ed2c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5ed2c-113">Principal</span><span class="sxs-lookup"><span data-stu-id="5ed2c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ed2c-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ed2c-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5ed2c-116">entero</span><span class="sxs-lookup"><span data-stu-id="5ed2c-116">int</span></span></p></td>
<td><p><span data-ttu-id="5ed2c-117">Principal</span><span class="sxs-lookup"><span data-stu-id="5ed2c-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ed2c-118">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ed2c-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5ed2c-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="5ed2c-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5ed2c-121">Principal</span><span class="sxs-lookup"><span data-stu-id="5ed2c-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ed2c-122">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ed2c-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="5ed2c-124">bit</span><span class="sxs-lookup"><span data-stu-id="5ed2c-124">bit</span></span></p></td>
<td><p><span data-ttu-id="5ed2c-125">Principal</span><span class="sxs-lookup"><span data-stu-id="5ed2c-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ed2c-126">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="5ed2c-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="5ed2c-127">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="5ed2c-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ed2c-128"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-128"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ed2c-129">Porcentaje de sesión en la que se activó el evento LowBandwidth para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="5ed2c-129">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="5ed2c-130">El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ed2c-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5ed2c-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5ed2c-132">Porcentaje de sesión en la que se activó el evento ReceiveSendQuality para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="5ed2c-132">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="5ed2c-133">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="5ed2c-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

