---
title: 'Lync Server 2013: tabla ConferenceUris'
description: 'Lync Server 2013: tabla ConferenceUris.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566746"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="07278-103">Tabla ConferenceUris en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07278-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07278-104">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="07278-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="07278-p101">La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="07278-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07278-107">Columna</span><span class="sxs-lookup"><span data-stu-id="07278-107">Column</span></span></th>
<th><span data-ttu-id="07278-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="07278-108">Data Type</span></span></th>
<th><span data-ttu-id="07278-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="07278-109">Key/Index</span></span></th>
<th><span data-ttu-id="07278-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="07278-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07278-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="07278-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="07278-112">datetime</span><span class="sxs-lookup"><span data-stu-id="07278-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="07278-113">Principal</span><span class="sxs-lookup"><span data-stu-id="07278-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="07278-114">Marca de tiempo, interna utilizada.</span><span class="sxs-lookup"><span data-stu-id="07278-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07278-115"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="07278-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="07278-116">entero</span><span class="sxs-lookup"><span data-stu-id="07278-116">int</span></span></p></td>
<td><p><span data-ttu-id="07278-117">Principal</span><span class="sxs-lookup"><span data-stu-id="07278-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="07278-118">Número único que identifica esta URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="07278-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07278-119"><strong>Uri</strong></span><span class="sxs-lookup"><span data-stu-id="07278-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="07278-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="07278-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="07278-121">URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="07278-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07278-122"><strong>Suma de comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="07278-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="07278-123">entero</span><span class="sxs-lookup"><span data-stu-id="07278-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="07278-p102">Suma de comprobación de ConferenceUri. Se utiliza para acelerar las búsquedas en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="07278-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07278-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="07278-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="07278-127">entero</span><span class="sxs-lookup"><span data-stu-id="07278-127">int</span></span></p></td>
<td><p><span data-ttu-id="07278-128">Externa</span><span class="sxs-lookup"><span data-stu-id="07278-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="07278-129">Tipo de URI, como por ejemplo conf:chat para conferencia de mensajería instantánea, o conf:audio-video para conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="07278-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="07278-130">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en la tabla de Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="07278-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

