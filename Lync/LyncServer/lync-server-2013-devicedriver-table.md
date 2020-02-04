---
title: 'Lync Server 2013: Tabla DeviceDriver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f52354a153f155f57ce6466ea8082b63ef105e34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="b2abe-102">Tabla DeviceDriver en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2abe-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2abe-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b2abe-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b2abe-104">La tabla DeviceDriver es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="b2abe-104">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="b2abe-105">Cada registro representa un controlador usado por un dispositivo de captura o un dispositivo de representación.</span><span class="sxs-lookup"><span data-stu-id="b2abe-105">Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2abe-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="b2abe-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b2abe-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="b2abe-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b2abe-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="b2abe-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b2abe-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="b2abe-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2abe-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="b2abe-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b2abe-111">int</span><span class="sxs-lookup"><span data-stu-id="b2abe-111">int</span></span></p></td>
<td><p><span data-ttu-id="b2abe-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b2abe-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2abe-113">Número único que identifica este registro de controlador de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b2abe-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2abe-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="b2abe-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="b2abe-115">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b2abe-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b2abe-116">solo</span><span class="sxs-lookup"><span data-stu-id="b2abe-116">unique</span></span></p></td>
<td><p><span data-ttu-id="b2abe-117">Nombre del controlador del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b2abe-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

