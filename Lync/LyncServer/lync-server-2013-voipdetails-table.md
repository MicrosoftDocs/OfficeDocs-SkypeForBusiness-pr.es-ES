---
title: 'Lync Server 2013: tabla VoipDetails'
description: 'Lync Server 2013: tabla VoipDetails.'
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566286"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="51457-103">Tabla VoipDetails en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51457-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51457-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="51457-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="51457-105">Cada registro representa una llamada de 1 2-Party en la que al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="51457-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51457-106">Columna</span><span class="sxs-lookup"><span data-stu-id="51457-106">Column</span></span></th>
<th><span data-ttu-id="51457-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="51457-107">Data Type</span></span></th>
<th><span data-ttu-id="51457-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="51457-108">Key/Index</span></span></th>
<th><span data-ttu-id="51457-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="51457-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51457-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="51457-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-111">datetime</span><span class="sxs-lookup"><span data-stu-id="51457-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="51457-112">Principal</span><span class="sxs-lookup"><span data-stu-id="51457-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="51457-113">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="51457-113">Time of session request.</span></span> <span data-ttu-id="51457-114">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="51457-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="51457-115">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51457-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="51457-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-117">entero</span><span class="sxs-lookup"><span data-stu-id="51457-117">int</span></span></p></td>
<td><p><span data-ttu-id="51457-118">Principal</span><span class="sxs-lookup"><span data-stu-id="51457-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="51457-119">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="51457-119">ID number to identify the session.</span></span> <span data-ttu-id="51457-120">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="51457-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="51457-121">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51457-122"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="51457-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-123">entero</span><span class="sxs-lookup"><span data-stu-id="51457-123">int</span></span></p></td>
<td><p><span data-ttu-id="51457-124">Externa</span><span class="sxs-lookup"><span data-stu-id="51457-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51457-125"><strong>PhoneId</strong> del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="51457-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="51457-126">Consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="51457-127">Si no es NULL y <strong>FromGatewayId</strong> no es null, el autor de la llamada era un usuario de RTC.</span><span class="sxs-lookup"><span data-stu-id="51457-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51457-128"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="51457-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-129">entero</span><span class="sxs-lookup"><span data-stu-id="51457-129">int</span></span></p></td>
<td><p><span data-ttu-id="51457-130">Externa</span><span class="sxs-lookup"><span data-stu-id="51457-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51457-131"><strong>PhoneId</strong> del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="51457-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="51457-132">Consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="51457-133">Si no es NULL y <strong>ToGatewayId</strong> no es null, el receptor de la llamada fue un usuario de RTC.</span><span class="sxs-lookup"><span data-stu-id="51457-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51457-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="51457-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-135">entero</span><span class="sxs-lookup"><span data-stu-id="51457-135">int</span></span></p></td>
<td><p><span data-ttu-id="51457-136">Externa</span><span class="sxs-lookup"><span data-stu-id="51457-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51457-137">El servidor de mediación del que procede la llamada.</span><span class="sxs-lookup"><span data-stu-id="51457-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="51457-138">Consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51457-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="51457-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-140">entero</span><span class="sxs-lookup"><span data-stu-id="51457-140">int</span></span></p></td>
<td><p><span data-ttu-id="51457-141">Externa</span><span class="sxs-lookup"><span data-stu-id="51457-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51457-142">El servidor de mediación al que se llama se dirige a.</span><span class="sxs-lookup"><span data-stu-id="51457-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="51457-143">Consulte la <a href="lync-server-2013-mediationservers-table.md">tabla MediationServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51457-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="51457-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-145">entero</span><span class="sxs-lookup"><span data-stu-id="51457-145">int</span></span></p></td>
<td><p><span data-ttu-id="51457-146">Externa</span><span class="sxs-lookup"><span data-stu-id="51457-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51457-147">Puerta de enlace desde la que procede la llamada.</span><span class="sxs-lookup"><span data-stu-id="51457-147">Gateway the call is coming from.</span></span> <span data-ttu-id="51457-148">Consulte la <a href="lync-server-2013-gateways-table.md">tabla puertas de enlace en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51457-149"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="51457-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-150">entero</span><span class="sxs-lookup"><span data-stu-id="51457-150">int</span></span></p></td>
<td><p><span data-ttu-id="51457-151">Externa</span><span class="sxs-lookup"><span data-stu-id="51457-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51457-152">Puerta de enlace a la que va a llamar.</span><span class="sxs-lookup"><span data-stu-id="51457-152">Gateway the call is going to.</span></span> <span data-ttu-id="51457-153">Consulte la <a href="lync-server-2013-gateways-table.md">tabla puertas de enlace en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51457-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="51457-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-155">entero</span><span class="sxs-lookup"><span data-stu-id="51457-155">int</span></span></p></td>
<td><p><span data-ttu-id="51457-156">Externa</span><span class="sxs-lookup"><span data-stu-id="51457-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51457-157">URI del usuario que ha desconectado la llamada, si el usuario tiene un URI.</span><span class="sxs-lookup"><span data-stu-id="51457-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="51457-158">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51457-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="51457-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="51457-160">entero</span><span class="sxs-lookup"><span data-stu-id="51457-160">int</span></span></p></td>
<td><p><span data-ttu-id="51457-161">Externa</span><span class="sxs-lookup"><span data-stu-id="51457-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51457-162">IDENTIFICADOR del teléfono que desconectó la llamada se desconectó de un teléfono.</span><span class="sxs-lookup"><span data-stu-id="51457-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="51457-163">Consulte la <a href="lync-server-2013-phones-table.md">tabla teléfonos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51457-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

