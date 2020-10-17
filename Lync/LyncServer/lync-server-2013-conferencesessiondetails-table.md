---
title: 'Lync Server 2013: tabla ConferenceSessionDetails'
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
ms.openlocfilehash: 57d8e3cb0a79c8ce6a6c1c51891fbad265f045de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529207"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="34ec1-102">Tabla ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ec1-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34ec1-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="34ec1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="34ec1-104">Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico.</span><span class="sxs-lookup"><span data-stu-id="34ec1-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34ec1-105">Columna</span><span class="sxs-lookup"><span data-stu-id="34ec1-105">Column</span></span></th>
<th><span data-ttu-id="34ec1-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="34ec1-106">Data Type</span></span></th>
<th><span data-ttu-id="34ec1-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="34ec1-107">Key/Index</span></span></th>
<th><span data-ttu-id="34ec1-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="34ec1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="34ec1-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="34ec1-111">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="34ec1-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-112">Hora de la solicitud de sesión; se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34ec1-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="34ec1-113">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-115">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-115">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-116">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="34ec1-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-117">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-117">ID number to identify the session.</span></span> <span data-ttu-id="34ec1-118">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34ec1-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="34ec1-119">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-121">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-121">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-122">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-123">URI de conferencia basada en Foco relacionada con esta sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="34ec1-124">Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="34ec1-125">Esta URI es una URI de conferencia basada en Foco.</span><span class="sxs-lookup"><span data-stu-id="34ec1-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-127">Identificador</span><span class="sxs-lookup"><span data-stu-id="34ec1-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-128">Identificador que distingue entre instancias de conferencias recurrentes.</span><span class="sxs-lookup"><span data-stu-id="34ec1-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="34ec1-129">Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="34ec1-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="34ec1-130">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34ec1-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-132">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-132">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-133">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-134">URI de conferencia para servidor de conferencia relacionada con esta sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="34ec1-135">Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="34ec1-136">Esta URI es la URI de conferencia basada en servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34ec1-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="34ec1-137">En las sesiones de conferencia basadas en Foco, esta columna será nula.</span><span class="sxs-lookup"><span data-stu-id="34ec1-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-139">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-139">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-140">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-141">IDENTIFICADOR de un usuario en la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34ec1-141">ID of one user in the conference session.</span></span> <span data-ttu-id="34ec1-142">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-144">identificador</span><span class="sxs-lookup"><span data-stu-id="34ec1-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-p107">GUID para identificar la instancia del extremo. Por ejemplo, si un usuarios inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un id. de extremo diferente.</span><span class="sxs-lookup"><span data-stu-id="34ec1-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-148">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-148">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-149">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-150">Señala el identificador de usuario en cuyo nombre llama el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="34ec1-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="34ec1-151">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-153">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-153">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-154">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-155">Identificador del usuario por el que se hace referencia a la sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="34ec1-156">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-158">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-158">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-159">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-160">Versión del cliente utilizada por el usuario de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34ec1-160">Client version used by the conference user.</span></span> <span data-ttu-id="34ec1-161">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-163">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-163">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-164">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-165">Versión del cliente utilizada por el usuario de servidor.</span><span class="sxs-lookup"><span data-stu-id="34ec1-165">Client version used by the conference server.</span></span> <span data-ttu-id="34ec1-166">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-168">datetime</span><span class="sxs-lookup"><span data-stu-id="34ec1-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="34ec1-169">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-170">Número con el que se identifica el diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="34ec1-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="34ec1-171">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-173">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-173">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-174">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-175">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-175">ID number to identify the session.</span></span> <span data-ttu-id="34ec1-176">Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de manera exclusiva una sesión que se reemplazó por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="34ec1-177">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-179">bit</span><span class="sxs-lookup"><span data-stu-id="34ec1-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-180">Indica si la sesión la inició el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34ec1-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-182">bit</span><span class="sxs-lookup"><span data-stu-id="34ec1-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-183">Indica si la sesión la finalizó el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="34ec1-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-185">bit</span><span class="sxs-lookup"><span data-stu-id="34ec1-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-186">Tanto si el usuario ha iniciado sesión desde un equipo interno como si no.</span><span class="sxs-lookup"><span data-stu-id="34ec1-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-188">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-189">Código de respuesta de protocolo de inicio de sesión (SIP) a la invitación de sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="34ec1-190">Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="34ec1-191">Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="34ec1-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-193">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-194">Identificador de diagnóstico capturado del encabezado SIP.</span><span class="sxs-lookup"><span data-stu-id="34ec1-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-196">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-196">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-197">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-198">Identificador del servidor front-end usado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="34ec1-199">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-201">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-201">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-202">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-203">Identificador del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="34ec1-204">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-206">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-206">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-207">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-208">El servidor de mediación que está utilizando la llamada.</span><span class="sxs-lookup"><span data-stu-id="34ec1-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="34ec1-209">Consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-211">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-211">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-212">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-213">La puerta de enlace que está utilizando la llamada.</span><span class="sxs-lookup"><span data-stu-id="34ec1-213">The gateway the call is using.</span></span> <span data-ttu-id="34ec1-214">Consulte la <a href="lync-server-2013-gateways-table.md">tabla puertas de enlace en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-216">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-216">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-217">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-218">El servidor perimetral que está utilizando la llamada.</span><span class="sxs-lookup"><span data-stu-id="34ec1-218">The Edge Server the call is using.</span></span> <span data-ttu-id="34ec1-219">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-221">entero</span><span class="sxs-lookup"><span data-stu-id="34ec1-221">int</span></span></p></td>
<td><p><span data-ttu-id="34ec1-222">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-223">Tipo de contenido empleado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-223">Content type used in the session.</span></span> <span data-ttu-id="34ec1-224">Consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34ec1-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-226">datetime</span><span class="sxs-lookup"><span data-stu-id="34ec1-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-p121">Hora de la primera solicitud INVITE. Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="34ec1-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-231">datetime</span><span class="sxs-lookup"><span data-stu-id="34ec1-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-232">Hora de la primera respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="34ec1-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="34ec1-233">Este campo suele rellenarse con datos generados a partir del mensaje INVITE inicial en la sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="34ec1-234">Si no hay ningún mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="34ec1-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-236">datetime</span><span class="sxs-lookup"><span data-stu-id="34ec1-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-237">Hora en que finalizó la sesión.</span><span class="sxs-lookup"><span data-stu-id="34ec1-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="34ec1-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="34ec1-240">Externa</span><span class="sxs-lookup"><span data-stu-id="34ec1-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="34ec1-241">Contiene el valor tipo de URI de MCU de la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="34ec1-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="34ec1-242">Este campo se utiliza para mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="34ec1-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="34ec1-243">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34ec1-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ec1-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-245">smallint</span><span class="sxs-lookup"><span data-stu-id="34ec1-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-p124">Conjunto de bits que indica los atributos del usuario. Se detallan las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="34ec1-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="34ec1-248">Integrado con el teléfono de escritorio: 1</span><span class="sxs-lookup"><span data-stu-id="34ec1-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ec1-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="34ec1-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="34ec1-250">smallint</span><span class="sxs-lookup"><span data-stu-id="34ec1-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34ec1-p125">Conjunto de bits que indica los atributos de la llamada. Se enumeran las siguientes definiciones de atributo:</span><span class="sxs-lookup"><span data-stu-id="34ec1-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="34ec1-253">Reintento de sesión: 1</span><span class="sxs-lookup"><span data-stu-id="34ec1-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="34ec1-254">\* Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1.</span><span class="sxs-lookup"><span data-stu-id="34ec1-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="34ec1-255">Si hay varias sesiones que comienzan exactamente a la misma hora, el valor de SessionIdSeq para una será 1, para otra, 2 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="34ec1-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

