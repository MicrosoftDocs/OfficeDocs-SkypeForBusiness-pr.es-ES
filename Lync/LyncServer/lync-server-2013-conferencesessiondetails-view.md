---
title: 'Lync Server 2013: vista ConferenceSessionDetails'
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
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="49fcb-102">Vista ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49fcb-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49fcb-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="49fcb-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="49fcb-104">La vista ConferenceSessionDetails almacena información sobre las sesiones de varias partes.</span><span class="sxs-lookup"><span data-stu-id="49fcb-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="49fcb-105">Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico.</span><span class="sxs-lookup"><span data-stu-id="49fcb-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="49fcb-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49fcb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49fcb-107">Columna</span><span class="sxs-lookup"><span data-stu-id="49fcb-107">Column</span></span></th>
<th><span data-ttu-id="49fcb-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="49fcb-108">Data Type</span></span></th>
<th><span data-ttu-id="49fcb-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="49fcb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="49fcb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="49fcb-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-112">Time of session request.</span></span> <span data-ttu-id="49fcb-113">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="49fcb-114">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-116">int</span><span class="sxs-lookup"><span data-stu-id="49fcb-116">int</span></span></p></td>
<td><p><span data-ttu-id="49fcb-117">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-117">ID number to identify the session.</span></span> <span data-ttu-id="49fcb-118">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="49fcb-119">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-121">datetime</span><span class="sxs-lookup"><span data-stu-id="49fcb-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="49fcb-122">Hora de la primera solicitud de invitación.</span><span class="sxs-lookup"><span data-stu-id="49fcb-122">Time of the first INVITE request.</span></span> <span data-ttu-id="49fcb-123">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="49fcb-124">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="49fcb-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="49fcb-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-127">URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="49fcb-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-130">URI de tipo de conferencia.</span><span class="sxs-lookup"><span data-stu-id="49fcb-130">Type of conference URI.</span></span> <span data-ttu-id="49fcb-131">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-133">identificador</span><span class="sxs-lookup"><span data-stu-id="49fcb-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="49fcb-134">Identificador que diferencia entre instancias de conferencias periódicas.</span><span class="sxs-lookup"><span data-stu-id="49fcb-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="49fcb-135">Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="49fcb-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="49fcb-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-138">URI del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="49fcb-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-141">Tipo de URI del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="49fcb-141">Type of conferencing server URI.</span></span> <span data-ttu-id="49fcb-142">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="49fcb-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-145">URI del usuario implicado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-148">Tipo de URI del usuario que formaba parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="49fcb-149">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-152">Espacio empresarial del usuario que formaba parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="49fcb-153">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-155">identificador</span><span class="sxs-lookup"><span data-stu-id="49fcb-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="49fcb-156">Identificador único del usuario que forma parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-158">datetime</span><span class="sxs-lookup"><span data-stu-id="49fcb-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="49fcb-159">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-162">Versión del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="49fcb-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-164">int</span><span class="sxs-lookup"><span data-stu-id="49fcb-164">int</span></span></p></td>
<td><p><span data-ttu-id="49fcb-165">Tipo de servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="49fcb-165">Type of conference server.</span></span> <span data-ttu-id="49fcb-166">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="49fcb-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-169">Categoría servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="49fcb-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-172">Versión del cliente utilizada por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-174">int</span><span class="sxs-lookup"><span data-stu-id="49fcb-174">int</span></span></p></td>
<td><p><span data-ttu-id="49fcb-175">Cliente usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="49fcb-176">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="49fcb-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-179">Nombre de la categoría del cliente que ha usado el usuario que forma parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="49fcb-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-182">URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-185">Tipo de URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="49fcb-186">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-189">Inquilino del usuario cuyo en nombre se ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="49fcb-190">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="49fcb-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-193">Identificador URI del usuario que remitió la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-196">Tipo de URI del usuario que ha remitido la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="49fcb-197">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-200">Espacio empresarial del usuario que remitió la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="49fcb-201">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="49fcb-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-204">IDENTIFICACIÓN del cuadro de diálogo SIP.</span><span class="sxs-lookup"><span data-stu-id="49fcb-204">SIP dialog ID.</span></span> <span data-ttu-id="49fcb-205">El formato es</span><span class="sxs-lookup"><span data-stu-id="49fcb-205">The format is</span></span></p>
<p><span data-ttu-id="49fcb-206">:d ialog; de-etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="49fcb-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-208">datetime</span><span class="sxs-lookup"><span data-stu-id="49fcb-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="49fcb-209">Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="49fcb-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="49fcb-210">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-212">int</span><span class="sxs-lookup"><span data-stu-id="49fcb-212">int</span></span></p></td>
<td><p><span data-ttu-id="49fcb-213">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-213">ID number to identify the session.</span></span> <span data-ttu-id="49fcb-214">Se usa junto con ReplaceDialogIdTime para identificar de forma única una sesión que se reemplaza por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="49fcb-215">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="49fcb-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-217">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="49fcb-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-218">IDENTIFICACIÓN del cuadro de diálogo SIP que reemplaza la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="49fcb-219">El formato de es:</span><span class="sxs-lookup"><span data-stu-id="49fcb-219">The format of the is:</span></span></p>
<p><span data-ttu-id="49fcb-220">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="49fcb-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-222">bit</span><span class="sxs-lookup"><span data-stu-id="49fcb-222">bit</span></span></p></td>
<td><p><span data-ttu-id="49fcb-223">Indica si la sesión ha sido iniciada por el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="49fcb-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-225">bit</span><span class="sxs-lookup"><span data-stu-id="49fcb-225">bit</span></span></p></td>
<td><p><span data-ttu-id="49fcb-226">Indica si el servidor de conferencia finalizó la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-228">bit</span><span class="sxs-lookup"><span data-stu-id="49fcb-228">bit</span></span></p></td>
<td><p><span data-ttu-id="49fcb-229">Indica si el usuario ha iniciado sesión en la red interna.</span><span class="sxs-lookup"><span data-stu-id="49fcb-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-231">datetime</span><span class="sxs-lookup"><span data-stu-id="49fcb-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="49fcb-232">Hora de la respuesta al primer mensaje de invitación.</span><span class="sxs-lookup"><span data-stu-id="49fcb-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="49fcb-233">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="49fcb-234">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="49fcb-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-236">int</span><span class="sxs-lookup"><span data-stu-id="49fcb-236">int</span></span></p></td>
<td><p><span data-ttu-id="49fcb-237">Código de respuesta SIP a la invitación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="49fcb-238">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="49fcb-239">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="49fcb-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-241">int</span><span class="sxs-lookup"><span data-stu-id="49fcb-241">int</span></span></p></td>
<td><p><span data-ttu-id="49fcb-242">IDENTIFICADOR de diagnóstico capturado de los encabezados de SIP de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-245">Tipo de contenido de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-248">FQDN del servidor front-end que capturó los datos para la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-249"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-251">FQDN del grupo de servidores que ha capturado los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-254">Servidor de mediación usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-255"><strong>Puerta</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-257">Puerta de enlace usada por el usuario que participó la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="49fcb-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="49fcb-260">FQDN del servidor perimetral usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49fcb-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-262">smallint</span><span class="sxs-lookup"><span data-stu-id="49fcb-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="49fcb-263">Indica los atributos del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="49fcb-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="49fcb-264">Se permiten las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="49fcb-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="49fcb-265">0x01: integrado con un teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="49fcb-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49fcb-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="49fcb-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="49fcb-267">smallint</span><span class="sxs-lookup"><span data-stu-id="49fcb-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="49fcb-268">Indica los atributos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="49fcb-268">Indicates the call attributes.</span></span> <span data-ttu-id="49fcb-269">Se permiten las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="49fcb-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="49fcb-270">0x01-reintento Session0</span><span class="sxs-lookup"><span data-stu-id="49fcb-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="49fcb-271">x02: una llamada realizada por el agente en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="49fcb-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

