---
title: 'Lync Server 2013: Opciones de implementación SIP directa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e88dd5a576e467fbca25e9f467bd168fd6401d17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="ce80a-102">Opciones de implementación SIP directa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce80a-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce80a-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ce80a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ce80a-104">En este tema se proporcionan topologías de ejemplo para implementar conexiones SIP directas.</span><span class="sxs-lookup"><span data-stu-id="ce80a-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="ce80a-105">Lync Server independiente</span><span class="sxs-lookup"><span data-stu-id="ce80a-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="ce80a-106">Si su organización usa una de las implementaciones descritas en esta sección, puede usar Lync Server 2013 como la única solución de telefonía para una parte o toda la organización.</span><span class="sxs-lookup"><span data-stu-id="ce80a-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="ce80a-107">En esta sección se describen las siguientes implementaciones en detalle:</span><span class="sxs-lookup"><span data-stu-id="ce80a-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="ce80a-108">**Implementación incremental:** Esta opción supone que tiene una infraestructura de intercambio privado existente (PBX) y tiene previsto presentar la telefonía IP en forma incremental para grupos más pequeños o equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="ce80a-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="ce80a-109">**Implementación solo con VoIP de Lync Server:** esta opción supone que está considerando la posibilidad de implementar una telefonía IP empresarial en un sitio que no tiene una infraestructura de telefonía tradicional.</span><span class="sxs-lookup"><span data-stu-id="ce80a-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="ce80a-110">Implementación incremental</span><span class="sxs-lookup"><span data-stu-id="ce80a-110">Incremental Deployment</span></span>

<span data-ttu-id="ce80a-111">En la implementación incremental, Lync Server 2013 es la única solución de telefonía para equipos individuales o departamentos, mientras que el resto de los usuarios de una organización continúa usando un sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="ce80a-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="ce80a-112">Esta estrategia de implementación incremental proporciona una forma de introducir la telefonía IP en su empresa a través de programas piloto controlados.</span><span class="sxs-lookup"><span data-stu-id="ce80a-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="ce80a-113">Los grupos de trabajo cuyas comunicaciones unificadas de Microsoft se sirven mejor a las comunicaciones unificadas de Microsoft se mueven a telefonía IP empresarial, mientras que otros usuarios permanecen en el PBX existente.</span><span class="sxs-lookup"><span data-stu-id="ce80a-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="ce80a-114">Se pueden migrar grupos de trabajo adicionales a la telefonía IP empresarial, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ce80a-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="ce80a-115">Se recomienda usar la opción incremental si tiene definidos claramente grupos de usuarios que tienen requisitos de comunicación en común y que se prestan a una administración centralizada.</span><span class="sxs-lookup"><span data-stu-id="ce80a-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="ce80a-116">Esta opción también es eficaz si tiene equipos o departamentos que están dispersos en áreas geográficas amplias, donde el ahorro en los cargos de larga distancia puede ser significativo.</span><span class="sxs-lookup"><span data-stu-id="ce80a-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="ce80a-117">De hecho, esta opción es útil para crear equipos virtuales cuyos miembros pueden estar dispersos por todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="ce80a-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="ce80a-118">Puede crear, modificar o desintegrar esos equipos con rapidez para desplazarse por los requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="ce80a-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="ce80a-119">La siguiente ilustración muestra la topología genérica para la implementación de telefonía IP empresarial detrás de un sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="ce80a-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="ce80a-120">Esta es la topología recomendada para una implementación incremental.</span><span class="sxs-lookup"><span data-stu-id="ce80a-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="ce80a-121">**Opción de implementación incremental**</span><span class="sxs-lookup"><span data-stu-id="ce80a-121">**Incremental deployment option**</span></span>

<span data-ttu-id="ce80a-122">![Diagrama de opción de migración departamental](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagrama de opción de migración departamental")</span><span class="sxs-lookup"><span data-stu-id="ce80a-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce80a-123">Si va a conectar su implementación de Lync Server a un socio certificado SIP certificado, una puerta de enlace de red telefónica conmutada (RTC) entre el servidor de mediación y la PBX no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="ce80a-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="ce80a-124">Para obtener una lista de socios de SIP directos certificados, consulte el sitio web del programa de interoperabilidad abierto de comunicaciones unificadas de Microsoft en <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span><span class="sxs-lookup"><span data-stu-id="ce80a-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ce80a-125">La ruta multimedia que se muestra en esta figura tiene habilitada la omisión de medios (configuración recomendada).</span><span class="sxs-lookup"><span data-stu-id="ce80a-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="ce80a-126">Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ce80a-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="ce80a-127">En esta topología, los departamentos o grupos de trabajo seleccionados están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ce80a-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="ce80a-128">Una puerta de enlace RTC vincula el grupo de trabajo habilitado para el protocolo de voz a través de Internet (VoIP) a la PBX.</span><span class="sxs-lookup"><span data-stu-id="ce80a-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="ce80a-129">Los usuarios que están habilitados para telefonía IP empresarial, incluidos los trabajadores remotos, se comunican a través de la red IP.</span><span class="sxs-lookup"><span data-stu-id="ce80a-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="ce80a-130">Las llamadas de los usuarios de Voice empresarial a la RTC y a los compañeros de trabajo que no están habilitados para telefonía IP empresarial se enrutan a la puerta de enlace PSTN correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ce80a-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="ce80a-131">Las llamadas de colegas que aún están en el sistema PBX, o de las personas que llaman en la RTC, se enrutan a la puerta de enlace PSTN, que reenvía las llamadas a Lync Server para su enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="ce80a-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="ce80a-132">Hay dos configuraciones recomendadas para conectar telefonía IP empresarial a una infraestructura PBX existente para la interoperabilidad: telefonía IP empresarial detrás de la PBX y la voz de empresa delante de la PBX.</span><span class="sxs-lookup"><span data-stu-id="ce80a-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="ce80a-133">Telefonía IP empresarial detrás de la PBX</span><span class="sxs-lookup"><span data-stu-id="ce80a-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="ce80a-134">Cuando se implementa la telefonía IP empresarial tras la PBX, todas las llamadas de la RTC llegan a la PBX, que dirige las llamadas a los usuarios de telefonía de la empresa a una puerta de enlace RTC y llama a los usuarios de PBX a la PBX.</span><span class="sxs-lookup"><span data-stu-id="ce80a-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="ce80a-135">Voz empresarial delante de la PBX</span><span class="sxs-lookup"><span data-stu-id="ce80a-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="ce80a-136">Cuando se implementa la telefonía IP empresarial delante del sistema PBX, todas las llamadas llegan a la puerta de enlace PSTN, que dirige las llamadas de usuarios de telefonía de empresa a Lync Server y llama a los usuarios de PBX a la PBX.</span><span class="sxs-lookup"><span data-stu-id="ce80a-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="ce80a-137">Las llamadas a la RTC desde los usuarios de Enterprise Voice y PBX se dirigen a través de la red IP a la puerta de enlace RTC más económica.</span><span class="sxs-lookup"><span data-stu-id="ce80a-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="ce80a-138">En la tabla siguiente se muestran las ventajas y desventajas de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="ce80a-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="ce80a-139">Ventajas y desventajas de implementar voz empresarial en la parte delantera de PBX</span><span class="sxs-lookup"><span data-stu-id="ce80a-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce80a-140">Ofrece</span><span class="sxs-lookup"><span data-stu-id="ce80a-140">Advantages</span></span></th>
<th><span data-ttu-id="ce80a-141">Desventajas</span><span class="sxs-lookup"><span data-stu-id="ce80a-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce80a-142">PBX aún da servicio a los usuarios que no tienen habilitada la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ce80a-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="ce80a-143">Es posible que las puertas de enlace existentes no admitan las características o la capacidad que usted desee.</span><span class="sxs-lookup"><span data-stu-id="ce80a-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce80a-144">PBX controla todos los dispositivos anteriores.</span><span class="sxs-lookup"><span data-stu-id="ce80a-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="ce80a-145">Requiere un tronco desde la puerta de enlace a la PBX y desde la puerta de enlace hasta el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ce80a-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="ce80a-146">Es posible que necesites más troncos del proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="ce80a-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce80a-147">Los usuarios de voz empresarial conservan los mismos números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="ce80a-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="ce80a-148">Implementación solo con VoIP de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ce80a-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="ce80a-149">Enterprise Voice ofrece nuevas empresas y también nuevos sitios de Office para empresas existentes, con la oportunidad de implementar una solución VoIP completa sin tener que preocuparse por la integración de PBX o incurrir en la implementación y el mantenimiento importantes. costos de una infraestructura IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ce80a-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="ce80a-150">Esta solución es compatible tanto con trabajadores remotos como en el sitio.</span><span class="sxs-lookup"><span data-stu-id="ce80a-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="ce80a-151">En esta implementación, todas las llamadas se enrutan a través de la red IP.</span><span class="sxs-lookup"><span data-stu-id="ce80a-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="ce80a-152">Las llamadas a la RTC se enrutan a la puerta de enlace PSTN adecuada.</span><span class="sxs-lookup"><span data-stu-id="ce80a-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="ce80a-153">Lync 2013 o Lync Phone Edition funciona como softphone.</span><span class="sxs-lookup"><span data-stu-id="ce80a-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="ce80a-154">El control remoto de llamadas no está disponible e innecesario porque no hay teléfonos PBX para que los usuarios puedan controlarlo.</span><span class="sxs-lookup"><span data-stu-id="ce80a-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="ce80a-155">Los servicios de correo de voz y de operador automático están disponibles a través de la implementación opcional de mensajería unificada de Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="ce80a-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce80a-156">Además de la infraestructura de red necesaria para admitir Lync Server 2013, una implementación de solo VoIP puede usar una pequeña y certificada puerta de enlace para admitir equipos de fax y dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="ce80a-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="ce80a-157">En la siguiente ilustración se muestra una topología típica para una implementación de solo VoIP.</span><span class="sxs-lookup"><span data-stu-id="ce80a-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="ce80a-158">**Opción de implementación solo de VoIP**</span><span class="sxs-lookup"><span data-stu-id="ce80a-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="ce80a-159">![Opción de implementación en entorno virgen](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opción de implementación en entorno virgen")</span><span class="sxs-lookup"><span data-stu-id="ce80a-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce80a-160">La ruta multimedia que se muestra en esta figura tiene habilitada la omisión de medios (configuración recomendada).</span><span class="sxs-lookup"><span data-stu-id="ce80a-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="ce80a-161">Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ce80a-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

