---
title: 'Lync Server 2013: Tabla Pool'
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
ms.openlocfilehash: 31fd637ac4d612d53804f679b82f1de53b327772
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="404c9-102">Tabla Pool en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="404c9-102">Pool table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="404c9-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="404c9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="404c9-104">La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="404c9-104">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="404c9-105">Cada registro de la tabla representa un grupo.</span><span class="sxs-lookup"><span data-stu-id="404c9-105">Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="404c9-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="404c9-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="404c9-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="404c9-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="404c9-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="404c9-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="404c9-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="404c9-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="404c9-110"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="404c9-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="404c9-111">int</span><span class="sxs-lookup"><span data-stu-id="404c9-111">int</span></span></p></td>
<td><p><span data-ttu-id="404c9-112">Primary</span><span class="sxs-lookup"><span data-stu-id="404c9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="404c9-113">Número único que identifica este grupo.</span><span class="sxs-lookup"><span data-stu-id="404c9-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="404c9-114"><strong>Nombredegrupo</strong></span><span class="sxs-lookup"><span data-stu-id="404c9-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="404c9-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="404c9-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="404c9-116">Solo </span><span class="sxs-lookup"><span data-stu-id="404c9-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="404c9-117">FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="404c9-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

