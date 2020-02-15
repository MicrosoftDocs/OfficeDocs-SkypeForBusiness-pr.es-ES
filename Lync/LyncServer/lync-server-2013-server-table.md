---
title: 'Lync Server 2013: tabla Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1a400387d88637fc45bcd3342ebbadb2bec6edf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="b71af-102">Tabla Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b71af-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b71af-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b71af-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b71af-p101">La tabla Server es una tabla auxiliar. Cada registro representa a un servidor.</span><span class="sxs-lookup"><span data-stu-id="b71af-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b71af-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b71af-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b71af-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b71af-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b71af-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b71af-111">int</span><span class="sxs-lookup"><span data-stu-id="b71af-111">int</span></span></p></td>
<td><p><span data-ttu-id="b71af-112">Principal</span><span class="sxs-lookup"><span data-stu-id="b71af-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b71af-113">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="b71af-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b71af-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="b71af-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b71af-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b71af-116">index</span><span class="sxs-lookup"><span data-stu-id="b71af-116">index</span></span></p></td>
<td><p><span data-ttu-id="b71af-117">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="b71af-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b71af-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="b71af-119">int</span><span class="sxs-lookup"><span data-stu-id="b71af-119">int</span></span></p></td>
<td><p><span data-ttu-id="b71af-120">Externa</span><span class="sxs-lookup"><span data-stu-id="b71af-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b71af-121">1: Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="b71af-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="b71af-122">2: Servidor de conferencia A/V16394: Servicio perimetral A/V32769: Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="b71af-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b71af-123"><strong>Nombredegrupo</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="b71af-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="b71af-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b71af-p102">Grupo al que pertenece el servidor. Solo aplicable para el servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="b71af-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b71af-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="b71af-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="b71af-128">datetime</span><span class="sxs-lookup"><span data-stu-id="b71af-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b71af-129">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b71af-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

