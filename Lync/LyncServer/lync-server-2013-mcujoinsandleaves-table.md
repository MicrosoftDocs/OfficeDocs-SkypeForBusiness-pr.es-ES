---
title: 'Lync Server 2013: Tabla McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a936b6d6d9b371238873909646a146b94f659c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="41d82-102">Tabla McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41d82-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d82-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="41d82-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="41d82-104">Cada registro de esta tabla contiene detalles de la llamada acerca de una combinación de una Unión de usuario o de un servidor de conferencia y un servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="41d82-105">Por ejemplo, si un usuario se une a una conferencia que incluye conferencias web y elementos de audio/vídeo, se creará un registro para la combinación de conferencias por Internet de ese usuario y otro para la combinación de audio y videoconferencias del usuario.</span><span class="sxs-lookup"><span data-stu-id="41d82-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41d82-106">Columna</span><span class="sxs-lookup"><span data-stu-id="41d82-106">Column</span></span></th>
<th><span data-ttu-id="41d82-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="41d82-107">Data Type</span></span></th>
<th><span data-ttu-id="41d82-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="41d82-108">Key/Index</span></span></th>
<th><span data-ttu-id="41d82-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="41d82-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41d82-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-111">datetime</span><span class="sxs-lookup"><span data-stu-id="41d82-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="41d82-112">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="41d82-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d82-113">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-113">Time of conference instance.</span></span> <span data-ttu-id="41d82-114">Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="41d82-115">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="41d82-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d82-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-117">int</span><span class="sxs-lookup"><span data-stu-id="41d82-117">int</span></span></p></td>
<td><p><span data-ttu-id="41d82-118">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="41d82-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d82-119">Número de identificación para identificar la instancia de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="41d82-120">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma exclusiva una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="41d82-121">Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="41d82-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d82-122"><strong>Iddeusuario</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-123">int</span><span class="sxs-lookup"><span data-stu-id="41d82-123">int</span></span></p></td>
<td><p><span data-ttu-id="41d82-124">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="41d82-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d82-125">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="41d82-125">Unique number identifying this user.</span></span> <span data-ttu-id="41d82-126">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="41d82-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d82-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-128">int</span><span class="sxs-lookup"><span data-stu-id="41d82-128">int</span></span></p></td>
<td><p><span data-ttu-id="41d82-129">Primary</span><span class="sxs-lookup"><span data-stu-id="41d82-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="41d82-130">Si un usuario ha iniciado sesión en varios equipos o dispositivos a la vez, McuUserInstancerá de forma exclusiva la combinación de usuario y dispositivo.</span><span class="sxs-lookup"><span data-stu-id="41d82-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d82-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-132">bit</span><span class="sxs-lookup"><span data-stu-id="41d82-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="41d82-133">Si el usuario se une desde una RTC o no.</span><span class="sxs-lookup"><span data-stu-id="41d82-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d82-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-135">int</span><span class="sxs-lookup"><span data-stu-id="41d82-135">int</span></span></p></td>
<td><p><span data-ttu-id="41d82-136">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="41d82-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d82-137">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="41d82-138">Para obtener más información, consulte la <a href="lync-server-2013-mcus-table.md">tabla MCU en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="41d82-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d82-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-140">datetime</span><span class="sxs-lookup"><span data-stu-id="41d82-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="41d82-141">Extranjero</span><span class="sxs-lookup"><span data-stu-id="41d82-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d82-142">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="41d82-142">Time of session request.</span></span> <span data-ttu-id="41d82-143">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="41d82-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="41d82-144">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="41d82-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d82-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-146">int</span><span class="sxs-lookup"><span data-stu-id="41d82-146">int</span></span></p></td>
<td><p><span data-ttu-id="41d82-147">Extranjero</span><span class="sxs-lookup"><span data-stu-id="41d82-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d82-148">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="41d82-148">ID number to identify the session.</span></span> <span data-ttu-id="41d82-149">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="41d82-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="41d82-150">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="41d82-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d82-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-152">datetime</span><span class="sxs-lookup"><span data-stu-id="41d82-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="41d82-153">El momento en que este usuario se une a este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d82-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-155">datetime</span><span class="sxs-lookup"><span data-stu-id="41d82-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="41d82-156">Hora en que este usuario abandona este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d82-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="41d82-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="41d82-158">int</span><span class="sxs-lookup"><span data-stu-id="41d82-158">int</span></span></p></td>
<td><p><span data-ttu-id="41d82-159">Extranjero</span><span class="sxs-lookup"><span data-stu-id="41d82-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d82-160">Identificador que especifica el número de versión del uso de software de cliente en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="41d82-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="41d82-161">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="41d82-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="41d82-162">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41d82-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

