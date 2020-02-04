---
title: 'Lync Server 2013: Tabla User'
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
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="3b4b3-102">Tabla User en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b4b3-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b4b3-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3b4b3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3b4b3-104">La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="3b4b3-105">Cada registro de la tabla representa un usuario.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b4b3-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3b4b3-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3b4b3-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3b4b3-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b4b3-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3b4b3-111">int</span><span class="sxs-lookup"><span data-stu-id="3b4b3-111">int</span></span></p></td>
<td><p><span data-ttu-id="3b4b3-112">Primary</span><span class="sxs-lookup"><span data-stu-id="3b4b3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3b4b3-113">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b4b3-114"><strong>URL</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="3b4b3-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3b4b3-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3b4b3-116">Solo</span><span class="sxs-lookup"><span data-stu-id="3b4b3-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="3b4b3-117">Cadena URI.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b4b3-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="3b4b3-119">int</span><span class="sxs-lookup"><span data-stu-id="3b4b3-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b4b3-120">1 es un tipo de URI desconocido.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="3b4b3-121">2 es el URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="3b4b3-122">4 es el URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="3b4b3-123">8 es el URI del teléfono.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b4b3-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3b4b3-125">int</span><span class="sxs-lookup"><span data-stu-id="3b4b3-125">int</span></span></p></td>
<td><p><span data-ttu-id="3b4b3-126">Extranjero</span><span class="sxs-lookup"><span data-stu-id="3b4b3-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3b4b3-127">Espacio empresarial del usuario al que se hace referencia desde la tabla de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b4b3-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3b4b3-129">datetime</span><span class="sxs-lookup"><span data-stu-id="3b4b3-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b4b3-130">Última marca de tiempo cuando el usuario tenía una mala llamada de audio.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b4b3-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="3b4b3-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="3b4b3-132">datetime</span><span class="sxs-lookup"><span data-stu-id="3b4b3-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b4b3-133">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="3b4b3-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

