---
title: 'Lync Server 2013: tabla ErrorDef'
description: 'Lync Server 2013: tabla ErrorDef.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542756"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="7931d-103">Tabla ErrorDef en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7931d-103">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7931d-104">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="7931d-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="7931d-105">La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse.</span><span class="sxs-lookup"><span data-stu-id="7931d-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="7931d-106">Cada registro es un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="7931d-106">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7931d-107">Columna</span><span class="sxs-lookup"><span data-stu-id="7931d-107">Column</span></span></th>
<th><span data-ttu-id="7931d-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7931d-108">Data Type</span></span></th>
<th><span data-ttu-id="7931d-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="7931d-109">Key/Index</span></span></th>
<th><span data-ttu-id="7931d-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="7931d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7931d-111"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="7931d-111"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="7931d-112">entero</span><span class="sxs-lookup"><span data-stu-id="7931d-112">int</span></span></p></td>
<td><p><span data-ttu-id="7931d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="7931d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7931d-114">Número de identificador único que identifica este tipo de error.</span><span class="sxs-lookup"><span data-stu-id="7931d-114">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7931d-115"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="7931d-115"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="7931d-116">entero</span><span class="sxs-lookup"><span data-stu-id="7931d-116">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7931d-117">Código de respuesta SIP estándar asociado a este error.</span><span class="sxs-lookup"><span data-stu-id="7931d-117">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7931d-118"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="7931d-118"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="7931d-119">entero</span><span class="sxs-lookup"><span data-stu-id="7931d-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7931d-120">IDENTIFICADOR de diagnóstico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7931d-120">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7931d-121"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="7931d-121"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="7931d-122">Int</span><span class="sxs-lookup"><span data-stu-id="7931d-122">Int</span></span></p></td>
<td><p><span data-ttu-id="7931d-123">Externa</span><span class="sxs-lookup"><span data-stu-id="7931d-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7931d-124">Tipo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7931d-124">Type of the call.</span></span> <span data-ttu-id="7931d-125">Consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7931d-125">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7931d-126"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="7931d-126"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="7931d-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="7931d-127">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7931d-128">Tipo de solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="7931d-128">Type of request that failed.</span></span></p>
<p><span data-ttu-id="7931d-129">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="7931d-129">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7931d-130"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="7931d-130"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="7931d-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="7931d-131">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7931d-132">Tipo de contenido de la solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="7931d-132">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="7931d-133">Estos datos pueden convertirse a formato de texto mediante el uso de esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="7931d-133">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

