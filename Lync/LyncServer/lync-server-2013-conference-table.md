---
title: 'Lync Server 2013: tabla de conferencia'
description: 'Lync Server 2013: tabla de conferencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565725b527399cb3be55c649dfd74d8bcb5f13a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550666"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="740b6-103">Tabla de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740b6-103">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="740b6-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="740b6-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="740b6-p101">La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="740b6-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="740b6-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="740b6-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="740b6-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="740b6-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="740b6-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="740b6-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="740b6-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="740b6-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="740b6-111"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="740b6-111"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="740b6-112">entero</span><span class="sxs-lookup"><span data-stu-id="740b6-112">int</span></span></p></td>
<td><p><span data-ttu-id="740b6-113">Principal</span><span class="sxs-lookup"><span data-stu-id="740b6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="740b6-114">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="740b6-114">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="740b6-115"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="740b6-115"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="740b6-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="740b6-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="740b6-117">singular</span><span class="sxs-lookup"><span data-stu-id="740b6-117">unique</span></span></p></td>
<td><p><span data-ttu-id="740b6-118">ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="740b6-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="740b6-119"><strong>Suma de comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="740b6-119"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="740b6-120">entero</span><span class="sxs-lookup"><span data-stu-id="740b6-120">int</span></span></p></td>
<td><p><span data-ttu-id="740b6-121">index</span><span class="sxs-lookup"><span data-stu-id="740b6-121">index</span></span></p></td>
<td><p><span data-ttu-id="740b6-p102">Suma de comprobación del URI de conferencia. Para uso interno.</span><span class="sxs-lookup"><span data-stu-id="740b6-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="740b6-124"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="740b6-124"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="740b6-125">datetime</span><span class="sxs-lookup"><span data-stu-id="740b6-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="740b6-126">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="740b6-126">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

