---
title: 'Lync Server 2013: tabla McuJoinsAndLeaves'
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
ms.openlocfilehash: ae21b9a8ec2107d8a2bd0a99f1e21d6f182a830e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="2f623-102">Tabla McuJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f623-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f623-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2f623-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2f623-104">Cada registro de esta tabla contiene información detallada sobre una combinación de un usuario o un servidor de conferencia y un usuario que se haya incorporado o abandonado.</span><span class="sxs-lookup"><span data-stu-id="2f623-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="2f623-105">Por ejemplo, si un usuario se une a una conferencia que incluye elementos de conferencia web y audio/vídeo, se creará un registro para la Unión a conferencias web del usuario y se creará otro registro para la combinación de conferencia de audio y vídeo del usuario.</span><span class="sxs-lookup"><span data-stu-id="2f623-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f623-106">Columna</span><span class="sxs-lookup"><span data-stu-id="2f623-106">Column</span></span></th>
<th><span data-ttu-id="2f623-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2f623-107">Data Type</span></span></th>
<th><span data-ttu-id="2f623-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="2f623-108">Key/Index</span></span></th>
<th><span data-ttu-id="2f623-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="2f623-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f623-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-111">datetime</span><span class="sxs-lookup"><span data-stu-id="2f623-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2f623-112">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="2f623-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2f623-113">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f623-113">Time of conference instance.</span></span> <span data-ttu-id="2f623-114">Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f623-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="2f623-115">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f623-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f623-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-117">int</span><span class="sxs-lookup"><span data-stu-id="2f623-117">int</span></span></p></td>
<td><p><span data-ttu-id="2f623-118">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="2f623-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2f623-119">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f623-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="2f623-120">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f623-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="2f623-121">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f623-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f623-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-123">int</span><span class="sxs-lookup"><span data-stu-id="2f623-123">int</span></span></p></td>
<td><p><span data-ttu-id="2f623-124">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="2f623-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2f623-125">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="2f623-125">Unique number identifying this user.</span></span> <span data-ttu-id="2f623-126">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f623-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f623-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-128">int</span><span class="sxs-lookup"><span data-stu-id="2f623-128">int</span></span></p></td>
<td><p><span data-ttu-id="2f623-129">Principal</span><span class="sxs-lookup"><span data-stu-id="2f623-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="2f623-130">Si un usuario ha iniciado sesión en varios equipos o dispositivos a la vez, McuUserInstance identifica de forma única la combinación de usuario y dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f623-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f623-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-132">bit</span><span class="sxs-lookup"><span data-stu-id="2f623-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2f623-133">Si el usuario se va a unir desde una RTC o no.</span><span class="sxs-lookup"><span data-stu-id="2f623-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f623-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-135">int</span><span class="sxs-lookup"><span data-stu-id="2f623-135">int</span></span></p></td>
<td><p><span data-ttu-id="2f623-136">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="2f623-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2f623-137">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f623-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="2f623-138">Consulte la <a href="lync-server-2013-mcus-table.md">tabla MCU en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f623-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f623-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-140">datetime</span><span class="sxs-lookup"><span data-stu-id="2f623-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="2f623-141">Externa</span><span class="sxs-lookup"><span data-stu-id="2f623-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2f623-142">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="2f623-142">Time of session request.</span></span> <span data-ttu-id="2f623-143">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="2f623-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2f623-144">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f623-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f623-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-146">int</span><span class="sxs-lookup"><span data-stu-id="2f623-146">int</span></span></p></td>
<td><p><span data-ttu-id="2f623-147">Externa</span><span class="sxs-lookup"><span data-stu-id="2f623-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2f623-148">Número con el que se identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="2f623-148">ID number to identify the session.</span></span> <span data-ttu-id="2f623-149">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="2f623-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2f623-150">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f623-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f623-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-152">datetime</span><span class="sxs-lookup"><span data-stu-id="2f623-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2f623-153">Hora a la que este usuario se une a este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f623-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f623-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-155">datetime</span><span class="sxs-lookup"><span data-stu-id="2f623-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2f623-156">Hora a la que este usuario abandonó este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f623-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f623-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="2f623-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2f623-158">int</span><span class="sxs-lookup"><span data-stu-id="2f623-158">int</span></span></p></td>
<td><p><span data-ttu-id="2f623-159">Externa</span><span class="sxs-lookup"><span data-stu-id="2f623-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2f623-160">Identificador que especifica el número de versión del uso de software de cliente en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f623-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="2f623-161">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f623-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2f623-162">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f623-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

