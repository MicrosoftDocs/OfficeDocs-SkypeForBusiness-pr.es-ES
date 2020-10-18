---
title: 'Lync Server 2013: vista de FocusJoinsAndLeaves'
description: 'Lync Server 2013: vista de FocusJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577456"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="889a5-103">Vista FocusJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="889a5-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="889a5-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="889a5-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="889a5-105">La vista FocusJoinsAndLeaves almacena la información sobre las incorporaciones y los abandonos de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="889a5-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="889a5-106">Cada conferencia se representa en esta vista con un registro que se escribe cada vez que un usuario se incorpora o abandona la conferencia.</span><span class="sxs-lookup"><span data-stu-id="889a5-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="889a5-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="889a5-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="889a5-108">Columna</span><span class="sxs-lookup"><span data-stu-id="889a5-108">Column</span></span></th>
<th><span data-ttu-id="889a5-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="889a5-109">Data Type</span></span></th>
<th><span data-ttu-id="889a5-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="889a5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="889a5-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="889a5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="889a5-113">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="889a5-113">Time of conference instance.</span></span> <span data-ttu-id="889a5-114">Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="889a5-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="889a5-115">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="889a5-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="889a5-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-117">entero</span><span class="sxs-lookup"><span data-stu-id="889a5-117">int</span></span></p></td>
<td><p><span data-ttu-id="889a5-118">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="889a5-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="889a5-119">Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="889a5-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="889a5-120">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="889a5-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="889a5-121"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-122">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="889a5-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="889a5-123">URI del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="889a5-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="889a5-124"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="889a5-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="889a5-126">Escriba la URI del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="889a5-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="889a5-127">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="889a5-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="889a5-128"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="889a5-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="889a5-130">Inquilino del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="889a5-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="889a5-131">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="889a5-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="889a5-132"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-133">identificador</span><span class="sxs-lookup"><span data-stu-id="889a5-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="889a5-134">Identificador único del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="889a5-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="889a5-135"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="889a5-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="889a5-137">Versión del cliente usada por el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="889a5-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="889a5-138"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-139">entero</span><span class="sxs-lookup"><span data-stu-id="889a5-139">int</span></span></p></td>
<td><p><span data-ttu-id="889a5-140">Cliente que ha usado el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="889a5-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="889a5-141">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="889a5-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="889a5-142"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-143">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="889a5-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="889a5-144">Nombre de la categoría del cliente usado por el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="889a5-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="889a5-145"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-146">entero</span><span class="sxs-lookup"><span data-stu-id="889a5-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="889a5-147"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-148">bit</span><span class="sxs-lookup"><span data-stu-id="889a5-148">bit</span></span></p></td>
<td><p><span data-ttu-id="889a5-149">Bit que representa si el usuario es interno o no.</span><span class="sxs-lookup"><span data-stu-id="889a5-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="889a5-150"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-151">datetime</span><span class="sxs-lookup"><span data-stu-id="889a5-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="889a5-152">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="889a5-152">Time of session request.</span></span> <span data-ttu-id="889a5-153">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="889a5-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="889a5-154">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="889a5-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="889a5-155"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-156">entero</span><span class="sxs-lookup"><span data-stu-id="889a5-156">int</span></span></p></td>
<td><p><span data-ttu-id="889a5-157">Si un usuario inicia sesión en varios equipos o dispositivos a la vez, UserInstance se usa para identificar de forma única la combinación usuario/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="889a5-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="889a5-158"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-159">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="889a5-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="889a5-p108">Identificador de diálogo SIP. El formato es: diálogo;etiqueta-origen;etiqueta-destino.</span><span class="sxs-lookup"><span data-stu-id="889a5-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="889a5-162"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-163">datetime</span><span class="sxs-lookup"><span data-stu-id="889a5-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="889a5-164">Hora a la que el usuario se incorporó a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="889a5-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="889a5-165"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-166">datetime</span><span class="sxs-lookup"><span data-stu-id="889a5-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="889a5-167">Hora a la que el usuario abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="889a5-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="889a5-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="889a5-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="889a5-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="889a5-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="889a5-170">Rol del usuario en la conferencia, por ejemplo moderador o asistente.</span><span class="sxs-lookup"><span data-stu-id="889a5-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

