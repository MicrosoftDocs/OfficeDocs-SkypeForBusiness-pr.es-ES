---
title: 'Lync Server 2013: tabla de medios'
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
ms.openlocfilehash: 369e1ace7e0f3f9326896373a640597360ded81d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516177"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="7a0ed-102">Tabla de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a0ed-102">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a0ed-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7a0ed-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7a0ed-p101">Cada registro representa un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a0ed-p102">No debe usarse la tabla Media para calcular la duración de los medios de una sesión. Esta tabla contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que el participante de la sesión acepta la sesión. Por lo general, EndTime implica la hora de finalización de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="7a0ed-110">Columna</span><span class="sxs-lookup"><span data-stu-id="7a0ed-110">Column</span></span></th>
<th><span data-ttu-id="7a0ed-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7a0ed-111">Data Type</span></span></th>
<th><span data-ttu-id="7a0ed-112">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="7a0ed-112">Key/Index</span></span></th>
<th><span data-ttu-id="7a0ed-113">Detalles</span><span class="sxs-lookup"><span data-stu-id="7a0ed-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a0ed-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7a0ed-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7a0ed-115">datetime</span><span class="sxs-lookup"><span data-stu-id="7a0ed-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="7a0ed-116">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="7a0ed-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7a0ed-117">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-117">Time of session request.</span></span> <span data-ttu-id="7a0ed-118">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7a0ed-119">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a0ed-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7a0ed-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7a0ed-121">entero</span><span class="sxs-lookup"><span data-stu-id="7a0ed-121">int</span></span></p></td>
<td><p><span data-ttu-id="7a0ed-122">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="7a0ed-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7a0ed-123">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-123">ID number to identify the session.</span></span> <span data-ttu-id="7a0ed-124">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7a0ed-125">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a0ed-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="7a0ed-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="7a0ed-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="7a0ed-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7a0ed-128">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="7a0ed-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7a0ed-129">Número único que identifica este tipo de medios.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-129">Unique number identifying this media type.</span></span> <span data-ttu-id="7a0ed-130">Consulte la <a href="lync-server-2013-medialist-table.md">tabla de medial en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a0ed-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="7a0ed-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7a0ed-132">datetime</span><span class="sxs-lookup"><span data-stu-id="7a0ed-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="7a0ed-133">Principal</span><span class="sxs-lookup"><span data-stu-id="7a0ed-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="7a0ed-p106">Hora a la que se envió una solicitud de medios, no la hora de inicio real de los medios. <strong>StartTime</strong> incluye el tiempo de establecimiento de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a0ed-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="7a0ed-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7a0ed-137">datetime</span><span class="sxs-lookup"><span data-stu-id="7a0ed-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a0ed-138">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7a0ed-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

