---
title: 'Lync Server 2013: Tabla ErrorDef'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef21484d564419a5ab5cce7373ceb0b0b71e4a29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="ca55f-102">Tabla ErrorDef en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca55f-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca55f-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="ca55f-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="ca55f-104">La tabla ErrorDef almacena información acerca de cada tipo de error que puede ocurrir.</span><span class="sxs-lookup"><span data-stu-id="ca55f-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="ca55f-105">Cada registro es un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="ca55f-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca55f-106">Columna</span><span class="sxs-lookup"><span data-stu-id="ca55f-106">Column</span></span></th>
<th><span data-ttu-id="ca55f-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ca55f-107">Data Type</span></span></th>
<th><span data-ttu-id="ca55f-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="ca55f-108">Key/Index</span></span></th>
<th><span data-ttu-id="ca55f-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="ca55f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca55f-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="ca55f-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca55f-111">int</span><span class="sxs-lookup"><span data-stu-id="ca55f-111">int</span></span></p></td>
<td><p><span data-ttu-id="ca55f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ca55f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca55f-113">Número de identificación único que identifica este tipo de error.</span><span class="sxs-lookup"><span data-stu-id="ca55f-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca55f-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ca55f-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ca55f-115">int</span><span class="sxs-lookup"><span data-stu-id="ca55f-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ca55f-116">Código de respuesta SIP estándar asociado a este error.</span><span class="sxs-lookup"><span data-stu-id="ca55f-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca55f-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="ca55f-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca55f-118">int</span><span class="sxs-lookup"><span data-stu-id="ca55f-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ca55f-119">IDENTIFICADOR de diagnóstico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ca55f-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca55f-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ca55f-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca55f-121">ENT</span><span class="sxs-lookup"><span data-stu-id="ca55f-121">Int</span></span></p></td>
<td><p><span data-ttu-id="ca55f-122">Extranjero</span><span class="sxs-lookup"><span data-stu-id="ca55f-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca55f-123">Tipo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ca55f-123">Type of the call.</span></span> <span data-ttu-id="ca55f-124">Para obtener más información, consulte la <a href="lync-server-2013-calltype-table.md">tabla CallType en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ca55f-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca55f-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="ca55f-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca55f-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="ca55f-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ca55f-127">Tipo de solicitud en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="ca55f-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="ca55f-128">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ca55f-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca55f-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="ca55f-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca55f-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="ca55f-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ca55f-131">Tipo de contenido de la solicitud en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="ca55f-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="ca55f-132">Estos datos se pueden convertir a formato de texto con este sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ca55f-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

