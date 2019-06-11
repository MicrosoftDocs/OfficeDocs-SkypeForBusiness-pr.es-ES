---
title: 'Lync Server 2013: Tabla UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09bb2e3a71f81014bcb08952c03b59c93ac6a62f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="9ca7d-102">Tabla UserAgent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ca7d-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ca7d-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="9ca7d-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="9ca7d-104">La tabla UserAgent es una tabla de soporte que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="9ca7d-105">Cada registro de la tabla representa un agente de usuario</span><span class="sxs-lookup"><span data-stu-id="9ca7d-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ca7d-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="9ca7d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9ca7d-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="9ca7d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9ca7d-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="9ca7d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9ca7d-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="9ca7d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ca7d-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="9ca7d-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca7d-111">int</span><span class="sxs-lookup"><span data-stu-id="9ca7d-111">int</span></span></p></td>
<td><p><span data-ttu-id="9ca7d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="9ca7d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9ca7d-113">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca7d-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="9ca7d-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca7d-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9ca7d-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ca7d-116">Solo</span><span class="sxs-lookup"><span data-stu-id="9ca7d-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="9ca7d-117">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca7d-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="9ca7d-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca7d-119">smallint</span><span class="sxs-lookup"><span data-stu-id="9ca7d-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ca7d-120">1 es el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="9ca7d-121">2 es un servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="9ca7d-122">4 es Lync.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="9ca7d-123">8 es teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="9ca7d-124">16 es la consola de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="9ca7d-125">32 es la herramienta de validación de implementación (DVT).</span><span class="sxs-lookup"><span data-stu-id="9ca7d-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="9ca7d-126">64 son Lync en equipos Macintosh.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="9ca7d-127">128 es el operador R2 de Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="9ca7d-128">256 es el servicio de anuncios de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="9ca7d-129">512 es operador automático de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="9ca7d-130">1024 es una aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="9ca7d-131">2048 está fuera del control de voz.</span><span class="sxs-lookup"><span data-stu-id="9ca7d-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

