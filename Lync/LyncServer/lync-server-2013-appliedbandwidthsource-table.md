---
title: 'Lync Server 2013: Tabla AppliedBandwidthSource'
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
ms.openlocfilehash: 6978802893b2c4af4f4d4199c3e35452200d8d4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="54cf8-102">Tabla AppliedBandwidthSource en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54cf8-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54cf8-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="54cf8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="54cf8-104">La tabla AppliedBandwidthSource es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="54cf8-104">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="54cf8-105">Cada registro representa un origen.</span><span class="sxs-lookup"><span data-stu-id="54cf8-105">Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54cf8-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="54cf8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="54cf8-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="54cf8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="54cf8-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="54cf8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="54cf8-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="54cf8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54cf8-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="54cf8-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="54cf8-111">int</span><span class="sxs-lookup"><span data-stu-id="54cf8-111">int</span></span></p></td>
<td><p><span data-ttu-id="54cf8-112">Primary</span><span class="sxs-lookup"><span data-stu-id="54cf8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="54cf8-113">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="54cf8-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54cf8-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="54cf8-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="54cf8-115">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54cf8-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54cf8-116">Solo</span><span class="sxs-lookup"><span data-stu-id="54cf8-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="54cf8-117">Este es el origen del límite de ancho de banda que se impone.</span><span class="sxs-lookup"><span data-stu-id="54cf8-117">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="54cf8-118">Describe de dónde viene el límite de ancho de banda (por ejemplo, "servidor de directivas", "convertir servidor" o "modalidad de moda").</span><span class="sxs-lookup"><span data-stu-id="54cf8-118">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

