---
title: 'Lync Server 2013: tabla de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98a34028ebec126c8d5fc5ec838a22180ccb0fa7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="afef7-102">Tabla user en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afef7-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afef7-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="afef7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="afef7-p101">La tabla User es una tabla de apoyo donde se almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.</span><span class="sxs-lookup"><span data-stu-id="afef7-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afef7-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="afef7-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="afef7-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="afef7-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afef7-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="afef7-111">int</span><span class="sxs-lookup"><span data-stu-id="afef7-111">int</span></span></p></td>
<td><p><span data-ttu-id="afef7-112">Principal</span><span class="sxs-lookup"><span data-stu-id="afef7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="afef7-113">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="afef7-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afef7-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="afef7-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="afef7-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="afef7-116">Única</span><span class="sxs-lookup"><span data-stu-id="afef7-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="afef7-117">Cadena del URI.</span><span class="sxs-lookup"><span data-stu-id="afef7-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afef7-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="afef7-119">int</span><span class="sxs-lookup"><span data-stu-id="afef7-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afef7-120">1 es un tipo de URI desconocido.</span><span class="sxs-lookup"><span data-stu-id="afef7-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="afef7-121">2 es un URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="afef7-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="afef7-122">4 es un URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="afef7-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="afef7-123">8 es un URI de teléfono.</span><span class="sxs-lookup"><span data-stu-id="afef7-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afef7-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="afef7-125">int</span><span class="sxs-lookup"><span data-stu-id="afef7-125">int</span></span></p></td>
<td><p><span data-ttu-id="afef7-126">Externa</span><span class="sxs-lookup"><span data-stu-id="afef7-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afef7-127">Inquilino del usuario, con referencia a la tabla Tenant.</span><span class="sxs-lookup"><span data-stu-id="afef7-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afef7-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afef7-129">datetime</span><span class="sxs-lookup"><span data-stu-id="afef7-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afef7-130">Última marca de tiempo en la que el usuario tuvo una llamada de audio de mala calidad.</span><span class="sxs-lookup"><span data-stu-id="afef7-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afef7-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="afef7-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="afef7-132">datetime</span><span class="sxs-lookup"><span data-stu-id="afef7-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afef7-133">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="afef7-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

