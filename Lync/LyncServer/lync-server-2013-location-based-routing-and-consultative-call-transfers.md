---
title: 'Lync Server 2013: transferencias de llamadas de consultoría y enrutamiento de Location-Based'
description: 'Lync Server 2013: transferencias de llamadas de consultoría y enrutamiento de Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567676"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="d1895-103">Location-Based el enrutamiento y las transferencias de llamadas de asesoría en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1895-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1895-104">_**Última modificación del tema:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="d1895-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="d1895-105">Además de imponer el enrutamiento de Location-Based a las reuniones de Lync, la aplicación de conferencia de enrutamiento de Location-Based aplica Location-Based restricciones de enrutamiento en las transferencias de llamadas de consultoría que se transfieren a los extremos de RTC.</span><span class="sxs-lookup"><span data-stu-id="d1895-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="d1895-106">Una transferencia de llamada Consultiva es una llamada establecida entre dos partes en la que una de las partes transfiere la llamada a un nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="d1895-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="d1895-107">Por ejemplo, un punto de conexión RTC llama al usuario A (llamado de Lync).</span><span class="sxs-lookup"><span data-stu-id="d1895-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="d1895-108">El usuario A determina el usuario de RTC que se debe reenviar al usuario B (usuario de Lync).</span><span class="sxs-lookup"><span data-stu-id="d1895-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="d1895-109">El usuario A realiza la llamada con el usuario RTC en espera y llama al usuario B. el usuario B acuerda hablar con el usuario RTC.</span><span class="sxs-lookup"><span data-stu-id="d1895-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="d1895-110">El usuario A transfiere la llamada en espera al usuario B.</span><span class="sxs-lookup"><span data-stu-id="d1895-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="d1895-111">**Flujo de llamada de transferencia de llamada Consultiva**</span><span class="sxs-lookup"><span data-stu-id="d1895-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="d1895-112">![Enrutamiento basado en ubicación para diagrama de conferencia](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Enrutamiento basado en ubicación para diagrama de conferencia")</span><span class="sxs-lookup"><span data-stu-id="d1895-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="d1895-113">Cuando un usuario habilitado para el enrutamiento de Location-Based inicia una transferencia de llamada Consultiva de un extremo de RTC (tal como se muestra en la figura anterior), se crean dos llamadas activas, una llamada entre el usuario de RTC y el usuario de Lync A y la otra entre el usuario de Lync A y el usuario B de Lync. el comportamiento de la aplicación de conferencia de enrutamiento de Location-Based:</span><span class="sxs-lookup"><span data-stu-id="d1895-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="d1895-114">Si el enrutamiento de tronco SIP la llamada RTC está autorizada para redirigir la llamada RTC al sitio de red donde se encuentra el usuario B de Lync (por ejemplo, el destino de transferencia), se permitirá la transferencia de llamadas; de lo contrario, se bloqueará la transferencia de la llamada Consultiva.</span><span class="sxs-lookup"><span data-stu-id="d1895-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="d1895-115">Esta autorización se realiza en función de la ubicación de la entidad transferida que se encuentra en el mismo sitio de red que el tronco SIP que enruta la llamada activa al punto de conexión de RTC.</span><span class="sxs-lookup"><span data-stu-id="d1895-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="d1895-116">Si el enrutamiento de tronco SIP la llamada RTC entrante no está autorizada para enrutar llamadas al sitio de red en el que se encuentra la entidad de transferencia (usuario de Lync B) o la entidad transferida se encuentra en un sitio de red desconocido, se bloqueará la transferencia de la llamada Consultiva al punto de conexión de RTC (por ejemplo, el destino de transferencia de llamadas).</span><span class="sxs-lookup"><span data-stu-id="d1895-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="d1895-117">En la tabla siguiente se describe cómo se aplican las restricciones de enrutamiento de Location-Based por la aplicación de conferencia de Location-Based enrutamiento para las transferencias de llamadas de consultoría.</span><span class="sxs-lookup"><span data-stu-id="d1895-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="d1895-118">Aunque los extremos de PBX no están directamente asociados a un sitio de red, el tronco SIP al que se conecta la PBX se puede asignar a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="d1895-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="d1895-119">Por lo tanto, el extremo de PBX se puede asociar indirectamente con un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="d1895-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1895-120">Sitio de red de la persona que ha transferido la llamada</span><span class="sxs-lookup"><span data-stu-id="d1895-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="d1895-121">Sitio de red del destino de transferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="d1895-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="d1895-122">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="d1895-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1895-123">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1895-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1895-124">Usuario de Lync en el mismo sitio de red (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="d1895-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="d1895-125">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="d1895-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1895-126">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1895-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1895-127">Usuario de Lync en sitios de red diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="d1895-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="d1895-128">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="d1895-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1895-129">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1895-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1895-130">Usuario de Lync en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="d1895-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="d1895-131">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="d1895-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1895-132">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1895-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1895-133">Usuario de Lync federado</span><span class="sxs-lookup"><span data-stu-id="d1895-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="d1895-134">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="d1895-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1895-135">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1895-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1895-136">Extremo de PBX en el mismo sitio (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="d1895-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="d1895-137">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="d1895-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1895-138">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1895-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1895-139">Extremo de PBX en sitios diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="d1895-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="d1895-140">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="d1895-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1895-141">Extremo de PBX en el mismo sitio (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="d1895-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="d1895-142">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1895-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1895-143">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="d1895-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1895-144">Extremo de PBX en un sitio diferente (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="d1895-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="d1895-145">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1895-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1895-146">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="d1895-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1895-147">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="d1895-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="d1895-148">Usuario de Lync en el mismo sitio de red (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="d1895-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="d1895-149">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="d1895-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1895-150">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="d1895-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="d1895-151">Usuario de Lync en sitios de red diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="d1895-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="d1895-152">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="d1895-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1895-153">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="d1895-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="d1895-154">Usuario de Lync en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="d1895-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="d1895-155">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="d1895-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1895-156">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="d1895-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="d1895-157">Usuario de Lync federado</span><span class="sxs-lookup"><span data-stu-id="d1895-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="d1895-158">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="d1895-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

