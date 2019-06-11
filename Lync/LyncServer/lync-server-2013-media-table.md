---
title: 'Lync Server 2013: Tabla Media'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8b3aaff56e782307f3146fdcee7d4410340198
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="9f4e0-102">Tabla Media en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f4e0-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f4e0-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9f4e0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9f4e0-104">Cada registro representa un tipo de medio usado en una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="9f4e0-105">Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f4e0-106">La tabla de medios no se debe usar para calcular la duración multimedia de una sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="9f4e0-107">Esta tabla contiene los detalles de señalización de intercambio de medios en una sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="9f4e0-108">El intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica el momento en que se envió la invitación. La hora de la invitación no significa necesariamente la hora de inicio del medio, porque los elementos multimedia solo se inician después de que la sesión acepte la sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="9f4e0-109">La EndTime normalmente significa la hora de finalización de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="9f4e0-110">Columna</span><span class="sxs-lookup"><span data-stu-id="9f4e0-110">Column</span></span></th>
<th><span data-ttu-id="9f4e0-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9f4e0-111">Data Type</span></span></th>
<th><span data-ttu-id="9f4e0-112">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="9f4e0-112">Key/Index</span></span></th>
<th><span data-ttu-id="9f4e0-113">Detalles</span><span class="sxs-lookup"><span data-stu-id="9f4e0-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f4e0-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9f4e0-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9f4e0-115">datetime</span><span class="sxs-lookup"><span data-stu-id="9f4e0-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f4e0-116">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="9f4e0-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f4e0-117">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-117">Time of session request.</span></span> <span data-ttu-id="9f4e0-118">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9f4e0-119">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9f4e0-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f4e0-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9f4e0-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9f4e0-121">int</span><span class="sxs-lookup"><span data-stu-id="9f4e0-121">int</span></span></p></td>
<td><p><span data-ttu-id="9f4e0-122">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="9f4e0-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f4e0-123">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-123">ID number to identify the session.</span></span> <span data-ttu-id="9f4e0-124">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9f4e0-125">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9f4e0-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f4e0-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="9f4e0-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="9f4e0-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f4e0-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f4e0-128">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="9f4e0-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f4e0-129">Número único que identifica este tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-129">Unique number identifying this media type.</span></span> <span data-ttu-id="9f4e0-130">Para obtener más información, consulte la <a href="lync-server-2013-medialist-table.md">tabla medial en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9f4e0-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f4e0-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="9f4e0-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9f4e0-132">datetime</span><span class="sxs-lookup"><span data-stu-id="9f4e0-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f4e0-133">Primary</span><span class="sxs-lookup"><span data-stu-id="9f4e0-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="9f4e0-134">Este es el tiempo que se envió una solicitud de medios, no la hora real de inicio de medios.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="9f4e0-135"><strong>StartTime</strong> incluye la hora de configuración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f4e0-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9f4e0-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9f4e0-137">datetime</span><span class="sxs-lookup"><span data-stu-id="9f4e0-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f4e0-138">Esta es la hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9f4e0-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

