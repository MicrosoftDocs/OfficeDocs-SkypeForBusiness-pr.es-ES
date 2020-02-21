---
title: 'Lync Server 2013: opciones de implementación SIP directa'
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
ms.openlocfilehash: e521e1665361e15fffdf1e058731d04bc2eb9aa4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="a553b-102">Opciones de implementación SIP directa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a553b-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a553b-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a553b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a553b-104">En este tema se proporcionan ejemplos de topologías para implementar conexiones SIP directas.</span><span class="sxs-lookup"><span data-stu-id="a553b-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="a553b-105">Lync Server independiente</span><span class="sxs-lookup"><span data-stu-id="a553b-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="a553b-106">Si su organización usa una de las implementaciones descritas en esta sección, puede usar Lync Server 2013 como solución de telefonía única para una parte o la totalidad de una organización.</span><span class="sxs-lookup"><span data-stu-id="a553b-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="a553b-107">En esta sección se describen las siguientes implementaciones en detalle:</span><span class="sxs-lookup"><span data-stu-id="a553b-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="a553b-108">**Implementación incremental:** Esta opción presupone que tiene una infraestructura existente de central de conmutación (PBX) y que pretende presentar la telefonía IP empresarial incrementalmente a grupos más pequeños o a equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="a553b-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="a553b-109">**Implementación de Lync Server con VoIP-only:** esta opción presupone que está pensando en implementar Enterprise Voice en un sitio que no tiene una infraestructura de telefonía tradicional.</span><span class="sxs-lookup"><span data-stu-id="a553b-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="a553b-110">Implementación incremental</span><span class="sxs-lookup"><span data-stu-id="a553b-110">Incremental Deployment</span></span>

<span data-ttu-id="a553b-111">En la implementación incremental, Lync Server 2013 es la única solución de telefonía para equipos o departamentos individuales, mientras que el resto de los usuarios de una organización siguen usando una PBX.</span><span class="sxs-lookup"><span data-stu-id="a553b-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="a553b-112">Esta estrategia de implementación incremental proporciona una forma de introducir la telefonía IP en su empresa a través de programas piloto controlados.</span><span class="sxs-lookup"><span data-stu-id="a553b-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="a553b-113">Los grupos de trabajo cuyas comunicaciones unificadas de Microsoft atienden mejor a las necesidades de comunicación se mueven a telefonía IP empresarial, mientras que otros usuarios permanecen en la PBX existente.</span><span class="sxs-lookup"><span data-stu-id="a553b-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="a553b-114">Los grupos de trabajo adicionales se pueden migrar a la telefonía IP empresarial, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a553b-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="a553b-115">Se recomienda usar la opción incremental si tiene definidos claramente los grupos de usuarios con requisitos de comunicación en común y que se presten a una administración centralizada.</span><span class="sxs-lookup"><span data-stu-id="a553b-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="a553b-116">Esta opción también es efectiva si tiene equipos o departamentos que se propagan en áreas geográficas anchas, donde el ahorro en los gastos de larga distancia puede ser significativo.</span><span class="sxs-lookup"><span data-stu-id="a553b-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="a553b-117">De hecho, esta opción es útil para crear equipos virtuales cuyos miembros pueden estar dispersos por todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="a553b-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="a553b-118">Puede crear, modificar o Disband estos equipos en una respuesta rápida para cambiar los requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="a553b-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="a553b-119">En la siguiente figura se muestra la topología genérica para la implementación de telefonía IP empresarial detrás de una PBX.</span><span class="sxs-lookup"><span data-stu-id="a553b-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="a553b-120">Esta es la topología recomendada para la implementación incremental.</span><span class="sxs-lookup"><span data-stu-id="a553b-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="a553b-121">**Opción de implementación incremental**</span><span class="sxs-lookup"><span data-stu-id="a553b-121">**Incremental deployment option**</span></span>

<span data-ttu-id="a553b-122">![Diagrama de opción de migración departamental](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagrama de opción de migración departamental")</span><span class="sxs-lookup"><span data-stu-id="a553b-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a553b-123">Si va a conectar su implementación de Lync Server a un socio de SIP directo certificado, no se requiere una puerta de enlace de red telefónica conmutada (RTC) entre el servidor de mediación y la PBX.</span><span class="sxs-lookup"><span data-stu-id="a553b-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="a553b-124">Para obtener una lista de asociados de SIP directos certificados, consulte el sitio web del programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft en <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span><span class="sxs-lookup"><span data-stu-id="a553b-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a553b-125">La ruta de medios que se muestra en esta figura tiene habilitada la omisión de medios (la configuración recomendada).</span><span class="sxs-lookup"><span data-stu-id="a553b-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="a553b-126">Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a553b-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="a553b-127">En esta topología, los departamentos o grupos de trabajo seleccionados están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a553b-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="a553b-128">Una puerta de enlace RTC vincula el grupo de trabajo de voz sobre protocolo de Internet (VoIP) habilitado a la PBX.</span><span class="sxs-lookup"><span data-stu-id="a553b-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="a553b-129">Los usuarios que están habilitados para telefonía IP empresarial, incluidos los trabajadores remotos, se comunican a través de la red IP.</span><span class="sxs-lookup"><span data-stu-id="a553b-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="a553b-130">Las llamadas de los usuarios de Enterprise Voice a la RTC y a los compañeros de trabajo que no están habilitados para la telefonía IP empresarial se enrutan a la puerta de enlace RTC correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a553b-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="a553b-131">Las llamadas de compañeros que todavía están en el sistema PBX, o de las personas que llaman en la RTC, se enrutan a la puerta de enlace RTC, que reenvía las llamadas a Lync Server para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a553b-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="a553b-132">Hay dos configuraciones recomendadas para conectar telefonía IP empresarial a una infraestructura PBX existente para la interoperabilidad: telefonía IP empresarial detrás de PBX y telefonía IP empresarial delante de la PBX.</span><span class="sxs-lookup"><span data-stu-id="a553b-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="a553b-133">Telefonía IP empresarial detrás del PBX</span><span class="sxs-lookup"><span data-stu-id="a553b-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="a553b-134">Cuando se implementa la telefonía IP empresarial tras la PBX, todas las llamadas de la RTC llegan a la PBX, que enruta las llamadas a los usuarios de Enterprise Voice a una puerta de enlace RTC y llama a los usuarios de PBX a la PBX.</span><span class="sxs-lookup"><span data-stu-id="a553b-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="a553b-135">Telefonía IP empresarial delante de la PBX</span><span class="sxs-lookup"><span data-stu-id="a553b-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="a553b-136">Cuando se implementa la telefonía IP empresarial delante de la PBX, todas las llamadas llegan a la puerta de enlace RTC, que enruta las llamadas de los usuarios de Enterprise Voice a Lync Server y llama a los usuarios de PBX a la PBX.</span><span class="sxs-lookup"><span data-stu-id="a553b-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="a553b-137">Las llamadas a la RTC desde los usuarios de Enterprise Voice y PBX se enrutan a través de la red IP a la puerta de enlace RTC más rentable.</span><span class="sxs-lookup"><span data-stu-id="a553b-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="a553b-138">En la siguiente tabla se muestran las ventajas y desventajas de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="a553b-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="a553b-139">Ventajas y desventajas de la implementación de la telefonía IP empresarial en la parte frontal de la PBX</span><span class="sxs-lookup"><span data-stu-id="a553b-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a553b-140">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a553b-140">Advantages</span></span></th>
<th><span data-ttu-id="a553b-141">Desventajas</span><span class="sxs-lookup"><span data-stu-id="a553b-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a553b-142">PBX todavía da servicio a los usuarios que no están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a553b-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="a553b-143">Es posible que las puertas de enlace existentes no admitan las características o la capacidad que desee.</span><span class="sxs-lookup"><span data-stu-id="a553b-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a553b-144">PBX controla todos los dispositivos anteriores.</span><span class="sxs-lookup"><span data-stu-id="a553b-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="a553b-145">Requiere un tronco desde la puerta de enlace al PBX y desde la puerta de enlace al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a553b-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="a553b-146">Es posible que necesite más troncos del proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="a553b-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a553b-147">Los usuarios de Enterprise Voice mantienen los mismos números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="a553b-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="a553b-148">Implementación de solo VoIP de Lync Server</span><span class="sxs-lookup"><span data-stu-id="a553b-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="a553b-149">La telefonía IP empresarial proporciona nuevas empresas y también nuevos sitios de Office para las empresas existentes, con la oportunidad de implementar una solución VoIP completa sin tener que preocuparse de la integración de PBX o incurrir en la implementación y el mantenimiento importantes. costos de una infraestructura de IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="a553b-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="a553b-150">Esta solución admite tanto a los trabajadores en el sitio como a los remotos.</span><span class="sxs-lookup"><span data-stu-id="a553b-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="a553b-151">En esta implementación, todas las llamadas se enrutan a través de la red IP.</span><span class="sxs-lookup"><span data-stu-id="a553b-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="a553b-152">Las llamadas a la RTC se enrutan a la puerta de enlace RTC correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a553b-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="a553b-153">Lync 2013 o Lync Phone Edition sirve como softphone.</span><span class="sxs-lookup"><span data-stu-id="a553b-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="a553b-154">El control remoto de llamadas no está disponible y no es necesario porque no hay teléfonos PBX para que los usuarios los controlen.</span><span class="sxs-lookup"><span data-stu-id="a553b-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="a553b-155">Los servicios de correo de voz y de operador automático están disponibles a través de la implementación opcional de mensajería unificada (UM) de Exchange.</span><span class="sxs-lookup"><span data-stu-id="a553b-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a553b-156">Además de la infraestructura de red necesaria para admitir Lync Server 2013, una implementación de solo VoIP puede usar una puerta de enlace de uso reducido para admitir equipos de fax y dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="a553b-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="a553b-157">En la siguiente figura se muestra una topología típica para una implementación de solo VoIP.</span><span class="sxs-lookup"><span data-stu-id="a553b-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="a553b-158">**Opción de implementación de solo VoIP**</span><span class="sxs-lookup"><span data-stu-id="a553b-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="a553b-159">![Opción de implementación de en entorno virgen](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opción de implementación de en entorno virgen")</span><span class="sxs-lookup"><span data-stu-id="a553b-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a553b-160">La ruta de medios que se muestra en esta figura tiene habilitada la omisión de medios (la configuración recomendada).</span><span class="sxs-lookup"><span data-stu-id="a553b-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="a553b-161">Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="a553b-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

