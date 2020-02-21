---
title: 'Lync Server 2013: tabla VideoClientEvent'
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
ms.openlocfilehash: a687e503b9dfd02c296e1e96d88b93c716d7c54b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="11ce4-102">Tabla VideoClientEvent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11ce4-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11ce4-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="11ce4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="11ce4-104">Cada registro contiene un evento de cliente para un punto de conexión en una videollamada.</span><span class="sxs-lookup"><span data-stu-id="11ce4-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="11ce4-105">Normalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="11ce4-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11ce4-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="11ce4-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="11ce4-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="11ce4-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11ce4-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="11ce4-111">datetime</span><span class="sxs-lookup"><span data-stu-id="11ce4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="11ce4-112">Principal</span><span class="sxs-lookup"><span data-stu-id="11ce4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="11ce4-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11ce4-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11ce4-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="11ce4-115">int</span><span class="sxs-lookup"><span data-stu-id="11ce4-115">int</span></span></p></td>
<td><p><span data-ttu-id="11ce4-116">Principal</span><span class="sxs-lookup"><span data-stu-id="11ce4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="11ce4-117">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11ce4-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11ce4-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="11ce4-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="11ce4-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="11ce4-120">Principal</span><span class="sxs-lookup"><span data-stu-id="11ce4-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="11ce4-121">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="11ce4-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11ce4-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="11ce4-123">bit</span><span class="sxs-lookup"><span data-stu-id="11ce4-123">bit</span></span></p></td>
<td><p><span data-ttu-id="11ce4-124">Principal</span><span class="sxs-lookup"><span data-stu-id="11ce4-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="11ce4-125">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="11ce4-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="11ce4-126">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="11ce4-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11ce4-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11ce4-128">Porcentaje de sesión en la que se activó el evento LowBandwidth para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="11ce4-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="11ce4-129">El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="11ce4-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11ce4-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="11ce4-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="11ce4-131">Porcentaje de sesión en la que se activó el evento ReceiveSendQuality para un estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="11ce4-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="11ce4-132">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="11ce4-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

