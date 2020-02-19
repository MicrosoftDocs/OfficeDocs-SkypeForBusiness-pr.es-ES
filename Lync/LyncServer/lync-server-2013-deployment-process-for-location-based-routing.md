---
title: 'Lync Server 2013: proceso de implementación para el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46da1be1d18477d56fa4b3046557102e8771ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d1ea5-102">Proceso de implementación para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ea5-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1ea5-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="d1ea5-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d1ea5-104">En este tema se proporciona información general sobre el proceso implicado en la configuración del enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="d1ea5-105">Debe implementar Lync Server Enterprise Edition o Standard Edition con Enterprise Voice antes de configurar el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="d1ea5-106">Los componentes requeridos por el enrutamiento basado en ubicación ya están instalados y habilitados al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="d1ea5-107">Proceso de implementación de enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1ea5-108">Fase</span><span class="sxs-lookup"><span data-stu-id="d1ea5-108">Phase</span></span></th>
<th><span data-ttu-id="d1ea5-109">Pasos</span><span class="sxs-lookup"><span data-stu-id="d1ea5-109">Steps</span></span></th>
<th><span data-ttu-id="d1ea5-110">Grupos y roles necesarios</span><span class="sxs-lookup"><span data-stu-id="d1ea5-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="d1ea5-111">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ea5-112">Implementar la telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="d1ea5-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d1ea5-113">Configuración de troncos</span><span class="sxs-lookup"><span data-stu-id="d1ea5-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="d1ea5-114">Crear directivas de voz</span><span class="sxs-lookup"><span data-stu-id="d1ea5-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="d1ea5-115">Definir rutas de voz</span><span class="sxs-lookup"><span data-stu-id="d1ea5-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d1ea5-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="d1ea5-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="d1ea5-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d1ea5-117">CsAdministrator</span></span><br />
<span data-ttu-id="d1ea5-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d1ea5-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-119">Implementación de telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="d1ea5-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ea5-120">Comprobar la implementación de la telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="d1ea5-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1ea5-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="d1ea5-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="d1ea5-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d1ea5-122">CsAdministrator</span></span><br />
<span data-ttu-id="d1ea5-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d1ea5-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1ea5-124">Configuración de regiones de red, sitios y subredes</span><span class="sxs-lookup"><span data-stu-id="d1ea5-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d1ea5-125">Crear regiones de red</span><span class="sxs-lookup"><span data-stu-id="d1ea5-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="d1ea5-126">Crear sitios de red</span><span class="sxs-lookup"><span data-stu-id="d1ea5-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="d1ea5-127">Asociar subredes con sitios de red</span><span class="sxs-lookup"><span data-stu-id="d1ea5-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d1ea5-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="d1ea5-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="d1ea5-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d1ea5-129">CsAdministrator</span></span><br />
<span data-ttu-id="d1ea5-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d1ea5-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-131">Acerca de las regiones de red, sitios y subredes</span><span class="sxs-lookup"><span data-stu-id="d1ea5-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="d1ea5-132">Crear o modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="d1ea5-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="d1ea5-133">Crear o modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="d1ea5-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="d1ea5-134">Asociar una subred a un sitio de red</span><span class="sxs-lookup"><span data-stu-id="d1ea5-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ea5-135">Configurar el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d1ea5-136">Crear directivas de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="d1ea5-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="d1ea5-137">Definir una configuración de tronco separada por tronco</span><span class="sxs-lookup"><span data-stu-id="d1ea5-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="d1ea5-138">Modificar directivas de voz</span><span class="sxs-lookup"><span data-stu-id="d1ea5-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="d1ea5-139">Habilitar la configuración de enrutamiento basada en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d1ea5-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="d1ea5-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="d1ea5-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d1ea5-141">CsAdministrator</span></span><br />
<span data-ttu-id="d1ea5-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d1ea5-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="d1ea5-143">Implementación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1ea5-143">Sample Deployment</span></span>

<span data-ttu-id="d1ea5-144">La siguiente implementación se usa para ilustrar aún más los mecanismos habilitados por el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="d1ea5-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="d1ea5-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="d1ea5-146">Llamadas RTC entrantes</span><span class="sxs-lookup"><span data-stu-id="d1ea5-146">Incoming PSTN calls</span></span>

<span data-ttu-id="d1ea5-147">Un administrador puede habilitar el tronco definido para enrutar las llamadas a "puerta de enlace del sitio 1" para el enrutamiento basado en ubicación y asociar la "puerta de enlace del sitio 1" al sitio 1.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="d1ea5-148">Una vez habilitada, las llamadas que se redirigen a través de "puerta de enlace del sitio 1" solo se enrutarán a los usuarios que se encuentren en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="d1ea5-149">Todas las llamadas enrutadas a través del tronco "puerta de enlace de sitio 1" dirigidas a los usuarios de un sitio diferente, como el sitio 2, se bloquearán para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="d1ea5-150">Todas las llamadas RTC entrantes a través de la "puerta de enlace del sitio 1" solo se permitirán enrutar a extremos ubicados en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="d1ea5-151">Por ejemplo, cuando "el usuario de Lync 1" se desplaza al sitio 2, todas las llamadas RTC entrantes a través de la "puerta de enlace del sitio 1" no se enrutarán a los puntos de conexión de "usuario de Lync 1" ubicados en el sitio 2.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="d1ea5-152">La misma regla de enrutamiento se aplica si "Lync User 1" se desplaza a un sitio de red desconocido en el que no se puede determinar la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="d1ea5-153">En la tabla siguiente se describe la experiencia del usuario de "Lync User 1" en este contexto.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="d1ea5-154">Extremos del usuario de Lync 1 ubicados en el sitio de red 1</span><span class="sxs-lookup"><span data-stu-id="d1ea5-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="d1ea5-155">Extremos del usuario de Lync 1 ubicados en el sitio de red 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="d1ea5-156">Extremos del usuario de Lync 1 ubicados en un sitio de red desconocido</span><span class="sxs-lookup"><span data-stu-id="d1ea5-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ea5-157">Llamadas RTC entrantes a Lync User 1</span><span class="sxs-lookup"><span data-stu-id="d1ea5-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-158">Las llamadas se enrutan a los extremos en esta ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-159">Las llamadas no se enrutan a los extremos en esta ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-160">Las llamadas no se enrutan a los extremos en esta ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="d1ea5-161">Llamadas RTC salientes</span><span class="sxs-lookup"><span data-stu-id="d1ea5-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="d1ea5-162">Se hace referencia a las rutas de voz en las dos directivas de voz asignadas directamente a los usuarios y en las directivas de enrutamiento de voz asignadas a los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="d1ea5-163">Ambas directivas contienen referencias a rutas, que se pueden usar para enrutar una llamada de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="d1ea5-164">Por ejemplo, un administrador puede definir una directiva de enrutamiento de voz para todos los usuarios ubicados en el sitio de red 1 para enrutar todas las llamadas salientes a través de la "puerta de enlace del sitio 1", mientras que la Directiva de voz de algunos usuarios define una ruta para todas las llamadas salientes a través de la "puerta de enlace del sitio 2".</span><span class="sxs-lookup"><span data-stu-id="d1ea5-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="d1ea5-165">Mientras que estos usuarios se encuentran en el sitio de red 1, sus llamadas salientes se enrutarán a través de la "puerta de enlace del sitio 1".</span><span class="sxs-lookup"><span data-stu-id="d1ea5-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="d1ea5-166">Cuando un usuario se encuentra en un sitio de red configurado para el enrutamiento basado en ubicación, la ruta de la Directiva de enrutamiento de voz del sitio de red invalida la ruta de la Directiva de voz del usuario.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="d1ea5-167">Esta regla es especialmente útil para los usuarios que se mueven temporalmente a un sitio diferente.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="d1ea5-168">En este caso concreto, un usuario siempre usará una puerta de enlace local a su ubicación; Si el "usuario de Lync 3" se encuentra en "sitio 2", todas sus llamadas salientes se enrutarán a través de "puerta de enlace de sitio 2", pero si viajan al sitio 1, todas las llamadas salientes realizadas mientras se encuentre en el sitio 1 se enrutarán a través de la "puerta de enlace del sitio 1".</span><span class="sxs-lookup"><span data-stu-id="d1ea5-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="d1ea5-169">En la tabla siguiente se muestra la experiencia del usuario de Lync usuario 1 que realiza una llamada saliente desde los siguientes sitios de red.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="d1ea5-170">Sitio de red 1</span><span class="sxs-lookup"><span data-stu-id="d1ea5-170">Network site 1</span></span></th>
<th><span data-ttu-id="d1ea5-171">Sitio de red 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-171">Network site 2</span></span></th>
<th><span data-ttu-id="d1ea5-172">Sitio de red desconocido o no habilitado para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ea5-173">Autorización de llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="d1ea5-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-174">Directiva de voz del usuario 1 de Lync</span><span class="sxs-lookup"><span data-stu-id="d1ea5-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-175">Directiva de voz del usuario 1 de Lync</span><span class="sxs-lookup"><span data-stu-id="d1ea5-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-176">Directiva de voz del usuario 1 de Lync</span><span class="sxs-lookup"><span data-stu-id="d1ea5-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ea5-177">Enrutamiento de llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="d1ea5-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-178">Directiva de enrutamiento de voz de sitio 1</span><span class="sxs-lookup"><span data-stu-id="d1ea5-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-179">Directiva de enrutamiento de voz de sitio 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-180">Directiva de voz del usuario y solo en sistemas no habilitados para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="d1ea5-181">Transferencias y reenvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="d1ea5-181">Call transfers and forwards</span></span>

<span data-ttu-id="d1ea5-182">Cuando se transfieren o reenvían llamadas, el enrutamiento de las llamadas se ve afectado por el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="d1ea5-183">La siguiente tabla muestra el usuario de Lync 1 que transfiere o reenvía una llamada RTC a otro usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1ea5-184">Inicio de la transferencia o reenvío de llamadas de usuario</span><span class="sxs-lookup"><span data-stu-id="d1ea5-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="d1ea5-185">Lync usuario 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-185">Lync user 2</span></span></th>
<th><span data-ttu-id="d1ea5-186">Lync usuario 4</span><span class="sxs-lookup"><span data-stu-id="d1ea5-186">Lync user 4</span></span></th>
<th><span data-ttu-id="d1ea5-187">El usuario de Lync del sitio de red no está habilitado para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ea5-188">Lync usuario 1</span><span class="sxs-lookup"><span data-stu-id="d1ea5-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-189">Se permite la transferencia o el desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="d1ea5-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-190">No se permite el desvío o la transferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="d1ea5-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-191">No se permite el desvío o la transferencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="d1ea5-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="d1ea5-192">En la tabla siguiente se muestra cómo el enrutamiento basado en ubicación afecta a cómo se enruta la llamada en función de la ubicación del usuario de Lync que se está transfiriendo (Lync User 2, Lync User 4, etc.) a un punto de conexión de RTC.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1ea5-193">Punto de conexión en el que se transfiere o reenvía una llamada</span><span class="sxs-lookup"><span data-stu-id="d1ea5-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="d1ea5-194">Lync usuario 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-194">Lync user 2</span></span></th>
<th><span data-ttu-id="d1ea5-195">Lync usuario 4</span><span class="sxs-lookup"><span data-stu-id="d1ea5-195">Lync user 4</span></span></th>
<th><span data-ttu-id="d1ea5-196">El usuario de Lync del sitio de red no está habilitado para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ea5-197">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="d1ea5-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-198">La transferencia o desvío de llamadas se enruta a través de la Directiva de enrutamiento de voz del sitio 1 y de salida a través de la puerta de enlace del sitio 1</span><span class="sxs-lookup"><span data-stu-id="d1ea5-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-199">La transferencia o desvío de llamadas se enruta a través de la Directiva de enrutamiento de voz del sitio 2 y de salida a través de la puerta de enlace del sitio 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-200">La transferencia o desvío de llamadas se redirige a través de la Directiva de voz de usuario de Lync y se salida a través de una puerta de enlace no habilitada para el enrutamiento basado en ubicación (si está disponible)</span><span class="sxs-lookup"><span data-stu-id="d1ea5-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="d1ea5-201">Llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="d1ea5-201">Simultaneous ringing</span></span>

<span data-ttu-id="d1ea5-202">Una vez que se haya configurado el enrutamiento basado en ubicación en la topología de muestra, se aplican las siguientes interacciones.</span><span class="sxs-lookup"><span data-stu-id="d1ea5-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="d1ea5-203">En la tabla siguiente se muestra si el enrutamiento basado en ubicación permite las llamadas simultáneas para diferentes usuarios de Lync (por ejemplo, el usuario de Lync 2, el usuario de Lync 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="d1ea5-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1ea5-204">Destino de llamada RTC entrante</span><span class="sxs-lookup"><span data-stu-id="d1ea5-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="d1ea5-205">Lync usuario 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-205">Lync user 2</span></span></th>
<th><span data-ttu-id="d1ea5-206">Lync usuario 4</span><span class="sxs-lookup"><span data-stu-id="d1ea5-206">Lync user 4</span></span></th>
<th><span data-ttu-id="d1ea5-207">El usuario de Lync del sitio de red no está habilitado para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ea5-208">Lync usuario 1</span><span class="sxs-lookup"><span data-stu-id="d1ea5-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-209">Se permite la llamada simultánea</span><span class="sxs-lookup"><span data-stu-id="d1ea5-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-210">No se permite la llamada simultánea</span><span class="sxs-lookup"><span data-stu-id="d1ea5-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-211">No se permite la llamada simultánea</span><span class="sxs-lookup"><span data-stu-id="d1ea5-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="d1ea5-212">La siguiente tabla muestra si el enrutamiento basado en ubicación permite realizar llamadas simultáneas a un punto de conexión de RTC de diferentes usuarios de Lync (por ejemplo, el usuario de Lync 2, el usuario de Lync 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="d1ea5-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1ea5-213">Destino de llamada simultánea</span><span class="sxs-lookup"><span data-stu-id="d1ea5-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="d1ea5-214">Lync usuario 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-214">Lync user 2</span></span></th>
<th><span data-ttu-id="d1ea5-215">Lync usuario 4</span><span class="sxs-lookup"><span data-stu-id="d1ea5-215">Lync user 4</span></span></th>
<th><span data-ttu-id="d1ea5-216">El usuario de Lync del sitio de red no está habilitado para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ea5-217">Usuario de Lync 1 teléfono móvil (extremo de RTC)</span><span class="sxs-lookup"><span data-stu-id="d1ea5-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-218">Llamada enrutada a través de la Directiva de enrutamiento de voz del sitio de red 1 y salida a través de la puerta de enlace del sitio 1</span><span class="sxs-lookup"><span data-stu-id="d1ea5-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-219">Llamada enrutada a través de la Directiva de enrutamiento de voz del sitio 2 de red y salida a través de la puerta de enlace del sitio 2</span><span class="sxs-lookup"><span data-stu-id="d1ea5-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="d1ea5-220">Llamada enrutada a través de la Directiva de voz del autor de la llamada y se deshará a través de una puerta de enlace RTC que no está habilitada para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="d1ea5-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1ea5-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1ea5-221">See Also</span></span>


[<span data-ttu-id="d1ea5-222">Planeación del enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ea5-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

