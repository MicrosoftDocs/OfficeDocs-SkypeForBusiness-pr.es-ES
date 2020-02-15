---
title: 'Lync Server 2013: vista de FocusJoinsAndLeaves'
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
ms.openlocfilehash: 8c5c10cc90064e9ed3237dcd4cd4cbed1021d1b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="29a3c-102">Vista FocusJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29a3c-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29a3c-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="29a3c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="29a3c-104">La vista FocusJoinsAndLeaves almacena la información sobre las incorporaciones y los abandonos de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="29a3c-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="29a3c-105">Cada conferencia se representa en esta vista con un registro que se escribe cada vez que un usuario se incorpora o abandona la conferencia.</span><span class="sxs-lookup"><span data-stu-id="29a3c-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="29a3c-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29a3c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29a3c-107">Columna</span><span class="sxs-lookup"><span data-stu-id="29a3c-107">Column</span></span></th>
<th><span data-ttu-id="29a3c-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="29a3c-108">Data Type</span></span></th>
<th><span data-ttu-id="29a3c-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="29a3c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="29a3c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="29a3c-112">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="29a3c-112">Time of conference instance.</span></span> <span data-ttu-id="29a3c-113">Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="29a3c-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="29a3c-114">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="29a3c-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a3c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-116">int</span><span class="sxs-lookup"><span data-stu-id="29a3c-116">int</span></span></p></td>
<td><p><span data-ttu-id="29a3c-117">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="29a3c-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="29a3c-118">Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="29a3c-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="29a3c-119">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="29a3c-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="29a3c-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="29a3c-122">URI del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="29a3c-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a3c-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29a3c-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29a3c-125">Escriba la URI del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="29a3c-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29a3c-126">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="29a3c-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29a3c-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29a3c-129">Inquilino del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="29a3c-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29a3c-130">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="29a3c-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a3c-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-132">identificador</span><span class="sxs-lookup"><span data-stu-id="29a3c-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="29a3c-133">Identificador único del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="29a3c-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29a3c-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29a3c-136">Versión del cliente usada por el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="29a3c-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a3c-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-138">int</span><span class="sxs-lookup"><span data-stu-id="29a3c-138">int</span></span></p></td>
<td><p><span data-ttu-id="29a3c-139">Cliente que ha usado el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="29a3c-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29a3c-140">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="29a3c-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="29a3c-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="29a3c-143">Nombre de la categoría del cliente usado por el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="29a3c-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a3c-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-145">int</span><span class="sxs-lookup"><span data-stu-id="29a3c-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-147">bit</span><span class="sxs-lookup"><span data-stu-id="29a3c-147">bit</span></span></p></td>
<td><p><span data-ttu-id="29a3c-148">Bit que representa si el usuario es interno o no.</span><span class="sxs-lookup"><span data-stu-id="29a3c-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a3c-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-150">datetime</span><span class="sxs-lookup"><span data-stu-id="29a3c-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="29a3c-151">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="29a3c-151">Time of session request.</span></span> <span data-ttu-id="29a3c-152">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="29a3c-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="29a3c-153">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="29a3c-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-155">int</span><span class="sxs-lookup"><span data-stu-id="29a3c-155">int</span></span></p></td>
<td><p><span data-ttu-id="29a3c-156">Si un usuario inicia sesión en varios equipos o dispositivos a la vez, UserInstance se usa para identificar de forma única la combinación usuario/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29a3c-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a3c-157"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-158">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="29a3c-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="29a3c-p108">Identificador de diálogo SIP. El formato es: diálogo;etiqueta-origen;etiqueta-destino.</span><span class="sxs-lookup"><span data-stu-id="29a3c-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-162">datetime</span><span class="sxs-lookup"><span data-stu-id="29a3c-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="29a3c-163">Hora a la que el usuario se incorporó a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="29a3c-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a3c-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-165">datetime</span><span class="sxs-lookup"><span data-stu-id="29a3c-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="29a3c-166">Hora a la que el usuario abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="29a3c-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a3c-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="29a3c-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="29a3c-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29a3c-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29a3c-169">Rol del usuario en la conferencia, por ejemplo moderador o asistente.</span><span class="sxs-lookup"><span data-stu-id="29a3c-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

