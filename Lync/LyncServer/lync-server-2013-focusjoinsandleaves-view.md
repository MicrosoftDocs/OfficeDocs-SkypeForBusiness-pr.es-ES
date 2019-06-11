---
title: 'Lync Server 2013: vista FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="a82f4-102">Vista FocusJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a82f4-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a82f4-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a82f4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a82f4-104">La vista FocusJoinsAndLeaves almacena información acerca de la Unión y la información de salida de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="a82f4-105">Cada conferencia se representa en esta vista por un registro que se escribe cada vez que un usuario se une y sale de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="a82f4-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a82f4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a82f4-107">Columna</span><span class="sxs-lookup"><span data-stu-id="a82f4-107">Column</span></span></th>
<th><span data-ttu-id="a82f4-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a82f4-108">Data Type</span></span></th>
<th><span data-ttu-id="a82f4-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="a82f4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a82f4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a82f4-112">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-112">Time of conference instance.</span></span> <span data-ttu-id="a82f4-113">Se usa junto con SessionIdSeq para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="a82f4-114">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a82f4-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a82f4-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-116">int</span><span class="sxs-lookup"><span data-stu-id="a82f4-116">int</span></span></p></td>
<td><p><span data-ttu-id="a82f4-117">Número de identificación para identificar la instancia de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="a82f4-118">Se usa junto con SessionIdTime para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="a82f4-119">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a82f4-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a82f4-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a82f4-122">URI del usuario en el que se capturó la información de unión o salida de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a82f4-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a82f4-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a82f4-125">Tipo de URI del usuario cuya información de unión o salida de conferencia se capturó.</span><span class="sxs-lookup"><span data-stu-id="a82f4-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="a82f4-126">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a82f4-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a82f4-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a82f4-129">Espacio empresarial del usuario cuya información de unión o salida de conferencia fue capturada.</span><span class="sxs-lookup"><span data-stu-id="a82f4-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="a82f4-130">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a82f4-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a82f4-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-132">identificador</span><span class="sxs-lookup"><span data-stu-id="a82f4-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a82f4-133">Identificador único del usuario cuya información de unión o salida de conferencia se capturó.</span><span class="sxs-lookup"><span data-stu-id="a82f4-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a82f4-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a82f4-136">Versión del cliente usada por el usuario cuya información de unión o salida de conferencia ha sido capturada.</span><span class="sxs-lookup"><span data-stu-id="a82f4-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a82f4-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-138">int</span><span class="sxs-lookup"><span data-stu-id="a82f4-138">int</span></span></p></td>
<td><p><span data-ttu-id="a82f4-139">Cliente usado por el usuario cuya información de unión o salida de conferencia fue capturada.</span><span class="sxs-lookup"><span data-stu-id="a82f4-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="a82f4-140">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a82f4-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a82f4-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a82f4-143">Nombre de la categoría del cliente usada por el usuario cuya información de unión o salida de conferencia fue capturada.</span><span class="sxs-lookup"><span data-stu-id="a82f4-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a82f4-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-145">int</span><span class="sxs-lookup"><span data-stu-id="a82f4-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-147">bit</span><span class="sxs-lookup"><span data-stu-id="a82f4-147">bit</span></span></p></td>
<td><p><span data-ttu-id="a82f4-148">Bit que representa si el usuario es un usuario interno o no.</span><span class="sxs-lookup"><span data-stu-id="a82f4-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a82f4-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-150">datetime</span><span class="sxs-lookup"><span data-stu-id="a82f4-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="a82f4-151">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="a82f4-151">Time of session request.</span></span> <span data-ttu-id="a82f4-152">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="a82f4-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a82f4-153">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a82f4-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-155">int</span><span class="sxs-lookup"><span data-stu-id="a82f4-155">int</span></span></p></td>
<td><p><span data-ttu-id="a82f4-156">Si un usuario ha iniciado sesión en varios equipos o dispositivos al mismo tiempo, UserInstance se usa para identificar de forma inequívoca la combinación de usuario y dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a82f4-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a82f4-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-158">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="a82f4-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a82f4-159">IDENTIFICACIÓN del cuadro de diálogo SIP de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a82f4-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="a82f4-160">El formato es: diálogo; de-etiqueta; to-TAG.</span><span class="sxs-lookup"><span data-stu-id="a82f4-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-162">datetime</span><span class="sxs-lookup"><span data-stu-id="a82f4-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="a82f4-163">El momento en que el usuario se unió a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a82f4-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-165">datetime</span><span class="sxs-lookup"><span data-stu-id="a82f4-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="a82f4-166">Tiempo que el usuario abandonó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a82f4-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a82f4-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="a82f4-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="a82f4-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a82f4-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a82f4-169">Función del usuario en la Conferencia, como moderador o asistente.</span><span class="sxs-lookup"><span data-stu-id="a82f4-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

