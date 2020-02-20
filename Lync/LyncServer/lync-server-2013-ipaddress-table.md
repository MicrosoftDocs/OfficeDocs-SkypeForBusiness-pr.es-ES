---
title: 'Lync Server 2013: tabla IPAddress'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2be3760d16053e07010f4be1df39adbbd39130a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="e95b5-102">Tabla IPAddress en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e95b5-102">IPAddress table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e95b5-103">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="e95b5-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="e95b5-104">La tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="e95b5-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="e95b5-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e95b5-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e95b5-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="e95b5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e95b5-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="e95b5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e95b5-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="e95b5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e95b5-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="e95b5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e95b5-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="e95b5-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e95b5-111">int</span><span class="sxs-lookup"><span data-stu-id="e95b5-111">int</span></span></p></td>
<td><p><span data-ttu-id="e95b5-112">Principal</span><span class="sxs-lookup"><span data-stu-id="e95b5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e95b5-113">Identificador único de la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="e95b5-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95b5-114"><strong>DirIP</strong></span><span class="sxs-lookup"><span data-stu-id="e95b5-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e95b5-115">VARCHAR (50)</span><span class="sxs-lookup"><span data-stu-id="e95b5-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="e95b5-116">Única</span><span class="sxs-lookup"><span data-stu-id="e95b5-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="e95b5-p102">Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a IpAddressKey. Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="e95b5-p102">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

