---
title: 'Lync Server 2013: Tabla VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="291b0-102">Tabla VoipDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="291b0-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="291b0-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="291b0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="291b0-104">Cada registro representa una llamada de fiesta de 1 2 en la que al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="291b0-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="291b0-105">Columna</span><span class="sxs-lookup"><span data-stu-id="291b0-105">Column</span></span></th>
<th><span data-ttu-id="291b0-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="291b0-106">Data Type</span></span></th>
<th><span data-ttu-id="291b0-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="291b0-107">Key/Index</span></span></th>
<th><span data-ttu-id="291b0-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="291b0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="291b0-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="291b0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="291b0-111">Primary</span><span class="sxs-lookup"><span data-stu-id="291b0-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="291b0-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="291b0-112">Time of session request.</span></span> <span data-ttu-id="291b0-113">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="291b0-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="291b0-114">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="291b0-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-116">int</span><span class="sxs-lookup"><span data-stu-id="291b0-116">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-117">Primary</span><span class="sxs-lookup"><span data-stu-id="291b0-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="291b0-118">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="291b0-118">ID number to identify the session.</span></span> <span data-ttu-id="291b0-119">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="291b0-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="291b0-120">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="291b0-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-122">int</span><span class="sxs-lookup"><span data-stu-id="291b0-122">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-123">Extranjero</span><span class="sxs-lookup"><span data-stu-id="291b0-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="291b0-124"><strong>PhoneId</strong> de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="291b0-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="291b0-125">Para obtener más información, consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="291b0-126">Si no es NULL y <strong>FromGatewayId</strong> no es null, la persona que llama era un usuario de la RTC.</span><span class="sxs-lookup"><span data-stu-id="291b0-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="291b0-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-128">int</span><span class="sxs-lookup"><span data-stu-id="291b0-128">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-129">Extranjero</span><span class="sxs-lookup"><span data-stu-id="291b0-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="291b0-130"><strong>PhoneId</strong> del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="291b0-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="291b0-131">Para obtener más información, consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="291b0-132">Si no es NULL y <strong>ToGatewayId</strong> no es null, el receptor de la llamada fue un usuario de la RTC.</span><span class="sxs-lookup"><span data-stu-id="291b0-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="291b0-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-134">int</span><span class="sxs-lookup"><span data-stu-id="291b0-134">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-135">Extranjero</span><span class="sxs-lookup"><span data-stu-id="291b0-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="291b0-136">El servidor de mediación del que procede la llamada.</span><span class="sxs-lookup"><span data-stu-id="291b0-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="291b0-137">Para obtener más información, consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="291b0-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-139">int</span><span class="sxs-lookup"><span data-stu-id="291b0-139">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-140">Extranjero</span><span class="sxs-lookup"><span data-stu-id="291b0-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="291b0-141">El servidor de mediación llamado es el.</span><span class="sxs-lookup"><span data-stu-id="291b0-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="291b0-142">Para obtener más información, consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="291b0-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-144">int</span><span class="sxs-lookup"><span data-stu-id="291b0-144">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-145">Extranjero</span><span class="sxs-lookup"><span data-stu-id="291b0-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="291b0-146">Puerta de enlace de la cual procede la llamada.</span><span class="sxs-lookup"><span data-stu-id="291b0-146">Gateway the call is coming from.</span></span> <span data-ttu-id="291b0-147">Para obtener más información, consulte la <a href="lync-server-2013-gateways-table.md">tabla de puertas de enlace en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="291b0-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-149">int</span><span class="sxs-lookup"><span data-stu-id="291b0-149">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-150">Extranjero</span><span class="sxs-lookup"><span data-stu-id="291b0-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="291b0-151">Puerta de enlace a la que va la llamada.</span><span class="sxs-lookup"><span data-stu-id="291b0-151">Gateway the call is going to.</span></span> <span data-ttu-id="291b0-152">Para obtener más información, consulte la <a href="lync-server-2013-gateways-table.md">tabla de puertas de enlace en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="291b0-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-154">int</span><span class="sxs-lookup"><span data-stu-id="291b0-154">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-155">Extranjero</span><span class="sxs-lookup"><span data-stu-id="291b0-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="291b0-156">URI del usuario que desconectó la llamada, si el usuario tiene un URI.</span><span class="sxs-lookup"><span data-stu-id="291b0-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="291b0-157">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="291b0-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="291b0-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="291b0-159">int</span><span class="sxs-lookup"><span data-stu-id="291b0-159">int</span></span></p></td>
<td><p><span data-ttu-id="291b0-160">Extranjero</span><span class="sxs-lookup"><span data-stu-id="291b0-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="291b0-161">El identificador del teléfono que desconectó la llamada se desconectó de un teléfono.</span><span class="sxs-lookup"><span data-stu-id="291b0-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="291b0-162">Para obtener más información, consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="291b0-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

