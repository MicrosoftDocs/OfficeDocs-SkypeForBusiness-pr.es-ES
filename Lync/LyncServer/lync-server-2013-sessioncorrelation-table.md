---
title: 'Lync Server 2013: tabla SessionCorrelation'
description: 'Lync Server 2013: tabla SessionCorrelation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814b7e8539d89f87e7df60ceb03e70800553fb55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579666"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="b49ff-103">Tabla SessionCorrelation en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b49ff-103">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b49ff-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b49ff-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b49ff-105">La tabla SessionCorrelation es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="b49ff-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="b49ff-106">Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="b49ff-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b49ff-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="b49ff-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b49ff-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="b49ff-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b49ff-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="b49ff-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b49ff-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="b49ff-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b49ff-111"><strong>Suma de comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="b49ff-111"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="b49ff-112">entero</span><span class="sxs-lookup"><span data-stu-id="b49ff-112">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b49ff-113"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="b49ff-113"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b49ff-114">entero</span><span class="sxs-lookup"><span data-stu-id="b49ff-114">int</span></span></p></td>
<td><p><span data-ttu-id="b49ff-115">Principal</span><span class="sxs-lookup"><span data-stu-id="b49ff-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="b49ff-116">Número único que identifica este servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="b49ff-116">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b49ff-117"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="b49ff-117"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="b49ff-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b49ff-118">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b49ff-119">Única</span><span class="sxs-lookup"><span data-stu-id="b49ff-119">Unique</span></span></p></td>
<td><p><span data-ttu-id="b49ff-120">Las sesiones que están correlacionadas tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="b49ff-120">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b49ff-121"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="b49ff-121"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="b49ff-122">datetime</span><span class="sxs-lookup"><span data-stu-id="b49ff-122">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b49ff-123">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b49ff-123">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

