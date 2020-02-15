---
title: 'Lync Server 2013: vista de McuJoinsAndLeaves'
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
ms.openlocfilehash: 9eae65a6f19e0eb73098ed5990d6881d0129b34e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="fd140-102">Vista McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd140-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd140-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fd140-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fd140-104">La vista McuJoinsAndLeaves almacena información sobre el momento en que los usuarios se unen a un servidor de conferencia o lo abandonan.</span><span class="sxs-lookup"><span data-stu-id="fd140-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="fd140-105">Cada uno de los registros de esta vista contiene detalles de llamada sobre una combinación del servidor de conferencia y de la información sobre la entrada o la salida del mismo.</span><span class="sxs-lookup"><span data-stu-id="fd140-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="fd140-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd140-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd140-107">Columna</span><span class="sxs-lookup"><span data-stu-id="fd140-107">Column</span></span></th>
<th><span data-ttu-id="fd140-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fd140-108">Data Type</span></span></th>
<th><span data-ttu-id="fd140-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="fd140-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd140-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fd140-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fd140-112">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-112">Time of conference instance.</span></span> <span data-ttu-id="fd140-113">Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="fd140-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="fd140-114">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fd140-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd140-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-116">int</span><span class="sxs-lookup"><span data-stu-id="fd140-116">int</span></span></p></td>
<td><p><span data-ttu-id="fd140-117">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="fd140-118">Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="fd140-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="fd140-119">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fd140-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd140-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fd140-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fd140-122">URI del servidor de conferencia al que se conectó el usuario.</span><span class="sxs-lookup"><span data-stu-id="fd140-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd140-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fd140-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fd140-125">URI del servidor de conferencia al que se conectó el usuario.</span><span class="sxs-lookup"><span data-stu-id="fd140-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="fd140-126">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fd140-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd140-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fd140-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fd140-129">URI del usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd140-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fd140-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fd140-132">Tipo de URI del usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="fd140-133">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fd140-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd140-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fd140-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fd140-136">Inquilino del usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="fd140-137">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fd140-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd140-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fd140-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fd140-140">Versión del cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd140-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-142">int</span><span class="sxs-lookup"><span data-stu-id="fd140-142">int</span></span></p></td>
<td><p><span data-ttu-id="fd140-143">Cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="fd140-144">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fd140-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd140-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fd140-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fd140-147">Nombre de la categoría del cliente usado por el usuario del que se capturó la información de entrada/salida del servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd140-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-149">int</span><span class="sxs-lookup"><span data-stu-id="fd140-149">int</span></span></p></td>
<td><p><span data-ttu-id="fd140-150">Identificación única de la combinación usuario/dispositivo para los usuarios con una sesión iniciada en varios dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fd140-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd140-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-152">bit</span><span class="sxs-lookup"><span data-stu-id="fd140-152">bit</span></span></p></td>
<td><p><span data-ttu-id="fd140-153">Bit que representa si el usuario es interno o no.</span><span class="sxs-lookup"><span data-stu-id="fd140-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd140-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-155">datetime</span><span class="sxs-lookup"><span data-stu-id="fd140-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="fd140-156">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="fd140-156">Time of session request.</span></span> <span data-ttu-id="fd140-157">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="fd140-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="fd140-158">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fd140-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd140-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-160">int</span><span class="sxs-lookup"><span data-stu-id="fd140-160">int</span></span></p></td>
<td><p><span data-ttu-id="fd140-161">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="fd140-161">ID number to identify the session.</span></span> <span data-ttu-id="fd140-162">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="fd140-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="fd140-163">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fd140-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd140-164"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-165">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="fd140-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="fd140-p110">Identificador de diálogo SIP. El formato es: diálogo;etiqueta-origen;etiqueta-destino.</span><span class="sxs-lookup"><span data-stu-id="fd140-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd140-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-169">datetime</span><span class="sxs-lookup"><span data-stu-id="fd140-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="fd140-170">Hora a la que el usuario se unió al servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd140-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="fd140-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fd140-172">datetime</span><span class="sxs-lookup"><span data-stu-id="fd140-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="fd140-173">Hora a la que el usuario abandonó el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fd140-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

