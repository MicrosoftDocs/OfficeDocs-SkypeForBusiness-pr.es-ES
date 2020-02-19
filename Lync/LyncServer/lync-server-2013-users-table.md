---
title: 'Lync Server 2013: tabla de usuarios'
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
ms.openlocfilehash: 18d3afde02d93848c656a08617f08dcb55dc4a9a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="14174-102">Tabla users en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14174-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14174-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="14174-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="14174-104">La tabla users es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="14174-104">The Users table is a supporting table.</span></span> <span data-ttu-id="14174-105">Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14174-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14174-106">Columna</span><span class="sxs-lookup"><span data-stu-id="14174-106">Column</span></span></th>
<th><span data-ttu-id="14174-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="14174-107">Data Type</span></span></th>
<th><span data-ttu-id="14174-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="14174-108">Key/Index</span></span></th>
<th><span data-ttu-id="14174-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="14174-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14174-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="14174-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="14174-111">datetime</span><span class="sxs-lookup"><span data-stu-id="14174-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14174-112">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="14174-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14174-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="14174-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="14174-114">int</span><span class="sxs-lookup"><span data-stu-id="14174-114">int</span></span></p></td>
<td><p><span data-ttu-id="14174-115">Principal</span><span class="sxs-lookup"><span data-stu-id="14174-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="14174-116">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="14174-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14174-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="14174-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="14174-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="14174-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="14174-119">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="14174-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14174-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="14174-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="14174-121">int</span><span class="sxs-lookup"><span data-stu-id="14174-121">int</span></span></p></td>
<td><p><span data-ttu-id="14174-122">Externa</span><span class="sxs-lookup"><span data-stu-id="14174-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="14174-123">IDENTIFICADOR de inquilino de este usuario.</span><span class="sxs-lookup"><span data-stu-id="14174-123">This user’s Tenant ID.</span></span> <span data-ttu-id="14174-124">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="14174-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14174-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="14174-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="14174-126">int</span><span class="sxs-lookup"><span data-stu-id="14174-126">int</span></span></p></td>
<td><p><span data-ttu-id="14174-127">Externa</span><span class="sxs-lookup"><span data-stu-id="14174-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="14174-128">Tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="14174-128">This user’s URI type.</span></span> <span data-ttu-id="14174-129">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="14174-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

