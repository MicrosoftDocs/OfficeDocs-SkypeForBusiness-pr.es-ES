---
title: 'Lync Server 2013: Tabla Subnet'
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
ms.openlocfilehash: d107889b49ec16c51224b075a8fb7f7a7cec1b00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="d843e-102">Tabla Subnet en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d843e-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d843e-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d843e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d843e-104">La tabla de subred es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="d843e-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="d843e-105">Cada registro representa una subred definida en la opción de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="d843e-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d843e-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="d843e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d843e-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="d843e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d843e-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="d843e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d843e-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="d843e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d843e-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="d843e-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="d843e-111">int</span><span class="sxs-lookup"><span data-stu-id="d843e-111">int</span></span></p></td>
<td><p><span data-ttu-id="d843e-112">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d843e-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d843e-113">Representación de enteros de la IP de subred.</span><span class="sxs-lookup"><span data-stu-id="d843e-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843e-114"><strong>Máscaradesubred</strong></span><span class="sxs-lookup"><span data-stu-id="d843e-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="d843e-115">int</span><span class="sxs-lookup"><span data-stu-id="d843e-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d843e-116">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="d843e-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843e-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="d843e-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d843e-118">int</span><span class="sxs-lookup"><span data-stu-id="d843e-118">int</span></span></p></td>
<td><p><span data-ttu-id="d843e-119">Extranjero</span><span class="sxs-lookup"><span data-stu-id="d843e-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d843e-120">Se hace referencia a ellos desde la <a href="lync-server-2013-usersite-table.md">tabla UserSite en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d843e-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843e-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="d843e-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="d843e-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="d843e-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d843e-123">La descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="d843e-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

