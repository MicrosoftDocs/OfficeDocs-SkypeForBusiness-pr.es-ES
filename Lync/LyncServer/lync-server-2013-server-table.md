---
title: 'Lync Server 2013: Tabla Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363c07a6ab3be8f5acdf0286a4223f96a8bd3700
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="1e226-102">Tabla Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e226-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e226-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1e226-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1e226-104">La tabla del servidor es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="1e226-104">The Server table is a supporting table.</span></span> <span data-ttu-id="1e226-105">Cada registro representa un servidor.</span><span class="sxs-lookup"><span data-stu-id="1e226-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e226-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1e226-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1e226-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1e226-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e226-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="1e226-111">int</span><span class="sxs-lookup"><span data-stu-id="1e226-111">int</span></span></p></td>
<td><p><span data-ttu-id="1e226-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1e226-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1e226-113">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="1e226-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e226-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="1e226-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1e226-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1e226-116">clasificación</span><span class="sxs-lookup"><span data-stu-id="1e226-116">index</span></span></p></td>
<td><p><span data-ttu-id="1e226-117">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="1e226-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e226-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="1e226-119">int</span><span class="sxs-lookup"><span data-stu-id="1e226-119">int</span></span></p></td>
<td><p><span data-ttu-id="1e226-120">Extranjero</span><span class="sxs-lookup"><span data-stu-id="1e226-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1e226-121">1: servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1e226-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="1e226-122">2: Server16394 de conferencia a/V: service32769 Edge: Gateway</span><span class="sxs-lookup"><span data-stu-id="1e226-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e226-123"><strong>Nombredegrupo</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="1e226-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="1e226-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e226-125">Grupo al que pertenece el servidor.</span><span class="sxs-lookup"><span data-stu-id="1e226-125">Pool the server belongs to.</span></span> <span data-ttu-id="1e226-126">Solo es aplicable para el servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="1e226-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e226-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="1e226-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="1e226-128">datetime</span><span class="sxs-lookup"><span data-stu-id="1e226-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e226-129">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="1e226-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

