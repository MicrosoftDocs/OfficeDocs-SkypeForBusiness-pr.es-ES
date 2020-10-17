---
title: 'Lync Server 2013: tabla McuJoinsAndLeaves'
description: 'Lync Server 2013: tabla McuJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556506"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="33e0b-103">Tabla McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33e0b-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33e0b-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="33e0b-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="33e0b-105">Cada registro de esta tabla contiene información detallada sobre una combinación de un usuario o un servidor de conferencia y un usuario que se haya incorporado o abandonado.</span><span class="sxs-lookup"><span data-stu-id="33e0b-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="33e0b-106">Por ejemplo, si un usuario se une a una conferencia que incluye elementos de conferencia web y audio/vídeo, se creará un registro para la Unión a conferencias web del usuario y se creará otro registro para la combinación de conferencia de audio y vídeo del usuario.</span><span class="sxs-lookup"><span data-stu-id="33e0b-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33e0b-107">Columna</span><span class="sxs-lookup"><span data-stu-id="33e0b-107">Column</span></span></th>
<th><span data-ttu-id="33e0b-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="33e0b-108">Data Type</span></span></th>
<th><span data-ttu-id="33e0b-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="33e0b-109">Key/Index</span></span></th>
<th><span data-ttu-id="33e0b-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="33e0b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33e0b-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="33e0b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="33e0b-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="33e0b-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="33e0b-114">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="33e0b-114">Time of conference instance.</span></span> <span data-ttu-id="33e0b-115">Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="33e0b-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="33e0b-116">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33e0b-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33e0b-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-118">entero</span><span class="sxs-lookup"><span data-stu-id="33e0b-118">int</span></span></p></td>
<td><p><span data-ttu-id="33e0b-119">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="33e0b-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="33e0b-120">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="33e0b-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="33e0b-121">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="33e0b-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="33e0b-122">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33e0b-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33e0b-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-124">entero</span><span class="sxs-lookup"><span data-stu-id="33e0b-124">int</span></span></p></td>
<td><p><span data-ttu-id="33e0b-125">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="33e0b-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="33e0b-126">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="33e0b-126">Unique number identifying this user.</span></span> <span data-ttu-id="33e0b-127">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33e0b-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33e0b-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-129">entero</span><span class="sxs-lookup"><span data-stu-id="33e0b-129">int</span></span></p></td>
<td><p><span data-ttu-id="33e0b-130">Principal</span><span class="sxs-lookup"><span data-stu-id="33e0b-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="33e0b-131">Si un usuario ha iniciado sesión en varios equipos o dispositivos a la vez, McuUserInstance identifica de forma única la combinación de usuario y dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33e0b-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33e0b-132"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-133">bit</span><span class="sxs-lookup"><span data-stu-id="33e0b-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="33e0b-134">Si el usuario se va a unir desde una RTC o no.</span><span class="sxs-lookup"><span data-stu-id="33e0b-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33e0b-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-136">entero</span><span class="sxs-lookup"><span data-stu-id="33e0b-136">int</span></span></p></td>
<td><p><span data-ttu-id="33e0b-137">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="33e0b-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="33e0b-138">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="33e0b-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="33e0b-139">Consulte la <a href="lync-server-2013-mcus-table.md">tabla MCU en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33e0b-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33e0b-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-141">datetime</span><span class="sxs-lookup"><span data-stu-id="33e0b-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="33e0b-142">Externa</span><span class="sxs-lookup"><span data-stu-id="33e0b-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="33e0b-143">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="33e0b-143">Time of session request.</span></span> <span data-ttu-id="33e0b-144">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="33e0b-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="33e0b-145">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33e0b-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33e0b-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-147">entero</span><span class="sxs-lookup"><span data-stu-id="33e0b-147">int</span></span></p></td>
<td><p><span data-ttu-id="33e0b-148">Externa</span><span class="sxs-lookup"><span data-stu-id="33e0b-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="33e0b-149">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="33e0b-149">ID number to identify the session.</span></span> <span data-ttu-id="33e0b-150">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="33e0b-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="33e0b-151">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33e0b-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33e0b-152"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-153">datetime</span><span class="sxs-lookup"><span data-stu-id="33e0b-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="33e0b-154">Hora a la que este usuario se une a este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="33e0b-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33e0b-155"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-156">datetime</span><span class="sxs-lookup"><span data-stu-id="33e0b-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="33e0b-157">Hora a la que este usuario abandonó este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="33e0b-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33e0b-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="33e0b-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="33e0b-159">entero</span><span class="sxs-lookup"><span data-stu-id="33e0b-159">int</span></span></p></td>
<td><p><span data-ttu-id="33e0b-160">Externa</span><span class="sxs-lookup"><span data-stu-id="33e0b-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="33e0b-161">Identificador que especifica el número de versión del uso de software de cliente en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="33e0b-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="33e0b-162">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33e0b-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="33e0b-163">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33e0b-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

