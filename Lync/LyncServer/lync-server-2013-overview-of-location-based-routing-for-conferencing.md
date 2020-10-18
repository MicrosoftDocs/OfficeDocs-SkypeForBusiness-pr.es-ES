---
title: 'Lync Server 2013: información general sobre el enrutamiento de Location-Based para conferencias'
description: 'Lync Server 2013: información general sobre el enrutamiento de Location-Based para conferencias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a8fe9cdf4a797243c3ec04b3466011f374fb0d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577376"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="5de66-103">Información general sobre el enrutamiento de Location-Based para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de66-103">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5de66-104">_**Última modificación del tema:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="5de66-104">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="5de66-105">La aplicación de conferencia de Location-Based enrutamiento proporciona a las conferencias de Lync un mecanismo para evitar el desvío de peajes RTC.</span><span class="sxs-lookup"><span data-stu-id="5de66-105">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="5de66-106">La aplicación supervisa las conferencias activas y aplica Location-Based restricciones de enrutamiento en función de la ubicación de los usuarios de Lync que participan.</span><span class="sxs-lookup"><span data-stu-id="5de66-106">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="5de66-107">La aplicación de conferencia de Location-Based enrutamiento determina si se debe aplicar Location-Based el enrutamiento en una reunión de Lync si se cumplen los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="5de66-107">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="5de66-108">El organizador de la reunión está habilitado para Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="5de66-108">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="5de66-109">Location-Based restricciones de enrutamiento solo se aplicarán a las conferencias organizadas por usuarios habilitados para Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="5de66-109">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="5de66-110">Al menos un participante de la reunión es un punto de conexión RTC.</span><span class="sxs-lookup"><span data-stu-id="5de66-110">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="5de66-111">Location-Based restricciones de enrutamiento solo son aplicables a las conferencias que incluyen extremos de RTC.</span><span class="sxs-lookup"><span data-stu-id="5de66-111">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="5de66-112">El sitio de red en el que se ubica la puerta de enlace RTC que se usa para salvar la Conferencia a la RTC se encuentra, así como los sitios de red desde donde se conectan los organizadores y participantes.</span><span class="sxs-lookup"><span data-stu-id="5de66-112">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="5de66-113">La aplicación de conferencia de Location-Based enrutamiento evita la participación de los usuarios de Lync y los extremos de RTC de distintos sitios de red en la misma conferencia.</span><span class="sxs-lookup"><span data-stu-id="5de66-113">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="5de66-114">Si el organizador de una reunión está habilitado para Location-Based el enrutamiento, la aplicación de conferencia exige las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="5de66-114">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="5de66-115">Los puntos de conexión que se pueden unir a una reunión de Lync dependen de los extremos que ya se hayan unido a la Conferencia, y esta restricción se ajusta como extremos Unidos y los nuevos puntos de conexión se unen a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="5de66-115">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="5de66-116">Si los organizadores y participantes se unen a una reunión de Lync desde el mismo sitio de red, se permite unirse a otro participante de un sitio de red diferente o a un participante de un sitio de red desconocido desde el mismo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="5de66-116">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="5de66-117">Si los organizadores y participantes se unen a la reunión desde sitios de red diferentes o desconocidos, un extremo de RTC no puede unirse a la reunión si la llamada RTC Progress desde un tronco SIP habilitado para Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="5de66-117">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="5de66-118">Si todos los organizadores y participantes se unen a la reunión desde el mismo sitio de red y hay participantes que se unen a la misma reunión desde la RTC, un punto de conexión de Lync desde un sitio de red diferente no puede unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="5de66-118">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="5de66-119">En la tabla siguiente se resumen las restricciones de enrutamiento Location-Based la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="5de66-119">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5de66-120">Usuario (s) en una conferencia en un punto determinado</span><span class="sxs-lookup"><span data-stu-id="5de66-120">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="5de66-121">Usuarios que han permitido unirse a la Conferencia</span><span class="sxs-lookup"><span data-stu-id="5de66-121">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="5de66-122">Usuario (s) sin permiso para unirse a la Conferencia</span><span class="sxs-lookup"><span data-stu-id="5de66-122">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5de66-123">Usuarios de Lync VoIP Client (s) de un único sitio de red</span><span class="sxs-lookup"><span data-stu-id="5de66-123">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="5de66-124">Usuario de cliente VoIP de Lync desde el mismo sitio de red</span><span class="sxs-lookup"><span data-stu-id="5de66-124">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="5de66-125">Usuario de cliente VoIP de Lync desde un sitio de red diferente</span><span class="sxs-lookup"><span data-stu-id="5de66-125">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="5de66-126">Usuario de cliente VoIP de Lync desde un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="5de66-126">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="5de66-127">Usuario de cliente VoIP de Lync federado</span><span class="sxs-lookup"><span data-stu-id="5de66-127">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="5de66-128">Unirse a un usuario desde un punto de conexión RTC</span><span class="sxs-lookup"><span data-stu-id="5de66-128">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="5de66-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="5de66-129">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5de66-130">Usuarios de Lync VoIP Client (s) desde un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="5de66-130">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="5de66-131">Usuario de cliente VoIP de Lync desde cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="5de66-131">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="5de66-132">Usuario del cliente VoIP de Lync desde un sitio desconocido</span><span class="sxs-lookup"><span data-stu-id="5de66-132">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="5de66-133">Usuario de cliente VoIP de Lync federado</span><span class="sxs-lookup"><span data-stu-id="5de66-133">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="5de66-134">Unión de usuarios a través de un punto de conexión RTC</span><span class="sxs-lookup"><span data-stu-id="5de66-134">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5de66-135">Usuarios de clientes de VoIP de Lync de distintos sitios de red</span><span class="sxs-lookup"><span data-stu-id="5de66-135">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="5de66-136">Usuario de cliente VoIP de Lync desde cualquier sitio de red</span><span class="sxs-lookup"><span data-stu-id="5de66-136">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="5de66-137">Usuario de cliente VoIP de Lync desde un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="5de66-137">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="5de66-138">Usuario de cliente VoIP de Lync federado</span><span class="sxs-lookup"><span data-stu-id="5de66-138">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="5de66-139">Unión de usuarios a través de un punto de conexión RTC</span><span class="sxs-lookup"><span data-stu-id="5de66-139">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5de66-140">Usuarios del cliente de VoIP de Lync de un único sitio de red y usuarios que se unen desde un punto de conexión de RTC</span><span class="sxs-lookup"><span data-stu-id="5de66-140">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="5de66-141">Usuario de cliente VoIP de Lync desde el mismo sitio de red</span><span class="sxs-lookup"><span data-stu-id="5de66-141">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="5de66-142">Usuario de cliente VoIP de Lync desde un sitio de red diferente</span><span class="sxs-lookup"><span data-stu-id="5de66-142">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="5de66-143">Usuario de cliente VoIP de Lync desde un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="5de66-143">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="5de66-144">Usuario de cliente VoIP de Lync federado</span><span class="sxs-lookup"><span data-stu-id="5de66-144">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5de66-145">Las siguientes son características adicionales de la aplicación de conferencia de enrutamiento de Location-Based:</span><span class="sxs-lookup"><span data-stu-id="5de66-145">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="5de66-146">Cuando un usuario no está autorizado para unirse a una conferencia dada Location-Based restricciones de enrutamiento, se rechazarán las llamadas de los usuarios a la Conferencia y su cliente de Lync informará de que la llamada no se completó o ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="5de66-146">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="5de66-147">Un punto de conexión RTC que se une a una conferencia con Location-Based las fuerzas de enrutamiento no se verá restringido a unirse a la Conferencia independientemente de su estado si el punto de conexión se une a través de un tronco que no está habilitado para Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="5de66-147">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="5de66-148">Un sistema PBX conectado a un servidor de mediación a través de un tronco SIP que no esté de salida las llamadas a la RTC tendrán las mismas fuerzas que los usuarios de Lync que se encuentran en el mismo sitio de red en el que se define el tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="5de66-148">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="5de66-149">Por ejemplo, un extremo de RTC podrá unirse a una conferencia con un usuario de PBX y un usuario de Lync si se encuentran en el mismo sitio de red; de lo contrario, el punto de conexión de RTC no podrá unirse a la Conferencia si el usuario de PBX se encuentra en un sitio de red diferente del usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="5de66-149">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

