---
title: 'Lync Server 2013: vista de VoIPDetails'
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
ms.openlocfilehash: 4222ad7251c17501b1d9edec8cbdd8bafc015773
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="8db52-102">Vista VoIPDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8db52-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8db52-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8db52-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8db52-104">La vista VoIPDetails almacena información sobre las sesiones punto a punto, donde al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="8db52-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="8db52-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8db52-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8db52-106">La vista VoIPDetails contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">vista SessionDetails en Lync Server 2013</A> , además de las columnas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="8db52-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8db52-107">Columna</span><span class="sxs-lookup"><span data-stu-id="8db52-107">Column</span></span></th>
<th><span data-ttu-id="8db52-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8db52-108">Data Type</span></span></th>
<th><span data-ttu-id="8db52-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="8db52-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8db52-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8db52-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8db52-112">URI de teléfono del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8db52-113"><strong>El perfeccionamiento</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8db52-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8db52-115">URI de teléfono del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8db52-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8db52-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8db52-118">URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8db52-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8db52-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8db52-121">Tipo de URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="8db52-122">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8db52-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8db52-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8db52-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8db52-125">Inquilino del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8db52-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8db52-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8db52-128">URI de teléfono del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8db52-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8db52-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8db52-131">Servidor de mediación usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8db52-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8db52-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8db52-134">Servidor de mediación usado por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8db52-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8db52-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8db52-137">Puerta de enlace usada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8db52-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="8db52-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="8db52-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8db52-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8db52-140">Puerta de enlace usada por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="8db52-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

