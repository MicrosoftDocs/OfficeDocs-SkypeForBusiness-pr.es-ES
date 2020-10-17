---
title: 'Lync Server 2013: vista de McuJoinsAndLeaves'
description: 'Lync Server 2013: vista de McuJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556496"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="4e9cd-103">Vista McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9cd-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e9cd-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4e9cd-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4e9cd-105">La vista McuJoinsAndLeaves almacena información sobre el momento en que los usuarios se unen a un servidor de conferencia o lo abandonan.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="4e9cd-106">Cada uno de los registros de esta vista contiene detalles de llamada sobre una combinación del servidor de conferencia y de la información sobre la entrada o la salida del mismo.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="4e9cd-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e9cd-108">Columna</span><span class="sxs-lookup"><span data-stu-id="4e9cd-108">Column</span></span></th>
<th><span data-ttu-id="4e9cd-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4e9cd-109">Data Type</span></span></th>
<th><span data-ttu-id="4e9cd-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="4e9cd-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4e9cd-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-113">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-113">Time of conference instance.</span></span> <span data-ttu-id="4e9cd-114">Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="4e9cd-115">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e9cd-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-117">entero</span><span class="sxs-lookup"><span data-stu-id="4e9cd-117">int</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-118">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="4e9cd-119">Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="4e9cd-120">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4e9cd-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-123">URI del servidor de conferencia al que se conectó el usuario.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e9cd-124"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4e9cd-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-126">URI del servidor de conferencia al que se conectó el usuario.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="4e9cd-127">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-129">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4e9cd-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-130">URI del usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e9cd-131"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4e9cd-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-133">Tipo de URI del usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="4e9cd-134">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-135"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4e9cd-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-137">Inquilino del usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="4e9cd-138">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e9cd-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4e9cd-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-141">Versión del cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-142"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-143">entero</span><span class="sxs-lookup"><span data-stu-id="4e9cd-143">int</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-144">Cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="4e9cd-145">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e9cd-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-147">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4e9cd-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-148">Nombre de la categoría del cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-150">entero</span><span class="sxs-lookup"><span data-stu-id="4e9cd-150">int</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-151">Identificación única de la combinación usuario/dispositivo para los usuarios con una sesión iniciada en varios dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e9cd-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-153">bit</span><span class="sxs-lookup"><span data-stu-id="4e9cd-153">bit</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-154">Bit que representa si el usuario es interno o no.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-156">datetime</span><span class="sxs-lookup"><span data-stu-id="4e9cd-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-157">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-157">Time of session request.</span></span> <span data-ttu-id="4e9cd-158">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="4e9cd-159">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e9cd-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-161">entero</span><span class="sxs-lookup"><span data-stu-id="4e9cd-161">int</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-162">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-162">ID number to identify the session.</span></span> <span data-ttu-id="4e9cd-163">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="4e9cd-164">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-165"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-166">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="4e9cd-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-p110">Identificador de diálogo SIP. El formato es: diálogo;etiqueta-origen;etiqueta-destino.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e9cd-169"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-170">datetime</span><span class="sxs-lookup"><span data-stu-id="4e9cd-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-171">Hora a la que el usuario se unió al servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e9cd-172"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e9cd-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e9cd-173">datetime</span><span class="sxs-lookup"><span data-stu-id="4e9cd-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e9cd-174">Hora a la que el usuario abandonó el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

