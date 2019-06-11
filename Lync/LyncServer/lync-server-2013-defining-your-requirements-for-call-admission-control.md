---
title: 'Lync Server 2013: Definición de los requisitos de la organización para el servicio de control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7737d303c7239df451c71b4f92d4dcd8dfe5b2e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="739d1-102">Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="739d1-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="739d1-103">_**Última modificación del tema:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="739d1-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="739d1-p101">La planificación del servicio de control de admisión de llamadas (CAC) requiere información detallada sobre la topología de red de la empresa. Para obtener ayuda para planificar las directivas del servicio de control de admisión de llamadas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="739d1-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="739d1-106">Identifica los concentradores o las redes troncales (denominados *regiones de red*) dentro de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="739d1-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="739d1-107">Identifica las oficinas o las ubicaciones (denominadas *sitios de red*) dentro de cada región de red.</span><span class="sxs-lookup"><span data-stu-id="739d1-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="739d1-108">Determina la ruta de red entre cada par de regiones de red.</span><span class="sxs-lookup"><span data-stu-id="739d1-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="739d1-109">Determina los límites de ancho de banda para cada vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="739d1-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="739d1-110">Los límites de ancho de banda hacen referencia a la parte del ancho de banda de un vínculo WAN que se asigna a la telefonía IP empresarial y al tráfico de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="739d1-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="739d1-111">Cuando un vínculo WAN se describe como “con ancho de banda restringido”, tiene un límite de ancho de banda inferior al tráfico máximo esperado a través del vínculo.</span><span class="sxs-lookup"><span data-stu-id="739d1-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="739d1-112">Identifica las subredes IP asignadas a cada sitio de red.</span><span class="sxs-lookup"><span data-stu-id="739d1-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="739d1-113">Para explicar estos conceptos, usaremos la topología de red de ejemplo que se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="739d1-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="739d1-114">**Topología de ejemplo para el servicio de control de admisión de llamadas**</span><span class="sxs-lookup"><span data-stu-id="739d1-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="739d1-115">![Ejemplo de topología de red de Litware Inc.] (images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Ejemplo de topología de red de Litware Inc.")</span><span class="sxs-lookup"><span data-stu-id="739d1-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="739d1-p103">Todos los sitios de red están asociados a una región de red. Por ejemplo, Portland, Reno y Albuquerque están incluidos en la región Norteamérica. En esta figura, solo se muestran los vínculos WAN que tienen aplicadas directivas de CAC con límites de ancho de banda. Los sitios de red de Chicago, Nueva York y Detroit aparecen dentro del óvalo regional Norteamérica porque no tienen ancho de banda restringido y, por lo tanto, no precisan directivas de CAC.</span><span class="sxs-lookup"><span data-stu-id="739d1-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="739d1-120">Los componentes de esta topología de ejemplo se explican en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="739d1-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="739d1-121">Para obtener más información sobre cómo se planificó esta topología, incluidos los límites de ancho de banda, vea [ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="739d1-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="739d1-122">Identificar regiones de red</span><span class="sxs-lookup"><span data-stu-id="739d1-122">Identify Network Regions</span></span>

<span data-ttu-id="739d1-123">Una región de red representa una red troncal de red o un concentrador de red.</span><span class="sxs-lookup"><span data-stu-id="739d1-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="739d1-p105">Un concentrador de red o una red troncal es parte de la infraestructura de una red informática que interconecta las diferentes partes de la red, lo que proporciona una ruta de acceso para el intercambio de información entre las diferentes LAN o subredes. Una red troncal puede enlazar diversas redes, ya sea de una pequeña ubicación a una extensa área geográfica. Con frecuencia, la capacidad de la red troncal es mayor que la de las redes que se conectan a ella.</span><span class="sxs-lookup"><span data-stu-id="739d1-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="739d1-p106">Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red contiene un grupo de sitios de red (vea la definición de sitios de red que aparece más adelante en este tema). Trabaja con el equipo de operaciones de red para identificar tus regiones de red.</span><span class="sxs-lookup"><span data-stu-id="739d1-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="739d1-130">Asociar un sitio central a cada región de red</span><span class="sxs-lookup"><span data-stu-id="739d1-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="739d1-131">CAC requiere que se defina un sitio central de Lync Server para cada región de red.</span><span class="sxs-lookup"><span data-stu-id="739d1-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="739d1-132">El sitio central está seleccionado con la mejor conectividad de red y el mayor ancho de banda respecto al resto de sitios dentro de esa región de la red.</span><span class="sxs-lookup"><span data-stu-id="739d1-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="739d1-133">El ejemplo anterior de topología de red muestra tres regiones de red, cada una con un sitio central que administra las decisiones de CAC.</span><span class="sxs-lookup"><span data-stu-id="739d1-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="739d1-134">En el ejemplo anterior, la asociación correspondiente se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="739d1-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="739d1-135">Los sitios centrales no corresponden necesariamente a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="739d1-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="739d1-136">En los ejemplos de esta documentación, algunos sitios centrales (Chicago, Londres y Pekín) comparten el mismo nombre que los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="739d1-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="739d1-137">Sin embargo, incluso si un sitio central y un sitio de red comparten el mismo nombre, el sitio central es un elemento de la topología de Lync Server, mientras que el sitio de red es parte de la red general en la que reside la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="739d1-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="739d1-138">Regiones de red, sitios centrales y sitios de red</span><span class="sxs-lookup"><span data-stu-id="739d1-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="739d1-139">Región de red</span><span class="sxs-lookup"><span data-stu-id="739d1-139">Network Region</span></span></th>
<th><span data-ttu-id="739d1-140">Sitio central</span><span class="sxs-lookup"><span data-stu-id="739d1-140">Central Site</span></span></th>
<th><span data-ttu-id="739d1-141">Sitios de red</span><span class="sxs-lookup"><span data-stu-id="739d1-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="739d1-142">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="739d1-142">North America</span></span></p></td>
<td><p><span data-ttu-id="739d1-143">Chicago</span><span class="sxs-lookup"><span data-stu-id="739d1-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="739d1-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="739d1-144">Chicago</span></span></p>
<p><span data-ttu-id="739d1-145">Nueva York</span><span class="sxs-lookup"><span data-stu-id="739d1-145">New York</span></span></p>
<p><span data-ttu-id="739d1-146">Detroit</span><span class="sxs-lookup"><span data-stu-id="739d1-146">Detroit</span></span></p>
<p><span data-ttu-id="739d1-147">Portland</span><span class="sxs-lookup"><span data-stu-id="739d1-147">Portland</span></span></p>
<p><span data-ttu-id="739d1-148">Reno</span><span class="sxs-lookup"><span data-stu-id="739d1-148">Reno</span></span></p>
<p><span data-ttu-id="739d1-149">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="739d1-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="739d1-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="739d1-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="739d1-151">Londres</span><span class="sxs-lookup"><span data-stu-id="739d1-151">London</span></span></p></td>
<td><p><span data-ttu-id="739d1-152">Londres</span><span class="sxs-lookup"><span data-stu-id="739d1-152">London</span></span></p>
<p><span data-ttu-id="739d1-153">Colonia</span><span class="sxs-lookup"><span data-stu-id="739d1-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="739d1-154">APAC</span><span class="sxs-lookup"><span data-stu-id="739d1-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="739d1-155">Pekín</span><span class="sxs-lookup"><span data-stu-id="739d1-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="739d1-156">Pekín</span><span class="sxs-lookup"><span data-stu-id="739d1-156">Beijing</span></span></p>
<p><span data-ttu-id="739d1-157">Manila</span><span class="sxs-lookup"><span data-stu-id="739d1-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="739d1-158">Identificar sitios de red</span><span class="sxs-lookup"><span data-stu-id="739d1-158">Identify Network Sites</span></span>

<span data-ttu-id="739d1-p109">Un sitio de red representa una ubicación en la que la organización tiene un local físico, por ejemplo, oficinas, un conjunto de edificios o un campus. Un local físico con una LAN y que tiene conectividad WAN con otros sitios se considera un sitio de red. Comienza por realizar un inventario de las oficinas de la organización. En nuestra topología de ejemplo, la región de red Norteamérica está formada por los siguientes sitios de red: Nueva York, Chicago, Detroit, Portland, Reno y Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="739d1-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="739d1-p110">Necesitas asociar todos los sitios de red con una región de red. En función de si el sitio de red tiene un vínculo WAN restringido, se asocia una directiva de ancho de banda con el sitio de red. Para obtener más detalles sobre las directivas de CAC y el ancho de banda que se asigna con ellas, mira "Definir directivas de ancho de banda" más adelante en este tema. Para configurar el CAC, asocia sitios de red con regiones de red y, luego, crea directivas de asignación de ancho de banda para aplicarlas a las conexiones con ancho de banda restringido entre un sitio o una región determinado y las conexiones WAN entre los sitios y las regiones.</span><span class="sxs-lookup"><span data-stu-id="739d1-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="739d1-167">Identificar vínculos de red</span><span class="sxs-lookup"><span data-stu-id="739d1-167">Identify Network Links</span></span>

<span data-ttu-id="739d1-p111">Los vínculos de red representan conexiones a la WAN física que vincula diferentes regiones y sitios. En nuestra topología de ejemplo, hay dos vínculos de red regional, cinco vínculos de red entre regiones y sitios, y un vínculo de red entre dos sitios.</span><span class="sxs-lookup"><span data-stu-id="739d1-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="739d1-170">Los dos vínculos de red regional están entre Norteamérica y EMEA, representado como NA-EMEA-LINK y entre APAC y EMEA, representado como EMEA-APAC-LINK.</span><span class="sxs-lookup"><span data-stu-id="739d1-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="739d1-p112">Los vínculos de sitios se indican con las líneas que conectan Portland, Reno y Albuquerque con la región Norteamérica, Manila con la región APAC y Colonia con la región EMEA. La línea entre Reno y Albuquerque muestra un vínculo de red directo entre estos dos sitios.</span><span class="sxs-lookup"><span data-stu-id="739d1-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="739d1-173">Definir directivas de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="739d1-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="739d1-p113">Colabora con el equipo de operaciones de red para determinar la cantidad de ancho de banda WAN disponible para el tráfico de audio y vídeo en tiempo real a través de los vínculos WAN de la organización. Normalmente, las directivas de ancho de banda se aplican a vínculos WAN si el uso del ancho de banda está restringido; es decir, si se espera que sea mayor que el ancho de banda que se puede asignar para modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="739d1-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="739d1-p114">Las *directivas de ancho de banda* de CAC definen el ancho de banda máximo que se puede reservar para las modalidades de audio y vídeo en tiempo real. Ya que CAC no limita el ancho de banda de otro tráfico, no puede evitar que el tráfico de otros datos, como una transferencia de archivos grande o un streaming de música, use todo el ancho de banda de la red.</span><span class="sxs-lookup"><span data-stu-id="739d1-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="739d1-178">Las directivas de ancho de banda del CAC pueden definir cualquiera de las siguientes opciones o todas ellas:</span><span class="sxs-lookup"><span data-stu-id="739d1-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="739d1-179">Ancho de banda total máximo asignado para audio.</span><span class="sxs-lookup"><span data-stu-id="739d1-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="739d1-180">Ancho de banda total máximo asignado para vídeo.</span><span class="sxs-lookup"><span data-stu-id="739d1-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="739d1-181">Ancho de banda máximo asignado para una única llamada de audio (sesión).</span><span class="sxs-lookup"><span data-stu-id="739d1-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="739d1-182">Ancho de banda máximo asignado para una única videollamada (sesión).</span><span class="sxs-lookup"><span data-stu-id="739d1-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="739d1-183">Todos los valores de ancho de banda de CAC representan los límites máximos de ancho de banda <EM>unidireccional</EM>.</span><span class="sxs-lookup"><span data-stu-id="739d1-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="739d1-184">Las características de la Directiva de voz de Lync Server 2013 proporcionan la capacidad de invalidar las comprobaciones de la Directiva de ancho de banda para las llamadas entrantes al usuario (no para las llamadas salientes que son colocadas por el usuario).</span><span class="sxs-lookup"><span data-stu-id="739d1-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="739d1-185">Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="739d1-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="739d1-186">Esta configuración se tiene que usar con moderación.</span><span class="sxs-lookup"><span data-stu-id="739d1-186">This setting should be used sparingly.</span></span> <span data-ttu-id="739d1-187">Para obtener más información, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">crear una directiva de voz y configurar los registros de uso de RTC en Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="739d1-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="739d1-p116">Para optimizar la utilización del ancho de banda por sesión, ten en cuenta el tipo de códecs de audio y vídeo que se van a usar. En concreto, evita una asignación insuficiente de ancho de banda a un códec que crees que se va a usar con frecuencia. Por el contrario, si deseas evitar que los medios usen un códec que precisa mayor ancho de banda, deberás establecer un ancho de banda máximo por sesión lo suficientemente bajo para disuadir su uso. En lo que respecta al audio, no todos los códecs están disponibles para todos los escenarios. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="739d1-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="739d1-193">Las llamadas de audio de punto a punto entre puntos de conexión de Lync usarán RTAudio (8kHz) o RTAudio (16kHz) cuando se Factoran en el ancho de banda y en la priorización de los códecs.</span><span class="sxs-lookup"><span data-stu-id="739d1-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="739d1-194">Las llamadas en conferencia entre puntos de conexión de Lync y el servicio de conferencia A/V usarán G. 722 o Siren.</span><span class="sxs-lookup"><span data-stu-id="739d1-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="739d1-195">Las llamadas a la red de telefonía pública conmutada (RTC) a o desde puntos de conexión de Lync usarán G. 711 o RTAudio (8kHz).</span><span class="sxs-lookup"><span data-stu-id="739d1-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="739d1-196">Usa la tabla que aparece a continuación para optimizar la configuración del ancho de banda máximo por sesión.</span><span class="sxs-lookup"><span data-stu-id="739d1-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="739d1-197">Utilización de ancho de banda por códecs</span><span class="sxs-lookup"><span data-stu-id="739d1-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="739d1-198">Códec</span><span class="sxs-lookup"><span data-stu-id="739d1-198">Codec</span></span></th>
<th><span data-ttu-id="739d1-199">Requisito de ancho de banda sin corrección de errores de reenvío (FEC)</span><span class="sxs-lookup"><span data-stu-id="739d1-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="739d1-200">Requisito de ancho de banda con corrección de errores de reenvío (FEC)</span><span class="sxs-lookup"><span data-stu-id="739d1-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="739d1-201">RTAudio (8 kHz)</span><span class="sxs-lookup"><span data-stu-id="739d1-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="739d1-202">49,8 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-203">61,6 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="739d1-204">RTAudio (16 kHz)</span><span class="sxs-lookup"><span data-stu-id="739d1-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="739d1-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="739d1-207">Siren</span><span class="sxs-lookup"><span data-stu-id="739d1-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="739d1-208">57,6 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-209">73,6 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="739d1-210">G.711</span><span class="sxs-lookup"><span data-stu-id="739d1-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="739d1-211">102 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="739d1-213">G.722</span><span class="sxs-lookup"><span data-stu-id="739d1-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="739d1-214">105,6 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-215">169,6 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="739d1-216">RTVideo (CIF 15 fps)</span><span class="sxs-lookup"><span data-stu-id="739d1-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="739d1-217">260 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-218">No aplicable</span><span class="sxs-lookup"><span data-stu-id="739d1-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="739d1-219">RTVideo (VGA 30 fps)</span><span class="sxs-lookup"><span data-stu-id="739d1-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="739d1-220">610 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-221">No disponible</span><span class="sxs-lookup"><span data-stu-id="739d1-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="739d1-p117">Los requisitos de ancho de banda tienen en cuenta la sobrecarga para: Ethernet II, IP, Protocolo de datagramas de usuario (UDP), Protocolo de transporte en tiempo real (RTP) y Protocolo de transporte en tiempo real seguro (SRTP). También incluyen 10 kbps para sobrecarga de RTCP.</span><span class="sxs-lookup"><span data-stu-id="739d1-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="739d1-224">Los códecs G.722.1 y Siren son similares, pero ofrecen diferentes velocidades de bits.</span><span class="sxs-lookup"><span data-stu-id="739d1-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="739d1-225">G. 722, el códec predeterminado para conferencias de Lync Server, es completamente diferente de los códecs G. 722.1 y SIREN.</span><span class="sxs-lookup"><span data-stu-id="739d1-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="739d1-226">El códec Siren se usa en Lync Server en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="739d1-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="739d1-227">Si la directiva de ancho de banda tiene un valor demasiado bajo para el uso de G.722.</span><span class="sxs-lookup"><span data-stu-id="739d1-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="739d1-228">Si un cliente de Communications Server 2007 o Communications Server 2007 R2 se conecta a un servicio de conferencias de Lync Server (porque esos clientes no admiten el códec G. 722).</span><span class="sxs-lookup"><span data-stu-id="739d1-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="739d1-229">Utilización de ancho de banda por escenario</span><span class="sxs-lookup"><span data-stu-id="739d1-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="739d1-230">Escenario</span><span class="sxs-lookup"><span data-stu-id="739d1-230">Scenario</span></span></th>
<th><span data-ttu-id="739d1-231">Requisito de ancho de banda optimizado para cantidad (kbps)</span><span class="sxs-lookup"><span data-stu-id="739d1-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="739d1-232">Requisito de ancho de banda para modo de equilibrado (kbps)</span><span class="sxs-lookup"><span data-stu-id="739d1-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="739d1-233">Requisito de ancho de banda optimizado para calidad (kbps)</span><span class="sxs-lookup"><span data-stu-id="739d1-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="739d1-234">Llamadas de audio de punto a punto</span><span class="sxs-lookup"><span data-stu-id="739d1-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="739d1-235">45 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="739d1-238">Llamadas de conferencia</span><span class="sxs-lookup"><span data-stu-id="739d1-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="739d1-239">53 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="739d1-242">Llamadas RTC (entre Lync 2013 y puerta de enlace RTC, con omisión de medios)</span><span class="sxs-lookup"><span data-stu-id="739d1-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="739d1-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="739d1-246">Llamadas RTC (entre Lync 2013 y servidor de mediación, sin omisión de medios)</span><span class="sxs-lookup"><span data-stu-id="739d1-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="739d1-247">45 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="739d1-250">Llamadas RTC (entre el servidor de mediación y la puerta de enlace RTC, sin omisión de medios)</span><span class="sxs-lookup"><span data-stu-id="739d1-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="739d1-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="739d1-254">Lync: las llamadas a Polycom</span><span class="sxs-lookup"><span data-stu-id="739d1-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="739d1-255">101 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-256">101 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="739d1-257">101 kbps</span><span class="sxs-lookup"><span data-stu-id="739d1-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="739d1-258">Identificar subredes IP</span><span class="sxs-lookup"><span data-stu-id="739d1-258">Identify IP Subnets</span></span>

<span data-ttu-id="739d1-p118">Para cada sitio de red, tendrás que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, tu trabajo se habrá simplificado en gran medida.</span><span class="sxs-lookup"><span data-stu-id="739d1-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="739d1-p119">En nuestro ejemplo, el sitio Nueva York de la región Norteamérica tiene asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Demos por supuesto que Alberto, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación. Cuando encienda su PC y se conecte a la red, su PC obtendrá una dirección IP de uno de los cuatro rangos reservados a Nueva York, por ejemplo, 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="739d1-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="739d1-264">Las subredes IP especificadas durante la configuración de red del servidor necesitan coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="739d1-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="739d1-265">Un cliente de Lync toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada.</span><span class="sxs-lookup"><span data-stu-id="739d1-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="739d1-266">Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente.</span><span class="sxs-lookup"><span data-stu-id="739d1-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="739d1-267">Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales.</span><span class="sxs-lookup"><span data-stu-id="739d1-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="739d1-268">(Si implementas el servicio de control de admisión de llamadas, pero no la omisión de medios, el servicio de control de admisión de llamadas funcionará correctamente incluso aunque configures subredes virtuales).</span><span class="sxs-lookup"><span data-stu-id="739d1-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="739d1-269">Por ejemplo, si un cliente inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred IP 255.255.255.0, Lync 2013 le solicitará la identificación de omisión asociada con la subred 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="739d1-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="739d1-270">Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia porque el registrador está buscando específicamente la subred 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="739d1-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="739d1-271">Por lo tanto, es importante que el administrador escriba las subredes exactamente como se proporciona en los clientes de Lync (que se aprovisionan con subredes durante la configuración de la red, ya sea estáticamente o mediante DHCP).</span><span class="sxs-lookup"><span data-stu-id="739d1-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

