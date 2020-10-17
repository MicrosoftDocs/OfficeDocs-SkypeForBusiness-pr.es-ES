---
title: 'Lync Server 2013: vista de VoIPDetails'
description: 'Lync Server 2013: vista de VoIPDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566206"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="3faa5-103">Vista VoIPDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3faa5-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3faa5-104">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3faa5-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3faa5-105">La vista VoIPDetails almacena información sobre las sesiones punto a punto, donde al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="3faa5-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="3faa5-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3faa5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3faa5-107">La vista VoIPDetails contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">vista SessionDetails en Lync Server 2013</A> , además de las columnas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="3faa5-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3faa5-108">Columna</span><span class="sxs-lookup"><span data-stu-id="3faa5-108">Column</span></span></th>
<th><span data-ttu-id="3faa5-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="3faa5-109">Data Type</span></span></th>
<th><span data-ttu-id="3faa5-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="3faa5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3faa5-111"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3faa5-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-113">URI de teléfono del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3faa5-114"><strong>El perfeccionamiento</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3faa5-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-116">URI de teléfono del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3faa5-117"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3faa5-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-119">URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3faa5-120"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3faa5-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-122">Tipo de URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="3faa5-123">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3faa5-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3faa5-124"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3faa5-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-126">Inquilino del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3faa5-127"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3faa5-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-129">URI de teléfono del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3faa5-130"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3faa5-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-132">Servidor de mediación usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3faa5-133"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3faa5-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-135">Servidor de mediación usado por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3faa5-136"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3faa5-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-138">Puerta de enlace usada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3faa5-139"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="3faa5-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="3faa5-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3faa5-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3faa5-141">Puerta de enlace usada por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="3faa5-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

