---
title: 'Lync Server 2013: tabla de dispositivos'
description: 'Lync Server 2013: tabla de dispositivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763e1788e2874f9f9831c089ffe8fa077621b030
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576246"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="87f14-103">Tabla Devices en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87f14-103">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87f14-104">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="87f14-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="87f14-p101">La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="87f14-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87f14-107">Columna</span><span class="sxs-lookup"><span data-stu-id="87f14-107">Column</span></span></th>
<th><span data-ttu-id="87f14-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="87f14-108">Data Type</span></span></th>
<th><span data-ttu-id="87f14-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="87f14-109">Key/Index</span></span></th>
<th><span data-ttu-id="87f14-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="87f14-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87f14-111"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="87f14-111"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="87f14-112">entero</span><span class="sxs-lookup"><span data-stu-id="87f14-112">int</span></span></p></td>
<td><p><span data-ttu-id="87f14-113">Principal</span><span class="sxs-lookup"><span data-stu-id="87f14-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="87f14-114">Número único que identifica esta versión de hardware.</span><span class="sxs-lookup"><span data-stu-id="87f14-114">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87f14-115"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="87f14-115"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="87f14-116">entero</span><span class="sxs-lookup"><span data-stu-id="87f14-116">int</span></span></p></td>
<td><p><span data-ttu-id="87f14-117">Externa</span><span class="sxs-lookup"><span data-stu-id="87f14-117">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87f14-118">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87f14-118">Manufacturer of this device.</span></span> <span data-ttu-id="87f14-119">Consulte la <a href="lync-server-2013-manufacturers-table.md">tabla fabricantes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="87f14-119">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87f14-120"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="87f14-120"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="87f14-121">entero</span><span class="sxs-lookup"><span data-stu-id="87f14-121">int</span></span></p></td>
<td><p><span data-ttu-id="87f14-122">Externa</span><span class="sxs-lookup"><span data-stu-id="87f14-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87f14-123">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87f14-123">Hardware version of this device.</span></span> <span data-ttu-id="87f14-124">Consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="87f14-124">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87f14-125"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="87f14-125"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="87f14-126">BIGINT</span><span class="sxs-lookup"><span data-stu-id="87f14-126">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87f14-127">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="87f14-127">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

