---
title: 'Lync Server 2013: Tabla ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="c6fa5-102">Tabla ConferenceSessionDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fa5-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6fa5-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c6fa5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c6fa5-104">Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6fa5-105">Columna</span><span class="sxs-lookup"><span data-stu-id="c6fa5-105">Column</span></span></th>
<th><span data-ttu-id="c6fa5-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c6fa5-106">Data Type</span></span></th>
<th><span data-ttu-id="c6fa5-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="c6fa5-107">Key/Index</span></span></th>
<th><span data-ttu-id="c6fa5-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="c6fa5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-110">Fechas</span><span class="sxs-lookup"><span data-stu-id="c6fa5-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-111">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-112">Hora de la solicitud de sesión; se usa junto con <strong>SessionIdSeq</strong> para identificar de forma exclusiva una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="c6fa5-113">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-115">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-115">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-116">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-117">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-117">ID number to identify the session.</span></span> <span data-ttu-id="c6fa5-118">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma exclusiva una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="c6fa5-119">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-121">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-121">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-122">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-123">Centrar el URI de conferencia relacionado con esta sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="c6fa5-124">Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="c6fa5-125">Este URI es un URI de conferencia basado en el foco.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-127">Identificador</span><span class="sxs-lookup"><span data-stu-id="c6fa5-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-128">Identificador que diferencia entre instancias de conferencias periódicas.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="c6fa5-129">Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="c6fa5-130">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-132">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-132">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-133">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-134">URI de conferencia del servidor de conferencia relacionado con esta sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="c6fa5-135">Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="c6fa5-136">Este URI es el URI de conferencia basado en el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="c6fa5-137">Para sesiones de conferencia focalizadas, esta columna será nula.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-138"><strong>Iddeusuario</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-139">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-139">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-140">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-141">IDENTIFICADOR de un usuario en la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-141">ID of one user in the conference session.</span></span> <span data-ttu-id="c6fa5-142">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-144">identificador</span><span class="sxs-lookup"><span data-stu-id="c6fa5-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-145">Un GUID para identificar la instancia de Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="c6fa5-146">Por ejemplo, si un usuario inicia sesión en diferentes equipos con la misma cuenta, cada equipo tendrá un identificador de extremo diferente.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-148">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-148">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-149">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-150">Indica el identificador del usuario de la persona que llama en nombre.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="c6fa5-151">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-153">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-153">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-154">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-155">IDENTIFICADOR del usuario al que hace referencia la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="c6fa5-156">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-158">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-158">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-159">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-160">Versión del cliente usada por el usuario de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-160">Client version used by the conference user.</span></span> <span data-ttu-id="c6fa5-161">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-163">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-163">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-164">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-165">Versión de cliente usada por el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-165">Client version used by the conference server.</span></span> <span data-ttu-id="c6fa5-166">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-168">datetime</span><span class="sxs-lookup"><span data-stu-id="c6fa5-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-169">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-170">Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="c6fa5-171">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-173">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-173">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-174">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-175">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-175">ID number to identify the session.</span></span> <span data-ttu-id="c6fa5-176">Se usa junto con <strong>ReplacesDialogIdTime</strong> para identificar de forma única una sesión que se reemplaza por esta sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="c6fa5-177">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-179">bit</span><span class="sxs-lookup"><span data-stu-id="c6fa5-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-180">Indica si la sesión ha sido iniciada por el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-182">bit</span><span class="sxs-lookup"><span data-stu-id="c6fa5-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-183">Indica si la sesión finalizó por el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-185">bit</span><span class="sxs-lookup"><span data-stu-id="c6fa5-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-186">Si el usuario ha iniciado sesión en un interno o no.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-188">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-189">Código de respuesta del Protocolo de inicio de sesión (SIP) a la invitación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="c6fa5-190">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6fa5-191">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="c6fa5-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-193">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-194">IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-196">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-196">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-197">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-198">IDENTIFICADOR del servidor front-end usado para esta sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="c6fa5-199">Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-201">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-201">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-202">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-203">IDENTIFICADOR del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="c6fa5-204">Para obtener más información, consulte la <a href="lync-server-2013-pools-table.md">tabla de grupos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-206">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-206">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-207">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-208">El servidor de mediación que usa la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="c6fa5-209">Para obtener más información, consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-211">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-211">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-212">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-213">La puerta de enlace que usa la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-213">The gateway the call is using.</span></span> <span data-ttu-id="c6fa5-214">Para obtener más información, consulte la <a href="lync-server-2013-gateways-table.md">tabla de puertas de enlace en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-216">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-216">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-217">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-218">El servidor perimetral que usa la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-218">The Edge Server the call is using.</span></span> <span data-ttu-id="c6fa5-219">Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-221">int</span><span class="sxs-lookup"><span data-stu-id="c6fa5-221">int</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-222">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-223">Tipo de contenido usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-223">Content type used in the session.</span></span> <span data-ttu-id="c6fa5-224">Para obtener más información, consulte la <a href="lync-server-2013-contenttypes-table.md">tabla contentTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6fa5-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-226">datetime</span><span class="sxs-lookup"><span data-stu-id="c6fa5-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-227">La hora de la primera solicitud de invitación.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-227">The time of the first INVITE request.</span></span> <span data-ttu-id="c6fa5-228">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6fa5-229">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="c6fa5-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-231">datetime</span><span class="sxs-lookup"><span data-stu-id="c6fa5-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-232">Hora de la primera respuesta del SIP.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="c6fa5-233">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6fa5-234">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="c6fa5-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-236">datetime</span><span class="sxs-lookup"><span data-stu-id="c6fa5-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-237">La hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="c6fa5-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-240">Extranjero</span><span class="sxs-lookup"><span data-stu-id="c6fa5-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6fa5-241">Contiene el valor de tipo URI de MCU de la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="c6fa5-242">Este campo se usa para mejorar el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="c6fa5-243">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fa5-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-245">smallint</span><span class="sxs-lookup"><span data-stu-id="c6fa5-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-246">Un conjunto de bits que indica los atributos de usuario.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="c6fa5-247">Se muestran las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="c6fa5-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6fa5-248">Integrado con un teléfono de escritorio: 1</span><span class="sxs-lookup"><span data-stu-id="c6fa5-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fa5-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c6fa5-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6fa5-250">smallint</span><span class="sxs-lookup"><span data-stu-id="c6fa5-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6fa5-251">Un conjunto de bits que indica los atributos de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="c6fa5-252">Se muestran las siguientes definiciones de atributos:</span><span class="sxs-lookup"><span data-stu-id="c6fa5-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6fa5-253">Reintento de sesión: 1</span><span class="sxs-lookup"><span data-stu-id="c6fa5-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6fa5-254">\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="c6fa5-255">Si varias sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para una será 1, la otra será 2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

