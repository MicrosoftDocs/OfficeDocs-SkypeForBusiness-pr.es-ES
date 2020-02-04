---
title: 'Lync Server 2013: Tabla Device'
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
ms.openlocfilehash: 7fd06db1bd429526826962d5c3ad098642a3a42d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="ff5d9-102">Tabla Device en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff5d9-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff5d9-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ff5d9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ff5d9-104">La tabla de dispositivos es una tabla de soporte que almacena información sobre los diversos dispositivos de captura o de representación.</span><span class="sxs-lookup"><span data-stu-id="ff5d9-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="ff5d9-105">Cada registro de la tabla representa un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff5d9-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff5d9-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="ff5d9-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ff5d9-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="ff5d9-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ff5d9-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="ff5d9-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ff5d9-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="ff5d9-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff5d9-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="ff5d9-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ff5d9-111">int</span><span class="sxs-lookup"><span data-stu-id="ff5d9-111">int</span></span></p></td>
<td><p><span data-ttu-id="ff5d9-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ff5d9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff5d9-113">Número único que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff5d9-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff5d9-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="ff5d9-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="ff5d9-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ff5d9-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff5d9-116">DeviceName + DeviceType es único</span><span class="sxs-lookup"><span data-stu-id="ff5d9-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="ff5d9-117">Nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff5d9-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff5d9-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="ff5d9-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="ff5d9-119">bit</span><span class="sxs-lookup"><span data-stu-id="ff5d9-119">bit</span></span></p></td>
<td><p><span data-ttu-id="ff5d9-120">DeviceName + DeviceType es único</span><span class="sxs-lookup"><span data-stu-id="ff5d9-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="ff5d9-121">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff5d9-121">Device type.</span></span> <span data-ttu-id="ff5d9-122">1 es un dispositivo de captura, 0 es un dispositivo de representación.</span><span class="sxs-lookup"><span data-stu-id="ff5d9-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

