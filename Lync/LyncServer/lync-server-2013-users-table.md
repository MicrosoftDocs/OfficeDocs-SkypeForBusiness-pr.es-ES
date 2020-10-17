---
title: 'Lync Server 2013: tabla de usuarios'
description: 'Lync Server 2013: tabla de usuarios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548636"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="09c14-103">Tabla users en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09c14-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09c14-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="09c14-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="09c14-105">La tabla users es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="09c14-105">The Users table is a supporting table.</span></span> <span data-ttu-id="09c14-106">Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="09c14-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09c14-107">Columna</span><span class="sxs-lookup"><span data-stu-id="09c14-107">Column</span></span></th>
<th><span data-ttu-id="09c14-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="09c14-108">Data Type</span></span></th>
<th><span data-ttu-id="09c14-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="09c14-109">Key/Index</span></span></th>
<th><span data-ttu-id="09c14-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="09c14-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09c14-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="09c14-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="09c14-112">datetime</span><span class="sxs-lookup"><span data-stu-id="09c14-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09c14-113">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="09c14-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c14-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="09c14-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="09c14-115">entero</span><span class="sxs-lookup"><span data-stu-id="09c14-115">int</span></span></p></td>
<td><p><span data-ttu-id="09c14-116">Principal</span><span class="sxs-lookup"><span data-stu-id="09c14-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="09c14-117">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="09c14-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09c14-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="09c14-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="09c14-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="09c14-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="09c14-120">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="09c14-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c14-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="09c14-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="09c14-122">entero</span><span class="sxs-lookup"><span data-stu-id="09c14-122">int</span></span></p></td>
<td><p><span data-ttu-id="09c14-123">Externa</span><span class="sxs-lookup"><span data-stu-id="09c14-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09c14-124">IDENTIFICADOR de inquilino de este usuario.</span><span class="sxs-lookup"><span data-stu-id="09c14-124">This user’s Tenant ID.</span></span> <span data-ttu-id="09c14-125">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="09c14-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09c14-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="09c14-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="09c14-127">entero</span><span class="sxs-lookup"><span data-stu-id="09c14-127">int</span></span></p></td>
<td><p><span data-ttu-id="09c14-128">Externa</span><span class="sxs-lookup"><span data-stu-id="09c14-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="09c14-129">Tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="09c14-129">This user’s URI type.</span></span> <span data-ttu-id="09c14-130">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="09c14-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

