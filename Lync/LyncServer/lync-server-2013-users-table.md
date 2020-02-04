---
title: 'Lync Server 2013: Tabla Users'
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
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="ee506-102">Tabla Users en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee506-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee506-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ee506-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ee506-104">La tabla usuarios es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ee506-104">The Users table is a supporting table.</span></span> <span data-ttu-id="ee506-105">Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ee506-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee506-106">Columna</span><span class="sxs-lookup"><span data-stu-id="ee506-106">Column</span></span></th>
<th><span data-ttu-id="ee506-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ee506-107">Data Type</span></span></th>
<th><span data-ttu-id="ee506-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="ee506-108">Key/Index</span></span></th>
<th><span data-ttu-id="ee506-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="ee506-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee506-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ee506-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ee506-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ee506-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee506-112">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="ee506-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee506-113"><strong>Iddeusuario</strong></span><span class="sxs-lookup"><span data-stu-id="ee506-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee506-114">int</span><span class="sxs-lookup"><span data-stu-id="ee506-114">int</span></span></p></td>
<td><p><span data-ttu-id="ee506-115">Primary</span><span class="sxs-lookup"><span data-stu-id="ee506-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="ee506-116">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="ee506-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee506-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ee506-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ee506-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ee506-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ee506-119">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="ee506-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee506-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="ee506-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee506-121">int</span><span class="sxs-lookup"><span data-stu-id="ee506-121">int</span></span></p></td>
<td><p><span data-ttu-id="ee506-122">Extranjero</span><span class="sxs-lookup"><span data-stu-id="ee506-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ee506-123">El identificador de inquilino de este usuario.</span><span class="sxs-lookup"><span data-stu-id="ee506-123">This user’s Tenant ID.</span></span> <span data-ttu-id="ee506-124">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ee506-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee506-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ee506-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee506-126">int</span><span class="sxs-lookup"><span data-stu-id="ee506-126">int</span></span></p></td>
<td><p><span data-ttu-id="ee506-127">Extranjero</span><span class="sxs-lookup"><span data-stu-id="ee506-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ee506-128">Tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="ee506-128">This user’s URI type.</span></span> <span data-ttu-id="ee506-129">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ee506-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

