---
title: 'Lync Server 2013: tabla de medios'
description: 'Lync Server 2013: tabla de medios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e30d1f91c59b8e3aa7915fc0d513618d0f709f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558036"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="55e0b-103">Tabla de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55e0b-103">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55e0b-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="55e0b-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="55e0b-p101">Cada registro representa un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="55e0b-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55e0b-p102">No debe usarse la tabla Media para calcular la duración de los medios de una sesión. Esta tabla contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que el participante de la sesión acepta la sesión. Por lo general, EndTime implica la hora de finalización de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="55e0b-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55e0b-111">Columna</span><span class="sxs-lookup"><span data-stu-id="55e0b-111">Column</span></span></th>
<th><span data-ttu-id="55e0b-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="55e0b-112">Data Type</span></span></th>
<th><span data-ttu-id="55e0b-113">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="55e0b-113">Key/Index</span></span></th>
<th><span data-ttu-id="55e0b-114">Detalles</span><span class="sxs-lookup"><span data-stu-id="55e0b-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55e0b-115"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="55e0b-115"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="55e0b-116">datetime</span><span class="sxs-lookup"><span data-stu-id="55e0b-116">datetime</span></span></p></td>
<td><p><span data-ttu-id="55e0b-117">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="55e0b-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="55e0b-118">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="55e0b-118">Time of session request.</span></span> <span data-ttu-id="55e0b-119">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="55e0b-119">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="55e0b-120">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="55e0b-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55e0b-121"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="55e0b-121"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="55e0b-122">entero</span><span class="sxs-lookup"><span data-stu-id="55e0b-122">int</span></span></p></td>
<td><p><span data-ttu-id="55e0b-123">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="55e0b-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="55e0b-124">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="55e0b-124">ID number to identify the session.</span></span> <span data-ttu-id="55e0b-125">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="55e0b-125">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="55e0b-126">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="55e0b-126">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55e0b-127"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="55e0b-127"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="55e0b-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="55e0b-128">tinyint</span></span></p></td>
<td><p><span data-ttu-id="55e0b-129">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="55e0b-129">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="55e0b-130">Número único que identifica este tipo de medios.</span><span class="sxs-lookup"><span data-stu-id="55e0b-130">Unique number identifying this media type.</span></span> <span data-ttu-id="55e0b-131">Consulte la <a href="lync-server-2013-medialist-table.md">tabla de medial en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="55e0b-131">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55e0b-132"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="55e0b-132"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="55e0b-133">datetime</span><span class="sxs-lookup"><span data-stu-id="55e0b-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="55e0b-134">Principal</span><span class="sxs-lookup"><span data-stu-id="55e0b-134">Primary</span></span></p></td>
<td><p><span data-ttu-id="55e0b-p106">Hora a la que se envió una solicitud de medios, no la hora de inicio real de los medios. <strong>StartTime</strong> incluye el tiempo de establecimiento de la sesión.</span><span class="sxs-lookup"><span data-stu-id="55e0b-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55e0b-137"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="55e0b-137"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="55e0b-138">datetime</span><span class="sxs-lookup"><span data-stu-id="55e0b-138">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="55e0b-139">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="55e0b-139">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

