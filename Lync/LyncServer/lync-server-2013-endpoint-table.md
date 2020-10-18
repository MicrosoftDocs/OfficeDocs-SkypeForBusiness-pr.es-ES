---
title: 'Lync Server 2013: tabla de extremos'
description: 'Lync Server 2013: tabla de extremos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575626"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="20d03-103">Tabla Endpoint en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20d03-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20d03-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="20d03-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="20d03-105">La tabla de extremos es una tabla de apoyo que almacena información sobre los puntos de conexión que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="20d03-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="20d03-106">Cada registro de la tabla representa un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="20d03-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20d03-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="20d03-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="20d03-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="20d03-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20d03-111"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="20d03-112">entero</span><span class="sxs-lookup"><span data-stu-id="20d03-112">int</span></span></p></td>
<td><p><span data-ttu-id="20d03-113">Principal</span><span class="sxs-lookup"><span data-stu-id="20d03-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="20d03-114">Número único que identifica este extremo.</span><span class="sxs-lookup"><span data-stu-id="20d03-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20d03-115"><strong>Nombre</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="20d03-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="20d03-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="20d03-117">Única</span><span class="sxs-lookup"><span data-stu-id="20d03-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="20d03-118">Nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="20d03-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20d03-119"><strong>MacOS</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="20d03-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="20d03-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="20d03-121">Sistema operativo (SO) del extremo.</span><span class="sxs-lookup"><span data-stu-id="20d03-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20d03-122"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="20d03-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="20d03-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20d03-124">Nombre de la CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="20d03-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20d03-125"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="20d03-126">smallint</span><span class="sxs-lookup"><span data-stu-id="20d03-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20d03-127">Número de núcleos de CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="20d03-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20d03-128"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="20d03-129">entero</span><span class="sxs-lookup"><span data-stu-id="20d03-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20d03-130">Velocidad del procesador de la CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="20d03-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20d03-131"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="20d03-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="20d03-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="20d03-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20d03-133">Marca de bits que indica si el sistema se está ejecutando en un entorno virtualizado:</span><span class="sxs-lookup"><span data-stu-id="20d03-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="20d03-134">0x0000 – ninguno</span><span class="sxs-lookup"><span data-stu-id="20d03-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="20d03-135">0x0001: HyperV</span><span class="sxs-lookup"><span data-stu-id="20d03-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="20d03-136">0x0002: VMWare</span><span class="sxs-lookup"><span data-stu-id="20d03-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="20d03-137">0x0004: Virtual PC</span><span class="sxs-lookup"><span data-stu-id="20d03-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="20d03-138">0x0008 – equipo de Xen</span><span class="sxs-lookup"><span data-stu-id="20d03-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

