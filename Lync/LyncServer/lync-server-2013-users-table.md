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
ms.openlocfilehash: 5ebf521b1cf215e2a7d5bdd30e5fa4be92334a79
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530037"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="f03be-102">Tabla users en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f03be-102">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f03be-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f03be-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f03be-104">La tabla users es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="f03be-104">The Users table is a supporting table.</span></span> <span data-ttu-id="f03be-105">Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f03be-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f03be-106">Columna</span><span class="sxs-lookup"><span data-stu-id="f03be-106">Column</span></span></th>
<th><span data-ttu-id="f03be-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f03be-107">Data Type</span></span></th>
<th><span data-ttu-id="f03be-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="f03be-108">Key/Index</span></span></th>
<th><span data-ttu-id="f03be-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="f03be-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f03be-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f03be-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f03be-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f03be-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f03be-112">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="f03be-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f03be-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f03be-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f03be-114">entero</span><span class="sxs-lookup"><span data-stu-id="f03be-114">int</span></span></p></td>
<td><p><span data-ttu-id="f03be-115">Principal</span><span class="sxs-lookup"><span data-stu-id="f03be-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="f03be-116">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="f03be-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f03be-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="f03be-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f03be-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f03be-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f03be-119">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="f03be-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f03be-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="f03be-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="f03be-121">entero</span><span class="sxs-lookup"><span data-stu-id="f03be-121">int</span></span></p></td>
<td><p><span data-ttu-id="f03be-122">Externa</span><span class="sxs-lookup"><span data-stu-id="f03be-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f03be-123">IDENTIFICADOR de inquilino de este usuario.</span><span class="sxs-lookup"><span data-stu-id="f03be-123">This user’s Tenant ID.</span></span> <span data-ttu-id="f03be-124">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f03be-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f03be-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f03be-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f03be-126">entero</span><span class="sxs-lookup"><span data-stu-id="f03be-126">int</span></span></p></td>
<td><p><span data-ttu-id="f03be-127">Externa</span><span class="sxs-lookup"><span data-stu-id="f03be-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f03be-128">Tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="f03be-128">This user’s URI type.</span></span> <span data-ttu-id="f03be-129">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f03be-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

