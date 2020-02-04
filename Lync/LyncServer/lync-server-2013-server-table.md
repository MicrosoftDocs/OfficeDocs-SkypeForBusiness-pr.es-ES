---
title: 'Lync Server 2013: Tabla Server'
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
ms.openlocfilehash: c1d0cdb5733e6fc6e21d1dcda1fff6214332de6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="98382-102">Tabla Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98382-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98382-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="98382-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="98382-104">La tabla del servidor es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="98382-104">The Server table is a supporting table.</span></span> <span data-ttu-id="98382-105">Cada registro representa un servidor.</span><span class="sxs-lookup"><span data-stu-id="98382-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98382-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="98382-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="98382-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="98382-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="98382-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="98382-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="98382-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="98382-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98382-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="98382-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="98382-111">int</span><span class="sxs-lookup"><span data-stu-id="98382-111">int</span></span></p></td>
<td><p><span data-ttu-id="98382-112">Primary</span><span class="sxs-lookup"><span data-stu-id="98382-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="98382-113">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="98382-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98382-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="98382-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="98382-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="98382-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="98382-116">clasificación</span><span class="sxs-lookup"><span data-stu-id="98382-116">index</span></span></p></td>
<td><p><span data-ttu-id="98382-117">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="98382-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98382-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="98382-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="98382-119">int</span><span class="sxs-lookup"><span data-stu-id="98382-119">int</span></span></p></td>
<td><p><span data-ttu-id="98382-120">Extranjero</span><span class="sxs-lookup"><span data-stu-id="98382-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="98382-121">1: servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="98382-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="98382-122">2: Server16394 de conferencia a/V: service32769 Edge: Gateway</span><span class="sxs-lookup"><span data-stu-id="98382-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98382-123"><strong>Nombredegrupo</strong></span><span class="sxs-lookup"><span data-stu-id="98382-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="98382-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="98382-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="98382-125">Grupo al que pertenece el servidor.</span><span class="sxs-lookup"><span data-stu-id="98382-125">Pool the server belongs to.</span></span> <span data-ttu-id="98382-126">Solo es aplicable para el servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="98382-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98382-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="98382-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="98382-128">datetime</span><span class="sxs-lookup"><span data-stu-id="98382-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="98382-129">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="98382-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

