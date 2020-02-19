---
title: 'Lync Server 2013: tabla ErrorDef'
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
ms.openlocfilehash: c333017f122454d68bc452a5c183f8c09b6347a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="2fcfe-102">Tabla ErrorDef en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fcfe-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fcfe-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="2fcfe-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="2fcfe-104">La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="2fcfe-105">Cada registro es un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2fcfe-106">Columna</span><span class="sxs-lookup"><span data-stu-id="2fcfe-106">Column</span></span></th>
<th><span data-ttu-id="2fcfe-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2fcfe-107">Data Type</span></span></th>
<th><span data-ttu-id="2fcfe-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="2fcfe-108">Key/Index</span></span></th>
<th><span data-ttu-id="2fcfe-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="2fcfe-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2fcfe-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="2fcfe-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="2fcfe-111">int</span><span class="sxs-lookup"><span data-stu-id="2fcfe-111">int</span></span></p></td>
<td><p><span data-ttu-id="2fcfe-112">Principal</span><span class="sxs-lookup"><span data-stu-id="2fcfe-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2fcfe-113">Número de identificador único que identifica este tipo de error.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fcfe-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="2fcfe-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2fcfe-115">int</span><span class="sxs-lookup"><span data-stu-id="2fcfe-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2fcfe-116">Código de respuesta SIP estándar asociado a este error.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fcfe-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="2fcfe-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="2fcfe-118">int</span><span class="sxs-lookup"><span data-stu-id="2fcfe-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2fcfe-119">IDENTIFICADOR de diagnóstico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fcfe-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="2fcfe-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="2fcfe-121">Int</span><span class="sxs-lookup"><span data-stu-id="2fcfe-121">Int</span></span></p></td>
<td><p><span data-ttu-id="2fcfe-122">Externa</span><span class="sxs-lookup"><span data-stu-id="2fcfe-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2fcfe-123">Tipo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-123">Type of the call.</span></span> <span data-ttu-id="2fcfe-124">Consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2fcfe-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="2fcfe-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="2fcfe-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="2fcfe-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2fcfe-127">Tipo de solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="2fcfe-128">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="2fcfe-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2fcfe-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="2fcfe-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="2fcfe-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="2fcfe-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2fcfe-131">Tipo de contenido de la solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="2fcfe-132">Estos datos pueden convertirse a formato de texto mediante el uso de esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="2fcfe-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

