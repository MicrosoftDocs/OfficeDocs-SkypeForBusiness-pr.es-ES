---
title: 'Lync Server 2013: tabla ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96e8f035dbc0005bb331a188a308f456992f091
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="e5bd3-102">Tabla ClientVersions en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5bd3-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5bd3-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e5bd3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e5bd3-p101">La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos versiones y tipos de clientes que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="e5bd3-p101">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5bd3-106">Columna</span><span class="sxs-lookup"><span data-stu-id="e5bd3-106">Column</span></span></th>
<th><span data-ttu-id="e5bd3-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e5bd3-107">Data Type</span></span></th>
<th><span data-ttu-id="e5bd3-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="e5bd3-108">Key/Index</span></span></th>
<th><span data-ttu-id="e5bd3-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="e5bd3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5bd3-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="e5bd3-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5bd3-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="e5bd3-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="e5bd3-112">Principal</span><span class="sxs-lookup"><span data-stu-id="e5bd3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5bd3-113">Número único que identifica esta versión y este tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="e5bd3-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5bd3-114"><strong>Versión</strong></span><span class="sxs-lookup"><span data-stu-id="e5bd3-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="e5bd3-115"><strong>nvarchar (256)</strong></span><span class="sxs-lookup"><span data-stu-id="e5bd3-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5bd3-116">Nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="e5bd3-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5bd3-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e5bd3-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5bd3-118">int</span><span class="sxs-lookup"><span data-stu-id="e5bd3-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5bd3-119">Especifica el tipo de cliente usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="e5bd3-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="e5bd3-120">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e5bd3-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="e5bd3-121">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5bd3-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

