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
ms.openlocfilehash: 8906519253445ea67f3fa674a9a1315f8f6cf18b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="8d042-102">Tabla Devices en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d042-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d042-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="8d042-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="8d042-p101">La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="8d042-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d042-106">Columna</span><span class="sxs-lookup"><span data-stu-id="8d042-106">Column</span></span></th>
<th><span data-ttu-id="8d042-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d042-107">Data Type</span></span></th>
<th><span data-ttu-id="8d042-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="8d042-108">Key/Index</span></span></th>
<th><span data-ttu-id="8d042-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d042-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d042-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="8d042-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="8d042-111">int</span><span class="sxs-lookup"><span data-stu-id="8d042-111">int</span></span></p></td>
<td><p><span data-ttu-id="8d042-112">Principal</span><span class="sxs-lookup"><span data-stu-id="8d042-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8d042-113">Número único que identifica esta versión de hardware.</span><span class="sxs-lookup"><span data-stu-id="8d042-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d042-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="8d042-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8d042-115">int</span><span class="sxs-lookup"><span data-stu-id="8d042-115">int</span></span></p></td>
<td><p><span data-ttu-id="8d042-116">Externa</span><span class="sxs-lookup"><span data-stu-id="8d042-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8d042-117">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d042-117">Manufacturer of this device.</span></span> <span data-ttu-id="8d042-118">Consulte la <a href="lync-server-2013-manufacturers-table.md">tabla fabricantes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d042-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d042-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="8d042-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="8d042-120">int</span><span class="sxs-lookup"><span data-stu-id="8d042-120">int</span></span></p></td>
<td><p><span data-ttu-id="8d042-121">Externa</span><span class="sxs-lookup"><span data-stu-id="8d042-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8d042-122">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d042-122">Hardware version of this device.</span></span> <span data-ttu-id="8d042-123">Consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d042-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d042-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="8d042-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="8d042-125">BIGINT</span><span class="sxs-lookup"><span data-stu-id="8d042-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8d042-126">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="8d042-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

