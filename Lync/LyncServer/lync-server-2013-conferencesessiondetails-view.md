---
title: 'Lync Server 2013: vista de ConferenceSessionDetails'
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
ms.openlocfilehash: be9d3566a951ee1b65d87e423627f556254173b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="a9c7c-102">Vista ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9c7c-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9c7c-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="a9c7c-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="a9c7c-104">La vista ConferenceSessionDetails almacena información sobre sesiones con varios participantes.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="a9c7c-105">Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="a9c7c-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9c7c-107">Columna</span><span class="sxs-lookup"><span data-stu-id="a9c7c-107">Column</span></span></th>
<th><span data-ttu-id="a9c7c-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a9c7c-108">Data Type</span></span></th>
<th><span data-ttu-id="a9c7c-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="a9c7c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a9c7c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-112">Time of session request.</span></span> <span data-ttu-id="a9c7c-113">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a9c7c-114">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-116">int</span><span class="sxs-lookup"><span data-stu-id="a9c7c-116">int</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-117">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-117">ID number to identify the session.</span></span> <span data-ttu-id="a9c7c-118">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a9c7c-119">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-121">datetime</span><span class="sxs-lookup"><span data-stu-id="a9c7c-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-p104">Hora de la primera solicitud de invitación. Este campo se rellena normalmente con datos generados por el mensaje INVITE inicial en la sesión. Si no aparece ningún mensaje INVITE, el campo se rellena con la fecha y hora del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="a9c7c-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-125"><strong>Uri</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-127">URI de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-130">Tipo de URI de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-130">Type of conference URI.</span></span> <span data-ttu-id="a9c7c-131">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-133">identificador</span><span class="sxs-lookup"><span data-stu-id="a9c7c-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-p106">Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-138">URI del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-141">Tipo de URI del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-141">Type of conferencing server URI.</span></span> <span data-ttu-id="a9c7c-142">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-145">URI del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-148">Tipo de URI del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="a9c7c-149">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-152">Inquilino del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="a9c7c-153">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-155">identificador</span><span class="sxs-lookup"><span data-stu-id="a9c7c-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-156">Identificador único del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-158">datetime</span><span class="sxs-lookup"><span data-stu-id="a9c7c-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-159">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-162">Versión del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-164">int</span><span class="sxs-lookup"><span data-stu-id="a9c7c-164">int</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-165">Tipo del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-165">Type of conference server.</span></span> <span data-ttu-id="a9c7c-166">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-169">Categoría del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-172">Versión del cliente usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-174">int</span><span class="sxs-lookup"><span data-stu-id="a9c7c-174">int</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-175">Cliente usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="a9c7c-176">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-179">Nombre de categoría del cliente usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-182">URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-185">Tipo de URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="a9c7c-186">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-189">Inquilino del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="a9c7c-190">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-193">URI del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-196">Tipo de URI del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="a9c7c-197">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-200">Inquilino del usuario que hizo referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="a9c7c-201">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-202"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-p116">Id. del diálogo SIP. El formato es</span><span class="sxs-lookup"><span data-stu-id="a9c7c-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="a9c7c-206">:d ialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="a9c7c-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-208">datetime</span><span class="sxs-lookup"><span data-stu-id="a9c7c-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-209">Número de identificador que identifica el cuadro de diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="a9c7c-210">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-212">int</span><span class="sxs-lookup"><span data-stu-id="a9c7c-212">int</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-213">Número de identificador que identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-213">ID number to identify the session.</span></span> <span data-ttu-id="a9c7c-214">Se usa junto a ReplaceDialogIdTime para identificar únicamente una sesión que se reemplaza por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="a9c7c-215">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-217">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-p119">Id. del diálogo SIP que reemplaza esta sesión. El formato es:</span><span class="sxs-lookup"><span data-stu-id="a9c7c-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="a9c7c-220">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="a9c7c-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-222">bit</span><span class="sxs-lookup"><span data-stu-id="a9c7c-222">bit</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-223">Indica si el servidor de conferencias inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-225">bit</span><span class="sxs-lookup"><span data-stu-id="a9c7c-225">bit</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-226">Indica si el servidor de conferencias finalizó la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-228">bit</span><span class="sxs-lookup"><span data-stu-id="a9c7c-228">bit</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-229">Indica si el usuario ha iniciado sesión desde la red interna.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-231">datetime</span><span class="sxs-lookup"><span data-stu-id="a9c7c-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-p120">Fecha y hora de la respuesta al primer mensaje INVITE. Este campo se suele rellenar con los datos generados a partir del mensaje INVITE inicial. Si no hay un mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="a9c7c-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-236">int</span><span class="sxs-lookup"><span data-stu-id="a9c7c-236">int</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-p121">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="a9c7c-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-241">int</span><span class="sxs-lookup"><span data-stu-id="a9c7c-241">int</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-242">Identificador de diagnóstico capturado de los encabezados SIP de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-245">Tipo de contenido para la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-248">FQDN del servidor front-end que capturó los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-251">FQDN del grupo que captura los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-254">Servidor de mediación usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-255"><strong>Puerta de enlace</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-257">Puerta de enlace usada por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9c7c-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-260">FQDN del servidor perimetral usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="a9c7c-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c7c-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-262">smallint</span><span class="sxs-lookup"><span data-stu-id="a9c7c-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-p122">Indica los atributos del usuario que participó en la sesión. Se permiten las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="a9c7c-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="a9c7c-265">0x01 - Integrado con el teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="a9c7c-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9c7c-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a9c7c-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a9c7c-267">smallint</span><span class="sxs-lookup"><span data-stu-id="a9c7c-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="a9c7c-p123">Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="a9c7c-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a9c7c-270">0x01 - Reintento de sesión0</span><span class="sxs-lookup"><span data-stu-id="a9c7c-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="a9c7c-271">x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas</span><span class="sxs-lookup"><span data-stu-id="a9c7c-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

