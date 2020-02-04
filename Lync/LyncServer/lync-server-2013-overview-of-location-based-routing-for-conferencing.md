---
title: 'Lync Server 2013: información general sobre el enrutamiento basado en la ubicación para conferencias'
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
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="47a09-102">Información general de enrutamiento basado en ubicación para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a09-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47a09-103">_**Última modificación del tema:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="47a09-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="47a09-104">La aplicación de conferencia de enrutamiento basada en la ubicación proporciona a las conferencias de Lync un mecanismo para la prevención de la omisión de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="47a09-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="47a09-105">La aplicación supervisa las conferencias activas e impone restricciones de enrutamiento basadas en la ubicación en función de la ubicación de los usuarios de Lync que participan.</span><span class="sxs-lookup"><span data-stu-id="47a09-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="47a09-106">La aplicación de conferencia de enrutamiento basada en la ubicación determina si se debe aplicar el enrutamiento basado en la ubicación en una reunión de Lync si se cumplen los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="47a09-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="47a09-107">El organizador de la reunión está habilitado para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="47a09-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="47a09-108">Las restricciones de enrutamiento basadas en la ubicación solo se aplicarán a conferencias organizadas por usuarios que están habilitados para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="47a09-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="47a09-109">Al menos uno de los participantes de la reunión es un extremo de RTC.</span><span class="sxs-lookup"><span data-stu-id="47a09-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="47a09-110">Las restricciones de enrutamiento basadas en la ubicación solo se aplican a las conferencias que incluyen puntos de conexión RTC.</span><span class="sxs-lookup"><span data-stu-id="47a09-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="47a09-111">El sitio de red donde se utiliza la puerta de enlace RTC para conectar la conferencia con la RTC se encuentra (al igual que los sitios de red) en la ubicación desde donde se conectan los organizadores y los participantes.</span><span class="sxs-lookup"><span data-stu-id="47a09-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="47a09-112">La aplicación de conferencia de enrutamiento basado en la ubicación impide la participación de los usuarios de Lync y los puntos finales de RTC de diferentes sitios de red en la misma conferencia.</span><span class="sxs-lookup"><span data-stu-id="47a09-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="47a09-113">Si el organizador de una reunión está habilitado para el enrutamiento basado en la ubicación, la aplicación de conferencias aplicará las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="47a09-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="47a09-114">Los puntos de conexión que pueden unirse a una reunión de Lync dependen de los puntos de conexión que ya se hayan unido a la Conferencia, y esta restricción se ajusta como puntos de conexión Unidos y los puntos de conexión nuevos se unen a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="47a09-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="47a09-115">Si los organizadores y los participantes se unen a una reunión de Lync desde el mismo sitio de red, se permite que otro participante de RTC, otro participante del mismo sitio de red, otro participante de un sitio de red diferente o de un participante de un sitio de red desconocido participación.</span><span class="sxs-lookup"><span data-stu-id="47a09-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="47a09-116">Si organizadores y participantes se unen a la reunión desde diferentes sitios de red o sitios de red desconocidos, no se permite la entrada a la reunión de un extremo de RTC, si la llamada de RTC entra de un tronco SIP habilitado para el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="47a09-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="47a09-117">Si todos los organizadores y participantes se unen a la reunión desde el mismo sitio de red y hay participantes que se unen a la misma reunión de la RTC, no se permite unirse a la reunión con un punto de conexión de Lync desde un sitio de red diferente.</span><span class="sxs-lookup"><span data-stu-id="47a09-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="47a09-118">En la tabla siguiente se resumen las restricciones de enrutamiento basadas en la ubicación de las conferencias.</span><span class="sxs-lookup"><span data-stu-id="47a09-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47a09-119">Usuario(s) en una conferencia en un momento determinado</span><span class="sxs-lookup"><span data-stu-id="47a09-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="47a09-120">Usuarios(s) con permiso para unirse a la conferencia</span><span class="sxs-lookup"><span data-stu-id="47a09-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="47a09-121">Usuarios(s) sin permiso para unirse a la conferencia</span><span class="sxs-lookup"><span data-stu-id="47a09-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47a09-122">Usuarios del cliente de VoIP de Lync desde un único sitio de red</span><span class="sxs-lookup"><span data-stu-id="47a09-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="47a09-123">Usuario de cliente de VoIP de Lync desde el mismo sitio de red</span><span class="sxs-lookup"><span data-stu-id="47a09-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="47a09-124">Usuario de cliente de VoIP de Lync desde un sitio de red diferente</span><span class="sxs-lookup"><span data-stu-id="47a09-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="47a09-125">Usuario de cliente de VoIP de Lync desde un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="47a09-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="47a09-126">Usuario del cliente VoIP de Lync federado</span><span class="sxs-lookup"><span data-stu-id="47a09-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="47a09-127">Usuario que se une desde un extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="47a09-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="47a09-128">Ninguno</span><span class="sxs-lookup"><span data-stu-id="47a09-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47a09-129">Usuarios del cliente de VoIP de Lync desde un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="47a09-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="47a09-130">Usuario de cliente de VoIP de Lync desde cualquier sitio</span><span class="sxs-lookup"><span data-stu-id="47a09-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="47a09-131">Usuario de cliente de VoIP de Lync desde un sitio desconocido</span><span class="sxs-lookup"><span data-stu-id="47a09-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="47a09-132">Usuario del cliente VoIP de Lync federado</span><span class="sxs-lookup"><span data-stu-id="47a09-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="47a09-133">Usuario que se une a través de un extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="47a09-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47a09-134">Usuarios de Lync VoIP clientes de diferentes sitios de red</span><span class="sxs-lookup"><span data-stu-id="47a09-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="47a09-135">Usuario de cliente de VoIP de Lync desde cualquier sitio de red</span><span class="sxs-lookup"><span data-stu-id="47a09-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="47a09-136">Usuario de cliente de VoIP de Lync desde un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="47a09-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="47a09-137">Usuario del cliente VoIP de Lync federado</span><span class="sxs-lookup"><span data-stu-id="47a09-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="47a09-138">Usuario que se une a través de un extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="47a09-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47a09-139">Usuarios del cliente de VoIP de Lync desde un único sitio de red y usuarios que se unen desde un punto final de RTC</span><span class="sxs-lookup"><span data-stu-id="47a09-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="47a09-140">Usuario de cliente de VoIP de Lync desde el mismo sitio de red</span><span class="sxs-lookup"><span data-stu-id="47a09-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="47a09-141">Usuario de cliente de VoIP de Lync desde un sitio de red diferente</span><span class="sxs-lookup"><span data-stu-id="47a09-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="47a09-142">Usuario de cliente de VoIP de Lync desde un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="47a09-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="47a09-143">Usuario del cliente VoIP de Lync federado</span><span class="sxs-lookup"><span data-stu-id="47a09-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="47a09-144">A continuación se muestran características adicionales de la aplicación de conferencia de enrutamiento basada en ubicación:</span><span class="sxs-lookup"><span data-stu-id="47a09-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="47a09-145">Cuando un usuario no puede unirse a una conferencia con las restricciones de enrutamiento basadas en la ubicación, se rechazarán las llamadas de los usuarios a la Conferencia y su cliente de Lync informará de que la llamada no se completó o ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="47a09-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="47a09-146">Un punto final de RTC que se une a una conferencia con las fuerzas de enrutamiento basadas en la ubicación no se verá restringido a unirse a la Conferencia, independientemente de su estado, si el punto de conexión se une a través de un tronco que no está habilitado para el enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="47a09-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="47a09-147">Un sistema PBX conectado a un servidor de mediación a través de un tronco de SIP que no esté de salida las llamadas a la RTC tendrán las mismas fuerzas que los usuarios de Lync que se encuentren en el mismo sitio de red en el que se define el tronco del SIP.</span><span class="sxs-lookup"><span data-stu-id="47a09-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="47a09-148">Por ejemplo, un punto final de RTC podrá unirse a una conferencia con un usuario de PBX y un usuario de Lync si se encuentran en el mismo sitio de red; de lo contrario, el punto final de RTC no podrá unirse a la Conferencia si el usuario de PBX se encuentra en otro sitio de red que el usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="47a09-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

