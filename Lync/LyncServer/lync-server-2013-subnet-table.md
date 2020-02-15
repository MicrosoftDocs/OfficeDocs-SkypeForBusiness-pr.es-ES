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
ms.openlocfilehash: ff03309ab4c71f2dfda9aac96223cde2cd6e000a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="7a1c0-102">Tabla de subred en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a1c0-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a1c0-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7a1c0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7a1c0-p101">La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7a1c0-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a1c0-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="7a1c0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7a1c0-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="7a1c0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7a1c0-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="7a1c0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7a1c0-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="7a1c0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a1c0-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="7a1c0-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="7a1c0-111">int</span><span class="sxs-lookup"><span data-stu-id="7a1c0-111">int</span></span></p></td>
<td><p><span data-ttu-id="7a1c0-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="7a1c0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7a1c0-113">Representación en número entero de la IP de la subred.</span><span class="sxs-lookup"><span data-stu-id="7a1c0-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a1c0-114"><strong>Máscaradesubred</strong></span><span class="sxs-lookup"><span data-stu-id="7a1c0-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="7a1c0-115">int</span><span class="sxs-lookup"><span data-stu-id="7a1c0-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a1c0-116">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="7a1c0-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a1c0-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="7a1c0-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7a1c0-118">int</span><span class="sxs-lookup"><span data-stu-id="7a1c0-118">int</span></span></p></td>
<td><p><span data-ttu-id="7a1c0-119">Externa</span><span class="sxs-lookup"><span data-stu-id="7a1c0-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7a1c0-120">Referencia de la <a href="lync-server-2013-usersite-table.md">tabla UserSite en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7a1c0-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a1c0-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="7a1c0-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="7a1c0-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="7a1c0-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a1c0-123">Descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="7a1c0-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

