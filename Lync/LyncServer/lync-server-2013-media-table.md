---
title: 'Lync Server 2013: Tabla Media'
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
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="17f93-102">Tabla Media en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17f93-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17f93-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="17f93-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="17f93-104">Cada registro representa un tipo de medio usado en una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="17f93-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="17f93-105">Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="17f93-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17f93-106">La tabla de medios no se debe usar para calcular la duración multimedia de una sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="17f93-107">Esta tabla contiene los detalles de señalización de intercambio de medios en una sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="17f93-108">El intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica el momento en que se envió la invitación. La hora de la invitación no significa necesariamente la hora de inicio del medio, porque los elementos multimedia solo se inician después de que la sesión acepte la sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="17f93-109">La EndTime normalmente significa la hora de finalización de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="17f93-110">Columna</span><span class="sxs-lookup"><span data-stu-id="17f93-110">Column</span></span></th>
<th><span data-ttu-id="17f93-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="17f93-111">Data Type</span></span></th>
<th><span data-ttu-id="17f93-112">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="17f93-112">Key/Index</span></span></th>
<th><span data-ttu-id="17f93-113">Detalles</span><span class="sxs-lookup"><span data-stu-id="17f93-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17f93-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="17f93-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17f93-115">datetime</span><span class="sxs-lookup"><span data-stu-id="17f93-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="17f93-116">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="17f93-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="17f93-117">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-117">Time of session request.</span></span> <span data-ttu-id="17f93-118">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="17f93-119">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17f93-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f93-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="17f93-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="17f93-121">int</span><span class="sxs-lookup"><span data-stu-id="17f93-121">int</span></span></p></td>
<td><p><span data-ttu-id="17f93-122">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="17f93-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="17f93-123">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-123">ID number to identify the session.</span></span> <span data-ttu-id="17f93-124">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="17f93-125">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17f93-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f93-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="17f93-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="17f93-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="17f93-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="17f93-128">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="17f93-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="17f93-129">Número único que identifica este tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="17f93-129">Unique number identifying this media type.</span></span> <span data-ttu-id="17f93-130">Para obtener más información, consulte la <a href="lync-server-2013-medialist-table.md">tabla medial en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17f93-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17f93-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="17f93-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17f93-132">datetime</span><span class="sxs-lookup"><span data-stu-id="17f93-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="17f93-133">Primary</span><span class="sxs-lookup"><span data-stu-id="17f93-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="17f93-134">Este es el tiempo que se envió una solicitud de medios, no la hora real de inicio de medios.</span><span class="sxs-lookup"><span data-stu-id="17f93-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="17f93-135"><strong>StartTime</strong> incluye la hora de configuración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17f93-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="17f93-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17f93-137">datetime</span><span class="sxs-lookup"><span data-stu-id="17f93-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="17f93-138">Esta es la hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="17f93-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

