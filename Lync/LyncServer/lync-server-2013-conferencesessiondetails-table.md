---
title: 'Lync Server 2013: tabla ConferenceSessionDetails'
description: 'Lync Server 2013: tabla ConferenceSessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566786"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="ecd6c-103">Tabla ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecd6c-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecd6c-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ecd6c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ecd6c-105">Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ecd6c-106">Columna</span><span class="sxs-lookup"><span data-stu-id="ecd6c-106">Column</span></span></th>
<th><span data-ttu-id="ecd6c-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ecd6c-107">Data Type</span></span></th>
<th><span data-ttu-id="ecd6c-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="ecd6c-108">Key/Index</span></span></th>
<th><span data-ttu-id="ecd6c-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="ecd6c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="ecd6c-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="ecd6c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-113">Hora de la solicitud de sesión; se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="ecd6c-114">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-116">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-116">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-117">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="ecd6c-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-118">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-118">ID number to identify the session.</span></span> <span data-ttu-id="ecd6c-119">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="ecd6c-120">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-122">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-122">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-123">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-124">URI de conferencia basada en Foco relacionada con esta sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="ecd6c-125">Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ecd6c-126">Esta URI es una URI de conferencia basada en Foco.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-128">Identificador</span><span class="sxs-lookup"><span data-stu-id="ecd6c-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-129">Identificador que distingue entre instancias de conferencias recurrentes.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="ecd6c-130">Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="ecd6c-131">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-133">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-133">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-134">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-135">URI de conferencia para servidor de conferencia relacionada con esta sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="ecd6c-136">Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ecd6c-137">Esta URI es la URI de conferencia basada en servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="ecd6c-138">En las sesiones de conferencia basadas en Foco, esta columna será nula.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-140">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-140">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-141">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-142">IDENTIFICADOR de un usuario en la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-142">ID of one user in the conference session.</span></span> <span data-ttu-id="ecd6c-143">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-144"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-145">identificador</span><span class="sxs-lookup"><span data-stu-id="ecd6c-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-p107">GUID para identificar la instancia del extremo. Por ejemplo, si un usuarios inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un id. de extremo diferente.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-149">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-149">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-150">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-151">Señala el identificador de usuario en cuyo nombre llama el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="ecd6c-152">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-154">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-154">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-155">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-156">Identificador del usuario por el que se hace referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="ecd6c-157">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-159">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-159">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-160">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-161">Versión del cliente utilizada por el usuario de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-161">Client version used by the conference user.</span></span> <span data-ttu-id="ecd6c-162">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-163"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-164">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-164">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-165">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-166">Versión del cliente utilizada por el usuario de servidor.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-166">Client version used by the conference server.</span></span> <span data-ttu-id="ecd6c-167">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-168"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-169">datetime</span><span class="sxs-lookup"><span data-stu-id="ecd6c-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-170">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-171">Número con el que se identifica el diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="ecd6c-172">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-173"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-174">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-174">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-175">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-176">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-176">ID number to identify the session.</span></span> <span data-ttu-id="ecd6c-177">Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de manera exclusiva una sesión que se reemplazó por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="ecd6c-178">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-180">bit</span><span class="sxs-lookup"><span data-stu-id="ecd6c-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-181">Indica si la sesión la inició el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-183">bit</span><span class="sxs-lookup"><span data-stu-id="ecd6c-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-184">Indica si la sesión la finalizó el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-186">bit</span><span class="sxs-lookup"><span data-stu-id="ecd6c-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-187">Tanto si el usuario ha iniciado sesión desde un equipo interno como si no.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-189">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-190">Código de respuesta de protocolo de inicio de sesión (SIP) a la invitación de sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="ecd6c-191">Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ecd6c-192">Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="ecd6c-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-193"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-194">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-195">Identificador de diagnóstico capturado del encabezado SIP.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-197">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-197">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-198">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-199">Identificador del servidor front-end usado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="ecd6c-200">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-201"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-202">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-202">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-203">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-204">Identificador del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="ecd6c-205">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-207">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-207">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-208">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-209">El servidor de mediación que está utilizando la llamada.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="ecd6c-210">Consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-211"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-212">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-212">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-213">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-214">La puerta de enlace que está utilizando la llamada.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-214">The gateway the call is using.</span></span> <span data-ttu-id="ecd6c-215">Consulte la <a href="lync-server-2013-gateways-table.md">tabla puertas de enlace en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-217">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-217">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-218">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-219">El servidor perimetral que está utilizando la llamada.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-219">The Edge Server the call is using.</span></span> <span data-ttu-id="ecd6c-220">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-222">entero</span><span class="sxs-lookup"><span data-stu-id="ecd6c-222">int</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-223">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-224">Tipo de contenido empleado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-224">Content type used in the session.</span></span> <span data-ttu-id="ecd6c-225">Consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-226"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-227">datetime</span><span class="sxs-lookup"><span data-stu-id="ecd6c-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-p121">Hora de la primera solicitud INVITE. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="ecd6c-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-232">datetime</span><span class="sxs-lookup"><span data-stu-id="ecd6c-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-233">Hora de la primera respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="ecd6c-234">Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ecd6c-235">Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="ecd6c-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-237">datetime</span><span class="sxs-lookup"><span data-stu-id="ecd6c-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-238">Hora en que finalizó la sesión.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-240">tinyint</span><span class="sxs-lookup"><span data-stu-id="ecd6c-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-241">Externa</span><span class="sxs-lookup"><span data-stu-id="ecd6c-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ecd6c-242">Contiene el valor tipo de URI de MCU de la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="ecd6c-243">Este campo se utiliza para mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="ecd6c-244">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ecd6c-245"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-246">smallint</span><span class="sxs-lookup"><span data-stu-id="ecd6c-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-p124">Conjunto de bits que indica los atributos del usuario. Se detallan las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="ecd6c-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ecd6c-249">Integrado con el teléfono de escritorio: 1</span><span class="sxs-lookup"><span data-stu-id="ecd6c-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ecd6c-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ecd6c-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ecd6c-251">smallint</span><span class="sxs-lookup"><span data-stu-id="ecd6c-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ecd6c-p125">Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="ecd6c-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="ecd6c-254">Reintento de sesión: 1</span><span class="sxs-lookup"><span data-stu-id="ecd6c-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ecd6c-255">\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="ecd6c-256">Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ecd6c-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

