---
title: 'Lync Server 2013: Tabla ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="a6cd2-102">Tabla ConferenceUris en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6cd2-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6cd2-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="a6cd2-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="a6cd2-104">La tabla ConfereneUris es una tabla de soporte que almacena una lista de los distintos URI de conferencia que participaron en sesiones de conferencia registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a6cd2-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="a6cd2-105">Cada registro de la tabla representa un URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a6cd2-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6cd2-106">Columna</span><span class="sxs-lookup"><span data-stu-id="a6cd2-106">Column</span></span></th>
<th><span data-ttu-id="a6cd2-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a6cd2-107">Data Type</span></span></th>
<th><span data-ttu-id="a6cd2-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="a6cd2-108">Key/Index</span></span></th>
<th><span data-ttu-id="a6cd2-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="a6cd2-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6cd2-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="a6cd2-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="a6cd2-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a6cd2-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a6cd2-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a6cd2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6cd2-113">Marca de tiempo, usada internamente.</span><span class="sxs-lookup"><span data-stu-id="a6cd2-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6cd2-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="a6cd2-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6cd2-115">int</span><span class="sxs-lookup"><span data-stu-id="a6cd2-115">int</span></span></p></td>
<td><p><span data-ttu-id="a6cd2-116">Primary</span><span class="sxs-lookup"><span data-stu-id="a6cd2-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6cd2-117">Número único que identifica este URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a6cd2-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6cd2-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="a6cd2-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a6cd2-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a6cd2-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6cd2-120">URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a6cd2-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6cd2-121"><strong>Comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="a6cd2-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="a6cd2-122">int</span><span class="sxs-lookup"><span data-stu-id="a6cd2-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6cd2-123">Suma de comprobación de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="a6cd2-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="a6cd2-124">Se usa para aumentar la velocidad de las búsquedas de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a6cd2-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6cd2-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a6cd2-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a6cd2-126">int</span><span class="sxs-lookup"><span data-stu-id="a6cd2-126">int</span></span></p></td>
<td><p><span data-ttu-id="a6cd2-127">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a6cd2-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a6cd2-128">Tipo de URI, como conf: chat para conferencias de mensajería instantánea o conf: audio-video para conferencias de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="a6cd2-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="a6cd2-129">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en la tabla de 2013 de Lync Server</a> .</span><span class="sxs-lookup"><span data-stu-id="a6cd2-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

