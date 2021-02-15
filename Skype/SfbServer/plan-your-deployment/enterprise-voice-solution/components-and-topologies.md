---
title: Componentes y topologías para el control de admisión de llamadas en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planificación del control de admisión de llamadas (CAC) si tiene una red MPLS, un tronco SIP o una puerta de enlace RTC o PBX de terceros. Se aplica a skype empresarial server Telefonía IP empresarial.
ms.openlocfilehash: e40525121020259a40f10d90cd79d70aaa749ac3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825850"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="1ec44-104">Componentes y topologías para el control de admisión de llamadas en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1ec44-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="1ec44-105">Planificación del control de admisión de llamadas (CAC) si tiene una red MPLS, un tronco SIP o una puerta de enlace RTC o PBX de terceros.</span><span class="sxs-lookup"><span data-stu-id="1ec44-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="1ec44-106">Se aplica a skype empresarial server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="1ec44-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="1ec44-107">Los temas de esta sección ofrecen información acerca de las consideraciones especiales para implementar el control de admisión de llamadas (CAC) con diversos tipos de topologías de red.</span><span class="sxs-lookup"><span data-stu-id="1ec44-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="1ec44-108">Control de admisión de llamadas en una red MPLS</span><span class="sxs-lookup"><span data-stu-id="1ec44-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="1ec44-p103">En una red de conmutación de etiquetas multiprotocolo (MPLS), todos los sitios se conectan mediante una malla completa. Es decir, todos los sitios se conectan directamente a la red troncal del proveedor del servicio de internet MPLS, y se proporciona ancho de banda a todos los sitios para que lo usen a través de un vínculo WAN a la nube MPLS. No existe ningún concentrador de red ni ningún sitio central que controle el enrutamiento IP. En la siguiente figura se muestra una red sencilla basada en la tecnología MPLS.</span><span class="sxs-lookup"><span data-stu-id="1ec44-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="1ec44-113">**Red MPLS de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="1ec44-113">**Example MPLS network**</span></span>

![CAC con MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="1ec44-p104">Para implementar el control admisión de llamadas (CAC) en una red MPLS, debe crear una región de red que represente la nube MPLS y un sitio de red que represente cada uno de los sitios satélite MPLS. En la siguiente figura se muestra cómo deberán configurarse la región de red y los sitios de red para representar la red MPLS de ejemplo de la figura anterior. Los límites de ancho de banda generales y los límites de sesión de ancho de banda se basan en la capacidad del vínculo WAN desde el sitio de red hasta la región de red que representa la nube MPLS.</span><span class="sxs-lookup"><span data-stu-id="1ec44-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="1ec44-118">**Región de red y sitios de red para una red MPLS**</span><span class="sxs-lookup"><span data-stu-id="1ec44-118">**Network region and network sites for an MPLS network**</span></span>

![Control de admisión de llamadas (CAC) con diagrama MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="1ec44-120">Control de admisión de llamadas en un tronco SIP</span><span class="sxs-lookup"><span data-stu-id="1ec44-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="1ec44-p105">Para implementar el control de admisión de llamadas (CAC) en un tronco SIP, debe crear un sitio de red para representar al proveedor de servicios de telefonía de Internet (ITSP). Para aplicar valores de directivas de ancho de banda al tronco SIP, debe crear una directiva entre el sitio de red de su empresa y el sitio de red que cree para representar al ITSP.</span><span class="sxs-lookup"><span data-stu-id="1ec44-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="1ec44-123">La siguiente ilustración muestra un ejemplo de implementación de CAC en un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="1ec44-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="1ec44-124">**Configuración de CAC en un tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="1ec44-124">**CAC configuration on a SIP trunk**</span></span>

![Diagrama de enlace troncal SIP de control de admisión de llamadas](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="1ec44-126">Para configurar el CAC en un tronco SIP, deberá realizar las siguientes tareas durante la implementación de CAC:</span><span class="sxs-lookup"><span data-stu-id="1ec44-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="1ec44-127">Cree un sitio de red para representar al ITSP.</span><span class="sxs-lookup"><span data-stu-id="1ec44-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="1ec44-128">Asocie el sitio de red a una región de red adecuada y asigne un ancho de banda de cero para el audio y el vídeo de este sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1ec44-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="1ec44-129">Para ver más detalles, consulte [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="1ec44-129">For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ec44-130">Para el ITSP, no funciona esta configuración de sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1ec44-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="1ec44-131">Los valores de la directiva de ancho de banda se aplican, en realidad, en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="1ec44-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="1ec44-132">Cree un vínculo entre sitios para el tronco SIP, usando los valores de los parámetros correspondientes al sitio que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="1ec44-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="1ec44-133">Por ejemplo, use el nombre del sitio de red de su empresa como el valor del parámetro NetworkSiteID1 y el sitio de red ITSP como el valor del parámetro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="1ec44-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="1ec44-134">Para obtener más información, consulte Crear directivas entre sitios de red en [Skype Empresarial Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) en la documentación sobre implementación y [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1ec44-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="1ec44-135">Obtiene la dirección IP del punto de terminación de medios del controlador de borde de sesión (SCB) de tu ITSP.</span><span class="sxs-lookup"><span data-stu-id="1ec44-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="1ec44-136">Agregue esa dirección IP con una máscara de subred de 32 al sitio de red que representa al ITSP.</span><span class="sxs-lookup"><span data-stu-id="1ec44-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="1ec44-137">Para ver más detalles, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ec44-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="1ec44-138">Control de admisión de llamadas con una puerta de enlace RTC o PBX de terceros</span><span class="sxs-lookup"><span data-stu-id="1ec44-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="1ec44-139">En este tema se describen ejemplos de cómo se puede implementar el control de admisión de llamadas (CAC) en el vínculo entre la interfaz de puerta de enlace del servidor de mediación y una puerta de enlace de red telefónica conmutada (RTC) o central de conmutación (PBX) de terceros.</span><span class="sxs-lookup"><span data-stu-id="1ec44-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="1ec44-140">Caso 1: Control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="1ec44-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="1ec44-141">El CAC se puede implementar en el vínculo WAN desde la interfaz de puerta de enlace del servidor de mediación a una puerta de enlace RTC o PBX de terceros.</span><span class="sxs-lookup"><span data-stu-id="1ec44-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="1ec44-142">**Caso 1: Control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC**</span><span class="sxs-lookup"><span data-stu-id="1ec44-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Caso 1: CAC entre la puerta de enlace RTC del servidor de mediación](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="1ec44-144">En este ejemplo, el control de admisión de llamadas se aplica entre el servidor de mediación y una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="1ec44-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="1ec44-145">Si un usuario de cliente de Skype Empresarial en el sitio de red 1 hace una llamada RTC a través de la puerta de enlace RTC en el sitio de red 2, los medios fluyen a través del vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="1ec44-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="1ec44-146">Por tanto, se llevan a cabo dos comprobaciones de control de admisión de llamadas para cada sesión RTC:</span><span class="sxs-lookup"><span data-stu-id="1ec44-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="1ec44-147">Entre la aplicación cliente de Skype Empresarial y el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1ec44-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="1ec44-148">Entre el servidor de mediación y la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="1ec44-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="1ec44-149">Esto funciona tanto para las llamadas RTC entrantes a un cliente en el Sitio de red 1 como para las llamadas RTC salientes desde una aplicación cliente en el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="1ec44-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-150">Asegúrese de que la subred IP a la que pertenezca la puerta de enlace RTC esté configurada y asociada con el Sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="1ec44-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-151">Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="1ec44-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-152">Para ver más detalles, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ec44-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="1ec44-153">Caso 2: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con punto de terminación de medios (MTP, Media Termination Point)</span><span class="sxs-lookup"><span data-stu-id="1ec44-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="1ec44-p111">Esta configuración es similar a la del Caso 1. En ambos casos, el servidor de mediación sabe en qué dispositivo terminan los medios en el extremo opuesto del vínculo WAN, y la dirección IP de la puerta de enlace RTC o de la PBX que tiene el MTP está configurada en el servidor de mediación como siguiente salto.</span><span class="sxs-lookup"><span data-stu-id="1ec44-p111">This configuration is similar to Case 1. In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="1ec44-156">**Caso 2: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con MTP**</span><span class="sxs-lookup"><span data-stu-id="1ec44-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Caso 2: CAC entre PBX del servidor de mediación con MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="1ec44-158">En este ejemplo, el control de admisión de llamadas se aplica entre el servidor de mediación y el MTP o la PBX.</span><span class="sxs-lookup"><span data-stu-id="1ec44-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="1ec44-159">Si un usuario de cliente de Skype Empresarial en el sitio de red 1 hace una llamada RTC a través de la PBX/MTP ubicada en el sitio de red 2, los medios fluyen a través del vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="1ec44-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="1ec44-160">Por tanto, se llevan a cabo dos comprobaciones de control de admisión de llamadas para cada sesión RTC:</span><span class="sxs-lookup"><span data-stu-id="1ec44-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="1ec44-161">Entre la aplicación cliente de Skype Empresarial y el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1ec44-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="1ec44-162">Entre el servidor de mediación y la PBX o el MTP</span><span class="sxs-lookup"><span data-stu-id="1ec44-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="1ec44-163">Esto funciona tanto para las llamadas RTC entrantes a un cliente en el Sitio de red 1 como para las llamadas RTC salientes desde un cliente en el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="1ec44-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-164">Asegúrese de que la subred IP a la que pertenezca el MTP esté configurada y asociada con el Sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="1ec44-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-165">Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="1ec44-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-166">Para ver más detalles, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ec44-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="1ec44-167">Caso 3: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP</span><span class="sxs-lookup"><span data-stu-id="1ec44-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="1ec44-p113">El Caso 3 es ligeramente diferente a los dos primeros casos. Si no hay ningún MTP en la PBX de terceros, en el caso de una solicitud de sesión saliente enviada a la PBX de terceros, el servidor de mediación no sabe dónde terminarán los medios en el límite de la PBX. En tal caso, los medios se transmiten directamente entre el servidor de mediación y el dispositivo del extremo de terceros.</span><span class="sxs-lookup"><span data-stu-id="1ec44-p113">Case 3 is slightly different from the first two cases. If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary. In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="1ec44-171">**Caso 3: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP**</span><span class="sxs-lookup"><span data-stu-id="1ec44-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Caso 3: CAC entre PBX del servidor de mediación sin MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="1ec44-173">En este ejemplo, si un usuario de cliente de Skype Empresarial en el sitio de red 1 realiza una llamada a un usuario a través de la PBX, el servidor de mediación solo puede realizar comprobaciones de CAC en la parte de proxy (entre la aplicación cliente de Skype Empresarial y el servidor de mediación).</span><span class="sxs-lookup"><span data-stu-id="1ec44-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="1ec44-174">Dado que el servidor de mediación no tiene información sobre el dispositivo del extremo, durante el proceso de solicitud de la sesión, no pueden realizarse comprobaciones de control de admisión de llamadas en el vínculo WAN (entre el servidor de mediación y el extremo de terceros) antes del establecimiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="1ec44-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="1ec44-175">Sin embargo, una vez establecida la sesión, el servidor de mediación facilita la cantidad de ancho de banda usada en el tronco.</span><span class="sxs-lookup"><span data-stu-id="1ec44-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="1ec44-176">Para las llamadas realizadas desde el extremo de terceros, la información sobre el dispositivo del extremo está disponible en el momento de la solicitud de la sesión y la comprobación de control de admisión de llamadas puede realizarse en ambas partes del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="1ec44-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-177">Asegúrese de que la subred IP a la que pertenezca el dispositivo del extremo esté configurada y asociada con el Sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="1ec44-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-178">Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="1ec44-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-179">Para ver más detalles, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ec44-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


