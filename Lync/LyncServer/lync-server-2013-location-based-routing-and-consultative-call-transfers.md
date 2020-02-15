---
title: 'Lync Server 2013: enrutamiento basado en ubicación y transferencias de llamadas de asesoría'
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
ms.openlocfilehash: a72ddbba79bf0de777c8567164475ab573d09a2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="c3498-102">Enrutamiento basado en ubicación y transferencias de llamadas de asesoría en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3498-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3498-103">_**Última modificación del tema:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="c3498-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="c3498-104">Además de aplicar el enrutamiento basado en ubicación a las reuniones de Lync, la aplicación de conferencia de enrutamiento basada en ubicación aplica las restricciones de enrutamiento basadas en ubicación en las transferencias de llamadas de consulta que se transfieren a los extremos de RTC.</span><span class="sxs-lookup"><span data-stu-id="c3498-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="c3498-105">Una transferencia de llamada Consultiva es una llamada establecida entre dos partes en la que una de las partes transfiere la llamada a un nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="c3498-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="c3498-106">Por ejemplo, un punto de conexión RTC llama al usuario A (llamado de Lync).</span><span class="sxs-lookup"><span data-stu-id="c3498-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="c3498-107">El usuario A determina el usuario de RTC que se debe reenviar al usuario B (usuario de Lync).</span><span class="sxs-lookup"><span data-stu-id="c3498-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="c3498-108">El usuario A realiza la llamada con el usuario RTC en espera y llama al usuario B. el usuario B acuerda hablar con el usuario RTC.</span><span class="sxs-lookup"><span data-stu-id="c3498-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="c3498-109">El usuario A transfiere la llamada en espera al usuario B.</span><span class="sxs-lookup"><span data-stu-id="c3498-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="c3498-110">**Flujo de llamada de transferencia de llamada Consultiva**</span><span class="sxs-lookup"><span data-stu-id="c3498-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="c3498-111">![Enrutamiento basado en ubicación para diagrama de conferencia](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Enrutamiento basado en ubicación para diagrama de conferencia")</span><span class="sxs-lookup"><span data-stu-id="c3498-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="c3498-112">Cuando un usuario habilitado para el enrutamiento basado en ubicación inicia una transferencia de llamada Consultiva de un extremo de RTC (como se muestra en la figura anterior), se crean dos llamadas activas, una llamada entre el usuario de RTC y el usuario de Lync A, y la otra entre el usuario de Lync A y el usuario B de Lync. la aplicación de conferencia de enrutamiento basada en ubicación aplica el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="c3498-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="c3498-113">Si el enrutamiento de tronco SIP la llamada RTC está autorizada para redirigir la llamada RTC al sitio de red donde se encuentra el usuario B de Lync (por ejemplo, el destino de transferencia), se permitirá la transferencia de llamadas; de lo contrario, se bloqueará la transferencia de la llamada Consultiva.</span><span class="sxs-lookup"><span data-stu-id="c3498-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="c3498-114">Esta autorización se realiza en función de la ubicación de la entidad transferida que se encuentra en el mismo sitio de red que el tronco SIP que enruta la llamada activa al punto de conexión de RTC.</span><span class="sxs-lookup"><span data-stu-id="c3498-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="c3498-115">Si el enrutamiento de tronco SIP, la llamada RTC entrante no está autorizada para enrutar llamadas al sitio de red donde se encuentra la entidad de transferencia (usuario de Lync B) o la entidad transferida se encuentra en un sitio de red desconocido y, a continuación, la transferencia de la llamada consultiva a la RTC. se bloqueará el punto de conexión (por ejemplo, el destino de transferencia de llamadas).</span><span class="sxs-lookup"><span data-stu-id="c3498-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="c3498-116">En la tabla siguiente se describe el modo en que la aplicación de conferencia de enrutamiento basada en ubicación aplica las restricciones de enrutamiento basadas en ubicación para las transferencias de llamadas de consultoría.</span><span class="sxs-lookup"><span data-stu-id="c3498-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="c3498-117">Aunque los extremos de PBX no están directamente asociados a un sitio de red, el tronco SIP al que se conecta la PBX se puede asignar a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="c3498-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="c3498-118">Por lo tanto, el extremo de PBX se puede asociar indirectamente con un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="c3498-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3498-119">Sitio de red de la persona que ha transferido la llamada</span><span class="sxs-lookup"><span data-stu-id="c3498-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="c3498-120">Sitio de red del destino de transferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="c3498-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="c3498-121">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="c3498-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3498-122">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="c3498-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c3498-123">Usuario de Lync en el mismo sitio de red (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="c3498-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c3498-124">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="c3498-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3498-125">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="c3498-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c3498-126">Usuario de Lync en sitios de red diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="c3498-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c3498-127">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="c3498-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3498-128">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="c3498-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c3498-129">Usuario de Lync en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="c3498-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="c3498-130">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="c3498-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3498-131">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="c3498-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c3498-132">Usuario de Lync federado</span><span class="sxs-lookup"><span data-stu-id="c3498-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="c3498-133">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="c3498-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3498-134">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="c3498-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c3498-135">Extremo de PBX en el mismo sitio (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="c3498-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c3498-136">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="c3498-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3498-137">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="c3498-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c3498-138">Extremo de PBX en sitios diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="c3498-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c3498-139">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="c3498-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3498-140">Extremo de PBX en el mismo sitio (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="c3498-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c3498-141">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="c3498-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c3498-142">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="c3498-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3498-143">Extremo de PBX en un sitio diferente (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="c3498-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c3498-144">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="c3498-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c3498-145">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="c3498-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3498-146">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="c3498-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c3498-147">Usuario de Lync en el mismo sitio de red (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="c3498-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c3498-148">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="c3498-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3498-149">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="c3498-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c3498-150">Usuario de Lync en sitios de red diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="c3498-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c3498-151">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="c3498-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3498-152">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="c3498-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c3498-153">Usuario de Lync en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="c3498-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="c3498-154">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="c3498-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3498-155">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="c3498-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c3498-156">Usuario de Lync federado</span><span class="sxs-lookup"><span data-stu-id="c3498-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="c3498-157">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="c3498-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

