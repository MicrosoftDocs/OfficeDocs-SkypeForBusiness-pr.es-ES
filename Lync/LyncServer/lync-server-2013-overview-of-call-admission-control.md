---
title: 'Lync Server 2013: información general sobre el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a72ce-102">Información general sobre el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a72ce-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a72ce-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="a72ce-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="a72ce-104">Las comunicaciones en tiempo real son sensibles a la latencia y la pérdida de paquetes que se pueden producir en redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="a72ce-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="a72ce-105">El control de admisión de llamadas (CAC) determina, en base al ancho de banda de la red disponible, si está permitido establecer sesiones de comunicación en tiempo real, como son las llamadas de voz o vídeo.</span><span class="sxs-lookup"><span data-stu-id="a72ce-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="a72ce-106">El diseño CAC de Lync Server 2013 ofrece cuatro atributos principales:</span><span class="sxs-lookup"><span data-stu-id="a72ce-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="a72ce-107">Es fácil de implementar y administrar, y no requiere equipamiento adicional, como ocurre con los enrutadores especialmente configurados.</span><span class="sxs-lookup"><span data-stu-id="a72ce-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="a72ce-p102">Está dirigido a casos de uso de comunicaciones unificadas críticas, como los escenarios con usuarios remotos o múltiples puntos de presencia. Las directivas del CAC se aplican de acuerdo con el lugar donde se ubica el extremo, no con el lugar donde se hospeda el usuario.</span><span class="sxs-lookup"><span data-stu-id="a72ce-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="a72ce-110">Además de las llamadas de voz, puede aplicarse a otro tráfico, como las videollamadas y las sesiones de conferencia de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="a72ce-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="a72ce-111">Proporciona la flexibilidad necesaria para habilitar la representación de varios tipos de topologías de red.</span><span class="sxs-lookup"><span data-stu-id="a72ce-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="a72ce-112">Para obtener ejemplos, vea [componentes y topologías de CAC en Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="a72ce-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="a72ce-113">Si una sesión de vídeo o voz nueva supera los límites de ancho de banda que se han establecido en un vínculo WAN, la sesión se bloquea o (solo para llamadas telefónicas) se desvía a la RTC.</span><span class="sxs-lookup"><span data-stu-id="a72ce-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="a72ce-p104">El CAC controla el tráfico en tiempo real solo para voz y vídeo. No controla el tráfico de datos.</span><span class="sxs-lookup"><span data-stu-id="a72ce-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="a72ce-116">Los administradores definen las directivas de CAC, que se aplican mediante el servicio de directivas de ancho de banda instalado con cada grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a72ce-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="a72ce-117">La configuración de CAC se propaga automáticamente a todos los servidores front-end de Lync Server de su red.</span><span class="sxs-lookup"><span data-stu-id="a72ce-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="a72ce-118">Para las llamadas en las que se produce un error debido a las directivas del CAC, el orden de prioridad para desviar la llamada es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a72ce-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="a72ce-119">Internet</span><span class="sxs-lookup"><span data-stu-id="a72ce-119">Internet</span></span>

2.  <span data-ttu-id="a72ce-120">RTC</span><span class="sxs-lookup"><span data-stu-id="a72ce-120">PSTN</span></span>

3.  <span data-ttu-id="a72ce-121">Correo de voz</span><span class="sxs-lookup"><span data-stu-id="a72ce-121">Voice mail</span></span>

<span data-ttu-id="a72ce-p106">Información de las capturas del registro de detalles de llamadas (CDR) sobre las llamadas que se desvían a la RTC o al correo de voz. El CDR no captura información sobre las llamadas que se desvían a Internet, ya que Internet se considera una ruta de acceso alternativa en lugar de una opción secundaria.</span><span class="sxs-lookup"><span data-stu-id="a72ce-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a72ce-124">Los depósitos de correo de voz no se denegarán por restricciones del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="a72ce-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="a72ce-p107">El servicio de directivas de ancho de banda genera dos tipos de archivo de registro en formato de valores separados por comas (CSV). El archivo de registro de **errores de comprobación** captura información cuando se deniegan las solicitudes de ancho de banda. El archivo de registro de **uso de vínculos** captura una instantánea de la topología de red y del uso del ancho de banda del vínculo WAN. Estos dos archivos de registro pueden ayudarte a ajustar las directivas del CAC en función del uso.</span><span class="sxs-lookup"><span data-stu-id="a72ce-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="a72ce-129">Consideraciones relacionadas con el servicio de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="a72ce-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="a72ce-130">El administrador elige instalar el servicio de directiva de ancho de banda en el primer grupo configurado en la ubicación central.</span><span class="sxs-lookup"><span data-stu-id="a72ce-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="a72ce-131">Dado que hay una única ubicación central por región de red, solo hay un servicio de directivas de ancho de banda en cada región de red, que administra la directiva de ancho de banda para dicha región, sus sitios asociados y los vínculos a esos sitios.</span><span class="sxs-lookup"><span data-stu-id="a72ce-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="a72ce-132">El servicio de directivas de ancho de banda se ejecuta como parte de los servidores front-end y, por lo tanto, la alta disponibilidad está integrada en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="a72ce-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="a72ce-133">El servicio de directivas de ancho de banda que se ejecuta en cada servidor front-end se sincroniza cada 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="a72ce-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="a72ce-134">Si se produce un error en el grupo de servidores front end, ya no se aplican las directivas CAC para ese sitio hasta que el grupo de servidores front-end y, en consecuencia, el servicio de directivas de ancho de banda vuelva a estar operativo.</span><span class="sxs-lookup"><span data-stu-id="a72ce-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="a72ce-135">Esto implica que todas las llamadas pasarán mientras el servicio de directivas de ancho de banda esté fuera de servicio.</span><span class="sxs-lookup"><span data-stu-id="a72ce-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="a72ce-136">En consecuencia, existe la posibilidad de saturación del ancho de banda de los vínculos durante este período.</span><span class="sxs-lookup"><span data-stu-id="a72ce-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="a72ce-137">El servicio de directivas de ancho de banda proporciona alta disponibilidad dentro de un grupo de servidores front-end; sin embargo, no proporciona redundancia en los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a72ce-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="a72ce-138">El servicio de directivas de ancho de banda no puede realizar la conmutación por error de un grupo front-end a otro.</span><span class="sxs-lookup"><span data-stu-id="a72ce-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="a72ce-139">Una vez que se restaura el servicio al grupo de servidores front-end, el servicio de directivas de ancho de banda se reanuda y puede aplicar de nuevo las comprobaciones de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="a72ce-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="a72ce-140">Consideraciones relacionadas con la red</span><span class="sxs-lookup"><span data-stu-id="a72ce-140">Network Considerations</span></span>

<span data-ttu-id="a72ce-141">Aunque el servicio de directivas de ancho de banda de Lync Server 2013 exige la restricción de ancho de banda para el audio y el vídeo, esta restricción no se aplica al enrutador de red (capa 2 y 3).</span><span class="sxs-lookup"><span data-stu-id="a72ce-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="a72ce-142">Lync Server 2010 CAC no puede impedir que una aplicación de datos consuma todo el ancho de banda de la red en un vínculo de WAN, incluido el ancho de banda reservado para audio y vídeo por la Directiva CAC.</span><span class="sxs-lookup"><span data-stu-id="a72ce-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="a72ce-143">Para proteger el ancho de banda necesario en la red, puedes implementar un protocolo de calidad de servicio (QoS) como, por ejemplo, los servicios diferenciados (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="a72ce-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="a72ce-144">Así pues, el procedimiento recomendado es coordinar las directivas de ancho de banda del CAC que definas con cualquier configuración de QoS que puedas implementar.</span><span class="sxs-lookup"><span data-stu-id="a72ce-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="a72ce-145">Rutas de acceso de señalización y medios sobre VPN</span><span class="sxs-lookup"><span data-stu-id="a72ce-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="a72ce-p111">Si tu empresa admite medios a través de VPN, asegúrate de que tanto la secuencia de medios como la secuencia de señalización pasen por la VPN o se redirijan a través de Internet. De forma predeterminada, las secuencias de medios y de señalización pasan por el túnel VPN.</span><span class="sxs-lookup"><span data-stu-id="a72ce-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="a72ce-148">Servicio de control de admisión de llamadas de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="a72ce-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="a72ce-149">El control de admisión de llamadas no se aplica a los usuarios remotos cuando el tráfico de red fluye a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="a72ce-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="a72ce-150">Dado que el tráfico multimedia atraviesa Internet, que no está administrado por Lync Server, no se puede aplicar CAC.</span><span class="sxs-lookup"><span data-stu-id="a72ce-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="a72ce-151">Sin embargo, se realizarán comprobaciones CACs en la parte de la llamada que fluye a través de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="a72ce-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="a72ce-152">Servicio de control de admisión de llamadas de conexiones RTC</span><span class="sxs-lookup"><span data-stu-id="a72ce-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="a72ce-153">El control de admisión de llamadas es obligatorio en el servidor de mediación, independientemente de si está conectado a un IP/PBX, una puerta de enlace RTC o un tronco de SIP.</span><span class="sxs-lookup"><span data-stu-id="a72ce-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="a72ce-154">Debido a que el servidor de mediación es un agente de usuario inverso (B2BUA), finaliza los medios.</span><span class="sxs-lookup"><span data-stu-id="a72ce-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="a72ce-155">Tiene dos lados de conexión: un lado que está conectado a Lync Server y un lado de puerta de enlace, que está conectado a puertas de enlace RTC, IP/PBX o a troncos de SIP.</span><span class="sxs-lookup"><span data-stu-id="a72ce-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="a72ce-156">Para obtener más información acerca de las conexiones RTC, consulte [planificación de la conectividad RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="a72ce-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="a72ce-157">Se puede aplicar CAC a ambos lados del servidor de mediación, a menos que se habilite la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="a72ce-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="a72ce-158">Si se habilita la omisión de multimedia, el tráfico multimedia no atraviesa el servidor de mediación, sino que se transmite directamente entre el cliente de Lync y la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="a72ce-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="a72ce-159">En este caso, el CAC no es necesario.</span><span class="sxs-lookup"><span data-stu-id="a72ce-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="a72ce-160">Para obtener más información, consulte [planificación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a72ce-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="a72ce-161">En la siguiente figura se muestra cómo se aplica el CAC a las conexiones RTC con la omisión de medios habilitada e inhabilitada.</span><span class="sxs-lookup"><span data-stu-id="a72ce-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="a72ce-162">**Cumplimiento del control de admisión de llamadas en conexiones al RTC**</span><span class="sxs-lookup"><span data-stu-id="a72ce-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="a72ce-163">![Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz")</span><span class="sxs-lookup"><span data-stu-id="a72ce-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="a72ce-164">Compatibilidad del control de admisión de llamadas con versiones anteriores de Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="a72ce-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="a72ce-165">El control de admisión de llamadas solo se puede habilitar en los extremos habilitados para Lync Server 2010 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a72ce-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="a72ce-166">El control de admisión de llamadas no se puede habilitar en los extremos que ejecutan Office Communicator 2007 R2 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a72ce-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="a72ce-167">**Aplicación de CAC en diferentes versiones de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="a72ce-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="a72ce-168">![Diagrama de comparación de versiones de voz CAC](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagrama de comparación de versiones de voz CAC")</span><span class="sxs-lookup"><span data-stu-id="a72ce-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

