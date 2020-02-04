---
title: 'Lync Server 2013: Tabla VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="8b449-102">Tabla VoipDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b449-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b449-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8b449-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8b449-104">Cada registro representa una llamada de fiesta de 1 2 en la que al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="8b449-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b449-105">Columna</span><span class="sxs-lookup"><span data-stu-id="8b449-105">Column</span></span></th>
<th><span data-ttu-id="8b449-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8b449-106">Data Type</span></span></th>
<th><span data-ttu-id="8b449-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="8b449-107">Key/Index</span></span></th>
<th><span data-ttu-id="8b449-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="8b449-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b449-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8b449-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="8b449-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8b449-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="8b449-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="8b449-112">Time of session request.</span></span> <span data-ttu-id="8b449-113">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="8b449-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8b449-114">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b449-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-116">int</span><span class="sxs-lookup"><span data-stu-id="8b449-116">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-117">Primary</span><span class="sxs-lookup"><span data-stu-id="8b449-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="8b449-118">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="8b449-118">ID number to identify the session.</span></span> <span data-ttu-id="8b449-119">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="8b449-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8b449-120">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b449-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-122">int</span><span class="sxs-lookup"><span data-stu-id="8b449-122">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-123">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8b449-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8b449-124"><strong>PhoneId</strong> de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="8b449-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="8b449-125">Para obtener más información, consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="8b449-126">Si no es NULL y <strong>FromGatewayId</strong> no es null, la persona que llama era un usuario de la RTC.</span><span class="sxs-lookup"><span data-stu-id="8b449-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b449-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-128">int</span><span class="sxs-lookup"><span data-stu-id="8b449-128">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-129">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8b449-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8b449-130"><strong>PhoneId</strong> del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8b449-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="8b449-131">Para obtener más información, consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="8b449-132">Si no es NULL y <strong>ToGatewayId</strong> no es null, el receptor de la llamada fue un usuario de la RTC.</span><span class="sxs-lookup"><span data-stu-id="8b449-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b449-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-134">int</span><span class="sxs-lookup"><span data-stu-id="8b449-134">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-135">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8b449-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8b449-136">El servidor de mediación del que procede la llamada.</span><span class="sxs-lookup"><span data-stu-id="8b449-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="8b449-137">Para obtener más información, consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b449-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-139">int</span><span class="sxs-lookup"><span data-stu-id="8b449-139">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-140">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8b449-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8b449-141">El servidor de mediación llamado es el.</span><span class="sxs-lookup"><span data-stu-id="8b449-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="8b449-142">Para obtener más información, consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b449-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-144">int</span><span class="sxs-lookup"><span data-stu-id="8b449-144">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-145">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8b449-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8b449-146">Puerta de enlace de la cual procede la llamada.</span><span class="sxs-lookup"><span data-stu-id="8b449-146">Gateway the call is coming from.</span></span> <span data-ttu-id="8b449-147">Para obtener más información, consulte la <a href="lync-server-2013-gateways-table.md">tabla de puertas de enlace en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b449-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-149">int</span><span class="sxs-lookup"><span data-stu-id="8b449-149">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-150">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8b449-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8b449-151">Puerta de enlace a la que va la llamada.</span><span class="sxs-lookup"><span data-stu-id="8b449-151">Gateway the call is going to.</span></span> <span data-ttu-id="8b449-152">Para obtener más información, consulte la <a href="lync-server-2013-gateways-table.md">tabla de puertas de enlace en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b449-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-154">int</span><span class="sxs-lookup"><span data-stu-id="8b449-154">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-155">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8b449-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8b449-156">URI del usuario que desconectó la llamada, si el usuario tiene un URI.</span><span class="sxs-lookup"><span data-stu-id="8b449-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="8b449-157">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b449-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="8b449-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="8b449-159">int</span><span class="sxs-lookup"><span data-stu-id="8b449-159">int</span></span></p></td>
<td><p><span data-ttu-id="8b449-160">Extranjero</span><span class="sxs-lookup"><span data-stu-id="8b449-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8b449-161">El identificador del teléfono que desconectó la llamada se desconectó de un teléfono.</span><span class="sxs-lookup"><span data-stu-id="8b449-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="8b449-162">Para obtener más información, consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8b449-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

