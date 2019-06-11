---
title: 'Lync Server 2013: enrutamiento basado en la ubicación y transferencias de llamadas Consultiva'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7c7b73efb670c5569b8c4600c1759e981cda211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="38ef6-102">Enrutamiento basado en la ubicación y transferencias de llamadas Consultiva en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38ef6-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38ef6-103">_**Última modificación del tema:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="38ef6-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="38ef6-104">Además de exigir el enrutamiento basado en la ubicación para las reuniones de Lync, la aplicación de conferencia de enrutamiento basada en la ubicación aplica restricciones de enrutamiento basadas en la ubicación en las transferencias de llamadas Consultiva que salida a puntos de conexión RTC.</span><span class="sxs-lookup"><span data-stu-id="38ef6-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="38ef6-105">Una transferencia de llamadas Consultiva es una llamada establecida entre dos partes cuando una de las partes la transfiere a un nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="38ef6-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="38ef6-106">Por ejemplo, un punto final de RTC llama al usuario A (llamada de Lync).</span><span class="sxs-lookup"><span data-stu-id="38ef6-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="38ef6-107">El usuario A determina que el usuario de RTC debe reenviarse al usuario B (usuario de Lync).</span><span class="sxs-lookup"><span data-stu-id="38ef6-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="38ef6-108">El usuario A coloca la llamada con el usuario de la RTC en espera y llama al usuario B. el usuario B acepta hablar con el usuario de la RTC.</span><span class="sxs-lookup"><span data-stu-id="38ef6-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="38ef6-109">El usuario A transfiere la llamada en espera al usuario B.</span><span class="sxs-lookup"><span data-stu-id="38ef6-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="38ef6-110">**Flujo de llamadas de transferencia de llamada de consulta**</span><span class="sxs-lookup"><span data-stu-id="38ef6-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="38ef6-111">![Enrutamiento basado en la ubicación del diagrama de conferencias] (images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Enrutamiento basado en la ubicación del diagrama de conferencias")</span><span class="sxs-lookup"><span data-stu-id="38ef6-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="38ef6-112">Cuando un usuario habilitado para el enrutamiento basado en la ubicación inicia una llamada Consultiva de un extremo RTC (tal como se muestra en la ilustración anterior), se crean dos llamadas activas, una llamada entre el usuario de la RTC y el usuario de Lync A y la otra entre el usuario de Lync A y el usuario B de Lync. el comportamiento siguiente es aplicado por la aplicación de conferencia de enrutamiento basada en ubicación:</span><span class="sxs-lookup"><span data-stu-id="38ef6-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="38ef6-113">Si el enrutamiento de troncal del SIP la llamada RTC está autorizada para redirigir la llamada RTC al sitio de red donde se encuentra el usuario de Lync B (es decir, el destino de transferencia), se permitirá la transferencia de llamadas; de lo contrario, la transferencia de llamadas Consultiva se bloqueará.</span><span class="sxs-lookup"><span data-stu-id="38ef6-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="38ef6-114">Esta autorización se realiza en función de si la ubicación de la entidad transferida es el mismo sitio de red que el tronco SIP que está redirigiendo la llamada activa al extremo de RTC.</span><span class="sxs-lookup"><span data-stu-id="38ef6-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="38ef6-115">Si el enrutamiento de troncal del SIP, la llamada RTC entrante no está autorizada para enrutar llamadas al sitio de red donde se encuentra la entidad transferida (usuario de Lync B) o la parte transferida se encuentra en un sitio de red desconocido y, después, la transferencia de la llamada consultiva a la RTC. se bloqueará el punto de conexión (es decir, el destino de transferencia de llamadas).</span><span class="sxs-lookup"><span data-stu-id="38ef6-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="38ef6-116">En la tabla siguiente se describe cómo aplica la aplicación de conferencia de enrutamiento basada en ubicación las restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="38ef6-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="38ef6-117">A pesar de que los extremos de PBX no están directamente asociados con un sitio de red, el tronco SIP al cual está conectado la PBX se puede asignar a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="38ef6-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="38ef6-118">Por lo tanto, el extremo de PBX se puede asociar indirectamente con el sitio de red.</span><span class="sxs-lookup"><span data-stu-id="38ef6-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38ef6-119">Sitio de red de la entidad de origen de la transferencia de la llamada</span><span class="sxs-lookup"><span data-stu-id="38ef6-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="38ef6-120">Sitio de red del destino de la transferencia de la llamada</span><span class="sxs-lookup"><span data-stu-id="38ef6-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="38ef6-121">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="38ef6-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ef6-122">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="38ef6-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38ef6-123">Usuario de Lync en el mismo sitio de red (es decir, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="38ef6-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="38ef6-124">Se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ef6-125">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="38ef6-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38ef6-126">Usuario de Lync en diferentes sitios de red (p. ej., sitio 2)</span><span class="sxs-lookup"><span data-stu-id="38ef6-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="38ef6-127">No se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ef6-128">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="38ef6-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38ef6-129">Usuario de Lync en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="38ef6-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="38ef6-130">No se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ef6-131">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="38ef6-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38ef6-132">Usuario federado de Lync</span><span class="sxs-lookup"><span data-stu-id="38ef6-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="38ef6-133">No se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ef6-134">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="38ef6-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38ef6-135">Extremo de PBX en el mismo sitio (es decir, el sitio 1)</span><span class="sxs-lookup"><span data-stu-id="38ef6-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="38ef6-136">Se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ef6-137">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="38ef6-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38ef6-138">Extremo de PBX en un sitio diferente (es decir, el sitio 2)</span><span class="sxs-lookup"><span data-stu-id="38ef6-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="38ef6-139">No se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ef6-140">Extremo de PBX en el mismo sitio (es decir, el sitio 1)</span><span class="sxs-lookup"><span data-stu-id="38ef6-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="38ef6-141">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="38ef6-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38ef6-142">Se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ef6-143">Extremo de PBX en un sitio diferente (es decir, el sitio 2)</span><span class="sxs-lookup"><span data-stu-id="38ef6-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="38ef6-144">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="38ef6-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="38ef6-145">No se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ef6-146">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="38ef6-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="38ef6-147">Usuario de Lync en el mismo sitio de red (es decir, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="38ef6-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="38ef6-148">Se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ef6-149">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="38ef6-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="38ef6-150">Usuario de Lync en diferentes sitios de red (p. ej., sitio 2)</span><span class="sxs-lookup"><span data-stu-id="38ef6-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="38ef6-151">Se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ef6-152">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="38ef6-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="38ef6-153">Usuario de Lync en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="38ef6-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="38ef6-154">Se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ef6-155">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="38ef6-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="38ef6-156">Usuario federado de Lync</span><span class="sxs-lookup"><span data-stu-id="38ef6-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="38ef6-157">Se permitirá la transferencia de consulta</span><span class="sxs-lookup"><span data-stu-id="38ef6-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

