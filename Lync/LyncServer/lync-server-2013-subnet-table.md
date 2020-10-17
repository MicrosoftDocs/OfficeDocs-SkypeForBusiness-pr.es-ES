---
title: 'Lync Server 2013: tabla de subred'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d684efa2d4bd68880a3838893e5c5cfe2a1a3cc2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519437"
---
# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="97eeb-102">Tabla de subred en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97eeb-102">Subnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97eeb-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="97eeb-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="97eeb-p101">La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="97eeb-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97eeb-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="97eeb-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="97eeb-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="97eeb-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="97eeb-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="97eeb-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="97eeb-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="97eeb-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97eeb-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="97eeb-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="97eeb-111">entero</span><span class="sxs-lookup"><span data-stu-id="97eeb-111">int</span></span></p></td>
<td><p><span data-ttu-id="97eeb-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="97eeb-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="97eeb-113">Representación en número entero de la IP de la subred.</span><span class="sxs-lookup"><span data-stu-id="97eeb-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97eeb-114"><strong>Máscaradesubred</strong></span><span class="sxs-lookup"><span data-stu-id="97eeb-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="97eeb-115">entero</span><span class="sxs-lookup"><span data-stu-id="97eeb-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="97eeb-116">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="97eeb-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97eeb-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="97eeb-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="97eeb-118">entero</span><span class="sxs-lookup"><span data-stu-id="97eeb-118">int</span></span></p></td>
<td><p><span data-ttu-id="97eeb-119">Externa</span><span class="sxs-lookup"><span data-stu-id="97eeb-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="97eeb-120">Referencia de la <a href="lync-server-2013-usersite-table.md">tabla UserSite en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="97eeb-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97eeb-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="97eeb-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="97eeb-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="97eeb-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="97eeb-123">Descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="97eeb-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

