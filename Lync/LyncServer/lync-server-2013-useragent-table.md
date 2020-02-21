---
title: 'Lync Server 2013: tabla UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b9abca1aaaff164759f195f8f60de335e279335
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="cef77-102">Tabla UserAgent en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cef77-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cef77-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="cef77-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="cef77-104">La tabla UserAgent es una tabla de apoyo que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cef77-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="cef77-105">Cada registro de la tabla representa un agente de usuario</span><span class="sxs-lookup"><span data-stu-id="cef77-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cef77-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="cef77-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="cef77-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="cef77-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="cef77-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="cef77-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="cef77-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="cef77-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cef77-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="cef77-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="cef77-111">int</span><span class="sxs-lookup"><span data-stu-id="cef77-111">int</span></span></p></td>
<td><p><span data-ttu-id="cef77-112">Principal</span><span class="sxs-lookup"><span data-stu-id="cef77-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cef77-113">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="cef77-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cef77-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="cef77-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="cef77-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cef77-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cef77-116">Única</span><span class="sxs-lookup"><span data-stu-id="cef77-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="cef77-117">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="cef77-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cef77-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="cef77-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="cef77-119">smallint</span><span class="sxs-lookup"><span data-stu-id="cef77-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cef77-120">1 es el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="cef77-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="cef77-121">2 es un servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="cef77-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="cef77-122">4 es Lync.</span><span class="sxs-lookup"><span data-stu-id="cef77-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="cef77-123">8 es teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="cef77-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="cef77-124">16 es consola de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="cef77-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="cef77-125">32 es la herramienta de validación de implementación (DVT).</span><span class="sxs-lookup"><span data-stu-id="cef77-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="cef77-126">64 es Lync en equipos Macintosh.</span><span class="sxs-lookup"><span data-stu-id="cef77-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="cef77-127">128 es el operador de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="cef77-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="cef77-128">256 es el servicio de anuncio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cef77-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="cef77-129">512 es operador automático de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cef77-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="cef77-130">1024 es una aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="cef77-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="cef77-131">2048 está fuera del control de voz.</span><span class="sxs-lookup"><span data-stu-id="cef77-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

