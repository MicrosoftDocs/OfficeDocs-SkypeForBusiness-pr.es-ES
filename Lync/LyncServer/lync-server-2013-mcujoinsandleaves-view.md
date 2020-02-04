---
title: 'Lync Server 2013: vista McuJoinsAndLeaves'
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
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="7599b-102">Vista McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7599b-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7599b-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7599b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7599b-104">La vista McuJoinsAndLeaves almacena información sobre los usuarios que se unen y salen de la información de un servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7599b-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="7599b-105">Cada registro de esta vista contiene detalles de la llamada sobre una combinación de una Unión de usuario o el servidor abandonar y Conferencia.</span><span class="sxs-lookup"><span data-stu-id="7599b-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="7599b-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7599b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7599b-107">Columna</span><span class="sxs-lookup"><span data-stu-id="7599b-107">Column</span></span></th>
<th><span data-ttu-id="7599b-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7599b-108">Data Type</span></span></th>
<th><span data-ttu-id="7599b-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="7599b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7599b-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7599b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7599b-112">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7599b-112">Time of conference instance.</span></span> <span data-ttu-id="7599b-113">Se usa junto con SessionIdSeq para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7599b-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="7599b-114">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7599b-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7599b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-116">int</span><span class="sxs-lookup"><span data-stu-id="7599b-116">int</span></span></p></td>
<td><p><span data-ttu-id="7599b-117">Número de identificación para identificar la instancia de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="7599b-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="7599b-118">Se usa junto con SessionIdTime para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7599b-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="7599b-119">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7599b-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7599b-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7599b-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7599b-122">El URI del servidor de conferencia al que se conectó el usuario.</span><span class="sxs-lookup"><span data-stu-id="7599b-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7599b-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7599b-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7599b-125">El URI del servidor de conferencia al que se conectó el usuario.</span><span class="sxs-lookup"><span data-stu-id="7599b-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="7599b-126">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7599b-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7599b-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7599b-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7599b-129">El URI del usuario en el que se ha capturado la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="7599b-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7599b-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7599b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7599b-132">El tipo de URI del usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="7599b-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="7599b-133">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7599b-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7599b-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7599b-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7599b-136">El inquilino del usuario en el que se ha capturado la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="7599b-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="7599b-137">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7599b-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7599b-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7599b-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7599b-140">La versión de cliente utilizada por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="7599b-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7599b-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-142">int</span><span class="sxs-lookup"><span data-stu-id="7599b-142">int</span></span></p></td>
<td><p><span data-ttu-id="7599b-143">El cliente usado por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="7599b-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="7599b-144">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7599b-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7599b-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7599b-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7599b-147">El nombre de la categoría del cliente usada por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</span><span class="sxs-lookup"><span data-stu-id="7599b-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7599b-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-149">int</span><span class="sxs-lookup"><span data-stu-id="7599b-149">int</span></span></p></td>
<td><p><span data-ttu-id="7599b-150">Identifica de forma única la combinación de usuarios y dispositivos para los usuarios que tienen iniciada sesión simultáneamente en varios dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7599b-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7599b-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-152">bit</span><span class="sxs-lookup"><span data-stu-id="7599b-152">bit</span></span></p></td>
<td><p><span data-ttu-id="7599b-153">Bit que representa si el usuario es un usuario interno o no.</span><span class="sxs-lookup"><span data-stu-id="7599b-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7599b-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-155">datetime</span><span class="sxs-lookup"><span data-stu-id="7599b-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="7599b-156">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="7599b-156">Time of session request.</span></span> <span data-ttu-id="7599b-157">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="7599b-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="7599b-158">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7599b-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7599b-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-160">int</span><span class="sxs-lookup"><span data-stu-id="7599b-160">int</span></span></p></td>
<td><p><span data-ttu-id="7599b-161">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="7599b-161">ID number to identify the session.</span></span> <span data-ttu-id="7599b-162">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="7599b-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="7599b-163">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7599b-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7599b-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-165">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="7599b-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="7599b-166">IDENTIFICACIÓN del cuadro de diálogo SIP de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7599b-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="7599b-167">El formato es: diálogo; de-etiqueta; to-TAG.</span><span class="sxs-lookup"><span data-stu-id="7599b-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7599b-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-169">datetime</span><span class="sxs-lookup"><span data-stu-id="7599b-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="7599b-170">Momento en que el usuario se unió al servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7599b-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7599b-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="7599b-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7599b-172">datetime</span><span class="sxs-lookup"><span data-stu-id="7599b-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="7599b-173">El momento en que el usuario abandonó el servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7599b-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

