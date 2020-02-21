---
title: 'Lync Server 2013: tabla EndpointSubnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EndpointSubnet table
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398933(v=OCS.15)
ms:contentKeyID: 48185514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9619eb758f95c3d43d1db09a4e6dc64c36a6931
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="683b5-102">Tabla EndpointSubnet en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="683b5-102">EndpointSubnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="683b5-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="683b5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="683b5-p101">La tabla EndpointSubnet es una tabla auxiliar. Cada registro representa una subred capturada de extremos.</span><span class="sxs-lookup"><span data-stu-id="683b5-p101">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="683b5-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="683b5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="683b5-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="683b5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="683b5-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="683b5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="683b5-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="683b5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="683b5-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="683b5-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="683b5-111">int</span><span class="sxs-lookup"><span data-stu-id="683b5-111">int</span></span></p></td>
<td><p><span data-ttu-id="683b5-112">Principal</span><span class="sxs-lookup"><span data-stu-id="683b5-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="683b5-113">Representación de enteros para la subred.</span><span class="sxs-lookup"><span data-stu-id="683b5-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="683b5-114"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="683b5-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="683b5-115">datetime</span><span class="sxs-lookup"><span data-stu-id="683b5-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="683b5-116">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="683b5-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

