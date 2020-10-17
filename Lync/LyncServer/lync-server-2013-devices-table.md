---
title: 'Lync Server 2013: tabla de dispositivos'
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
ms.openlocfilehash: c5fdc4c3b20bdd60d2c8013b79a15bdfd30b56af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536937"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="921c8-102">Tabla Devices en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="921c8-102">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="921c8-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="921c8-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="921c8-p101">La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="921c8-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="921c8-106">Columna</span><span class="sxs-lookup"><span data-stu-id="921c8-106">Column</span></span></th>
<th><span data-ttu-id="921c8-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="921c8-107">Data Type</span></span></th>
<th><span data-ttu-id="921c8-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="921c8-108">Key/Index</span></span></th>
<th><span data-ttu-id="921c8-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="921c8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="921c8-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="921c8-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="921c8-111">entero</span><span class="sxs-lookup"><span data-stu-id="921c8-111">int</span></span></p></td>
<td><p><span data-ttu-id="921c8-112">Principal</span><span class="sxs-lookup"><span data-stu-id="921c8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="921c8-113">Número único que identifica esta versión de hardware.</span><span class="sxs-lookup"><span data-stu-id="921c8-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="921c8-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="921c8-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="921c8-115">entero</span><span class="sxs-lookup"><span data-stu-id="921c8-115">int</span></span></p></td>
<td><p><span data-ttu-id="921c8-116">Externa</span><span class="sxs-lookup"><span data-stu-id="921c8-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="921c8-117">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="921c8-117">Manufacturer of this device.</span></span> <span data-ttu-id="921c8-118">Consulte la <a href="lync-server-2013-manufacturers-table.md">tabla fabricantes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="921c8-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="921c8-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="921c8-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="921c8-120">entero</span><span class="sxs-lookup"><span data-stu-id="921c8-120">int</span></span></p></td>
<td><p><span data-ttu-id="921c8-121">Externa</span><span class="sxs-lookup"><span data-stu-id="921c8-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="921c8-122">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="921c8-122">Hardware version of this device.</span></span> <span data-ttu-id="921c8-123">Consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="921c8-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="921c8-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="921c8-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="921c8-125">BIGINT</span><span class="sxs-lookup"><span data-stu-id="921c8-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="921c8-126">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="921c8-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

