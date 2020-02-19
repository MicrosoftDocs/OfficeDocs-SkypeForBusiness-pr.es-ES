---
title: 'Lync Server 2013: tabla UserSite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ae68f3c5512c3f7828fe197712637e4a60e9ea5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="88b4c-102">Tabla UserSite en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b4c-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88b4c-103">_**Última modificación del tema:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="88b4c-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="88b4c-104">La tabla UserSite es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="88b4c-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="88b4c-105">Cada registro representa un sitio de usuario definido en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="88b4c-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88b4c-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="88b4c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="88b4c-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="88b4c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="88b4c-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="88b4c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="88b4c-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="88b4c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88b4c-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="88b4c-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="88b4c-111">int</span><span class="sxs-lookup"><span data-stu-id="88b4c-111">int</span></span></p></td>
<td><p><span data-ttu-id="88b4c-112">Principal</span><span class="sxs-lookup"><span data-stu-id="88b4c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="88b4c-113">Número único que identifica el sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="88b4c-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b4c-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="88b4c-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="88b4c-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="88b4c-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="88b4c-116">Única</span><span class="sxs-lookup"><span data-stu-id="88b4c-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="88b4c-117">Nombre del sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="88b4c-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b4c-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="88b4c-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="88b4c-119">int</span><span class="sxs-lookup"><span data-stu-id="88b4c-119">int</span></span></p></td>
<td><p><span data-ttu-id="88b4c-120">Externa</span><span class="sxs-lookup"><span data-stu-id="88b4c-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88b4c-121">Referencia de la <a href="lync-server-2013-region-table.md">tabla region en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="88b4c-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

