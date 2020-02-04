---
title: 'Lync Server 2013: Componentes necesarios para el acceso de usuarios externos'
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
ms.openlocfilehash: 550eb864ff7cc26eb0bfeace37759bb15b9816f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="608d7-102">Componentes necesarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="608d7-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="608d7-103">_**Última modificación del tema:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="608d7-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="608d7-104">La mayoría de los componentes perimetrales se implementan en una red perimetral.</span><span class="sxs-lookup"><span data-stu-id="608d7-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="608d7-105">Los siguientes componentes forman la topología perimetral de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="608d7-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="608d7-106">Excepto donde se indique lo contrario, los componentes forman parte de los [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) y en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="608d7-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="608d7-107">Los componentes perimetrales engloban los siguientes:</span><span class="sxs-lookup"><span data-stu-id="608d7-107">Edge components include the following:</span></span>

  - <span data-ttu-id="608d7-108">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="608d7-108">Edge Servers</span></span>

  - <span data-ttu-id="608d7-109">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="608d7-109">Reverse proxies</span></span>

  - <span data-ttu-id="608d7-110">Firewalls</span><span class="sxs-lookup"><span data-stu-id="608d7-110">Firewalls</span></span>

  - <span data-ttu-id="608d7-111">Directores (opcional y, lógicamente, ubicado en la red interna)</span><span class="sxs-lookup"><span data-stu-id="608d7-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="608d7-112">Equilibrio de carga para topologías perimetrales escaladas (equilibrio de carga de DNS o un equilibrador de carga de hardware)</span><span class="sxs-lookup"><span data-stu-id="608d7-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="608d7-p102">No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Necesita utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="608d7-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="608d7-115">Servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="608d7-115">Edge Servers</span></span>

<span data-ttu-id="608d7-116">Los servidores perimetrales envían y reciben tráfico de red para los servicios ofrecidos por los usuarios externos en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="608d7-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="608d7-117">El servidor perimetral ejecuta los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="608d7-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="608d7-118">**Servicio perimetral de acceso**   el servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico de protocolo de inicio de sesión entrante y saliente (SIP).</span><span class="sxs-lookup"><span data-stu-id="608d7-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="608d7-119">**Servicio perimetral de conferencias web**   el servicio perimetral de conferencias web permite a los usuarios externos unirse a reuniones hospedadas en la implementación interna de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="608d7-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="608d7-120">**Servicio perimetral a/v**   el servicio a/v Edge hace que el audio, el video, el uso compartido de aplicaciones y la transferencia de archivos estén disponibles para los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="608d7-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="608d7-121">Los usuarios pueden agregar audio y vídeo a las reuniones que incluyen participantes externos, y pueden comunicarse con audio o video directamente con un usuario externo en sesiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="608d7-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="608d7-122">El servicio perimetral A/V también proporciona compatibilidad con el uso compartido de escritorio y la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="608d7-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="608d7-123">**Servicio de proxy XMPP**   el servicio de proxy XMPP acepta y envía mensajes de protocolo de presencia y mensajería extensible (XMPP) a los socios de XMPP federados configurados.</span><span class="sxs-lookup"><span data-stu-id="608d7-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="608d7-124">Los usuarios externos autorizados pueden tener acceso a los servidores perimetrales para conectarse a la implementación interna de Lync Server 2013, pero los servidores perimetrales no proporcionan medios para ningún otro tipo de acceso a la red interna.</span><span class="sxs-lookup"><span data-stu-id="608d7-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="608d7-125">Los servidores perimetrales se implementan para proporcionar conexiones para clientes de Lync habilitados y otros servidores Microsoft Edge (como en los escenarios de Federación).</span><span class="sxs-lookup"><span data-stu-id="608d7-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="608d7-126">No están diseñados para permitir conexiones de otros tipos de clientes o servidores de punto final.</span><span class="sxs-lookup"><span data-stu-id="608d7-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="608d7-127">El servidor de puerta de enlace XMPP puede implementarse para permitir conexiones con socios XMPP configurados.</span><span class="sxs-lookup"><span data-stu-id="608d7-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="608d7-128">El servidor perimetral y la puerta de enlace XMPP solo admiten conexiones de punto final de estos tipos de Federación y cliente.</span><span class="sxs-lookup"><span data-stu-id="608d7-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="608d7-129">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="608d7-129">Reverse Proxy</span></span>

<span data-ttu-id="608d7-130">El proxy inverso es necesario para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="608d7-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="608d7-131">Para permitir que los usuarios se conecten a reuniones o conferencias de acceso telefónico local con direcciones URL simples</span><span class="sxs-lookup"><span data-stu-id="608d7-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="608d7-132">Para permitir que los usuarios externos descarguen contenido de la reunión</span><span class="sxs-lookup"><span data-stu-id="608d7-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="608d7-133">Para permitir a los usuarios externos expandir grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="608d7-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="608d7-134">Para permitir que el usuario obtenga un certificado basado en el usuario para la autenticación basada en certificados de cliente</span><span class="sxs-lookup"><span data-stu-id="608d7-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="608d7-135">Para permitir que los usuarios remotos descarguen archivos desde el servidor de la libreta de direcciones o para enviar consultas al servicio de consulta Web de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="608d7-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="608d7-136">Para permitir que los usuarios remotos obtengan actualizaciones del software del cliente y del dispositivo</span><span class="sxs-lookup"><span data-stu-id="608d7-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="608d7-137">Para habilitar dispositivos móviles para detectar automáticamente los servidores front-end que ofrecen servicios de movilidad</span><span class="sxs-lookup"><span data-stu-id="608d7-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="608d7-138">Para habilitar las notificaciones de inserción en dispositivos móviles desde el Office 365 o servicios de notificaciones push de Apple</span><span class="sxs-lookup"><span data-stu-id="608d7-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="608d7-139">Para obtener más información relacionada con los proxies inversos y los requisitos que deben cumplir los proxies inversos, consulte los detalles de [los requisitos de configuración para el proxy inverso en Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="608d7-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="608d7-140">Los usuarios externos no necesitan una conexión de red privada virtual (VPN) a la organización para poder participar en las comunicaciones con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="608d7-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="608d7-141">Si ha implementado tecnología VPN en su organización y los usuarios usan la VPN para Lync, el tráfico multimedia (como las videoconferencias) puede verse afectado negativamente.</span><span class="sxs-lookup"><span data-stu-id="608d7-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="608d7-142">Debe considerar proporcionar un medio para que el tráfico de medios se conecte directamente con el servicio perimetral de AV y omita la red privada virtual.</span><span class="sxs-lookup"><span data-stu-id="608d7-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="608d7-143">Para obtener más información, vea el artículo del blog de NextHop, "habilitar medios de Lync para eludir <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>un túnel VPN" en.</span><span class="sxs-lookup"><span data-stu-id="608d7-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="608d7-144">Firewall</span><span class="sxs-lookup"><span data-stu-id="608d7-144">Firewall</span></span>

<span data-ttu-id="608d7-145">Puede implementar su topología perimetral solo con un firewall externo o con firewalls externos e internos.</span><span class="sxs-lookup"><span data-stu-id="608d7-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="608d7-146">Las arquitecturas de escenario incluyen dos firewalls.</span><span class="sxs-lookup"><span data-stu-id="608d7-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="608d7-147">El uso de dos firewalls es el método recomendado, ya que garantiza el enrutamiento estricto desde un perímetro de red al otro y protege la implementación interna detrás de dos niveles de Firewall.</span><span class="sxs-lookup"><span data-stu-id="608d7-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="608d7-148">Director</span><span class="sxs-lookup"><span data-stu-id="608d7-148">Director</span></span>

<span data-ttu-id="608d7-149">Un director es un rol de servidor independiente y opcional de Lync Server 2013 que no aloja cuentas de usuario o proporciona servicios de presencia o de conferencia.</span><span class="sxs-lookup"><span data-stu-id="608d7-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="608d7-150">Actúa como un servidor interno del próximo salto al que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="608d7-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="608d7-151">El director preautentica las solicitudes entrantes y las redirige al grupo de servidores o al grupo de servidores principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="608d7-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="608d7-152">Al autenticar en el director, puede colocar solicitudes de cuentas de usuario desconocidas para la implementación.</span><span class="sxs-lookup"><span data-stu-id="608d7-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="608d7-153">Un director ayuda a aislar servidores Standard Edition y servidores de aplicaciones para el usuario de las agrupaciones front end de Enterprise Edition de tráfico malintencionado, como ataques de denegación de servicio (DoS).</span><span class="sxs-lookup"><span data-stu-id="608d7-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="608d7-154">Si la red se inunda con tráfico externo no válido en tal ataque, el tráfico termina en el director.</span><span class="sxs-lookup"><span data-stu-id="608d7-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="608d7-155">Para obtener más información sobre el uso de los directores, consulte [escenarios del Director de Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="608d7-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="608d7-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="608d7-156">See Also</span></span>


[<span data-ttu-id="608d7-157">Requisitos del equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="608d7-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

