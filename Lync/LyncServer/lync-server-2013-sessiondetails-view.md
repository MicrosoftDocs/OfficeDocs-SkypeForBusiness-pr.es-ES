---
title: 'Lync Server 2013: vista de SessionDetails'
description: 'Lync Server 2013: vista de SessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573246"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="9c51a-103">Vista SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c51a-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c51a-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9c51a-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9c51a-105">La vista SessionDetails almacena información sobre sesiones punto a punto, que podrían ser una llamada telefónica VoIP-VoIP, una sesión de mensajería instantánea (MI) entre dos partes o cualquier otro tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="9c51a-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c51a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c51a-107">Columna</span><span class="sxs-lookup"><span data-stu-id="9c51a-107">Column</span></span></th>
<th><span data-ttu-id="9c51a-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9c51a-108">Data Type</span></span></th>
<th><span data-ttu-id="9c51a-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="9c51a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9c51a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c51a-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-112">Time of session request.</span></span> <span data-ttu-id="9c51a-113">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9c51a-114">Consulte la tabla de <a href="lync-server-2013-dialogs-table.md">cuadros de diálogo en la tabla de Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-116">entero</span><span class="sxs-lookup"><span data-stu-id="9c51a-116">int</span></span></p></td>
<td><p><span data-ttu-id="9c51a-117">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-117">ID number to identify the session.</span></span> <span data-ttu-id="9c51a-118">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9c51a-119">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-121">datetime</span><span class="sxs-lookup"><span data-stu-id="9c51a-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c51a-p104">Fecha y hora de la primera solicitud INVITE. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO). Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="9c51a-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9c51a-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-129">URI del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-130"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-131">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9c51a-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-132">URI del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-133"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-135">Tipo de URI del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="9c51a-136">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-139">Tipo de URI del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="9c51a-140">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9c51a-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-143">Inquilino del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="9c51a-144">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-145"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-147">Inquilino del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="9c51a-148">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-150">identificador</span><span class="sxs-lookup"><span data-stu-id="9c51a-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9c51a-151">Identificador único del extremo del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-152"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-153">identificador</span><span class="sxs-lookup"><span data-stu-id="9c51a-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9c51a-154">Identificador único del extremo del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-156">datetime</span><span class="sxs-lookup"><span data-stu-id="9c51a-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c51a-157">Fecha y hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-159">entero</span><span class="sxs-lookup"><span data-stu-id="9c51a-159">int</span></span></p></td>
<td><p><span data-ttu-id="9c51a-160">Número de mensajes que envió el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-162">entero</span><span class="sxs-lookup"><span data-stu-id="9c51a-162">int</span></span></p></td>
<td><p><span data-ttu-id="9c51a-163">Número de mensajes que envió el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-166">Versión de cliente que usa el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-168">entero</span><span class="sxs-lookup"><span data-stu-id="9c51a-168">int</span></span></p></td>
<td><p><span data-ttu-id="9c51a-169">Cliente que usa el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-169">Client used by the user who started the session.</span></span> <span data-ttu-id="9c51a-170">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9c51a-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-173">Nombre de la categoría del cliente que usa el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-175">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-176">Versión de cliente que usa el usuario que se unió a la sesión</span><span class="sxs-lookup"><span data-stu-id="9c51a-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-177"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-178">entero</span><span class="sxs-lookup"><span data-stu-id="9c51a-178">int</span></span></p></td>
<td><p><span data-ttu-id="9c51a-179">Cliente que usa el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="9c51a-180">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-182">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9c51a-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-183">Nombre de la categoría del cliente que usa el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-185">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9c51a-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-186">URI del usuario destinatario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-188">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9c51a-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-189">Tipo de URI del usuario destinatario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="9c51a-190">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9c51a-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-193">URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-196">Tipo de URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="9c51a-197">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-200">Inquilino del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="9c51a-201">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-202"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-203">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9c51a-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-204">URI del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-205"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-206">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-207">Tipo de URI del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="9c51a-208">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-209"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-210">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-211">Inquilino del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="9c51a-212">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-213"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-214">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="9c51a-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-p116">Identificador del diálogo SIP. El formato es:</span><span class="sxs-lookup"><span data-stu-id="9c51a-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="9c51a-217">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="9c51a-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-218"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-219">identificador</span><span class="sxs-lookup"><span data-stu-id="9c51a-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9c51a-220">Identificador único global usado para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="9c51a-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-221"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-222">datetime</span><span class="sxs-lookup"><span data-stu-id="9c51a-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c51a-223">Fecha y hora del diálogo que se sustituyó por la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="9c51a-224">Se usa en combinación con ReplaceDialogIdSeq para identificar de forma exclusiva un diálogo que se sustituye con la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="9c51a-225">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-226"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-227">entero</span><span class="sxs-lookup"><span data-stu-id="9c51a-227">int</span></span></p></td>
<td><p><span data-ttu-id="9c51a-228">Número de identificador de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-228">ID number to identify the session.</span></span> <span data-ttu-id="9c51a-229">Se usa en combinación con ReplaceDialogIdTime para identificar de forma exclusiva un diálogo que se sustituye con la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="9c51a-230">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9c51a-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-231"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-232">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="9c51a-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-p119">El identificador de diálogo SIP que sustituye la sesión. El formato es:</span><span class="sxs-lookup"><span data-stu-id="9c51a-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="9c51a-235">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="9c51a-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-236"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-237">datetime</span><span class="sxs-lookup"><span data-stu-id="9c51a-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c51a-p120">Fecha y hora de la respuesta al primer mensaje INVITE. Este campo se suele rellenar con los datos generados a partir del mensaje INVITE inicial. Si no hay un mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="9c51a-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-242">entero</span><span class="sxs-lookup"><span data-stu-id="9c51a-242">int</span></span></p></td>
<td><p><span data-ttu-id="9c51a-p121">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="9c51a-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-246"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-247">entero</span><span class="sxs-lookup"><span data-stu-id="9c51a-247">int</span></span></p></td>
<td><p><span data-ttu-id="9c51a-248">Identificador de diagnóstico capturado de los encabezados SIP.</span><span class="sxs-lookup"><span data-stu-id="9c51a-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-251">Tipo de contenido de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-254">FQDN del servidor front-end que capturó los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-255"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-257">FQDN del grupo que capturó los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-260">FQDN del servidor perimetral que usa el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-262">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-263">FQDN del servidor perimetral que usa el usuario que inició la sesión</span><span class="sxs-lookup"><span data-stu-id="9c51a-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-265">bit</span><span class="sxs-lookup"><span data-stu-id="9c51a-265">bit</span></span></p></td>
<td><p><span data-ttu-id="9c51a-266">Indica si el usuario que inició la sesión se conectó desde la red interna.</span><span class="sxs-lookup"><span data-stu-id="9c51a-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-268">bit</span><span class="sxs-lookup"><span data-stu-id="9c51a-268">bit</span></span></p></td>
<td><p><span data-ttu-id="9c51a-269">Indica si el usuario que se unió a la sesión se conectó desde la red interna.</span><span class="sxs-lookup"><span data-stu-id="9c51a-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-271">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c51a-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-272">Prioridad de llamada de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9c51a-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-274">smallint</span><span class="sxs-lookup"><span data-stu-id="9c51a-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="9c51a-p122">Indica los atributos del usuario que inició la sesión. Las definiciones de atributos permitidas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c51a-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9c51a-277">0x01 - Integrado en teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="9c51a-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-279">smallint</span><span class="sxs-lookup"><span data-stu-id="9c51a-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="9c51a-p123">Indica los atributos del usuario que inició la sesión. Las definiciones de atributos permitidas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c51a-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9c51a-282">0x01 - Integrado en teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="9c51a-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c51a-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-284">smallint</span><span class="sxs-lookup"><span data-stu-id="9c51a-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="9c51a-p124">Indica los atributos de llamada. Se permiten las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="9c51a-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9c51a-287">0x01 - Reintento de sesión</span><span class="sxs-lookup"><span data-stu-id="9c51a-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="9c51a-288">0x02 - Una llamada realizada por un agente en nombre de un Grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="9c51a-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c51a-289"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="9c51a-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="9c51a-290">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="9c51a-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9c51a-291">Ubicación de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="9c51a-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

