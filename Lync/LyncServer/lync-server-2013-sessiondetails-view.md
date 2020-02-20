---
title: 'Lync Server 2013: vista de SessionDetails'
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
ms.openlocfilehash: 3f7a143a0812b19a840c7eb339e80611720a08b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="86dc5-102">Vista SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86dc5-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86dc5-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="86dc5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="86dc5-104">La vista SessionDetails almacena información sobre sesiones punto a punto, que podrían ser una llamada telefónica VoIP-VoIP, una sesión de mensajería instantánea (MI) entre dos partes o cualquier otro tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="86dc5-105">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86dc5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86dc5-106">Columna</span><span class="sxs-lookup"><span data-stu-id="86dc5-106">Column</span></span></th>
<th><span data-ttu-id="86dc5-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="86dc5-107">Data Type</span></span></th>
<th><span data-ttu-id="86dc5-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="86dc5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-110">datetime</span><span class="sxs-lookup"><span data-stu-id="86dc5-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="86dc5-111">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-111">Time of session request.</span></span> <span data-ttu-id="86dc5-112">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="86dc5-113">Consulte la tabla de <a href="lync-server-2013-dialogs-table.md">cuadros de diálogo en la tabla de Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-115">int</span><span class="sxs-lookup"><span data-stu-id="86dc5-115">int</span></span></p></td>
<td><p><span data-ttu-id="86dc5-116">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-116">ID number to identify the session.</span></span> <span data-ttu-id="86dc5-117">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="86dc5-118">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-120">datetime</span><span class="sxs-lookup"><span data-stu-id="86dc5-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="86dc5-p104">Fecha y hora de la primera solicitud INVITE. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO). Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="86dc5-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="86dc5-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-128">URI del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="86dc5-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-131">URI del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-134">Tipo de URI del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="86dc5-135">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-138">Tipo de URI del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="86dc5-139">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="86dc5-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-142">Inquilino del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="86dc5-143">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-146">Inquilino del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="86dc5-147">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-149">identificador</span><span class="sxs-lookup"><span data-stu-id="86dc5-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="86dc5-150">Identificador único del extremo del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-152">identificador</span><span class="sxs-lookup"><span data-stu-id="86dc5-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="86dc5-153">Identificador único del extremo del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-155">datetime</span><span class="sxs-lookup"><span data-stu-id="86dc5-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="86dc5-156">Fecha y hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-158">int</span><span class="sxs-lookup"><span data-stu-id="86dc5-158">int</span></span></p></td>
<td><p><span data-ttu-id="86dc5-159">Número de mensajes que envió el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-161">int</span><span class="sxs-lookup"><span data-stu-id="86dc5-161">int</span></span></p></td>
<td><p><span data-ttu-id="86dc5-162">Número de mensajes que envió el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-165">Versión de cliente que usa el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-167">int</span><span class="sxs-lookup"><span data-stu-id="86dc5-167">int</span></span></p></td>
<td><p><span data-ttu-id="86dc5-168">Cliente que usa el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-168">Client used by the user who started the session.</span></span> <span data-ttu-id="86dc5-169">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="86dc5-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-172">Nombre de la categoría del cliente que usa el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-175">Versión de cliente que usa el usuario que se unió a la sesión</span><span class="sxs-lookup"><span data-stu-id="86dc5-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-177">int</span><span class="sxs-lookup"><span data-stu-id="86dc5-177">int</span></span></p></td>
<td><p><span data-ttu-id="86dc5-178">Cliente que usa el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="86dc5-179">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="86dc5-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-182">Nombre de la categoría del cliente que usa el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="86dc5-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-185">URI del usuario destinatario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="86dc5-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-188">Tipo de URI del usuario destinatario de la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="86dc5-189">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="86dc5-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-192">URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-195">Tipo de URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="86dc5-196">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-199">Inquilino del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="86dc5-200">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="86dc5-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-203">URI del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-206">Tipo de URI del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="86dc5-207">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-210">Inquilino del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="86dc5-211">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-212"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-213">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="86dc5-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-p116">Identificador del diálogo SIP. El formato es:</span><span class="sxs-lookup"><span data-stu-id="86dc5-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="86dc5-216">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="86dc5-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-218">identificador</span><span class="sxs-lookup"><span data-stu-id="86dc5-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="86dc5-219">Identificador único global usado para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="86dc5-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-221">datetime</span><span class="sxs-lookup"><span data-stu-id="86dc5-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="86dc5-222">Fecha y hora del diálogo que se sustituyó por la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="86dc5-223">Se usa en combinación con ReplaceDialogIdSeq para identificar de forma exclusiva un diálogo que se sustituye con la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="86dc5-224">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-226">int</span><span class="sxs-lookup"><span data-stu-id="86dc5-226">int</span></span></p></td>
<td><p><span data-ttu-id="86dc5-227">Número de identificador de la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-227">ID number to identify the session.</span></span> <span data-ttu-id="86dc5-228">Se usa en combinación con ReplaceDialogIdTime para identificar de forma exclusiva un diálogo que se sustituye con la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="86dc5-229">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86dc5-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-231">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="86dc5-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-p119">El identificador de diálogo SIP que sustituye la sesión. El formato es:</span><span class="sxs-lookup"><span data-stu-id="86dc5-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="86dc5-234">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="86dc5-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-236">datetime</span><span class="sxs-lookup"><span data-stu-id="86dc5-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="86dc5-p120">Fecha y hora de la respuesta al primer mensaje INVITE. Este campo se suele rellenar con los datos generados a partir del mensaje INVITE inicial. Si no hay un mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="86dc5-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-241">int</span><span class="sxs-lookup"><span data-stu-id="86dc5-241">int</span></span></p></td>
<td><p><span data-ttu-id="86dc5-p121">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="86dc5-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-246">int</span><span class="sxs-lookup"><span data-stu-id="86dc5-246">int</span></span></p></td>
<td><p><span data-ttu-id="86dc5-247">Identificador de diagnóstico capturado de los encabezados SIP.</span><span class="sxs-lookup"><span data-stu-id="86dc5-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-250">Tipo de contenido de la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-253">FQDN del servidor front-end que capturó los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-256">FQDN del grupo que capturó los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-259">FQDN del servidor perimetral que usa el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-262">FQDN del servidor perimetral que usa el usuario que inició la sesión</span><span class="sxs-lookup"><span data-stu-id="86dc5-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-264">bit</span><span class="sxs-lookup"><span data-stu-id="86dc5-264">bit</span></span></p></td>
<td><p><span data-ttu-id="86dc5-265">Indica si el usuario que inició la sesión se conectó desde la red interna.</span><span class="sxs-lookup"><span data-stu-id="86dc5-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-267">bit</span><span class="sxs-lookup"><span data-stu-id="86dc5-267">bit</span></span></p></td>
<td><p><span data-ttu-id="86dc5-268">Indica si el usuario que se unió a la sesión se conectó desde la red interna.</span><span class="sxs-lookup"><span data-stu-id="86dc5-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86dc5-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-271">Prioridad de llamada de la sesión.</span><span class="sxs-lookup"><span data-stu-id="86dc5-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-273">smallint</span><span class="sxs-lookup"><span data-stu-id="86dc5-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="86dc5-p122">Indica los atributos del usuario que inició la sesión. Las definiciones de atributos permitidas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="86dc5-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="86dc5-276">0x01 - Integrado en teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="86dc5-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-278">smallint</span><span class="sxs-lookup"><span data-stu-id="86dc5-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="86dc5-p123">Indica los atributos del usuario que inició la sesión. Las definiciones de atributos permitidas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="86dc5-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="86dc5-281">0x01 - Integrado en teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="86dc5-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86dc5-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-283">smallint</span><span class="sxs-lookup"><span data-stu-id="86dc5-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="86dc5-p124">Indica los atributos de llamada. Se permiten las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="86dc5-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="86dc5-286">0x01 - Reintento de sesión</span><span class="sxs-lookup"><span data-stu-id="86dc5-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="86dc5-287">0x02 - Una llamada realizada por un agente en nombre de un Grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="86dc5-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86dc5-288"><strong>Ubicación</strong></span><span class="sxs-lookup"><span data-stu-id="86dc5-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="86dc5-289">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="86dc5-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="86dc5-290">Ubicación de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="86dc5-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

