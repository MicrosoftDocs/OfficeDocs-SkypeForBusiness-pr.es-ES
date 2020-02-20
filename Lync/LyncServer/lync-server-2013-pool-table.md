---
title: 'Lync Server 2013: tabla de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e10e3e6a3e27d66510b4cde0ef72a1a11288e8e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="32c0f-102">Tabla de grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c0f-102">Pool table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32c0f-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="32c0f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="32c0f-p101">La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.</span><span class="sxs-lookup"><span data-stu-id="32c0f-p101">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32c0f-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="32c0f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="32c0f-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="32c0f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="32c0f-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="32c0f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="32c0f-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="32c0f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32c0f-110"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="32c0f-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="32c0f-111">int</span><span class="sxs-lookup"><span data-stu-id="32c0f-111">int</span></span></p></td>
<td><p><span data-ttu-id="32c0f-112">Principal</span><span class="sxs-lookup"><span data-stu-id="32c0f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="32c0f-113">Número único con el que se identifica a este grupo.</span><span class="sxs-lookup"><span data-stu-id="32c0f-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32c0f-114"><strong>Nombredegrupo</strong></span><span class="sxs-lookup"><span data-stu-id="32c0f-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="32c0f-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32c0f-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32c0f-116">Singular </span><span class="sxs-lookup"><span data-stu-id="32c0f-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="32c0f-117">FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="32c0f-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

