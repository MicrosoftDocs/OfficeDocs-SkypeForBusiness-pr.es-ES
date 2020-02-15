---
title: 'Lync Server 2013: componentes necesarios para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e225f63da97ea48d98a5a2540a6b35a9c63c08f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="39e5f-102">Componentes necesarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39e5f-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39e5f-103">_**Última modificación del tema:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="39e5f-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="39e5f-104">La mayoría de los componentes perimetrales se implementan en una red perimetral.</span><span class="sxs-lookup"><span data-stu-id="39e5f-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="39e5f-105">Los siguientes componentes conforman la topología perimetral de una red perimetral.</span><span class="sxs-lookup"><span data-stu-id="39e5f-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="39e5f-106">Excepto donde se indique, los componentes forman parte de los [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) y se encuentran en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="39e5f-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="39e5f-107">Los componentes perimetrales engloban los siguientes:</span><span class="sxs-lookup"><span data-stu-id="39e5f-107">Edge components include the following:</span></span>

  - <span data-ttu-id="39e5f-108">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="39e5f-108">Edge Servers</span></span>

  - <span data-ttu-id="39e5f-109">Proxies inversos</span><span class="sxs-lookup"><span data-stu-id="39e5f-109">Reverse proxies</span></span>

  - <span data-ttu-id="39e5f-110">Firewalls</span><span class="sxs-lookup"><span data-stu-id="39e5f-110">Firewalls</span></span>

  - <span data-ttu-id="39e5f-111">Directores (opcionales y ubicados lógicamente en la red interna)</span><span class="sxs-lookup"><span data-stu-id="39e5f-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="39e5f-112">Equilibrio de carga para topologías perimetrales escaladas (equilibrio de carga de DNS o un equilibrador de carga de hardware)</span><span class="sxs-lookup"><span data-stu-id="39e5f-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="39e5f-p102">No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Debe utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="39e5f-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="39e5f-115">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="39e5f-115">Edge Servers</span></span>

<span data-ttu-id="39e5f-116">Los servidores perimetrales envían y reciben tráfico de red para los servicios ofrecidos por la implementación interna por los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="39e5f-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="39e5f-117">El servidor perimetral ejecuta los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="39e5f-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="39e5f-118">**Servicio perimetral de acceso**   el servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico SIP (Protocolo de inicio de sesión) saliente y entrante.</span><span class="sxs-lookup"><span data-stu-id="39e5f-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="39e5f-119">**Servicio perimetral de conferencia web**   el servicio perimetral de conferencia web permite a los usuarios externos unirse a reuniones hospedadas en la implementación interna de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39e5f-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="39e5f-120">**Servicio perimetral a/v**   el servicio perimetral a/v hace que el audio, vídeo, uso compartido de aplicaciones y transferencia de archivos estén disponibles para los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="39e5f-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="39e5f-121">Los usuarios pueden agregar audio y vídeo a las reuniones que incluyen participantes externos, y pueden comunicarse mediante audio o vídeo directamente con un usuario externo en sesiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="39e5f-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="39e5f-122">De igual modo, este servicio permite el uso compartido de escritorio y la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="39e5f-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="39e5f-123">**Servicio Proxy XMPP**   el servicio Proxy XMPP acepta y envía mensajes del Protocolo de mensajería y presencia extensible (XMPP) a y desde socios federados de XMPP configurados.</span><span class="sxs-lookup"><span data-stu-id="39e5f-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="39e5f-124">Los usuarios externos autorizados pueden tener acceso a los servidores perimetrales para conectarse a la implementación interna de Lync Server 2013, pero los servidores perimetrales no proporcionan medios para otros tipos de acceso a la red interna.</span><span class="sxs-lookup"><span data-stu-id="39e5f-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39e5f-125">Los servidores perimetrales se implementan para proporcionar conexiones para los clientes de Lync habilitados y otros servidores de Microsoft Edge (como en los escenarios de Federación).</span><span class="sxs-lookup"><span data-stu-id="39e5f-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="39e5f-126">Estos servidores no están diseñados para permitir conexiones desde otros tipos de servidores o clientes de extremos.</span><span class="sxs-lookup"><span data-stu-id="39e5f-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="39e5f-127">El servidor de puerta de enlace XMPP puede implementarse para permitir conexiones con socios XMPP configurados.</span><span class="sxs-lookup"><span data-stu-id="39e5f-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="39e5f-128">El servidor perimetral y la puerta de enlace XMPP solo admite conexiones de extremos procedentes de estos clientes y de estos tipos de federación</span><span class="sxs-lookup"><span data-stu-id="39e5f-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="39e5f-129">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="39e5f-129">Reverse Proxy</span></span>

<span data-ttu-id="39e5f-130">El proxy inverso se requiere para:</span><span class="sxs-lookup"><span data-stu-id="39e5f-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="39e5f-131">Dejar que los usuarios se conecten a reuniones o conferencias de acceso telefónico usando direcciones URL sencillas</span><span class="sxs-lookup"><span data-stu-id="39e5f-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="39e5f-132">Dejar que los usuarios descarguen el contenido de las reuniones</span><span class="sxs-lookup"><span data-stu-id="39e5f-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="39e5f-133">Dejar que los usuarios externos expandan grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="39e5f-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="39e5f-134">Dejar que los usuarios obtengan un certificado individual de usuario para la autenticación basada en certificados</span><span class="sxs-lookup"><span data-stu-id="39e5f-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="39e5f-135">Dejar que los usuarios remotos descarguen archivos del servidor de libreta de direcciones o envíen consultas al servicio de consulta web de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="39e5f-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="39e5f-136">Dejar que los usuarios remotos obtengan actualizaciones de software de dispositivo y de cliente</span><span class="sxs-lookup"><span data-stu-id="39e5f-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="39e5f-137">Para habilitar dispositivos móviles para detectar automáticamente servidores front-end que ofrecen servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="39e5f-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="39e5f-138">Para habilitar notificaciones de inserción para dispositivos móviles desde los servicios de notificación de inserción de Office 365 o Apple</span><span class="sxs-lookup"><span data-stu-id="39e5f-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="39e5f-139">Para obtener información adicional relacionada con los proxies inversos y los requisitos que deben cumplir los servidores proxy inversos, consulte los detalles de [los requisitos de configuración para el proxy inverso en Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="39e5f-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39e5f-140">Los usuarios externos no necesitan una conexión de red privada virtual (VPN) a la organización para poder participar en las comunicaciones con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39e5f-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="39e5f-141">Si ha implementado la tecnología VPN en su organización y los usuarios usan la VPN para Lync, el tráfico multimedia (por ejemplo, la videoconferencia) puede verse afectado negativamente.</span><span class="sxs-lookup"><span data-stu-id="39e5f-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="39e5f-142">Debe considerar la posibilidad de ofrecer un medio para que el tráfico de medios se conecte directamente con el servicio perimetral AV y omita la VPN.</span><span class="sxs-lookup"><span data-stu-id="39e5f-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="39e5f-143">Para obtener más información, consulte el artículo del blog NextHop, "Enabling Lync media to bypass a VPN Tunnel <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>", en.</span><span class="sxs-lookup"><span data-stu-id="39e5f-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="39e5f-144">Éste</span><span class="sxs-lookup"><span data-stu-id="39e5f-144">Firewall</span></span>

<span data-ttu-id="39e5f-145">La topología perimetral se puede implementar con únicamente un firewall externo o con un firewall interno y otro externo.</span><span class="sxs-lookup"><span data-stu-id="39e5f-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="39e5f-146">Las arquitecturas de escenario incluyen dos firewalls.</span><span class="sxs-lookup"><span data-stu-id="39e5f-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="39e5f-147">El uso de dos firewall es el método que se recomienda, en tanto garantiza el enrutamiento estricto desde un perímetro de red al otro, además de proteger la implementación interna detrás de dos niveles de firewall.</span><span class="sxs-lookup"><span data-stu-id="39e5f-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="39e5f-148">Dirección</span><span class="sxs-lookup"><span data-stu-id="39e5f-148">Director</span></span>

<span data-ttu-id="39e5f-149">Un director es un rol de servidor opcional e independiente en Lync Server 2013 que no aloja cuentas de usuario ni proporciona servicios de presencia o conferencia.</span><span class="sxs-lookup"><span data-stu-id="39e5f-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="39e5f-150">Actúa como un servidor interno del próximo salto en el que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="39e5f-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="39e5f-151">El director autentica las solicitudes de entrada y las redirige al servidor o grupo de servidores principales del usuario.</span><span class="sxs-lookup"><span data-stu-id="39e5f-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="39e5f-152">Mediante la autenticación previa en el director, puede colocar solicitudes de cuentas de usuario que son desconocidas para la implementación.</span><span class="sxs-lookup"><span data-stu-id="39e5f-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="39e5f-153">Un director ayuda a aislar los servidores Standard Edition y los servidores front-end de los grupos de servidores front-end Enterprise Edition de tráfico malintencionado, como los ataques por denegación de servicio (DoS).</span><span class="sxs-lookup"><span data-stu-id="39e5f-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="39e5f-154">Si la red está inundada con tráfico externo no válido en un ataque de este tipo, el tráfico termina en el director.</span><span class="sxs-lookup"><span data-stu-id="39e5f-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="39e5f-155">Para obtener más información sobre el uso de los directores, consulte [escenarios del Director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="39e5f-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="39e5f-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="39e5f-156">See Also</span></span>


[<span data-ttu-id="39e5f-157">Requisitos del equilibrador de carga de hardware para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39e5f-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

