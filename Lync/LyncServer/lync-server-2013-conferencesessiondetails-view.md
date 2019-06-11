---
title: 'Lync Server 2013: vista ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="7daa9-102">Vista ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7daa9-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7daa9-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="7daa9-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="7daa9-104">La vista ConferenceSessionDetails almacena información sobre las sesiones de varias partes.</span><span class="sxs-lookup"><span data-stu-id="7daa9-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="7daa9-105">Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico.</span><span class="sxs-lookup"><span data-stu-id="7daa9-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="7daa9-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7daa9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7daa9-107">Columna</span><span class="sxs-lookup"><span data-stu-id="7daa9-107">Column</span></span></th>
<th><span data-ttu-id="7daa9-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7daa9-108">Data Type</span></span></th>
<th><span data-ttu-id="7daa9-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="7daa9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7daa9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7daa9-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-112">Time of session request.</span></span> <span data-ttu-id="7daa9-113">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="7daa9-114">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-116">int</span><span class="sxs-lookup"><span data-stu-id="7daa9-116">int</span></span></p></td>
<td><p><span data-ttu-id="7daa9-117">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-117">ID number to identify the session.</span></span> <span data-ttu-id="7daa9-118">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="7daa9-119">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-121">datetime</span><span class="sxs-lookup"><span data-stu-id="7daa9-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="7daa9-122">Hora de la primera solicitud de invitación.</span><span class="sxs-lookup"><span data-stu-id="7daa9-122">Time of the first INVITE request.</span></span> <span data-ttu-id="7daa9-123">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7daa9-124">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="7daa9-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7daa9-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-127">URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="7daa9-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-130">URI de tipo de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7daa9-130">Type of conference URI.</span></span> <span data-ttu-id="7daa9-131">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-133">identificador</span><span class="sxs-lookup"><span data-stu-id="7daa9-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7daa9-134">Identificador que diferencia entre instancias de conferencias periódicas.</span><span class="sxs-lookup"><span data-stu-id="7daa9-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="7daa9-135">Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="7daa9-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7daa9-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-138">URI del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7daa9-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-141">Tipo de URI del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7daa9-141">Type of conferencing server URI.</span></span> <span data-ttu-id="7daa9-142">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7daa9-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-145">URI del usuario implicado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-148">Tipo de URI del usuario que formaba parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="7daa9-149">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-152">Espacio empresarial del usuario que formaba parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="7daa9-153">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-155">identificador</span><span class="sxs-lookup"><span data-stu-id="7daa9-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7daa9-156">Identificador único del usuario que forma parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-158">datetime</span><span class="sxs-lookup"><span data-stu-id="7daa9-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="7daa9-159">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-162">Versión del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7daa9-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-164">int</span><span class="sxs-lookup"><span data-stu-id="7daa9-164">int</span></span></p></td>
<td><p><span data-ttu-id="7daa9-165">Tipo de servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7daa9-165">Type of conference server.</span></span> <span data-ttu-id="7daa9-166">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7daa9-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-169">Categoría servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7daa9-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-172">Versión del cliente utilizada por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-174">int</span><span class="sxs-lookup"><span data-stu-id="7daa9-174">int</span></span></p></td>
<td><p><span data-ttu-id="7daa9-175">Cliente usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="7daa9-176">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7daa9-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-179">Nombre de la categoría del cliente que ha usado el usuario que forma parte de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7daa9-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-182">URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-185">Tipo de URI del usuario en cuyo nombre se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="7daa9-186">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-189">Inquilino del usuario cuyo en nombre se ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="7daa9-190">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7daa9-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-193">Identificador URI del usuario que remitió la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-196">Tipo de URI del usuario que ha remitido la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="7daa9-197">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-200">Espacio empresarial del usuario que remitió la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="7daa9-201">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="7daa9-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-204">IDENTIFICACIÓN del cuadro de diálogo SIP.</span><span class="sxs-lookup"><span data-stu-id="7daa9-204">SIP dialog ID.</span></span> <span data-ttu-id="7daa9-205">El formato es</span><span class="sxs-lookup"><span data-stu-id="7daa9-205">The format is</span></span></p>
<p><span data-ttu-id="7daa9-206">:d ialog; de-etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="7daa9-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-208">datetime</span><span class="sxs-lookup"><span data-stu-id="7daa9-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="7daa9-209">Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="7daa9-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="7daa9-210">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-212">int</span><span class="sxs-lookup"><span data-stu-id="7daa9-212">int</span></span></p></td>
<td><p><span data-ttu-id="7daa9-213">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-213">ID number to identify the session.</span></span> <span data-ttu-id="7daa9-214">Se usa junto con ReplaceDialogIdTime para identificar de forma única una sesión que se reemplaza por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="7daa9-215">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7daa9-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-217">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="7daa9-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-218">IDENTIFICACIÓN del cuadro de diálogo SIP que reemplaza la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="7daa9-219">El formato de es:</span><span class="sxs-lookup"><span data-stu-id="7daa9-219">The format of the is:</span></span></p>
<p><span data-ttu-id="7daa9-220">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="7daa9-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-222">bit</span><span class="sxs-lookup"><span data-stu-id="7daa9-222">bit</span></span></p></td>
<td><p><span data-ttu-id="7daa9-223">Indica si la sesión ha sido iniciada por el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7daa9-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-225">bit</span><span class="sxs-lookup"><span data-stu-id="7daa9-225">bit</span></span></p></td>
<td><p><span data-ttu-id="7daa9-226">Indica si el servidor de conferencia finalizó la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-228">bit</span><span class="sxs-lookup"><span data-stu-id="7daa9-228">bit</span></span></p></td>
<td><p><span data-ttu-id="7daa9-229">Indica si el usuario ha iniciado sesión en la red interna.</span><span class="sxs-lookup"><span data-stu-id="7daa9-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-231">datetime</span><span class="sxs-lookup"><span data-stu-id="7daa9-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="7daa9-232">Hora de la respuesta al primer mensaje de invitación.</span><span class="sxs-lookup"><span data-stu-id="7daa9-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="7daa9-233">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7daa9-234">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="7daa9-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-236">int</span><span class="sxs-lookup"><span data-stu-id="7daa9-236">int</span></span></p></td>
<td><p><span data-ttu-id="7daa9-237">Código de respuesta SIP a la invitación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="7daa9-238">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="7daa9-239">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="7daa9-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-241">int</span><span class="sxs-lookup"><span data-stu-id="7daa9-241">int</span></span></p></td>
<td><p><span data-ttu-id="7daa9-242">IDENTIFICADOR de diagnóstico capturado de los encabezados de SIP de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-245">Tipo de contenido de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-248">FQDN del servidor front-end que capturó los datos para la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-249"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-251">FQDN del grupo de servidores que ha capturado los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-254">Servidor de mediación usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-255"><strong>Puerta</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-257">Puerta de enlace usada por el usuario que participó la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7daa9-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7daa9-260">FQDN del servidor perimetral usado por el usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7daa9-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-262">smallint</span><span class="sxs-lookup"><span data-stu-id="7daa9-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="7daa9-263">Indica los atributos del usuario que participó en la sesión.</span><span class="sxs-lookup"><span data-stu-id="7daa9-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="7daa9-264">Se permiten las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="7daa9-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="7daa9-265">0x01: integrado con un teléfono de escritorio</span><span class="sxs-lookup"><span data-stu-id="7daa9-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7daa9-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="7daa9-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="7daa9-267">smallint</span><span class="sxs-lookup"><span data-stu-id="7daa9-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="7daa9-268">Indica los atributos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7daa9-268">Indicates the call attributes.</span></span> <span data-ttu-id="7daa9-269">Se permiten las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="7daa9-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="7daa9-270">0x01-reintento Session0</span><span class="sxs-lookup"><span data-stu-id="7daa9-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="7daa9-271">x02: una llamada realizada por el agente en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="7daa9-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

