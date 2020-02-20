---
title: 'Lync Server 2013: tabla MonitoredRegionLink'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MonitoredRegionLink table
ms:assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398874(v=OCS.15)
ms:contentKeyID: 48185487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ad8775d4ec7af73ce32887297524c011971ac6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoredregionlink-table-in-lync-server-2013"></a><span data-ttu-id="d57cf-102">Tabla MonitoredRegionLink en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d57cf-102">MonitoredRegionLink table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d57cf-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d57cf-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d57cf-p101">La tabla MonitoredRegionLink es una tabla auxiliar. Cada registro representa un vínculo entre dos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="d57cf-p101">The MonitoredRegionLink table is a supporting table. Each record represents one link between two countries/regions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d57cf-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="d57cf-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d57cf-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="d57cf-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d57cf-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="d57cf-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d57cf-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="d57cf-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d57cf-110"><strong>Region1Key</strong></span><span class="sxs-lookup"><span data-stu-id="d57cf-110"><strong>Region1Key</strong></span></span></p></td>
<td><p><span data-ttu-id="d57cf-111">int</span><span class="sxs-lookup"><span data-stu-id="d57cf-111">int</span></span></p></td>
<td><p><span data-ttu-id="d57cf-112">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="d57cf-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57cf-113">Se hace referencia a ella desde la <a href="lync-server-2013-region-table.md">tabla region en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d57cf-113">Referenced from the <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57cf-114"><strong>Region2Key</strong></span><span class="sxs-lookup"><span data-stu-id="d57cf-114"><strong>Region2Key</strong></span></span></p></td>
<td><p><span data-ttu-id="d57cf-115">int</span><span class="sxs-lookup"><span data-stu-id="d57cf-115">int</span></span></p></td>
<td><p><span data-ttu-id="d57cf-116">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="d57cf-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d57cf-117">Se hace referencia a ella desde la <a href="lync-server-2013-region-table.md">tabla region en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d57cf-117">Referenced from the <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

