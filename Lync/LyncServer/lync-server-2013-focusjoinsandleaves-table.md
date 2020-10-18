---
title: 'Lync Server 2013: tabla FocusJoinsAndLeaves'
description: 'Lync Server 2013: tabla FocusJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5796de16ed204ce4f33935d937cbaa425d63a67f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577446"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="7e73d-103">Tabla FocusJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e73d-103">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e73d-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7e73d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7e73d-105">Cada registro de esta tabla contiene la información de CDR sobre la Unión de un usuario y deja la información de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e73d-105">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="7e73d-106">Cada conferencia se representa en esta tabla mediante un registro cada vez que un usuario se une a la Conferencia y la abandona.</span><span class="sxs-lookup"><span data-stu-id="7e73d-106">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e73d-107">Columna</span><span class="sxs-lookup"><span data-stu-id="7e73d-107">Column</span></span></th>
<th><span data-ttu-id="7e73d-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7e73d-108">Data Type</span></span></th>
<th><span data-ttu-id="7e73d-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="7e73d-109">Key/Index</span></span></th>
<th><span data-ttu-id="7e73d-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="7e73d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e73d-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7e73d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e73d-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="7e73d-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e73d-114">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e73d-114">Time of conference instance.</span></span> <span data-ttu-id="7e73d-115">Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e73d-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7e73d-116">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7e73d-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e73d-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-118">entero</span><span class="sxs-lookup"><span data-stu-id="7e73d-118">int</span></span></p></td>
<td><p><span data-ttu-id="7e73d-119">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="7e73d-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e73d-120">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e73d-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="7e73d-121">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e73d-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7e73d-122">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7e73d-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e73d-123"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-123"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-124">datetime</span><span class="sxs-lookup"><span data-stu-id="7e73d-124">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e73d-125">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="7e73d-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e73d-126">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="7e73d-126">Time of session request.</span></span> <span data-ttu-id="7e73d-127">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="7e73d-127">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7e73d-128">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7e73d-128">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e73d-129"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-129"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-130">entero</span><span class="sxs-lookup"><span data-stu-id="7e73d-130">int</span></span></p></td>
<td><p><span data-ttu-id="7e73d-131">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="7e73d-131">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e73d-132">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e73d-132">ID number to identify the session.</span></span> <span data-ttu-id="7e73d-133">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="7e73d-133">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7e73d-134">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7e73d-134">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e73d-135"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-135"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-136">entero</span><span class="sxs-lookup"><span data-stu-id="7e73d-136">int</span></span></p></td>
<td><p><span data-ttu-id="7e73d-137">Externa</span><span class="sxs-lookup"><span data-stu-id="7e73d-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e73d-138">Número único que identifica a este usuario, al que se hace referencia en la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7e73d-138">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e73d-139"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-139"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-140">entero</span><span class="sxs-lookup"><span data-stu-id="7e73d-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7e73d-141">Si un usuario ha iniciado sesión en varios equipos o dispositivos a la vez, <strong>UserInstance</strong> se usa para identificar de forma única la combinación de usuario y dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7e73d-141">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e73d-142"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-142"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-143">bit</span><span class="sxs-lookup"><span data-stu-id="7e73d-143">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e73d-144">Si el usuario inició sesión de forma interna o no.</span><span class="sxs-lookup"><span data-stu-id="7e73d-144">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e73d-145"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-145"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-146">entero</span><span class="sxs-lookup"><span data-stu-id="7e73d-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e73d-147">El rol de este usuario en la Conferencia, como moderador o asistente.</span><span class="sxs-lookup"><span data-stu-id="7e73d-147">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e73d-148"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-148"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-149">datetime</span><span class="sxs-lookup"><span data-stu-id="7e73d-149">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e73d-150">Hora a la que este usuario se une a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e73d-150">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e73d-151"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-151"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-152">datetime</span><span class="sxs-lookup"><span data-stu-id="7e73d-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e73d-153">La hora a la que el usuario abandonó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e73d-153">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e73d-154"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-154"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-155">entero</span><span class="sxs-lookup"><span data-stu-id="7e73d-155">int</span></span></p></td>
<td><p><span data-ttu-id="7e73d-156">Externa</span><span class="sxs-lookup"><span data-stu-id="7e73d-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e73d-157">Versión del software cliente del usuario, a la que se hace referencia en la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7e73d-157">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e73d-158"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="7e73d-158"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e73d-159">Identificador</span><span class="sxs-lookup"><span data-stu-id="7e73d-159">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7e73d-160">Identificador único global (GUID) del extremo que se usa en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="7e73d-160">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="7e73d-161">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e73d-161">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

