---
title: Componentes y topologías para el servicio de control de admisión de llamadas en Skype Empresarial 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planear el servicio de control de admisión de llamadas (CAC) si tiene una red MPLS, un tronco SIP o una puerta de enlace RTC o PBX de terceros. Se aplica a Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: a49c0184c445481146496a9ce90e948f0b1c2f71
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business-2015"></a><span data-ttu-id="fa559-104">Componentes y topologías para el servicio de control de admisión de llamadas en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="fa559-104">Components and topologies for call admission control in Skype for Business 2015</span></span>
 
<span data-ttu-id="fa559-105">Planear el servicio de control de admisión de llamadas (CAC) si tiene una red MPLS, un tronco SIP o una puerta de enlace RTC o PBX de terceros.</span><span class="sxs-lookup"><span data-stu-id="fa559-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="fa559-106">Se aplica a Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa559-106">Applies to Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fa559-107">Los temas de esta sección ofrecen información sobre las consideraciones especiales para implementar el servicio de control de admisión de llamadas (CAC) con diversos tipos de topologías de red.</span><span class="sxs-lookup"><span data-stu-id="fa559-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>
  
## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="fa559-108">Servicio de control de admisión de llamadas en una red MPLS</span><span class="sxs-lookup"><span data-stu-id="fa559-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="fa559-p103">En una red de conmutación de etiquetas multiprotocolo (MPLS), todos los sitios se conectan a través de una malla completa. Es decir, todos los sitios se conectan directamente a la red troncal del proveedor de servicios de Internet MPLS y se proporciona ancho de banda a todos los sitios para que lo usen a través de un vínculo WAN a la nube MPLS. No existe ningún concentrador de red ni ningún sitio central que controle el enrutamiento IP. En la siguiente figura se muestra una red sencilla basada en la tecnología MPLS.</span><span class="sxs-lookup"><span data-stu-id="fa559-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>
  
<span data-ttu-id="fa559-113">**Red MPLS de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="fa559-113">**Example MPLS network**</span></span>

![Control de admisión de llamadas (CAC) con MPLS](../../media/CAC_MPLS_1.jpg)
  
<span data-ttu-id="fa559-p104">Para implementar el servicio de control de admisión de llamadas (CAC) en una red MPLS necesitas crear una región de red que represente la nube MPLS y un sitio de red que represente cada uno de los sitios satélite MPLS. En la siguiente figura se muestra cómo tendrán que configurarse la región de red y los sitios de red para representar la red MPLS de ejemplo de la figura anterior. Los límites de ancho de banda generales y los límites de sesión de ancho de banda se basan en la capacidad del vínculo WAN desde el sitio de red hasta la región de red que representa la nube MPLS.</span><span class="sxs-lookup"><span data-stu-id="fa559-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>
  
<span data-ttu-id="fa559-118">**Región de la red y sitios de red para una red MPLS**</span><span class="sxs-lookup"><span data-stu-id="fa559-118">**Network region and network sites for an MPLS network**</span></span>

![Diagrama de control de admisión de llamadas (CAC) con MPLS](../../media/CAC_MPLS_2.jpg)
  
## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="fa559-120">Servicio de control de admisión de llamadas en un tronco SIP</span><span class="sxs-lookup"><span data-stu-id="fa559-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="fa559-p105">Para implementar el servicio de control de admisión de llamadas (CAC) en un tronco SIP necesitas crear un sitio de red para representar al proveedor de servicios de telefonía por Internet (ITSP). Para aplicar valores de directivas de ancho de banda al tronco SIP necesitas crear una directiva entre el sitio de red de tu empresa y el sitio de red que crees para representar al ITSP.</span><span class="sxs-lookup"><span data-stu-id="fa559-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>
  
<span data-ttu-id="fa559-123">La siguiente figura muestra un ejemplo de implementación de CAC en un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="fa559-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>
  
<span data-ttu-id="fa559-124">**Configuración de CAC en un tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="fa559-124">**CAC configuration on a SIP trunk**</span></span>

![Diagrama de enlace troncal SIP del control de admisión de llamadas](../../media/CAC_SIP_trunk_1.jpg)
  
<span data-ttu-id="fa559-126">Para configurar el CAC en un tronco SIP necesitarás realizar las siguientes tareas durante la implementación de CAC:</span><span class="sxs-lookup"><span data-stu-id="fa559-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>
  
1. <span data-ttu-id="fa559-127">Crea un sitio de red para representar al ITSP.</span><span class="sxs-lookup"><span data-stu-id="fa559-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="fa559-128">Asocia el sitio de red a una región de red adecuada y asigna un ancho de banda de cero para el audio y el vídeo para este sitio de red.</span><span class="sxs-lookup"><span data-stu-id="fa559-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="fa559-129">Para obtener información detallada, vea [Configurar sitios de red para CAC](http://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="fa559-129">For details, see [Configure Network Sites for CAC](http://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa559-p107">Para el ITSP, no funciona esta configuración de sitio de red. Los valores de la directiva de ancho de banda se aplican, en realidad, en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="fa559-p107">For the ITSP, this network site configuration is not functional. Bandwidth policy values are actually applied in step 2.</span></span> 
  
2. <span data-ttu-id="fa559-132">Crea un vínculo entre sitios para el tronco SIP, usando los valores de los parámetros correspondientes al sitio que creaste en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="fa559-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="fa559-133">Por ejemplo, usa el nombre del sitio de red de tu empresa como el valor del parámetro NetworkSiteID1 y el sitio de red de ITSP como el valor del parámetro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="fa559-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="fa559-134">Para obtener más información, vea [directivas entre sitios de red crear en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) en la documentación de implementación y [CsNetworkInterSitePolicy de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fa559-134">For details, see [Create network intersite policies in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>
    
3. <span data-ttu-id="fa559-135">Obtenga la dirección IP de la controladora de borde de sesión (SCB) punto de terminación de medios desde el ITSP.</span><span class="sxs-lookup"><span data-stu-id="fa559-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="fa559-136">Agrega esa dirección IP con una máscara de subred de 32 al sitio de red que representa al ITSP.</span><span class="sxs-lookup"><span data-stu-id="fa559-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="fa559-137">Para obtener más información, vea [asociar una subred a un sitio de red](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa559-137">For details, see [Associate a Subnet with a Network Site](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>
    
## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="fa559-138">Servicio de control de admisión de llamadas con una PBX o una puerta de enlace RTC de terceros</span><span class="sxs-lookup"><span data-stu-id="fa559-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="fa559-139">Este tema describen algunos ejemplos de cómo se puede implementar el control de admisión de llamadas (CAC) en el vínculo entre la interfaz de puerta de enlace del servidor de mediación y una puerta de enlace de terceros de telefonía pública conmutada (RTC) de la red o una centralita privada (PBX).</span><span class="sxs-lookup"><span data-stu-id="fa559-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>
  
### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="fa559-140">Caso 1: servicio de control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="fa559-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="fa559-141">CAC puede implementarse en la WAN vínculo de la interfaz de puerta de enlace del servidor de mediación a una puerta de enlace de terceros PBX o RTC.</span><span class="sxs-lookup"><span data-stu-id="fa559-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>
  
<span data-ttu-id="fa559-142">**Caso 1: CAC entre el servidor de mediación y una puerta de enlace PSTN**</span><span class="sxs-lookup"><span data-stu-id="fa559-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Caso 1: Control de admisión de llamadas (CAC) entre el servidor de mediación y la puerta de enlace RTC](../../media/CAC_gateways_1.jpg)
  
<span data-ttu-id="fa559-144">En este ejemplo, se aplica CAC entre el servidor de mediación y una puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="fa559-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="fa559-145">Si un Skype para usuarios de cliente de empresa en el sitio de red 1 coloca una llamada PSTN a través de la puerta de enlace PSTN en el sitio de red 2, el medio fluye a través del vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="fa559-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="fa559-146">Por tanto, se llevan a cabo dos comprobaciones de CAC para cada sesión de RTC:</span><span class="sxs-lookup"><span data-stu-id="fa559-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>
  
- <span data-ttu-id="fa559-147">Entre el Skype para la aplicación de cliente de empresa y el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="fa559-147">Between the Skype for Business client application and the Mediation Server</span></span>
    
- <span data-ttu-id="fa559-148">Entre el servidor de mediación y la puerta de enlace PSTN</span><span class="sxs-lookup"><span data-stu-id="fa559-148">Between the Mediation Server and the PSTN gateway</span></span>
    
<span data-ttu-id="fa559-149">Esto funciona tanto para las llamadas RTC entrantes a un cliente en el sitio de red 1 como para las llamadas RTC salientes desde una aplicación cliente en el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="fa559-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa559-150">Asegúrate de que la subred IP a la que pertenece la puerta de enlace RTC esté configurada y asociada con el sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="fa559-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa559-151">Asegúrese de que la subred IP que ambas interfaces de servidor de mediación pertenecen a está configurada y asociada con el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="fa559-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa559-152">Para obtener más información, vea [asociar una subred a un sitio de red](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa559-152">For details, see [Associate a Subnet with a Network Site](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span> 
  
### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="fa559-153">Caso 2: CAC entre el servidor de mediación y una PBX de terceros con el punto de terminación de medios</span><span class="sxs-lookup"><span data-stu-id="fa559-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="fa559-154">Esta configuración es similar a la del caso 1.</span><span class="sxs-lookup"><span data-stu-id="fa559-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="fa559-155">En ambos casos, el servidor de mediación sabe cuál es el dispositivo finaliza los medios en el extremo opuesto del vínculo WAN y la dirección IP de la puerta de enlace PSTN o PBX con el punto de terminación de multimedia (MTP) está configurada en el servidor de mediación como el próximo salto.</span><span class="sxs-lookup"><span data-stu-id="fa559-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>
  
<span data-ttu-id="fa559-156">**Caso 2: CAC entre el servidor de mediación y una PBX de terceros con MTP**</span><span class="sxs-lookup"><span data-stu-id="fa559-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Caso 2: Control de admisión de llamadas (CAC) entre el servidor de mediación y la PBX con MTP](../../media/CAC_gateways_2.jpg)
  
<span data-ttu-id="fa559-158">En este ejemplo, se aplica CAC entre el servidor de mediación y el PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="fa559-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="fa559-159">Si un Skype para usuarios de cliente de empresa en el sitio de red 1 coloca una llamada PSTN a través de la PBX/MTP ubicado en el sitio de red 2, el medio fluye a través del vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="fa559-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="fa559-160">Por tanto, se llevan a cabo dos comprobaciones de CAC para cada sesión de RTC:</span><span class="sxs-lookup"><span data-stu-id="fa559-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>
  
- <span data-ttu-id="fa559-161">Entre el Skype para la aplicación de cliente de empresa y el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="fa559-161">Between the Skype for Business client application and the Mediation Server</span></span>
    
- <span data-ttu-id="fa559-162">Entre el servidor de mediación y el PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="fa559-162">Between the Mediation Server and the PBX/MTP</span></span>
    
<span data-ttu-id="fa559-163">Esto funciona tanto para las llamadas RTC entrantes a un cliente en el sitio de red 1 como para las llamadas RTC salientes desde un cliente en el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="fa559-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa559-164">Asegúrate de que la subred IP a la que pertenece el MTP esté configurada y asociada con el sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="fa559-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa559-165">Asegúrese de que la subred IP que ambas interfaces de servidor de mediación pertenecen a está configurada y asociada con el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="fa559-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa559-166">Para obtener más información, vea [asociar una subred a un sitio de red](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa559-166">For details, see [Associate a Subnet with a Network Site](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span> 
  
### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="fa559-167">Caso 3: CAC entre el servidor de mediación y una PBX de terceros sin un punto de terminación de medios</span><span class="sxs-lookup"><span data-stu-id="fa559-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="fa559-168">El caso 3 es ligeramente diferente a los dos primeros casos.</span><span class="sxs-lookup"><span data-stu-id="fa559-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="fa559-169">Si no hay ningún MTP en el PBX de terceros, para una sesión saliente solicitud a la PBX de terceros el servidor de mediación no sabe donde media terminará en el límite de PBX.</span><span class="sxs-lookup"><span data-stu-id="fa559-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="fa559-170">En este caso, los medios fluyen directamente entre el servidor de mediación y el dispositivo de extremo de terceros.</span><span class="sxs-lookup"><span data-stu-id="fa559-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>
  
<span data-ttu-id="fa559-171">**Caso 3: CAC entre el servidor de mediación y una PBX de terceros sin MTP**</span><span class="sxs-lookup"><span data-stu-id="fa559-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Caso 3: Control de admisión de llamadas (CAC) entre el servidor de mediación y la PBX sin MTP](../../media/CAC_gateways_3.jpg)
  
<span data-ttu-id="fa559-173">En este ejemplo, si un Skype para usuarios de cliente de empresa en el sitio de red 1 realiza una llamada a un usuario a través de la PBX, el servidor de mediación es capaz de realizar comprobaciones CAC sólo en la pata de proxy entre (Skype para la aplicación de cliente de empresa) y servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fa559-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="fa559-174">Porque el servidor de mediación no tiene información sobre el dispositivo de extremo mientras se está solicitando la sesión, no se puede realizar comprobaciones CAC en la WAN vínculo (entre el servidor de mediación y el extremo de terceros) antes de establecimiento de llamada.</span><span class="sxs-lookup"><span data-stu-id="fa559-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="fa559-175">Sin embargo, una vez establecida la sesión, el servidor de mediación facilita en la contabilidad para el ancho de banda utilizado en el maletero.</span><span class="sxs-lookup"><span data-stu-id="fa559-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>
  
<span data-ttu-id="fa559-176">Para las llamadas que se originan en el extremo de terceros, la información acerca de dicho dispositivo de extremo está disponible en el momento de la solicitud de sesión y verificación CAC puede realizarse en ambos lados del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fa559-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa559-177">Asegúrate de que la subred IP a la que pertenecen los dispositivos de extremo esté configurada y asociada con el sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="fa559-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa559-178">Asegúrese de que la subred IP que ambas interfaces de servidor de mediación pertenecen a está configurada y asociada con el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="fa559-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa559-179">Para obtener más información, vea [asociar una subred a un sitio de red](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa559-179">For details, see [Associate a Subnet with a Network Site](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span> 
  

