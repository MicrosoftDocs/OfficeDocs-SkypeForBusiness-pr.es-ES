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
ms.openlocfilehash: ea5843908cf97a66e40ed2e9f945941c84615212
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528007"
---
# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="2a986-102">Tabla de grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a986-102">Pool table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a986-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2a986-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2a986-p101">La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.</span><span class="sxs-lookup"><span data-stu-id="2a986-p101">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a986-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="2a986-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2a986-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="2a986-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2a986-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="2a986-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2a986-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="2a986-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a986-110"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="2a986-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2a986-111">entero</span><span class="sxs-lookup"><span data-stu-id="2a986-111">int</span></span></p></td>
<td><p><span data-ttu-id="2a986-112">Principal</span><span class="sxs-lookup"><span data-stu-id="2a986-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2a986-113">Número único con el que se identifica a este grupo.</span><span class="sxs-lookup"><span data-stu-id="2a986-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a986-114"><strong>Nombredegrupo</strong></span><span class="sxs-lookup"><span data-stu-id="2a986-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="2a986-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2a986-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2a986-116">Singular </span><span class="sxs-lookup"><span data-stu-id="2a986-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="2a986-117">FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="2a986-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

