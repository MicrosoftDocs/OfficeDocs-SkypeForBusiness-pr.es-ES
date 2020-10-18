---
title: 'Lync Server 2013: tabla Server'
description: 'Lync Server 2013: tabla Server.'
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
ms.openlocfilehash: 00990a91aec64063480d96a16380171990913ad4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576526"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="ab5c2-103">Tabla Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab5c2-103">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab5c2-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ab5c2-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ab5c2-p101">La tabla Server es una tabla auxiliar. Cada registro representa a un servidor.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab5c2-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ab5c2-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ab5c2-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ab5c2-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab5c2-111"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-111"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ab5c2-112">entero</span><span class="sxs-lookup"><span data-stu-id="ab5c2-112">int</span></span></p></td>
<td><p><span data-ttu-id="ab5c2-113">Principal</span><span class="sxs-lookup"><span data-stu-id="ab5c2-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab5c2-114">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-114">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab5c2-115"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-115"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="ab5c2-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ab5c2-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ab5c2-117">index</span><span class="sxs-lookup"><span data-stu-id="ab5c2-117">index</span></span></p></td>
<td><p><span data-ttu-id="ab5c2-118">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-118">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab5c2-119"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-119"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="ab5c2-120">entero</span><span class="sxs-lookup"><span data-stu-id="ab5c2-120">int</span></span></p></td>
<td><p><span data-ttu-id="ab5c2-121">Externa</span><span class="sxs-lookup"><span data-stu-id="ab5c2-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab5c2-122">1: Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="ab5c2-122">1: Mediation Server</span></span></p>
<p><span data-ttu-id="ab5c2-123">2: Servidor de conferencia A/V16394: Servicio perimetral A/V32769: Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="ab5c2-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab5c2-124"><strong>Nombredegrupo</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-124"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="ab5c2-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="ab5c2-125">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab5c2-p102">Grupo al que pertenece el servidor. Solo aplicable para el servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab5c2-128"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ab5c2-128"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ab5c2-129">datetime</span><span class="sxs-lookup"><span data-stu-id="ab5c2-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab5c2-130">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-130">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

