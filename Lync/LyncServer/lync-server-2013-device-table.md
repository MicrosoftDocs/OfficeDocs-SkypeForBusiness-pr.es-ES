---
title: 'Lync Server 2013: tabla de dispositivos'
description: 'Lync Server 2013: tabla de dispositivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46de64a49eace52d62cbd6384fcae680b5c511b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575646"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="be1e8-103">Tabla Device en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be1e8-103">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be1e8-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="be1e8-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="be1e8-p101">La tabla Dispositivo es una tabla auxiliar que almacena información sobre los diversos dispositivos de captura o presentación. Cada registro de la tabla representa un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be1e8-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be1e8-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="be1e8-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="be1e8-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="be1e8-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="be1e8-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="be1e8-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="be1e8-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="be1e8-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be1e8-111"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="be1e8-111"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="be1e8-112">entero</span><span class="sxs-lookup"><span data-stu-id="be1e8-112">int</span></span></p></td>
<td><p><span data-ttu-id="be1e8-113">Principal</span><span class="sxs-lookup"><span data-stu-id="be1e8-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="be1e8-114">Número único que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be1e8-114">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be1e8-115"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="be1e8-115"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="be1e8-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="be1e8-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="be1e8-117">DeviceName + DeviceType son únicos</span><span class="sxs-lookup"><span data-stu-id="be1e8-117">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="be1e8-118">Nombre del dispositivo</span><span class="sxs-lookup"><span data-stu-id="be1e8-118">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be1e8-119"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="be1e8-119"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="be1e8-120">bit</span><span class="sxs-lookup"><span data-stu-id="be1e8-120">bit</span></span></p></td>
<td><p><span data-ttu-id="be1e8-121">DeviceName + DeviceType son únicos</span><span class="sxs-lookup"><span data-stu-id="be1e8-121">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="be1e8-p102">Tipo de dispositivo. 1 es un dispositivo de captura, 0 es un dispositivo de presentación.</span><span class="sxs-lookup"><span data-stu-id="be1e8-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

