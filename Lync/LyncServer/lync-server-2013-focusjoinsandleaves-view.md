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
ms.openlocfilehash: 9e97346929851bec53ab228988d72fb4813316d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="ab2d5-102">Vista FocusJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab2d5-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab2d5-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ab2d5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ab2d5-104">La vista FocusJoinsAndLeaves almacena la información sobre las incorporaciones y los abandonos de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="ab2d5-105">Cada conferencia se representa en esta vista con un registro que se escribe cada vez que un usuario se incorpora o abandona la conferencia.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="ab2d5-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab2d5-107">Columna</span><span class="sxs-lookup"><span data-stu-id="ab2d5-107">Column</span></span></th>
<th><span data-ttu-id="ab2d5-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab2d5-108">Data Type</span></span></th>
<th><span data-ttu-id="ab2d5-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="ab2d5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ab2d5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-112">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-112">Time of conference instance.</span></span> <span data-ttu-id="ab2d5-113">Se usa junto con SessionIdSeq para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="ab2d5-114">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2d5-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-116">int</span><span class="sxs-lookup"><span data-stu-id="ab2d5-116">int</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-117">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="ab2d5-118">Se usa junto con SessionIdTime para identificar una instancia de conferencia de forma única.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="ab2d5-119">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ab2d5-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-122">URI del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2d5-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ab2d5-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-125">Escriba la URI del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="ab2d5-126">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ab2d5-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-129">Inquilino del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="ab2d5-130">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2d5-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-132">identificador</span><span class="sxs-lookup"><span data-stu-id="ab2d5-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-133">Identificador único del usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ab2d5-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-136">Versión del cliente usada por el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2d5-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-138">int</span><span class="sxs-lookup"><span data-stu-id="ab2d5-138">int</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-139">Cliente que ha usado el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="ab2d5-140">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ab2d5-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-143">Nombre de la categoría del cliente usado por el usuario del que se ha capturado la información de incorporación/abandono.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2d5-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-145">int</span><span class="sxs-lookup"><span data-stu-id="ab2d5-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-147">bit</span><span class="sxs-lookup"><span data-stu-id="ab2d5-147">bit</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-148">Bit que representa si el usuario es interno o no.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2d5-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-150">datetime</span><span class="sxs-lookup"><span data-stu-id="ab2d5-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-151">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-151">Time of session request.</span></span> <span data-ttu-id="ab2d5-152">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ab2d5-153">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-155">int</span><span class="sxs-lookup"><span data-stu-id="ab2d5-155">int</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-156">Si un usuario inicia sesión en varios equipos o dispositivos a la vez, UserInstance se usa para identificar de forma única la combinación usuario/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2d5-157"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-158">VARCHAR (775)</span><span class="sxs-lookup"><span data-stu-id="ab2d5-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-p108">Identificador de diálogo SIP. El formato es: diálogo;etiqueta-origen;etiqueta-destino.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-162">datetime</span><span class="sxs-lookup"><span data-stu-id="ab2d5-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-163">Hora a la que el usuario se incorporó a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2d5-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-165">datetime</span><span class="sxs-lookup"><span data-stu-id="ab2d5-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-166">Hora a la que el usuario abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2d5-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="ab2d5-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="ab2d5-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ab2d5-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ab2d5-169">Rol del usuario en la conferencia, por ejemplo moderador o asistente.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

