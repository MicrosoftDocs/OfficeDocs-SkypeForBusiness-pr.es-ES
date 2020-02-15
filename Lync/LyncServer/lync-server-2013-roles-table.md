---
title: 'Lync Server 2013: tabla roles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roles table
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399043(v=OCS.15)
ms:contentKeyID: 48185893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3c241f685e9acc24b82acab1c7f50e1e15754b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roles-table-in-lync-server-2013"></a><span data-ttu-id="1b6a9-102">Tabla roles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b6a9-102">Roles table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b6a9-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1b6a9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1b6a9-104">La tabla roles es una tabla estática que almacena la lista de posibles roles de conferencia, como Attendee y moderador.</span><span class="sxs-lookup"><span data-stu-id="1b6a9-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b6a9-105">Columna</span><span class="sxs-lookup"><span data-stu-id="1b6a9-105">Column</span></span></th>
<th><span data-ttu-id="1b6a9-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1b6a9-106">Data Type</span></span></th>
<th><span data-ttu-id="1b6a9-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="1b6a9-107">Key/Index</span></span></th>
<th><span data-ttu-id="1b6a9-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="1b6a9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b6a9-109"><strong>RoleId</strong></span><span class="sxs-lookup"><span data-stu-id="1b6a9-109"><strong>RoleId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b6a9-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1b6a9-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1b6a9-111">Principal</span><span class="sxs-lookup"><span data-stu-id="1b6a9-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b6a9-112"><strong>Rol</strong></span><span class="sxs-lookup"><span data-stu-id="1b6a9-112"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="1b6a9-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b6a9-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b6a9-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="1b6a9-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b6a9-115">0 - Desconocido</span><span class="sxs-lookup"><span data-stu-id="1b6a9-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="1b6a9-116">1-moderador</span><span class="sxs-lookup"><span data-stu-id="1b6a9-116">1 - Presenter</span></span></p></li>
<li><p><span data-ttu-id="1b6a9-117">2-Attendee</span><span class="sxs-lookup"><span data-stu-id="1b6a9-117">2 - Attendee</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

