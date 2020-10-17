---
title: 'Lync Server 2013: requisitos para el enrutamiento Location-Based para conferencias'
description: 'Lync Server 2013: requisitos para el enrutamiento de Location-Based para conferencias.'
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
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542526"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="6e4a7-103">Requisitos para Location-Based el enrutamiento para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e4a7-103">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e4a7-104">_**Última modificación del tema:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="6e4a7-104">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="6e4a7-105">Los siguientes son los requisitos necesarios para la instalación y configuración de la aplicación de conferencia de enrutamiento de Location-Based:</span><span class="sxs-lookup"><span data-stu-id="6e4a7-105">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="6e4a7-106">Lync Server 2013 la actualización acumulativa 2 debe implementarse en todos los servidores o grupos de servidores de la topología.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-106">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e4a7-107">Si un servidor de Lync o un grupo de servidores de la topología no tienen instalado la actualización acumulativa 2 o posterior de Lync Server 2013, no se podrá garantizar la aplicación de Location-Based el enrutamiento de reuniones de Lync.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-107">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="6e4a7-108">Lync Server 2013 Location-Based el enrutamiento es un requisito previo para Location-Based aplicación de conferencia de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-108">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="6e4a7-109">Para obtener más información sobre cómo configurar el enrutamiento de Lync Server 2013 Location-Based, consulte [configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6e4a7-109">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="6e4a7-110">Los requisitos de Location-Based aplicación de conferencia de enrutamiento son los mismos que los de Lync Server 2013 Location-Based el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-110">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="6e4a7-111">Para obtener más información, consulte [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6e4a7-111">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="6e4a7-112">Servidores compatibles</span><span class="sxs-lookup"><span data-stu-id="6e4a7-112">Supported Servers</span></span>

<span data-ttu-id="6e4a7-113">La aplicación de Location-Based de conferencia de enrutamiento requiere que se implemente la actualización acumulativa 2 de Lync Server 2013 en todos los grupos de Front-End y servidores Standard Edition de la topología.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-113">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="6e4a7-114">Si Lync Server 2013 la actualización acumulativa 2 no está instalada en algunos servidores de Lync de la topología, Location-Based restricciones de enrutamiento no se pueden aplicar completamente en las reuniones y las transferencias de llamadas de consultoría de Lync.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-114">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="6e4a7-115">En la siguiente tabla se identifica la combinación de roles de servidor y versiones que admiten el enrutamiento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-115">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e4a7-116">Versión del grupo de Front-End</span><span class="sxs-lookup"><span data-stu-id="6e4a7-116">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-117">Versión del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="6e4a7-117">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-118">Compatible</span><span class="sxs-lookup"><span data-stu-id="6e4a7-118">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e4a7-119">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e4a7-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-120">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e4a7-120">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-121">Sí</span><span class="sxs-lookup"><span data-stu-id="6e4a7-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e4a7-122">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e4a7-122">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-123">Actualización acumulativa 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e4a7-123">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-124">No</span><span class="sxs-lookup"><span data-stu-id="6e4a7-124">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e4a7-125">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e4a7-125">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6e4a7-126">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-127">No</span><span class="sxs-lookup"><span data-stu-id="6e4a7-127">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e4a7-128">Actualización acumulativa 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e4a7-128">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-129">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6e4a7-129">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-130">No</span><span class="sxs-lookup"><span data-stu-id="6e4a7-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e4a7-131">Actualización acumulativa 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e4a7-131">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-132">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="6e4a7-132">Any</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-133">No</span><span class="sxs-lookup"><span data-stu-id="6e4a7-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e4a7-134">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6e4a7-134">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-135">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="6e4a7-135">Any</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-136">No</span><span class="sxs-lookup"><span data-stu-id="6e4a7-136">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e4a7-137">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6e4a7-137">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-138">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="6e4a7-138">Any</span></span></p></td>
<td><p><span data-ttu-id="6e4a7-139">No</span><span class="sxs-lookup"><span data-stu-id="6e4a7-139">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="6e4a7-140">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="6e4a7-140">Supported Clients</span></span>

<span data-ttu-id="6e4a7-141">Los clientes de Lync que admiten el enrutamiento Location-Based de reuniones de Lync son los mismos clientes que admiten el enrutamiento de Lync Server 2013 Location-Based.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-141">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="6e4a7-142">Para obtener más información, consulte compatibilidad con el [cliente y el servidor para Location-Based enrutamiento](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="6e4a7-142">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="6e4a7-143">Requisitos del servidor de mediación para las transferencias de llamadas de consultoría</span><span class="sxs-lookup"><span data-stu-id="6e4a7-143">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="6e4a7-144">La aplicación de conferencia de Location-Based enrutamiento requiere la implementación de servidores de mediación independientes para imponer Location-Based restricciones de enrutamiento en las transferencias de llamadas de consultoría.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-144">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="6e4a7-145">Para aplicar Location-Based el enrutamiento de las transferencias de llamadas de consultoría, el servidor de mediación debe estar asociado solamente a un servidor de mediación del mismo nivel (es decir, PBX, puerta de enlace SIP, etc.) en las regiones de red en las que se requiere Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-145">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="6e4a7-146">Si se implementan más del servidor de mediación en la misma región de red, el servidor de mediación del mismo nivel debe estar asociado a un servidor de mediación diferente.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-146">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="6e4a7-147">Este requisito se detalla a continuación:</span><span class="sxs-lookup"><span data-stu-id="6e4a7-147">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="6e4a7-148">Servidor de mediación único por parte del mismo nivel del servidor de mediación cuando una transferencia de llamada de consulta se enruta a un servidor de mediación del mismo nivel a través de un servidor de mediación configurado con varios troncos SIP a varios interlocutores (es decir, PBX y puertas de enlace), se bloquea la transferencia de llamadas de consulta para evitar el desvío de peajes de RTC.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-148">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="6e4a7-149">Por ejemplo, en el caso de un servidor de mediación único que atiende un servidor de mediación de puerta de enlace RTC y un servidor del mismo nivel de mediación de PBX, se observará el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="6e4a7-149">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="6e4a7-150">Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un punto de conexión de RTC a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante transferencia Consultiva, la llamada no se permitirá para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="6e4a7-151">Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un extremo de PBX en el mismo sitio (sitio 1) a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante la transferencia Consultiva, la llamada no se permitirá incluso si no incurre en la posible omisión de peajes RTC.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-151">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="6e4a7-152">Servidores de mediación independientes por servidor de mediación del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="6e4a7-152">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="6e4a7-153">Cuando una transferencia de consulta se destina a un servidor de mediación del mismo nivel, la transferencia de consulta se evalúa en el servidor de mediación único que el servidor de mediación presta.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-153">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="6e4a7-154">La llamada no se permitirá o se permitirá en función de su potencial de incurrir en la omisión de peaje RTC, independientemente del resto de servidores de mediación del sitio que sean proporcionados por servidores de mediación independientes.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-154">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="6e4a7-155">Por ejemplo, en el caso de los servidores de mediación independientes que atienden un servidor de mediación de puerta de enlace RTC y un servidor del mismo nivel del servidor de mediación de PBX, se observará el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="6e4a7-155">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="6e4a7-156">Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un punto de conexión de RTC a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante transferencia Consultiva, la llamada no se permitirá para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="6e4a7-157">Cuando un usuario de Lync de un sitio determinado (por ejemplo, el sitio 1) intenta transferir una llamada con un extremo de PBX en el mismo sitio (sitio 1) a un usuario de Lync desde un sitio diferente (por ejemplo, el sitio 2) mediante la transferencia Consultiva, la llamada se permitirá ya que no se produce en la posible omisión de peajes RTC.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-157">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="6e4a7-158">Capacidades no admitidas por la aplicación de conferencia de enrutamiento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="6e4a7-158">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="6e4a7-159">Las siguientes funciones no son compatibles con la aplicación de Location-Based de conferencia de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="6e4a7-159">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="6e4a7-160">Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-160">Dial-in conferencing.</span></span> <span data-ttu-id="6e4a7-161">No se puede aplicar el enrutamiento Location-Based para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-161">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="6e4a7-162">Cualquier solicitud de acceso telefónico a una conferencia determinada no estará restringida por el Location-Based el enrutamiento, incluso si el organizador de la Conferencia es un usuario de Lync habilitado para Location-Based el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-162">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="6e4a7-163">Se recomienda no aprovisionar los números de acceso a la Conferencia en las regiones donde se deben aplicar las restricciones de enrutamiento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="6e4a7-163">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

