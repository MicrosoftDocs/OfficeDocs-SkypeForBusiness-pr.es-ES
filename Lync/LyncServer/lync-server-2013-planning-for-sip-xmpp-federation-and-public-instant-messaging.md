---
title: Planear el SIP, la Federación de XMPP y la mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88aa8c6f3f2f11b303a7e25eed96d5f0d7243cb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="3d076-102">Planificación de SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d076-103">_**Última modificación del tema:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="3d076-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="3d076-104">Los servidores perimetrales se pueden configurar para permitir a los usuarios externos y internos el acceso a los contactos de las organizaciones o servicios asociados.</span><span class="sxs-lookup"><span data-stu-id="3d076-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="3d076-105">Las federaciones, ya que estos acuerdos de socio son conocidos, pueden proporcionar cualquiera de los siguientes elementos o todos ellos a los contactos de su organización en la Federación de Partners o los contactos de la Federación del Partner con usted:</span><span class="sxs-lookup"><span data-stu-id="3d076-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="3d076-106">Mensajería instantánea y presencia</span><span class="sxs-lookup"><span data-stu-id="3d076-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="3d076-107">Colaboración y conferencias, por ejemplo: conferencias web</span><span class="sxs-lookup"><span data-stu-id="3d076-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="3d076-108">Audioconferencias, videoconferencias o ambos</span><span class="sxs-lookup"><span data-stu-id="3d076-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="3d076-109">En algunos casos, la comunicación, por ejemplo, la mensajería instantánea (mi) y la presencia entre un contacto de Microsoft Lync Server 2013 y el protocolo de presencia y mensajería extensible (XMPP), solo es compatible con usted y el contacto en el equipo federado. servidor.</span><span class="sxs-lookup"><span data-stu-id="3d076-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="3d076-110">En otros casos, como un servidor de Lync, Lync Server 2010 a la Federación de Lync Server 2013, se puede invitar a varios participantes a participar en la conversación.</span><span class="sxs-lookup"><span data-stu-id="3d076-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="3d076-111">Federación de Lync Server y Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="3d076-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="3d076-112">La Federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server admite comunicaciones de punto a punto y de varias personas.</span><span class="sxs-lookup"><span data-stu-id="3d076-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="3d076-113">Las conversaciones de punto a punto se pueden remitir a conversaciones de varios participantes, lo que permite las reuniones ad hoc.</span><span class="sxs-lookup"><span data-stu-id="3d076-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="3d076-114">Las reuniones (conferencias web o conferencias de audio y vídeo) se pueden programar para incluir contactos dentro de su organización, así como contactos en socios con los que se federe.</span><span class="sxs-lookup"><span data-stu-id="3d076-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="3d076-115">La Federación apareció por primera vez en Microsoft Office Live Communications Server 2005 y admitía un tipo de Federación, la Federación directa.</span><span class="sxs-lookup"><span data-stu-id="3d076-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="3d076-116">La Federación directa requirió conocer el dominio del Protocolo de inicio de sesión (SIP) del socio de Federación y el nombre de dominio completo (FQDN) del servidor perimetral del socio.</span><span class="sxs-lookup"><span data-stu-id="3d076-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="3d076-117">Live Communications Server 2005 con SP1 introdujo tipos de Federación adicionales, todos los cuales requerían que el socio federado publique los registros SRV del sistema de nombres de dominio (DNS) para ubicar su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="3d076-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="3d076-118">La terminología de esa versión era:</span><span class="sxs-lookup"><span data-stu-id="3d076-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="3d076-119">*Abrir Federación mejorada*: aceptar cualquier nombre de dominio SIP y usar DNS SRV para ubicar el servidor perimetral asociado</span><span class="sxs-lookup"><span data-stu-id="3d076-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="3d076-120">*Federación mejorada*: configure el nombre de dominio SIP del socio como un asociado de Federación de su organización y use DNS SRV para buscar el servidor perimetral asociado</span><span class="sxs-lookup"><span data-stu-id="3d076-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="3d076-121">*Federación directa*: configurar el nombre de dominio SIP del socio y el FQDN al servidor perimetral del socio</span><span class="sxs-lookup"><span data-stu-id="3d076-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="3d076-122">*Lista*de permitidos del servidor: aceptar cualquier dominio, usar DNS SRV para buscar el servidor perimetral de un proveedor de hospedaje o un proveedor de conectividad de mensajería instantánea pública (mi)</span><span class="sxs-lookup"><span data-stu-id="3d076-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="3d076-123">Microsoft Office Communications Server 2007 introdujo nombres actualizados para los tipos de Federación para definir mejor lo que hace realmente cada tipo de Federación:</span><span class="sxs-lookup"><span data-stu-id="3d076-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="3d076-124">Abrir la Federación mejorada se conocía como *dominio de socio descubierto*</span><span class="sxs-lookup"><span data-stu-id="3d076-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="3d076-125">La Federación mejorada se conocía como *dominio asociado permitido*</span><span class="sxs-lookup"><span data-stu-id="3d076-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="3d076-126">La Federación directa se conocía como *servidor asociado permitido*</span><span class="sxs-lookup"><span data-stu-id="3d076-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="3d076-127">La lista de permitidos del servidor se conocía como *proveedor de hospedaje* y *proveedor de mensajería instantánea pública*</span><span class="sxs-lookup"><span data-stu-id="3d076-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="3d076-128">Microsoft Lync Server 2010 introdujo una definición más estrecha de proveedor de hospedaje de acuerdo con Microsoft Lync Online 2010 y Microsoft Office 365, y también lo hizo según la misma lista permitida definida por el tipo de Federación de dominios de socio autorizado.</span><span class="sxs-lookup"><span data-stu-id="3d076-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="3d076-129">Habilitar la Federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server usa los servidores perimetrales y los proxy inversos para exigir las reglas y los dominios asociados permitidos que usted defina.</span><span class="sxs-lookup"><span data-stu-id="3d076-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="3d076-130">Desde una perspectiva de planeación, la Federación con otro Lync Server, Office Communications Server requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d076-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="3d076-131">Habilitar la Federación en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="3d076-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="3d076-132">Para obtener más información, vea el tema sobre la implementación de la [Federación SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="3d076-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="3d076-133">Determinar los requisitos para la detección de dominios federados:</span><span class="sxs-lookup"><span data-stu-id="3d076-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="3d076-134">Para la configuración manual de la Federación, debe tener el nombre de dominio completo (FQDN) del servidor perimetral y el nombre de dominio del asociado, o el nombre de dominio en línea, que se especifica en el panel de control de Lync Server, **Federación y acceso externo**, **SIP Dominios federados**.</span><span class="sxs-lookup"><span data-stu-id="3d076-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="3d076-135">Cree una directiva **nueva** o **edite** una existente para permitir o bloquear dominios por FQDN.</span><span class="sxs-lookup"><span data-stu-id="3d076-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="3d076-136">La configuración manual del servidor perimetral de un socio de Federación es propenso a fallar en el caso de que el socio cambie la dirección IP de su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="3d076-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="3d076-137">Para los <STRONG>nuevos dominios federados de SIP</STRONG>, debe proporcionar el <STRONG>nombre de dominio (o FQDN)</STRONG> para Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d076-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="3d076-138">Para Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server, también debe proporcionar un <STRONG>servicio perimetral de acceso (FQDN)</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3d076-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="3d076-139">Para la Federación de Partners detectada, donde los socios pueden descubrir su servidor perimetral, cree un registro SRV en su \_DNS externo-sipfederationtls. \_TCP.contoso.com, que apunta al puerto 5061 y al registro de host (A) de su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="3d076-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="3d076-140">Si admite clientes móviles de Microsoft Lync en Windows Phone o Apple iPhone, iPad u otros dispositivos Apple y está usando el servicio de notificaciones Push o el servicio de notificaciones push, debe planear _sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="3d076-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="3d076-141">&lt;Registros SRV&gt; de dominio SIP para cada dominio SIP que tenga clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="3d076-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="3d076-142">Android y Nokia Symbian Lync Mobile no usan la notificación de inserción y no están sujetos a este requisito.</span><span class="sxs-lookup"><span data-stu-id="3d076-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="3d076-143">Configurar directivas de acceso de usuarios externos para admitir dominios federados</span><span class="sxs-lookup"><span data-stu-id="3d076-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="3d076-144">Abra puertos de Firewall para el protocolo de inicio de sesión (SIP), las conferencias web y el audio/vídeo para alojar la Federación o los contactos que está habilitando.</span><span class="sxs-lookup"><span data-stu-id="3d076-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="3d076-145">Para obtener más información, consulte: [determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3d076-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="3d076-146">La siguiente información le ayudará a definir el certificado, el puerto/protocolo y los requisitos de DNS para la Federación con Microsoft Lync Server 2013 y Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3d076-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="3d076-147">Generalmente es un proceso de reenvío directo si ha planeado o implementado los servidores perimetrales de Microsoft Lync Server 2013, por lo general, en el planeamiento de certificados, Firewall y requisitos de Puerto/protocolo.</span><span class="sxs-lookup"><span data-stu-id="3d076-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="3d076-148">Puesto que la Federación es una característica adicional que usa el servidor perimetral existente, los requisitos de planeación suelen cumplirse al planear e implementar el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="3d076-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="3d076-149">Debe usar las siguientes tablas para determinar que se cumplen sus requisitos y realizar cambios en el puerto, protocolo y DNS según corresponda.</span><span class="sxs-lookup"><span data-stu-id="3d076-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3d076-150">Si tiene un grupo de servidores de tecnología perimetral y se está federando con socios de Lync Server 2013 o Lync Server 2010, puede usar equilibrio de carga DNS o equilibradores de carga de hardware en los lados frontales internos y externos de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="3d076-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="3d076-151">Si va a federar con Office Communications Server 2007 o con Office Communications Server 2007 R2, el equilibrio de carga de hardware proporcionará compatibilidad con la conmutación por error en el caso de un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="3d076-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="3d076-152">Office Communications Server 2007 y Office Communications Server 2007 R2 no tienen en cuenta el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="3d076-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="3d076-153">Los servidores perimetrales asociados establecerán comunicación con el primer servidor perimetral de su grupo que responda.</span><span class="sxs-lookup"><span data-stu-id="3d076-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="3d076-154">Si se produce un error en ese servidor perimetral, la comunicación no se realiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3d076-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="3d076-155">Los requisitos de certificados se suelen cumplir a través de la planificación de certificados para el servidor perimetral elegido o el plan del servidor perimetral agrupado.</span><span class="sxs-lookup"><span data-stu-id="3d076-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="3d076-156">Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="3d076-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="3d076-157">La conectividad de mensajería instantánea pública es una clase de Federación y está configurada para permitir a los usuarios internos y externos de Lync Server 2013 agregar contactos de cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3d076-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="3d076-158">Contactos de Messenger</span><span class="sxs-lookup"><span data-stu-id="3d076-158">Messenger contacts</span></span>

  - <span data-ttu-id="3d076-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="3d076-159">Yahoo\!</span></span> <span data-ttu-id="3d076-160">contactos</span><span class="sxs-lookup"><span data-stu-id="3d076-160">contacts</span></span>

  - <span data-ttu-id="3d076-161">Contactos de America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="3d076-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="3d076-162">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="3d076-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="3d076-163">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="3d076-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="3d076-164">Messenger hasta la fecha de cierre del servicio (la fecha exacta aún se debe decidir, pero no antes del 2013 de junio).</span><span class="sxs-lookup"><span data-stu-id="3d076-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="3d076-165">El PIC USL es una licencia por usuario y por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="3d076-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="3d076-166">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="3d076-166">Messenger.</span></span> <span data-ttu-id="3d076-167">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el cual no se renovará.</span><span class="sxs-lookup"><span data-stu-id="3d076-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="3d076-168">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="3d076-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="3d076-169">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="3d076-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="3d076-170">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="3d076-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3d076-171">Esta clase de Federación requiere las siguientes consideraciones de planeación:</span><span class="sxs-lookup"><span data-stu-id="3d076-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="3d076-172">Los usuarios de Windows Live Messenger pueden tener una comunicación visual o de audio de punto a punto con los usuarios de Lync Server 2013, además de la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="3d076-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="3d076-173">Los servidores perimetrales deben cumplir con requisitos de puerto y protocolo específicos.</span><span class="sxs-lookup"><span data-stu-id="3d076-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="3d076-174">Para obtener más información, consulte [determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d076-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="3d076-175">La mensajería instantánea de Yahoo no tiene requisitos únicos, excepto los que normalmente se usan en la planificación y la implementación del servidor perimetral típico que proporciona la Federación.</span><span class="sxs-lookup"><span data-stu-id="3d076-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="3d076-176">America Online requiere que el certificado del servidor perimetral asignado al servicio perimetral de acceso tenga un uso mejorado de clave (EKU) de cliente.</span><span class="sxs-lookup"><span data-stu-id="3d076-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="3d076-177">Federación de protocolo de presencia y mensajería extensible (XMPP)</span><span class="sxs-lookup"><span data-stu-id="3d076-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="3d076-178">Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podría implementar como una función de servidor independiente para permitir la Federación con implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="3d076-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="3d076-179">En Microsoft Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica.</span><span class="sxs-lookup"><span data-stu-id="3d076-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="3d076-180">La funcionalidad XMPP se instala en dos partes: un proxy XMPP que se ejecuta en el servidor perimetral y la puerta de enlace XMPP que se ejecuta en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="3d076-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="3d076-181">La implementación y configuración de XMPP se trata en [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) se planea la compatibilidad de XMPP en la organización mediante la definición de reglas de puerto y protocolo en el firewall, la configuración de certificados y la adición de DNS PTR.</span><span class="sxs-lookup"><span data-stu-id="3d076-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="3d076-182">En los temas siguientes de esta sección se resume la información necesaria para planear correctamente la Federación XMPP para su implementación.</span><span class="sxs-lookup"><span data-stu-id="3d076-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3d076-p120">La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="3d076-p120">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3d076-185">La Federación de XMPP no es compatible con los usuarios que están alojados en dispositivos de sucursales con las que es posible.</span><span class="sxs-lookup"><span data-stu-id="3d076-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="3d076-186">Esto se aplica a la información de presencia y a intercambiar mensajes INSTANTÁNEos.</span><span class="sxs-lookup"><span data-stu-id="3d076-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="3d076-187">En los siguientes temas se incluyen instrucciones para definir certificados, puertos de firewall y entradas DNS para los tipos de escenarios de Federación admitidos.</span><span class="sxs-lookup"><span data-stu-id="3d076-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="3d076-188">Resumen del certificado: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="3d076-189">Resumen de puertos: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="3d076-190">Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d076-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d076-191">See Also</span></span>


[<span data-ttu-id="3d076-192">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="3d076-193">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="3d076-194">Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="3d076-195">Determinar los requisitos DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="3d076-196">Administrar la configuración perimetral de acceso para su organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="3d076-197">Administrar dominios federados SIP para la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="3d076-198">Administrar proveedores federados SIP para la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d076-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

