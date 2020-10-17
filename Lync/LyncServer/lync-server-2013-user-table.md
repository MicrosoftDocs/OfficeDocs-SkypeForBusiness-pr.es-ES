---
title: 'Lync Server 2013: tabla de usuario'
description: 'Lync Server 2013: tabla de usuario.'
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
ms.openlocfilehash: 15d1ac08a229f4afea35a2727ef1105a5f24b826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558906"
---
# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="d2855-103">Tabla user en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2855-103">User table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2855-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d2855-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d2855-p101">La tabla User es una tabla de apoyo donde se almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.</span><span class="sxs-lookup"><span data-stu-id="d2855-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2855-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d2855-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d2855-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d2855-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2855-111"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-111"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d2855-112">entero</span><span class="sxs-lookup"><span data-stu-id="d2855-112">int</span></span></p></td>
<td><p><span data-ttu-id="d2855-113">Principal</span><span class="sxs-lookup"><span data-stu-id="d2855-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d2855-114">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="d2855-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2855-115"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-115"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="d2855-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d2855-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d2855-117">Única</span><span class="sxs-lookup"><span data-stu-id="d2855-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="d2855-118">Cadena del URI.</span><span class="sxs-lookup"><span data-stu-id="d2855-118">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2855-119"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-119"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="d2855-120">entero</span><span class="sxs-lookup"><span data-stu-id="d2855-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d2855-121">1 es un tipo de URI desconocido.</span><span class="sxs-lookup"><span data-stu-id="d2855-121">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="d2855-122">2 es un URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="d2855-122">2 is user URI.</span></span></p>
<p><span data-ttu-id="d2855-123">4 es un URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d2855-123">4 is conference URI.</span></span></p>
<p><span data-ttu-id="d2855-124">8 es un URI de teléfono.</span><span class="sxs-lookup"><span data-stu-id="d2855-124">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2855-125"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-125"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d2855-126">entero</span><span class="sxs-lookup"><span data-stu-id="d2855-126">int</span></span></p></td>
<td><p><span data-ttu-id="d2855-127">Externa</span><span class="sxs-lookup"><span data-stu-id="d2855-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d2855-128">Inquilino del usuario, con referencia a la tabla Tenant.</span><span class="sxs-lookup"><span data-stu-id="d2855-128">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2855-129"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-129"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d2855-130">datetime</span><span class="sxs-lookup"><span data-stu-id="d2855-130">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d2855-131">Última marca de tiempo en la que el usuario tuvo una llamada de audio de mala calidad.</span><span class="sxs-lookup"><span data-stu-id="d2855-131">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2855-132"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="d2855-132"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d2855-133">datetime</span><span class="sxs-lookup"><span data-stu-id="d2855-133">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d2855-134">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="d2855-134">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

