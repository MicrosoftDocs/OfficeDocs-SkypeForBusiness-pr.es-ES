---
title: 'Lync Server 2013: tabla AppliedBandwidthSource'
description: 'Lync Server 2013: tabla AppliedBandwidthSource.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc22d3a978a99cb13317e2a32fdb65382ce106c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573506"
---
# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="f1172-103">Tabla AppliedBandwidthSource en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1172-103">AppliedBandwidthSource table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1172-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f1172-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f1172-p101">La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.</span><span class="sxs-lookup"><span data-stu-id="f1172-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1172-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="f1172-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f1172-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="f1172-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f1172-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="f1172-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f1172-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="f1172-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1172-111"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f1172-111"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f1172-112">entero</span><span class="sxs-lookup"><span data-stu-id="f1172-112">int</span></span></p></td>
<td><p><span data-ttu-id="f1172-113">Principal</span><span class="sxs-lookup"><span data-stu-id="f1172-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f1172-114">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="f1172-114">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1172-115"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="f1172-115"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="f1172-116">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="f1172-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1172-117">Única</span><span class="sxs-lookup"><span data-stu-id="f1172-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="f1172-p102">Origen del límite de ancho de banda impuesto. Describe de dónde proviene el límite de ancho de banda (por ejemplo, “Servidor de directivas”, “Servidor TURN” o “Modalidad”).</span><span class="sxs-lookup"><span data-stu-id="f1172-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

