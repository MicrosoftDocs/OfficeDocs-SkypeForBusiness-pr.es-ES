---
title: 'Lync Server 2013: tabla VoipDetails'
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
ms.openlocfilehash: 26feac5b9995aa1a8444029442adcb9c935083d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535417"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="f75ca-102">Tabla VoipDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f75ca-102">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f75ca-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f75ca-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f75ca-104">Cada registro representa una llamada de 1 2-Party en la que al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="f75ca-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f75ca-105">Columna</span><span class="sxs-lookup"><span data-stu-id="f75ca-105">Column</span></span></th>
<th><span data-ttu-id="f75ca-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f75ca-106">Data Type</span></span></th>
<th><span data-ttu-id="f75ca-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="f75ca-107">Key/Index</span></span></th>
<th><span data-ttu-id="f75ca-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="f75ca-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f75ca-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f75ca-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f75ca-111">Principal</span><span class="sxs-lookup"><span data-stu-id="f75ca-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="f75ca-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="f75ca-112">Time of session request.</span></span> <span data-ttu-id="f75ca-113">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="f75ca-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f75ca-114">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f75ca-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-116">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-116">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-117">Principal</span><span class="sxs-lookup"><span data-stu-id="f75ca-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f75ca-118">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="f75ca-118">ID number to identify the session.</span></span> <span data-ttu-id="f75ca-119">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="f75ca-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f75ca-120">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f75ca-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-122">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-122">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-123">Externa</span><span class="sxs-lookup"><span data-stu-id="f75ca-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f75ca-124"><strong>PhoneId</strong> del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f75ca-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="f75ca-125">Consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f75ca-126">Si no es NULL y <strong>FromGatewayId</strong> no es null, el autor de la llamada era un usuario de RTC.</span><span class="sxs-lookup"><span data-stu-id="f75ca-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f75ca-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-128">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-128">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-129">Externa</span><span class="sxs-lookup"><span data-stu-id="f75ca-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f75ca-130"><strong>PhoneId</strong> del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f75ca-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="f75ca-131">Consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="f75ca-132">Si no es NULL y <strong>ToGatewayId</strong> no es null, el receptor de la llamada fue un usuario de RTC.</span><span class="sxs-lookup"><span data-stu-id="f75ca-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f75ca-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-134">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-134">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-135">Externa</span><span class="sxs-lookup"><span data-stu-id="f75ca-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f75ca-136">El servidor de mediación del que procede la llamada.</span><span class="sxs-lookup"><span data-stu-id="f75ca-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="f75ca-137">Consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f75ca-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-139">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-139">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-140">Externa</span><span class="sxs-lookup"><span data-stu-id="f75ca-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f75ca-141">El servidor de mediación al que se llama se dirige a.</span><span class="sxs-lookup"><span data-stu-id="f75ca-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="f75ca-142">Consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f75ca-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-144">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-144">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-145">Externa</span><span class="sxs-lookup"><span data-stu-id="f75ca-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f75ca-146">Puerta de enlace desde la que procede la llamada.</span><span class="sxs-lookup"><span data-stu-id="f75ca-146">Gateway the call is coming from.</span></span> <span data-ttu-id="f75ca-147">Consulte la <a href="lync-server-2013-gateways-table.md">tabla puertas de enlace en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f75ca-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-149">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-149">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-150">Externa</span><span class="sxs-lookup"><span data-stu-id="f75ca-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f75ca-151">Puerta de enlace a la que va a llamar.</span><span class="sxs-lookup"><span data-stu-id="f75ca-151">Gateway the call is going to.</span></span> <span data-ttu-id="f75ca-152">Consulte la <a href="lync-server-2013-gateways-table.md">tabla puertas de enlace en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f75ca-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-154">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-154">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-155">Externa</span><span class="sxs-lookup"><span data-stu-id="f75ca-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f75ca-156">URI del usuario que ha desconectado la llamada, si el usuario tiene un URI.</span><span class="sxs-lookup"><span data-stu-id="f75ca-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="f75ca-157">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f75ca-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="f75ca-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="f75ca-159">entero</span><span class="sxs-lookup"><span data-stu-id="f75ca-159">int</span></span></p></td>
<td><p><span data-ttu-id="f75ca-160">Externa</span><span class="sxs-lookup"><span data-stu-id="f75ca-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f75ca-161">IDENTIFICADOR del teléfono que desconectó la llamada se desconectó de un teléfono.</span><span class="sxs-lookup"><span data-stu-id="f75ca-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="f75ca-162">Consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f75ca-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

