---
title: 'Lync Server 2013: tabla FocusJoinsAndLeaves'
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
ms.openlocfilehash: 9f7691a008dae1fc822b6632a60f5324bb4e80fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500837"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="a3d09-102">Tabla FocusJoinsAndLeaves en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3d09-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3d09-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a3d09-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a3d09-104">Cada registro de esta tabla contiene la información de CDR sobre la Unión de un usuario y deja la información de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d09-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="a3d09-105">Cada conferencia se representa en esta tabla mediante un registro cada vez que un usuario se une a la Conferencia y la abandona.</span><span class="sxs-lookup"><span data-stu-id="a3d09-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3d09-106">Columna</span><span class="sxs-lookup"><span data-stu-id="a3d09-106">Column</span></span></th>
<th><span data-ttu-id="a3d09-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a3d09-107">Data Type</span></span></th>
<th><span data-ttu-id="a3d09-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="a3d09-108">Key/Index</span></span></th>
<th><span data-ttu-id="a3d09-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="a3d09-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3d09-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a3d09-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a3d09-112">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="a3d09-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3d09-113">Hora de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d09-113">Time of conference instance.</span></span> <span data-ttu-id="a3d09-114">Se usa junto con <strong>SessionIdSeq</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d09-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="a3d09-115">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3d09-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3d09-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-117">entero</span><span class="sxs-lookup"><span data-stu-id="a3d09-117">int</span></span></p></td>
<td><p><span data-ttu-id="a3d09-118">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="a3d09-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3d09-119">Número de identificación de la instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d09-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="a3d09-120">Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d09-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="a3d09-121">Consulte la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3d09-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3d09-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-123">datetime</span><span class="sxs-lookup"><span data-stu-id="a3d09-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="a3d09-124">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="a3d09-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3d09-125">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="a3d09-125">Time of session request.</span></span> <span data-ttu-id="a3d09-126">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a3d09-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a3d09-127">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3d09-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3d09-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-129">entero</span><span class="sxs-lookup"><span data-stu-id="a3d09-129">int</span></span></p></td>
<td><p><span data-ttu-id="a3d09-130">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="a3d09-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3d09-131">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="a3d09-131">ID number to identify the session.</span></span> <span data-ttu-id="a3d09-132">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="a3d09-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a3d09-133">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3d09-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3d09-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-135">entero</span><span class="sxs-lookup"><span data-stu-id="a3d09-135">int</span></span></p></td>
<td><p><span data-ttu-id="a3d09-136">Externa</span><span class="sxs-lookup"><span data-stu-id="a3d09-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3d09-137">Número único que identifica a este usuario, al que se hace referencia en la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a3d09-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3d09-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-139">entero</span><span class="sxs-lookup"><span data-stu-id="a3d09-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3d09-140">Si un usuario ha iniciado sesión en varios equipos o dispositivos a la vez, <strong>UserInstance</strong> se usa para identificar de forma única la combinación de usuario y dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3d09-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3d09-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-142">bit</span><span class="sxs-lookup"><span data-stu-id="a3d09-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a3d09-143">Si el usuario inició sesión de forma interna o no.</span><span class="sxs-lookup"><span data-stu-id="a3d09-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3d09-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-145">entero</span><span class="sxs-lookup"><span data-stu-id="a3d09-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a3d09-146">El rol de este usuario en la Conferencia, como moderador o asistente.</span><span class="sxs-lookup"><span data-stu-id="a3d09-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3d09-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-148">datetime</span><span class="sxs-lookup"><span data-stu-id="a3d09-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a3d09-149">Hora a la que este usuario se une a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d09-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3d09-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-151">datetime</span><span class="sxs-lookup"><span data-stu-id="a3d09-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a3d09-152">La hora a la que el usuario abandonó la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d09-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3d09-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-154">entero</span><span class="sxs-lookup"><span data-stu-id="a3d09-154">int</span></span></p></td>
<td><p><span data-ttu-id="a3d09-155">Externa</span><span class="sxs-lookup"><span data-stu-id="a3d09-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3d09-156">Versión del software cliente del usuario, a la que se hace referencia en la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a3d09-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3d09-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a3d09-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3d09-158">Identificador</span><span class="sxs-lookup"><span data-stu-id="a3d09-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3d09-159">Identificador único global (GUID) del extremo que se usa en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3d09-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="a3d09-160">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3d09-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

