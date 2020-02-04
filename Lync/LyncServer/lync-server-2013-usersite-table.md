---
title: 'Lync Server 2013: Tabla UserSite'
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
ms.openlocfilehash: 7e316fe33ac77784a681a71b9cabd0613bb1cc1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="8148d-102">Tabla UserSite en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8148d-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8148d-103">_**Última modificación del tema:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="8148d-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="8148d-104">La tabla UserSite es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="8148d-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="8148d-105">Cada registro representa un sitio de usuario definido en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="8148d-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8148d-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="8148d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8148d-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="8148d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8148d-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="8148d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8148d-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="8148d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8148d-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="8148d-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8148d-111">int</span><span class="sxs-lookup"><span data-stu-id="8148d-111">int</span></span></p></td>
<td><p><span data-ttu-id="8148d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="8148d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8148d-113">Número único que identifica el sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="8148d-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8148d-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="8148d-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="8148d-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8148d-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8148d-116">Solo</span><span class="sxs-lookup"><span data-stu-id="8148d-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="8148d-117">Nombre del sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="8148d-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8148d-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="8148d-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8148d-119">int</span><span class="sxs-lookup"><span data-stu-id="8148d-119">int</span></span></p></td>
<td><p><span data-ttu-id="8148d-120">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8148d-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8148d-121">Tabla de la tabla a la que se hace referencia <a href="lync-server-2013-region-table.md">en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8148d-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

