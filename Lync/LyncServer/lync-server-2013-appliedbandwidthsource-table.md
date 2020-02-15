---
title: 'Lync Server 2013: tabla AppliedBandwidthSource'
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
ms.openlocfilehash: 3fcbcad9c69731d2a39d990f2342b7427f98fb74
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="61476-102">Tabla AppliedBandwidthSource en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61476-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61476-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="61476-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="61476-p101">La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.</span><span class="sxs-lookup"><span data-stu-id="61476-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61476-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="61476-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="61476-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="61476-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="61476-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="61476-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="61476-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="61476-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61476-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="61476-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="61476-111">int</span><span class="sxs-lookup"><span data-stu-id="61476-111">int</span></span></p></td>
<td><p><span data-ttu-id="61476-112">Principal</span><span class="sxs-lookup"><span data-stu-id="61476-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="61476-113">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="61476-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61476-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="61476-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="61476-115">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="61476-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61476-116">Única</span><span class="sxs-lookup"><span data-stu-id="61476-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="61476-p102">Origen del límite de ancho de banda impuesto. Describe de dónde proviene el límite de ancho de banda (por ejemplo, “Servidor de directivas”, “Servidor TURN” o “Modalidad”).</span><span class="sxs-lookup"><span data-stu-id="61476-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

