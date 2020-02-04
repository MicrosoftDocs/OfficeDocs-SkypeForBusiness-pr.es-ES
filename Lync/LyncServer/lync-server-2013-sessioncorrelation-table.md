---
title: 'Lync Server 2013: Tabla SessionCorrelation'
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
ms.openlocfilehash: 6fe8deda7486d699073bf271953e382ac7b7c508
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="ecda2-102">Tabla SessionCorrelation en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecda2-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecda2-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ecda2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ecda2-104">La tabla SessionCorrelation es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="ecda2-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="ecda2-105">Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="ecda2-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ecda2-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="ecda2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ecda2-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="ecda2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ecda2-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="ecda2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ecda2-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="ecda2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecda2-110"><strong>Comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="ecda2-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="ecda2-111">int</span><span class="sxs-lookup"><span data-stu-id="ecda2-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecda2-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="ecda2-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ecda2-113">int</span><span class="sxs-lookup"><span data-stu-id="ecda2-113">int</span></span></p></td>
<td><p><span data-ttu-id="ecda2-114">Primary</span><span class="sxs-lookup"><span data-stu-id="ecda2-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="ecda2-115">Número único que identifica este servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="ecda2-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecda2-116"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="ecda2-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="ecda2-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ecda2-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ecda2-118">Solo</span><span class="sxs-lookup"><span data-stu-id="ecda2-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="ecda2-119">Las sesiones correlacionadas tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="ecda2-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecda2-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ecda2-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ecda2-121">datetime</span><span class="sxs-lookup"><span data-stu-id="ecda2-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ecda2-122">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="ecda2-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

