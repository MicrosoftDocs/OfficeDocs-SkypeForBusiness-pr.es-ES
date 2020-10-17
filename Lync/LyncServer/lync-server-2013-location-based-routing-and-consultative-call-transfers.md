---
title: 'Lync Server 2013: transferencias de llamadas de consultoría y enrutamiento de Location-Based'
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
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513817"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="ba6bb-102">Location-Based el enrutamiento y las transferencias de llamadas de asesoría en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba6bb-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba6bb-103">_**Última modificación del tema:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="ba6bb-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="ba6bb-104">Además de imponer el enrutamiento de Location-Based a las reuniones de Lync, la aplicación de conferencia de enrutamiento de Location-Based aplica Location-Based restricciones de enrutamiento en las transferencias de llamadas de consultoría que se transfieren a los extremos de RTC.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="ba6bb-105">Una transferencia de llamada Consultiva es una llamada establecida entre dos partes en la que una de las partes transfiere la llamada a un nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="ba6bb-106">Por ejemplo, un punto de conexión RTC llama al usuario A (llamado de Lync).</span><span class="sxs-lookup"><span data-stu-id="ba6bb-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="ba6bb-107">El usuario A determina el usuario de RTC que se debe reenviar al usuario B (usuario de Lync).</span><span class="sxs-lookup"><span data-stu-id="ba6bb-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="ba6bb-108">El usuario A realiza la llamada con el usuario RTC en espera y llama al usuario B. el usuario B acuerda hablar con el usuario RTC.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="ba6bb-109">El usuario A transfiere la llamada en espera al usuario B.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="ba6bb-110">**Flujo de llamada de transferencia de llamada Consultiva**</span><span class="sxs-lookup"><span data-stu-id="ba6bb-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="ba6bb-111">![Enrutamiento basado en ubicación para diagrama de conferencia](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Enrutamiento basado en ubicación para diagrama de conferencia")</span><span class="sxs-lookup"><span data-stu-id="ba6bb-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="ba6bb-112">Cuando un usuario habilitado para el enrutamiento de Location-Based inicia una transferencia de llamada Consultiva de un extremo de RTC (tal como se muestra en la figura anterior), se crean dos llamadas activas, una llamada entre el usuario de RTC y el usuario de Lync A y la otra entre el usuario de Lync A y el usuario B de Lync. el comportamiento de la aplicación de conferencia de enrutamiento de Location-Based:</span><span class="sxs-lookup"><span data-stu-id="ba6bb-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="ba6bb-113">Si el enrutamiento de tronco SIP la llamada RTC está autorizada para redirigir la llamada RTC al sitio de red donde se encuentra el usuario B de Lync (por ejemplo, el destino de transferencia), se permitirá la transferencia de llamadas; de lo contrario, se bloqueará la transferencia de la llamada Consultiva.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="ba6bb-114">Esta autorización se realiza en función de la ubicación de la entidad transferida que se encuentra en el mismo sitio de red que el tronco SIP que enruta la llamada activa al punto de conexión de RTC.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="ba6bb-115">Si el enrutamiento de tronco SIP la llamada RTC entrante no está autorizada para enrutar llamadas al sitio de red en el que se encuentra la entidad de transferencia (usuario de Lync B) o la entidad transferida se encuentra en un sitio de red desconocido, se bloqueará la transferencia de la llamada Consultiva al punto de conexión de RTC (por ejemplo, el destino de transferencia de llamadas).</span><span class="sxs-lookup"><span data-stu-id="ba6bb-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="ba6bb-116">En la tabla siguiente se describe cómo se aplican las restricciones de enrutamiento de Location-Based por la aplicación de conferencia de Location-Based enrutamiento para las transferencias de llamadas de consultoría.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="ba6bb-117">Aunque los extremos de PBX no están directamente asociados a un sitio de red, el tronco SIP al que se conecta la PBX se puede asignar a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="ba6bb-118">Por lo tanto, el extremo de PBX se puede asociar indirectamente con un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="ba6bb-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba6bb-119">Sitio de red de la persona que ha transferido la llamada</span><span class="sxs-lookup"><span data-stu-id="ba6bb-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-120">Sitio de red del destino de transferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="ba6bb-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-121">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="ba6bb-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba6bb-122">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="ba6bb-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-123">Usuario de Lync en el mismo sitio de red (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-124">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="ba6bb-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba6bb-125">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="ba6bb-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-126">Usuario de Lync en sitios de red diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-127">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="ba6bb-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba6bb-128">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="ba6bb-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-129">Usuario de Lync en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="ba6bb-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-130">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="ba6bb-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba6bb-131">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="ba6bb-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-132">Usuario de Lync federado</span><span class="sxs-lookup"><span data-stu-id="ba6bb-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-133">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="ba6bb-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba6bb-134">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="ba6bb-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-135">Extremo de PBX en el mismo sitio (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-136">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="ba6bb-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba6bb-137">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="ba6bb-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-138">Extremo de PBX en sitios diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-139">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="ba6bb-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba6bb-140">Extremo de PBX en el mismo sitio (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-141">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="ba6bb-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-142">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="ba6bb-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba6bb-143">Extremo de PBX en un sitio diferente (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-144">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="ba6bb-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-145">La transferencia Consultiva no se permitirá</span><span class="sxs-lookup"><span data-stu-id="ba6bb-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba6bb-146">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="ba6bb-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-147">Usuario de Lync en el mismo sitio de red (por ejemplo, sitio 1)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-148">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="ba6bb-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba6bb-149">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="ba6bb-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-150">Usuario de Lync en sitios de red diferentes (por ejemplo, sitio 2)</span><span class="sxs-lookup"><span data-stu-id="ba6bb-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-151">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="ba6bb-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba6bb-152">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="ba6bb-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-153">Usuario de Lync en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="ba6bb-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-154">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="ba6bb-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba6bb-155">Extremo de PBX en cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="ba6bb-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-156">Usuario de Lync federado</span><span class="sxs-lookup"><span data-stu-id="ba6bb-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="ba6bb-157">Se permitirá la transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="ba6bb-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

