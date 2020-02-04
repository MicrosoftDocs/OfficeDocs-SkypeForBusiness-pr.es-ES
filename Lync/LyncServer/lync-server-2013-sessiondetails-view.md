---
title: 'Lync Server 2013: vista SessionDetails'
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
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="7e370-102">Vista SessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e370-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e370-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7e370-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7e370-104">La vista SessionDetails almacena información sobre sesiones de punto a punto, que podrían ser una llamada de teléfono VoIP-VoIP, una sesión de mensajería instantánea de dos proveedores u otro tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="7e370-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e370-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e370-106">Columna</span><span class="sxs-lookup"><span data-stu-id="7e370-106">Column</span></span></th>
<th><span data-ttu-id="7e370-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7e370-107">Data Type</span></span></th>
<th><span data-ttu-id="7e370-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="7e370-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e370-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-110">datetime</span><span class="sxs-lookup"><span data-stu-id="7e370-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e370-111">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-111">Time of session request.</span></span> <span data-ttu-id="7e370-112">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="7e370-113">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en</a> la tabla de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e370-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-115">int</span><span class="sxs-lookup"><span data-stu-id="7e370-115">int</span></span></p></td>
<td><p><span data-ttu-id="7e370-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-116">ID number to identify the session.</span></span> <span data-ttu-id="7e370-117">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="7e370-118">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-120">datetime</span><span class="sxs-lookup"><span data-stu-id="7e370-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e370-121">Hora de la primera solicitud de invitación.</span><span class="sxs-lookup"><span data-stu-id="7e370-121">Time of the first INVITE request.</span></span> <span data-ttu-id="7e370-122">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7e370-123">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="7e370-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="7e370-124">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7e370-125">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="7e370-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e370-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e370-128">Identificador URI del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-129"><strong>ToUr</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e370-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e370-131">Identificador URI del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-134">Tipo de URI del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="7e370-135">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-138">Tipo de URI del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="7e370-139">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e370-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e370-142">Espacio empresarial del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="7e370-143">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-146">El inquilino del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="7e370-147">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-149">identificador</span><span class="sxs-lookup"><span data-stu-id="7e370-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7e370-150">Identificador único del extremo del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-152">identificador</span><span class="sxs-lookup"><span data-stu-id="7e370-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7e370-153">Identificador único del extremo del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-155">datetime</span><span class="sxs-lookup"><span data-stu-id="7e370-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e370-156">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-158">int</span><span class="sxs-lookup"><span data-stu-id="7e370-158">int</span></span></p></td>
<td><p><span data-ttu-id="7e370-159">Número de mensajes enviados por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-161">int</span><span class="sxs-lookup"><span data-stu-id="7e370-161">int</span></span></p></td>
<td><p><span data-ttu-id="7e370-162">Número de mensajes enviados por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-165">Versión del cliente usada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-167">int</span><span class="sxs-lookup"><span data-stu-id="7e370-167">int</span></span></p></td>
<td><p><span data-ttu-id="7e370-168">Cliente usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-168">Client used by the user who started the session.</span></span> <span data-ttu-id="7e370-169">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7e370-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7e370-172">Nombre de la categoría del cliente que ha usado el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-175">Versión de cliente usada por el usuario que se unió a la sesión</span><span class="sxs-lookup"><span data-stu-id="7e370-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-177">int</span><span class="sxs-lookup"><span data-stu-id="7e370-177">int</span></span></p></td>
<td><p><span data-ttu-id="7e370-178">Cliente usado por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="7e370-179">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7e370-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7e370-182">Nombre de la categoría del cliente que ha usado el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e370-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e370-185">URI del usuario de destino de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e370-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e370-188">Tipo de URI del usuario de destino de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="7e370-189">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e370-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e370-192">URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-195">Tipo de URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="7e370-196">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-199">Inquilino del usuario cuyo en nombre se ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="7e370-200">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e370-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e370-203">Identificador URI del usuario que remitió la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-206">Tipo de URI del usuario que ha remitido la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="7e370-207">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-210">Espacio empresarial del usuario que remitió la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="7e370-211">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-213">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="7e370-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="7e370-214">IDENTIFICACIÓN del cuadro de diálogo SIP.</span><span class="sxs-lookup"><span data-stu-id="7e370-214">SIP dialog ID.</span></span> <span data-ttu-id="7e370-215">El formato es:</span><span class="sxs-lookup"><span data-stu-id="7e370-215">The format is:</span></span></p>
<p><span data-ttu-id="7e370-216">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="7e370-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-218">identificador</span><span class="sxs-lookup"><span data-stu-id="7e370-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7e370-219">GUID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="7e370-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-221">datetime</span><span class="sxs-lookup"><span data-stu-id="7e370-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e370-222">Hora del cuadro de diálogo que se ha sustituido por la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="7e370-223">Se usa junto con ReplaceDialogIdSeq para identificar de forma exclusiva un cuadro de diálogo que se reemplaza por la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="7e370-224">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-226">int</span><span class="sxs-lookup"><span data-stu-id="7e370-226">int</span></span></p></td>
<td><p><span data-ttu-id="7e370-227">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-227">ID number to identify the session.</span></span> <span data-ttu-id="7e370-228">Se usa junto con ReplaceDialogIdTime para identificar de forma exclusiva un cuadro de diálogo que se reemplaza por la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="7e370-229">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e370-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-231">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="7e370-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="7e370-232">IDENTIFICACIÓN del cuadro de diálogo SIP que reemplaza la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="7e370-233">El formato es:</span><span class="sxs-lookup"><span data-stu-id="7e370-233">The format is:</span></span></p>
<p><span data-ttu-id="7e370-234">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="7e370-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-236">datetime</span><span class="sxs-lookup"><span data-stu-id="7e370-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e370-237">Hora de la respuesta al primer mensaje de invitación.</span><span class="sxs-lookup"><span data-stu-id="7e370-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="7e370-238">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7e370-239">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="7e370-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-241">int</span><span class="sxs-lookup"><span data-stu-id="7e370-241">int</span></span></p></td>
<td><p><span data-ttu-id="7e370-242">Código de respuesta SIP a la invitación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="7e370-243">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7e370-244">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="7e370-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-246">int</span><span class="sxs-lookup"><span data-stu-id="7e370-246">int</span></span></p></td>
<td><p><span data-ttu-id="7e370-247">IDENTIFICACIÓN de diagnóstico capturada de encabezados SIP.</span><span class="sxs-lookup"><span data-stu-id="7e370-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-250">Tipo de contenido de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-253">FQDN del servidor front-end que capturó los datos para la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-254"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-256">FQDN del grupo de servidores que ha capturado los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-259">FQDN del servidor perimetral usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-262">FQDN del servidor perimetral usado por el usuario que inició la sesión</span><span class="sxs-lookup"><span data-stu-id="7e370-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-264">bit</span><span class="sxs-lookup"><span data-stu-id="7e370-264">bit</span></span></p></td>
<td><p><span data-ttu-id="7e370-265">Indica si el usuario que inició la sesión inició sesión en la red interna.</span><span class="sxs-lookup"><span data-stu-id="7e370-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-267">bit</span><span class="sxs-lookup"><span data-stu-id="7e370-267">bit</span></span></p></td>
<td><p><span data-ttu-id="7e370-268">Indica si el usuario que se unió a la sesión ha iniciado sesión en la red interna.</span><span class="sxs-lookup"><span data-stu-id="7e370-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e370-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e370-271">Prioridad de la llamada de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-273">smallint</span><span class="sxs-lookup"><span data-stu-id="7e370-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e370-274">Indica los atributos del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="7e370-275">Se permiten las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="7e370-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="7e370-276">0x01: integrado con un teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="7e370-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-278">smallint</span><span class="sxs-lookup"><span data-stu-id="7e370-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e370-279">Indica los atributos del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e370-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="7e370-280">Se permiten las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="7e370-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="7e370-281">0x01: integrado con un teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="7e370-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e370-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-283">smallint</span><span class="sxs-lookup"><span data-stu-id="7e370-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e370-284">Indica los atributos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7e370-284">Indicates the call attributes.</span></span> <span data-ttu-id="7e370-285">Se permiten las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="7e370-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="7e370-286">0x01-reintento de sesión</span><span class="sxs-lookup"><span data-stu-id="7e370-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="7e370-287">0x02: una llamada realizada por el agente en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="7e370-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e370-288"><strong>Ubicación</strong></span><span class="sxs-lookup"><span data-stu-id="7e370-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="7e370-289">VARCHAR (Max)</span><span class="sxs-lookup"><span data-stu-id="7e370-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="7e370-290">Ubicación de la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="7e370-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

