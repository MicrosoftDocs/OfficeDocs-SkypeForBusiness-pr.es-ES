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
ms.openlocfilehash: c8987bc1078dfdfaec8cccdb6625ceb9846ef6a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499177"
---
# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="05b62-102">Tabla ClientVersions en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05b62-102">ClientVersions table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05b62-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="05b62-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="05b62-p101">La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos versiones y tipos de clientes que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="05b62-p101">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05b62-106">Columna</span><span class="sxs-lookup"><span data-stu-id="05b62-106">Column</span></span></th>
<th><span data-ttu-id="05b62-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="05b62-107">Data Type</span></span></th>
<th><span data-ttu-id="05b62-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="05b62-108">Key/Index</span></span></th>
<th><span data-ttu-id="05b62-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="05b62-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05b62-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="05b62-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="05b62-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="05b62-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="05b62-112">Principal</span><span class="sxs-lookup"><span data-stu-id="05b62-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="05b62-113">Número único que identifica esta versión y este tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="05b62-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05b62-114"><strong>Versión</strong></span><span class="sxs-lookup"><span data-stu-id="05b62-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="05b62-115"><strong>nvarchar (256)</strong></span><span class="sxs-lookup"><span data-stu-id="05b62-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05b62-116">Nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="05b62-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05b62-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="05b62-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="05b62-118">entero</span><span class="sxs-lookup"><span data-stu-id="05b62-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05b62-119">Especifica el tipo de cliente usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="05b62-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="05b62-120">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="05b62-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="05b62-121">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05b62-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

