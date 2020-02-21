---
title: 'Lync Server 2013: tabla DeviceDriver'
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
ms.openlocfilehash: 2813ac26bbfd21aa35dbe71c9c4477e8107b8967
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="7e0c1-102">Tabla DeviceDriver en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e0c1-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e0c1-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7e0c1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7e0c1-p101">La tabla DeviceDriver es una tabla auxiliar. Cada registro representa un controlador que usa un dispositivo de captura o un dispositivo de representación.</span><span class="sxs-lookup"><span data-stu-id="7e0c1-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e0c1-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="7e0c1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7e0c1-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="7e0c1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7e0c1-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="7e0c1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7e0c1-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="7e0c1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e0c1-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="7e0c1-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7e0c1-111">int</span><span class="sxs-lookup"><span data-stu-id="7e0c1-111">int</span></span></p></td>
<td><p><span data-ttu-id="7e0c1-112">Principal</span><span class="sxs-lookup"><span data-stu-id="7e0c1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e0c1-113">Número único de identificación de este registro de controlador de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7e0c1-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e0c1-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7e0c1-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7e0c1-115">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="7e0c1-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e0c1-116">singular</span><span class="sxs-lookup"><span data-stu-id="7e0c1-116">unique</span></span></p></td>
<td><p><span data-ttu-id="7e0c1-117">Nombre de controlador de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7e0c1-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

