---
title: 'Lync Server 2013: Tabla Conference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f57f7baf017507da44677cc475c99d192fe868f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="fb53e-102">Tabla Conference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb53e-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb53e-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fb53e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fb53e-104">La tabla de conferencia es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fb53e-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="fb53e-105">Cada registro representa una sesión de conferencia o de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="fb53e-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb53e-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="fb53e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fb53e-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="fb53e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fb53e-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="fb53e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fb53e-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="fb53e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb53e-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="fb53e-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fb53e-111">int</span><span class="sxs-lookup"><span data-stu-id="fb53e-111">int</span></span></p></td>
<td><p><span data-ttu-id="fb53e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="fb53e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fb53e-113">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fb53e-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb53e-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="fb53e-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="fb53e-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fb53e-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fb53e-116">solo</span><span class="sxs-lookup"><span data-stu-id="fb53e-116">unique</span></span></p></td>
<td><p><span data-ttu-id="fb53e-117">URI de conferencia si se trata de una conferencia o DialogID si se trata de una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="fb53e-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb53e-118"><strong>Comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="fb53e-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="fb53e-119">int</span><span class="sxs-lookup"><span data-stu-id="fb53e-119">int</span></span></p></td>
<td><p><span data-ttu-id="fb53e-120">clasificación</span><span class="sxs-lookup"><span data-stu-id="fb53e-120">index</span></span></p></td>
<td><p><span data-ttu-id="fb53e-121">Suma de comprobación del URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="fb53e-121">Checksum of the conference URI.</span></span> <span data-ttu-id="fb53e-122">Esto se usa internamente.</span><span class="sxs-lookup"><span data-stu-id="fb53e-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb53e-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="fb53e-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="fb53e-124">datetime</span><span class="sxs-lookup"><span data-stu-id="fb53e-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fb53e-125">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="fb53e-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

