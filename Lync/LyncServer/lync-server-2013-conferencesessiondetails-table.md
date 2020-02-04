---
title: 'Lync Server 2013: Tabla ConferenceSessionDetails'
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
ms.openlocfilehash: 61da586f3ecaf215b3bb636a80141ba8aaa19f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="b141d-102">Tabla ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b141d-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b141d-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b141d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b141d-104">Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico.</span><span class="sxs-lookup"><span data-stu-id="b141d-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b141d-105">Columna</span><span class="sxs-lookup"><span data-stu-id="b141d-105">Column</span></span></th>
<th><span data-ttu-id="b141d-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b141d-106">Data Type</span></span></th>
<th><span data-ttu-id="b141d-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="b141d-107">Key/Index</span></span></th>
<th><span data-ttu-id="b141d-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="b141d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b141d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-110">Fechas</span><span class="sxs-lookup"><span data-stu-id="b141d-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="b141d-111">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-112">Hora de la solicitud de sesión; se usa junto con <strong>SessionIdSeq</strong> para identificar de forma exclusiva una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b141d-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="b141d-113">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-115">int</span><span class="sxs-lookup"><span data-stu-id="b141d-115">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-116">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-117">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-117">ID number to identify the session.</span></span> <span data-ttu-id="b141d-118">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma exclusiva una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b141d-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="b141d-119">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-121">int</span><span class="sxs-lookup"><span data-stu-id="b141d-121">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-122">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-123">Centrar el URI de conferencia relacionado con esta sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="b141d-124">Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b141d-125">Este URI es un URI de conferencia basado en el foco.</span><span class="sxs-lookup"><span data-stu-id="b141d-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-127">Identificador</span><span class="sxs-lookup"><span data-stu-id="b141d-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-128">Identificador que diferencia entre instancias de conferencias periódicas.</span><span class="sxs-lookup"><span data-stu-id="b141d-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="b141d-129">Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="b141d-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="b141d-130">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b141d-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-132">int</span><span class="sxs-lookup"><span data-stu-id="b141d-132">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-133">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-134">URI de conferencia del servidor de conferencia relacionado con esta sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="b141d-135">Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b141d-136">Este URI es el URI de conferencia basado en el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b141d-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="b141d-137">Para sesiones de conferencia focalizadas, esta columna será nula.</span><span class="sxs-lookup"><span data-stu-id="b141d-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-138"><strong>Iddeusuario</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-139">int</span><span class="sxs-lookup"><span data-stu-id="b141d-139">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-140">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-141">IDENTIFICADOR de un usuario en la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b141d-141">ID of one user in the conference session.</span></span> <span data-ttu-id="b141d-142">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-144">identificador</span><span class="sxs-lookup"><span data-stu-id="b141d-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-145">Un GUID para identificar la instancia de Endpoint.</span><span class="sxs-lookup"><span data-stu-id="b141d-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="b141d-146">Por ejemplo, si un usuario inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un identificador de extremo diferente.</span><span class="sxs-lookup"><span data-stu-id="b141d-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-148">int</span><span class="sxs-lookup"><span data-stu-id="b141d-148">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-149">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-150">Indica el identificador del usuario de la persona que llama en nombre.</span><span class="sxs-lookup"><span data-stu-id="b141d-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="b141d-151">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-153">int</span><span class="sxs-lookup"><span data-stu-id="b141d-153">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-154">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-155">IDENTIFICADOR del usuario al que hace referencia la llamada.</span><span class="sxs-lookup"><span data-stu-id="b141d-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="b141d-156">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-158">int</span><span class="sxs-lookup"><span data-stu-id="b141d-158">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-159">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-160">Versión del cliente usada por el usuario de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="b141d-160">Client version used by the conference user.</span></span> <span data-ttu-id="b141d-161">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-163">int</span><span class="sxs-lookup"><span data-stu-id="b141d-163">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-164">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-165">Versión de cliente usada por el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b141d-165">Client version used by the conference server.</span></span> <span data-ttu-id="b141d-166">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-168">datetime</span><span class="sxs-lookup"><span data-stu-id="b141d-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="b141d-169">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-170">Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="b141d-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="b141d-171">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-173">int</span><span class="sxs-lookup"><span data-stu-id="b141d-173">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-174">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-175">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-175">ID number to identify the session.</span></span> <span data-ttu-id="b141d-176">Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de forma única una sesión que se reemplaza por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="b141d-177">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-179">bit</span><span class="sxs-lookup"><span data-stu-id="b141d-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-180">Indica si la sesión ha sido iniciada por el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b141d-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-182">bit</span><span class="sxs-lookup"><span data-stu-id="b141d-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-183">Indica si la sesión finalizó por el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b141d-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-185">bit</span><span class="sxs-lookup"><span data-stu-id="b141d-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-186">Si el usuario ha iniciado sesión en un interno o no.</span><span class="sxs-lookup"><span data-stu-id="b141d-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-188">int</span><span class="sxs-lookup"><span data-stu-id="b141d-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-189">Código de respuesta del Protocolo de inicio de sesión (SIP) a la invitación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="b141d-190">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b141d-191">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="b141d-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-193">int</span><span class="sxs-lookup"><span data-stu-id="b141d-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-194">IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.</span><span class="sxs-lookup"><span data-stu-id="b141d-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-196">int</span><span class="sxs-lookup"><span data-stu-id="b141d-196">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-197">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-198">IDENTIFICADOR del servidor front-end usado para esta sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="b141d-199">Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-201">int</span><span class="sxs-lookup"><span data-stu-id="b141d-201">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-202">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-203">IDENTIFICADOR del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="b141d-204">Para obtener más información, consulte la <a href="lync-server-2013-pools-table.md">tabla de grupos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-206">int</span><span class="sxs-lookup"><span data-stu-id="b141d-206">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-207">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-208">El servidor de mediación que usa la llamada.</span><span class="sxs-lookup"><span data-stu-id="b141d-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="b141d-209">Para obtener más información, consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-211">int</span><span class="sxs-lookup"><span data-stu-id="b141d-211">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-212">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-213">La puerta de enlace que usa la llamada.</span><span class="sxs-lookup"><span data-stu-id="b141d-213">The gateway the call is using.</span></span> <span data-ttu-id="b141d-214">Para obtener más información, consulte la <a href="lync-server-2013-gateways-table.md">tabla de puertas de enlace en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-216">int</span><span class="sxs-lookup"><span data-stu-id="b141d-216">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-217">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-218">El servidor perimetral que usa la llamada.</span><span class="sxs-lookup"><span data-stu-id="b141d-218">The Edge Server the call is using.</span></span> <span data-ttu-id="b141d-219">Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-221">int</span><span class="sxs-lookup"><span data-stu-id="b141d-221">int</span></span></p></td>
<td><p><span data-ttu-id="b141d-222">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-223">Tipo de contenido usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-223">Content type used in the session.</span></span> <span data-ttu-id="b141d-224">Para obtener más información, consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b141d-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-226">datetime</span><span class="sxs-lookup"><span data-stu-id="b141d-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-227">La hora de la primera solicitud de invitación.</span><span class="sxs-lookup"><span data-stu-id="b141d-227">The time of the first INVITE request.</span></span> <span data-ttu-id="b141d-228">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b141d-229">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="b141d-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-231">datetime</span><span class="sxs-lookup"><span data-stu-id="b141d-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-232">Hora de la primera respuesta del SIP.</span><span class="sxs-lookup"><span data-stu-id="b141d-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="b141d-233">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="b141d-234">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="b141d-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-236">datetime</span><span class="sxs-lookup"><span data-stu-id="b141d-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-237">La hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="b141d-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="b141d-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b141d-240">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b141d-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b141d-241">Contiene el valor de tipo URI de MCU de la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b141d-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="b141d-242">Este campo se usa para mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="b141d-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="b141d-243">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b141d-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b141d-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-245">smallint</span><span class="sxs-lookup"><span data-stu-id="b141d-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-246">Un conjunto de bits que indica los atributos de usuario.</span><span class="sxs-lookup"><span data-stu-id="b141d-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="b141d-247">Se muestran las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="b141d-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="b141d-248">Integrado con un teléfono de escritorio: 1</span><span class="sxs-lookup"><span data-stu-id="b141d-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141d-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b141d-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b141d-250">smallint</span><span class="sxs-lookup"><span data-stu-id="b141d-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b141d-251">Un conjunto de bits que indica los atributos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b141d-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="b141d-252">Se muestran las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="b141d-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="b141d-253">Reintento de sesión: 1</span><span class="sxs-lookup"><span data-stu-id="b141d-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b141d-254">\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1.</span><span class="sxs-lookup"><span data-stu-id="b141d-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="b141d-255">Si varias sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para una será 1, la otra será 2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="b141d-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

