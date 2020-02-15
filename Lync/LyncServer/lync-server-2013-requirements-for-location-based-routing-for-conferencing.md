---
title: 'Lync Server 2013: requisitos para el enrutamiento basado en ubicación para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5e97ed5e762b35489eac0b69fbfcad45a8e822
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="e0f5a-102">Requisitos para el enrutamiento basado en ubicación para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f5a-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0f5a-103">_**Última modificación del tema:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="e0f5a-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="e0f5a-104">Los siguientes son los requisitos necesarios para la instalación y configuración de la aplicación de conferencia de enrutamiento basada en ubicación:</span><span class="sxs-lookup"><span data-stu-id="e0f5a-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="e0f5a-105">Lync Server 2013 la actualización acumulativa 2 debe implementarse en todos los servidores o grupos de servidores de la topología.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0f5a-106">Si un servidor de Lync o un grupo de servidores de la topología no tienen instalado Lync Server 2013, actualización acumulativa 2 o superior, no se podrá garantizar la aplicación del enrutamiento basado en ubicación de las reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="e0f5a-107">Lync Server 2013 el enrutamiento basado en ubicación es un requisito previo para la aplicación de conferencia de enrutamiento basada en ubicación.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="e0f5a-108">Para obtener más información sobre cómo configurar el enrutamiento basado en ubicación 2013 de Lync Server, consulte [Configuring location-based Routing](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e0f5a-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="e0f5a-109">Los requisitos de la aplicación de conferencia de enrutamiento basada en ubicación son los mismos que los requisitos para el enrutamiento basado en ubicación 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="e0f5a-110">Para obtener más información, consulte [Planning for location-based Routing](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e0f5a-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="e0f5a-111">Servidores compatibles</span><span class="sxs-lookup"><span data-stu-id="e0f5a-111">Supported Servers</span></span>

<span data-ttu-id="e0f5a-112">La aplicación de conferencia de enrutamiento basada en ubicación requiere que se implemente la actualización acumulativa 2 de Lync Server 2013 en todos los grupos de servidores front-end y servidores Standard Edition de la topología.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="e0f5a-113">Si Lync Server 2013 la actualización acumulativa 2 no está instalada en algunos servidores de Lync de la topología, las restricciones de enrutamiento basadas en ubicación no se pueden aplicar completamente en las reuniones y las transferencias de llamadas de consultoría de Lync.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="e0f5a-114">En la siguiente tabla se identifica la combinación de roles de servidor y versiones que admiten el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0f5a-115">Versión del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e0f5a-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-116">Versión del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="e0f5a-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-117">Admitido</span><span class="sxs-lookup"><span data-stu-id="e0f5a-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0f5a-118">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f5a-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-119">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f5a-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-120">Sí</span><span class="sxs-lookup"><span data-stu-id="e0f5a-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0f5a-121">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f5a-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-122">Actualización acumulativa 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f5a-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-123">No</span><span class="sxs-lookup"><span data-stu-id="e0f5a-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0f5a-124">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f5a-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e0f5a-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-126">No</span><span class="sxs-lookup"><span data-stu-id="e0f5a-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0f5a-127">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f5a-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e0f5a-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-129">No</span><span class="sxs-lookup"><span data-stu-id="e0f5a-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0f5a-130">Actualización acumulativa 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f5a-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-131">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e0f5a-131">Any</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-132">No</span><span class="sxs-lookup"><span data-stu-id="e0f5a-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0f5a-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e0f5a-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-134">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e0f5a-134">Any</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-135">No</span><span class="sxs-lookup"><span data-stu-id="e0f5a-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0f5a-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e0f5a-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-137">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="e0f5a-137">Any</span></span></p></td>
<td><p><span data-ttu-id="e0f5a-138">No</span><span class="sxs-lookup"><span data-stu-id="e0f5a-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="e0f5a-139">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="e0f5a-139">Supported Clients</span></span>

<span data-ttu-id="e0f5a-140">Los clientes de Lync que admiten el enrutamiento basado en ubicación de las reuniones de Lync son los mismos clientes que admiten el enrutamiento basado en ubicación 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="e0f5a-141">Para obtener más información, consulte [compatibilidad de cliente y servidor para el enrutamiento basado en ubicación](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e0f5a-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="e0f5a-142">Requisitos del servidor de mediación para las transferencias de llamadas de consultoría</span><span class="sxs-lookup"><span data-stu-id="e0f5a-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="e0f5a-143">La aplicación de conferencia de enrutamiento basada en ubicación requiere la implementación de servidores de mediación independientes para aplicar restricciones de enrutamiento basadas en la ubicación en las transferencias de llamadas de consultoría.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="e0f5a-144">Para aplicar el enrutamiento basado en la ubicación de las transferencias de llamadas de consulta, el servidor de mediación debe estar asociado solamente a un servidor de mediación del mismo nivel (es decir, PBX, puerta de enlace SIP, etc.) en las regiones de red donde se requiere el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="e0f5a-145">Si se implementan más del servidor de mediación en la misma región de red, el servidor de mediación del mismo nivel debe estar asociado a un servidor de mediación diferente.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="e0f5a-146">Este requisito se detalla a continuación:</span><span class="sxs-lookup"><span data-stu-id="e0f5a-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="e0f5a-147">Servidor de mediación único por cada punto del servidor de mediación cuando una transferencia de llamada de consulta se enruta a un servidor de mediación del mismo nivel a través de un servidor de mediación configurado con varios troncos SIP a varios interlocutores (es decir, PBX y puertas de enlace), el consultivo la transferencia de llamadas está bloqueada para evitar el desvío de peaje de RTC si se permite la transferencia de llamada consultiva a través de algunos troncos SIP, pero no se permite a través de otros troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="e0f5a-148">Por ejemplo, en el caso de un servidor de mediación único que atiende un servidor de mediación de puerta de enlace RTC y un servidor del mismo nivel de mediación de PBX, se observará el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="e0f5a-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="e0f5a-149">Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un punto de conexión de RTC a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante transferencia Consultiva, la llamada no se permitirá para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="e0f5a-150">Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un extremo de PBX en el mismo sitio (sitio 1) a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante la transferencia Consultiva, la llamada no se permitirá incluso si no incurre en la tol posible RTC. l omitir.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="e0f5a-151">Servidores de mediación independientes por servidor de mediación del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e0f5a-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="e0f5a-152">Cuando una transferencia de consulta se destina a un servidor de mediación del mismo nivel, la transferencia de consulta se evalúa en el servidor de mediación único que el servidor de mediación presta.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="e0f5a-153">La llamada no se permitirá o se permitirá en función de su potencial de incurrir en la omisión de peaje RTC, independientemente del resto de servidores de mediación del sitio que sean proporcionados por servidores de mediación independientes.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="e0f5a-154">Por ejemplo, en el caso de los servidores de mediación independientes que atienden un servidor de mediación de puerta de enlace RTC y un servidor del mismo nivel del servidor de mediación de PBX, se observará el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="e0f5a-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="e0f5a-155">Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un punto de conexión de RTC a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante transferencia Consultiva, la llamada no se permitirá para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="e0f5a-156">Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un extremo de PBX en el mismo sitio (sitio 1) a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante transferencia Consultiva, la llamada se permitirá porque no incurre en posible omisión de peaje RTC. Ing.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="e0f5a-157">Capacidades no compatibles con la aplicación de conferencia de enrutamiento basada en ubicación</span><span class="sxs-lookup"><span data-stu-id="e0f5a-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="e0f5a-158">Las siguientes funciones no son compatibles con la aplicación de conferencia de enrutamiento basada en ubicación:</span><span class="sxs-lookup"><span data-stu-id="e0f5a-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="e0f5a-159">Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-159">Dial-in conferencing.</span></span> <span data-ttu-id="e0f5a-160">No se puede aplicar el enrutamiento basado en ubicación para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="e0f5a-161">Cualquier solicitud de acceso telefónico a una conferencia determinada no estará restringida por el enrutamiento basado en ubicación, incluso si el organizador de la Conferencia es un usuario de Lync habilitado para el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="e0f5a-162">Se recomienda no proporcionar los números de acceso de conferencia en las regiones donde se deben aplicar las restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="e0f5a-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

