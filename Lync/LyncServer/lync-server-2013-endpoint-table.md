---
title: 'Lync Server 2013: Tabla Endpoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cedf4d85cefd8a9fefb9f0ee4608f4a290fdc09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="f9115-102">Tabla Endpoint en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9115-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9115-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f9115-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f9115-104">La tabla de extremos es una tabla de soporte que almacena información sobre los puntos de conexión que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9115-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f9115-105">Cada registro de la tabla representa un punto final.</span><span class="sxs-lookup"><span data-stu-id="f9115-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9115-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f9115-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f9115-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f9115-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9115-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f9115-111">int</span><span class="sxs-lookup"><span data-stu-id="f9115-111">int</span></span></p></td>
<td><p><span data-ttu-id="f9115-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f9115-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9115-113">Número único que identifica este punto final.</span><span class="sxs-lookup"><span data-stu-id="f9115-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9115-114"><strong>Nombre.</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="f9115-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f9115-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f9115-116">Solo</span><span class="sxs-lookup"><span data-stu-id="f9115-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="f9115-117">Nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="f9115-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9115-118"><strong>Sistema operativo</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="f9115-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f9115-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9115-120">Sistema operativo (SO) del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f9115-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9115-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="f9115-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f9115-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9115-123">Nombre de la CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="f9115-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9115-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="f9115-125">smallint</span><span class="sxs-lookup"><span data-stu-id="f9115-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9115-126">Número de núcleos de CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="f9115-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9115-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="f9115-128">int</span><span class="sxs-lookup"><span data-stu-id="f9115-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9115-129">Velocidad del procesador de la CPU del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f9115-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9115-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f9115-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f9115-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="f9115-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9115-132">Marcador de bits que indica si el sistema se está ejecutando en un entorno virtualizado:</span><span class="sxs-lookup"><span data-stu-id="f9115-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="f9115-133">0x0000: ninguna</span><span class="sxs-lookup"><span data-stu-id="f9115-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="f9115-134">0x0001: HyperV</span><span class="sxs-lookup"><span data-stu-id="f9115-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="f9115-135">0x0002: VMWare</span><span class="sxs-lookup"><span data-stu-id="f9115-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="f9115-136">0x0004: Virtual PC</span><span class="sxs-lookup"><span data-stu-id="f9115-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="f9115-137">0x0008: Xen PC</span><span class="sxs-lookup"><span data-stu-id="f9115-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

