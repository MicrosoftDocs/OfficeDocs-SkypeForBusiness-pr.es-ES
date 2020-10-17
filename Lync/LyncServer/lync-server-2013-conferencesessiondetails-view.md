---
title: 'Lync Server 2013: vista de ConferenceSessionDetails'
description: 'Lync Server 2013: vista de ConferenceSessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566776"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="79037-103">Vista ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79037-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79037-104">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="79037-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="79037-105">La vista ConferenceSessionDetails almacena información sobre sesiones con varios participantes.</span><span class="sxs-lookup"><span data-stu-id="79037-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="79037-106">Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.</span><span class="sxs-lookup"><span data-stu-id="79037-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="79037-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79037-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79037-108">Columna</span><span class="sxs-lookup"><span data-stu-id="79037-108">Column</span></span></th>
<th><span data-ttu-id="79037-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="79037-109">Data Type</span></span></th>
<th><span data-ttu-id="79037-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="79037-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79037-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="79037-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-112">datetime</span><span class="sxs-lookup"><span data-stu-id="79037-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="79037-113">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-113">Time of session request.</span></span> <span data-ttu-id="79037-114">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="79037-115">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="79037-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-117">entero</span><span class="sxs-lookup"><span data-stu-id="79037-117">int</span></span></p></td>
<td><p><span data-ttu-id="79037-118">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-118">ID number to identify the session.</span></span> <span data-ttu-id="79037-119">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="79037-120">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-121"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="79037-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-122">datetime</span><span class="sxs-lookup"><span data-stu-id="79037-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="79037-p104">Hora de la primera solicitud de invitación. Este campo se rellena normalmente con datos generados por el mensaje INVITE inicial en la sesión. Si no aparece ningún mensaje INVITE, el campo se rellena con la fecha y hora del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="79037-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-126"><strong>Uri</strong></span><span class="sxs-lookup"><span data-stu-id="79037-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="79037-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="79037-128">URI de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="79037-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="79037-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-131">Tipo de URI de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="79037-131">Type of conference URI.</span></span> <span data-ttu-id="79037-132">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-133"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="79037-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-134">identificador</span><span class="sxs-lookup"><span data-stu-id="79037-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="79037-p106">Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="79037-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="79037-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="79037-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="79037-139">URI del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="79037-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="79037-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-142">Tipo de URI del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="79037-142">Type of conferencing server URI.</span></span> <span data-ttu-id="79037-143">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="79037-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="79037-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="79037-146">URI del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-147"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="79037-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-149">Tipo de URI del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="79037-150">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-151"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="79037-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-153">Inquilino del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="79037-154">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-155"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="79037-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-156">identificador</span><span class="sxs-lookup"><span data-stu-id="79037-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="79037-157">Identificador único del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="79037-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-159">datetime</span><span class="sxs-lookup"><span data-stu-id="79037-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="79037-160">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="79037-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-163">Versión del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="79037-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="79037-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-165">entero</span><span class="sxs-lookup"><span data-stu-id="79037-165">int</span></span></p></td>
<td><p><span data-ttu-id="79037-166">Tipo del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="79037-166">Type of conference server.</span></span> <span data-ttu-id="79037-167">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="79037-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="79037-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="79037-170">Categoría del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="79037-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="79037-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-172">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-173">Versión del cliente usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-174"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="79037-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-175">entero</span><span class="sxs-lookup"><span data-stu-id="79037-175">int</span></span></p></td>
<td><p><span data-ttu-id="79037-176">Cliente usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="79037-177">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="79037-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-179">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="79037-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="79037-180">Nombre de categoría del cliente usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="79037-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-182">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="79037-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="79037-183">URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="79037-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-185">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-186">Tipo de URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="79037-187">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="79037-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-189">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-190">Inquilino del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="79037-191">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-192"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="79037-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-193">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="79037-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="79037-194">URI del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-195"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="79037-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-196">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-197">Tipo de URI del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="79037-198">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-199"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="79037-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-200">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-201">Inquilino del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="79037-202">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-203"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="79037-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-204">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="79037-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="79037-p116">Id. del diálogo SIP. El formato es</span><span class="sxs-lookup"><span data-stu-id="79037-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="79037-207">:d ialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="79037-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-208"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="79037-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-209">datetime</span><span class="sxs-lookup"><span data-stu-id="79037-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="79037-210">Número de identificador que identifica el cuadro de diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="79037-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="79037-211">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-212"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="79037-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-213">entero</span><span class="sxs-lookup"><span data-stu-id="79037-213">int</span></span></p></td>
<td><p><span data-ttu-id="79037-214">Número de identificador que identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-214">ID number to identify the session.</span></span> <span data-ttu-id="79037-215">Se usa junto a ReplaceDialogIdTime para identificar únicamente una sesión que se reemplaza por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="79037-216">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="79037-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-217"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="79037-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-218">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="79037-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="79037-p119">Id. del diálogo SIP que reemplaza esta sesión. El formato es:</span><span class="sxs-lookup"><span data-stu-id="79037-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="79037-221">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="79037-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="79037-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-223">bit</span><span class="sxs-lookup"><span data-stu-id="79037-223">bit</span></span></p></td>
<td><p><span data-ttu-id="79037-224">Indica si el servidor de conferencias inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="79037-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-226">bit</span><span class="sxs-lookup"><span data-stu-id="79037-226">bit</span></span></p></td>
<td><p><span data-ttu-id="79037-227">Indica si el servidor de conferencias finalizó la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="79037-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-229">bit</span><span class="sxs-lookup"><span data-stu-id="79037-229">bit</span></span></p></td>
<td><p><span data-ttu-id="79037-230">Indica si el usuario ha iniciado sesión desde la red interna.</span><span class="sxs-lookup"><span data-stu-id="79037-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="79037-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-232">datetime</span><span class="sxs-lookup"><span data-stu-id="79037-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="79037-p120">Fecha y hora de la respuesta al primer mensaje INVITE. Este campo se suele rellenar con los datos generados a partir del mensaje INVITE inicial. Si no hay un mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="79037-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="79037-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-237">entero</span><span class="sxs-lookup"><span data-stu-id="79037-237">int</span></span></p></td>
<td><p><span data-ttu-id="79037-p121">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="79037-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-241"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="79037-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-242">entero</span><span class="sxs-lookup"><span data-stu-id="79037-242">int</span></span></p></td>
<td><p><span data-ttu-id="79037-243">Identificador de diagnóstico capturado de los encabezados SIP de la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="79037-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-245">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-246">Tipo de contenido para la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="79037-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-248">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-249">FQDN del servidor front-end que capturó los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-250"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="79037-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-251">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-252">FQDN del grupo que captura los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="79037-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-254">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-255">Servidor de mediación usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-256"><strong>Puerta de enlace</strong></span><span class="sxs-lookup"><span data-stu-id="79037-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-257">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-258">Puerta de enlace usada por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="79037-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-260">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79037-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="79037-261">FQDN del servidor perimetral usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="79037-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79037-262"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="79037-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-263">smallint</span><span class="sxs-lookup"><span data-stu-id="79037-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="79037-p122">Indica los atributos del usuario que participó en la sesión. Se permiten las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="79037-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="79037-266">0x01 - Integrado con el teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="79037-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79037-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="79037-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="79037-268">smallint</span><span class="sxs-lookup"><span data-stu-id="79037-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="79037-p123">Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="79037-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="79037-271">0x01 - Reintento de sesión0</span><span class="sxs-lookup"><span data-stu-id="79037-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="79037-272">x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas</span><span class="sxs-lookup"><span data-stu-id="79037-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

