---
title: 'Lync Server 2013: tabla IPAddress'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82eef0e1926bc794df7c6a80b28fa68008561315
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="a59b1-102">Tabla IPAddress en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a59b1-102">IPAddress table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a59b1-103">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a59b1-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a59b1-104">La tabla direcciónIP asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="a59b1-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a59b1-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a59b1-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a59b1-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="a59b1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a59b1-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="a59b1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a59b1-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="a59b1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a59b1-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="a59b1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a59b1-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="a59b1-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a59b1-111">int</span><span class="sxs-lookup"><span data-stu-id="a59b1-111">int</span></span></p></td>
<td><p><span data-ttu-id="a59b1-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a59b1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a59b1-113">Identificador único de la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="a59b1-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a59b1-114"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a59b1-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a59b1-115">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="a59b1-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="a59b1-116">Solo</span><span class="sxs-lookup"><span data-stu-id="a59b1-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="a59b1-117">Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a la IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="a59b1-117">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="a59b1-118">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="a59b1-118">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

