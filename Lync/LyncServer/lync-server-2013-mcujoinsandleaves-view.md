---
title: 'Lync Server 2013: vista McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="e7e44-102">Vista McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7e44-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7e44-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e7e44-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e7e44-104">La vista McuJoinsAndLeaves almacena información sobre los usuarios que se unen y salen de la información de un servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e7e44-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="e7e44-105">Cada registro de esta vista contiene detalles de la llamada sobre una combinación de una Unión de usuario o el servidor abandonar y Conferencia.</span><span class="sxs-lookup"><span data-stu-id="e7e44-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="e7e44-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7e44-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7e44-107">Columna</span><span class="sxs-lookup"><span data-stu-id="e7e44-107">Column</span></span></th>
<th><span data-ttu-id="e7e44-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e7e44-108">Data Type</span></span></th>
<th><span data-ttu-id="e7e44-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="e7e44-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e7e44-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e7e44-112">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e7e44-112">Time of conference instance.</span></span> <span data-ttu-id="e7e44-113">Se usa junto con SessionIdSeq para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e7e44-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="e7e44-114">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e7e44-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e44-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-116">int</span><span class="sxs-lookup"><span data-stu-id="e7e44-116">int</span></span></p></td>
<td><p><span data-ttu-id="e7e44-117">Número de identificación para identificar la instancia de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="e7e44-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="e7e44-118">Se usa junto con SessionIdTime para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e7e44-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="e7e44-119">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e7e44-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e7e44-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e7e44-122">El URI del servidor de conferencia al que se conectó el usuario.</span><span class="sxs-lookup"><span data-stu-id="e7e44-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e44-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e7e44-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e7e44-125">El URI del servidor de conferencia al que se conectó el usuario.</span><span class="sxs-lookup"><span data-stu-id="e7e44-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="e7e44-126">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e7e44-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e7e44-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e7e44-129">El URI del usuario en el que se ha capturado la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="e7e44-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e44-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e7e44-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e7e44-132">El tipo de URI del usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="e7e44-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e7e44-133">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e7e44-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e7e44-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e7e44-136">El inquilino del usuario en el que se ha capturado la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="e7e44-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e7e44-137">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e7e44-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e44-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e7e44-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e7e44-140">La versión de cliente utilizada por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="e7e44-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-142">int</span><span class="sxs-lookup"><span data-stu-id="e7e44-142">int</span></span></p></td>
<td><p><span data-ttu-id="e7e44-143">El cliente usado por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="e7e44-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e7e44-144">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e7e44-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e44-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e7e44-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e7e44-147">El nombre de la categoría del cliente usada por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="e7e44-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-149">int</span><span class="sxs-lookup"><span data-stu-id="e7e44-149">int</span></span></p></td>
<td><p><span data-ttu-id="e7e44-150">Identifica de forma única la combinación de usuarios y dispositivos para los usuarios que tienen iniciada sesión simultáneamente en varios dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e7e44-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e44-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-152">bit</span><span class="sxs-lookup"><span data-stu-id="e7e44-152">bit</span></span></p></td>
<td><p><span data-ttu-id="e7e44-153">Bit que representa si el usuario es un usuario interno o no.</span><span class="sxs-lookup"><span data-stu-id="e7e44-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-155">datetime</span><span class="sxs-lookup"><span data-stu-id="e7e44-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="e7e44-156">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="e7e44-156">Time of session request.</span></span> <span data-ttu-id="e7e44-157">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="e7e44-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e7e44-158">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e7e44-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e44-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-160">int</span><span class="sxs-lookup"><span data-stu-id="e7e44-160">int</span></span></p></td>
<td><p><span data-ttu-id="e7e44-161">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="e7e44-161">ID number to identify the session.</span></span> <span data-ttu-id="e7e44-162">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="e7e44-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e7e44-163">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e7e44-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-165">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="e7e44-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e7e44-166">IDENTIFICACIÓN del cuadro de diálogo SIP de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e7e44-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="e7e44-167">El formato es: diálogo; de-etiqueta; to-TAG.</span><span class="sxs-lookup"><span data-stu-id="e7e44-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7e44-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-169">datetime</span><span class="sxs-lookup"><span data-stu-id="e7e44-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="e7e44-170">Momento en que el usuario se unió al servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e7e44-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7e44-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e7e44-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e7e44-172">datetime</span><span class="sxs-lookup"><span data-stu-id="e7e44-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="e7e44-173">El momento en que el usuario abandonó el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e7e44-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

