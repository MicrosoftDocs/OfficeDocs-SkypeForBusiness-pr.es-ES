---
title: 'Lync Server 2013: tabla ConferenceUris'
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
ms.openlocfilehash: e9142be1b2d46a7d7634394970d07dfa450a22e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529177"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="27c2a-102">Tabla ConferenceUris en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27c2a-102">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27c2a-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="27c2a-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="27c2a-p101">La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="27c2a-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27c2a-106">Columna</span><span class="sxs-lookup"><span data-stu-id="27c2a-106">Column</span></span></th>
<th><span data-ttu-id="27c2a-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="27c2a-107">Data Type</span></span></th>
<th><span data-ttu-id="27c2a-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="27c2a-108">Key/Index</span></span></th>
<th><span data-ttu-id="27c2a-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="27c2a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27c2a-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="27c2a-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="27c2a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="27c2a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="27c2a-112">Principal</span><span class="sxs-lookup"><span data-stu-id="27c2a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="27c2a-113">Marca de tiempo, interna utilizada.</span><span class="sxs-lookup"><span data-stu-id="27c2a-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c2a-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="27c2a-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="27c2a-115">entero</span><span class="sxs-lookup"><span data-stu-id="27c2a-115">int</span></span></p></td>
<td><p><span data-ttu-id="27c2a-116">Principal</span><span class="sxs-lookup"><span data-stu-id="27c2a-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="27c2a-117">Número único que identifica esta URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="27c2a-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27c2a-118"><strong>Uri</strong></span><span class="sxs-lookup"><span data-stu-id="27c2a-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="27c2a-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="27c2a-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27c2a-120">URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="27c2a-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c2a-121"><strong>Suma de comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="27c2a-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="27c2a-122">entero</span><span class="sxs-lookup"><span data-stu-id="27c2a-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27c2a-p102">Suma de comprobación de ConferenceUri. Se utiliza para acelerar las búsquedas en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="27c2a-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27c2a-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="27c2a-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="27c2a-126">entero</span><span class="sxs-lookup"><span data-stu-id="27c2a-126">int</span></span></p></td>
<td><p><span data-ttu-id="27c2a-127">Externa</span><span class="sxs-lookup"><span data-stu-id="27c2a-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="27c2a-128">Tipo de URI, como por ejemplo conf:chat para conferencia de mensajería instantánea, o conf:audio-video para conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="27c2a-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="27c2a-129">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en la tabla de Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="27c2a-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

