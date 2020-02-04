---
title: 'Lync Server 2013: Tabla Devices'
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
ms.openlocfilehash: 381b03fc5680276a64fc327f423f74c6773c2ed3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="82b3c-102">Tabla Devices en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82b3c-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82b3c-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="82b3c-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="82b3c-104">La tabla dispositivos es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="82b3c-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="82b3c-105">Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="82b3c-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82b3c-106">Columna</span><span class="sxs-lookup"><span data-stu-id="82b3c-106">Column</span></span></th>
<th><span data-ttu-id="82b3c-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="82b3c-107">Data Type</span></span></th>
<th><span data-ttu-id="82b3c-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="82b3c-108">Key/Index</span></span></th>
<th><span data-ttu-id="82b3c-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="82b3c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82b3c-110"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="82b3c-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="82b3c-111">int</span><span class="sxs-lookup"><span data-stu-id="82b3c-111">int</span></span></p></td>
<td><p><span data-ttu-id="82b3c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="82b3c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="82b3c-113">Número único que identifica esta versión de hardware.</span><span class="sxs-lookup"><span data-stu-id="82b3c-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82b3c-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="82b3c-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="82b3c-115">int</span><span class="sxs-lookup"><span data-stu-id="82b3c-115">int</span></span></p></td>
<td><p><span data-ttu-id="82b3c-116">Extranjero</span><span class="sxs-lookup"><span data-stu-id="82b3c-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="82b3c-117">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="82b3c-117">Manufacturer of this device.</span></span> <span data-ttu-id="82b3c-118">Para obtener más información, consulte la <a href="lync-server-2013-manufacturers-table.md">tabla de fabricantes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82b3c-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82b3c-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="82b3c-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="82b3c-120">int</span><span class="sxs-lookup"><span data-stu-id="82b3c-120">int</span></span></p></td>
<td><p><span data-ttu-id="82b3c-121">Extranjero</span><span class="sxs-lookup"><span data-stu-id="82b3c-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="82b3c-122">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="82b3c-122">Hardware version of this device.</span></span> <span data-ttu-id="82b3c-123">Para obtener más información, consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82b3c-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82b3c-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="82b3c-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="82b3c-125">BIGINT</span><span class="sxs-lookup"><span data-stu-id="82b3c-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="82b3c-126">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="82b3c-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

