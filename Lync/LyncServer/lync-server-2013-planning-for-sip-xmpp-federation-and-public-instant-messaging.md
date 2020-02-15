---
title: Planeación de SIP, la Federación XMPP y la mensajería instantánea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2070d9e977a730b7c667a2c49a7e896d1309eef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="2271f-102">Planeación de SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2271f-103">_**Última modificación del tema:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="2271f-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="2271f-104">Los servidores perimetrales se pueden configurar para permitir que los usuarios internos y externos tengan acceso a contactos de organizaciones o servicios asociados.</span><span class="sxs-lookup"><span data-stu-id="2271f-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="2271f-105">Las federaciones, como se conocen estos acuerdos de socios, pueden proporcionar algunas o todas de las siguientes opciones a los contactos de su organización en la federación asociada o a los contactos de la federación asociada a los suyos:</span><span class="sxs-lookup"><span data-stu-id="2271f-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="2271f-106">Mensajería instantánea y presencia</span><span class="sxs-lookup"><span data-stu-id="2271f-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="2271f-107">Colaboración y conferencias, por ejemplo: conferencias web</span><span class="sxs-lookup"><span data-stu-id="2271f-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="2271f-108">Conferencias de audio, conferencias de vídeo o ambas</span><span class="sxs-lookup"><span data-stu-id="2271f-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="2271f-109">En algunos casos, la comunicación, por ejemplo, la mensajería instantánea (mi) y la presencia entre un contacto de Microsoft Lync Server 2013 y el protocolo extensible de mensajería y presencia (XMPP), es solo de punto a punto y solo admite usted y el contacto en el federado SIA.</span><span class="sxs-lookup"><span data-stu-id="2271f-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="2271f-110">En otros casos, como un Lync Server, Lync Server 2010 a Lync Server 2013 Federation, se puede invitar a varios participantes a unirse a la conversación.</span><span class="sxs-lookup"><span data-stu-id="2271f-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="2271f-111">Federación de Lync Server y Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="2271f-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="2271f-112">La Federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server admite comunicaciones de punto a punto y de varios participantes.</span><span class="sxs-lookup"><span data-stu-id="2271f-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="2271f-113">Las conversaciones de punto a punto se pueden escalar a conversaciones entre varias personas, lo que permite las reuniones ad hoc.</span><span class="sxs-lookup"><span data-stu-id="2271f-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="2271f-114">Las reuniones, las conferencias web o las conferencias de audio y vídeo se pueden programar para que incluyan contactos dentro de la organización, así como contactos en socios con los que haya establecido una relación de federación.</span><span class="sxs-lookup"><span data-stu-id="2271f-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="2271f-115">La Federación apareció por primera vez en Microsoft Office Live Communications Server 2005 y admitía un tipo de Federación, la Federación directa.</span><span class="sxs-lookup"><span data-stu-id="2271f-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="2271f-116">La Federación directa requirió conocer el dominio de protocolo de inicio de sesión (SIP) del socio de Federación y el nombre de dominio completo (FQDN) del servidor perimetral del asociado.</span><span class="sxs-lookup"><span data-stu-id="2271f-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="2271f-117">Live Communications Server 2005 con SP1 incorporó tipos de Federación adicionales, todos los cuales requerían que el socio federado publicara los registros SRV del sistema de nombres de dominio (DNS) para localizar su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="2271f-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="2271f-118">La terminología de aquella versión era:</span><span class="sxs-lookup"><span data-stu-id="2271f-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="2271f-119">*Federación ampliada abierta*: acepte cualquier nombre de dominio SIP y use DNS SRV para ubicar el servidor perimetral del asociado</span><span class="sxs-lookup"><span data-stu-id="2271f-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="2271f-120">*Federación mejorada*: configure el nombre de dominio SIP del asociado como asociado de Federación de su organización y use DNS SRV para buscar el servidor perimetral asociado</span><span class="sxs-lookup"><span data-stu-id="2271f-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="2271f-121">*Federación directa*: configure el nombre de dominio SIP del socio y el FQDN en el servidor perimetral del asociado</span><span class="sxs-lookup"><span data-stu-id="2271f-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="2271f-122">*Lista de permitidos del servidor*: aceptar cualquier dominio, usar DNS SRV para buscar el servidor perimetral de un proveedor de hospedaje o un proveedor de conectividad de mensajería instantánea (mi) pública</span><span class="sxs-lookup"><span data-stu-id="2271f-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="2271f-123">Microsoft Office Communications Server 2007 ha introducido un nombre actualizado para los tipos de Federación a fin de definir mejor el tipo de Federación que se ha realizado realmente:</span><span class="sxs-lookup"><span data-stu-id="2271f-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="2271f-124">La federación mejorada abierta se denominó *dominio de socio detectado*.</span><span class="sxs-lookup"><span data-stu-id="2271f-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="2271f-125">La federación mejorada se denominó *dominio de socio permitido*.</span><span class="sxs-lookup"><span data-stu-id="2271f-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="2271f-126">La federación directa se denominó *servidor de socio permitido*.</span><span class="sxs-lookup"><span data-stu-id="2271f-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="2271f-127">La lista de permisos del servidor se denominó *proveedor de hospedaje* y *proveedor de MI público*.</span><span class="sxs-lookup"><span data-stu-id="2271f-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="2271f-128">Microsoft Lync Server 2010 ha introducido una definición más estrecha del proveedor de hospedaje de acuerdo con Microsoft Lync Online 2010 y Microsoft Office 365, y también lo ha sujeto a la misma lista permitida definida por el tipo de Federación de dominio de socio permitido.</span><span class="sxs-lookup"><span data-stu-id="2271f-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="2271f-129">La habilitación de la Federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server usa los servidores perimetrales y los proxy inversos para aplicar las reglas y los dominios asociados permitidos que se definen.</span><span class="sxs-lookup"><span data-stu-id="2271f-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="2271f-130">Desde el punto de vista de la planeación, la Federación con otros Lync Server, Office Communications Server requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2271f-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="2271f-131">Habilite la federación en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="2271f-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="2271f-132">Para obtener más información, consulte el tema de implementación [configurar la Federación SIP, la Federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="2271f-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="2271f-133">Determine sus requisitos para la detección de dominios federados:</span><span class="sxs-lookup"><span data-stu-id="2271f-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="2271f-134">Para la configuración manual de la Federación, debe tener el nombre de dominio completo (FQDN) del servidor perimetral y el nombre de dominio del asociado, o el nombre de dominio en línea, que se especifica en el panel de control de Lync Server, **Federación y acceso externo**, **dominios federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="2271f-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="2271f-135">Cree una**nueva** directiva o **edite** una directiva actual para permitir o bloquear dominios por FQDN.</span><span class="sxs-lookup"><span data-stu-id="2271f-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="2271f-136">La configuración manual del servidor perimetral de un socio de Federación es propenso a errores en el caso de que el asociado cambie la dirección IP de su servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="2271f-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="2271f-137">Para los <STRONG>nuevos dominios federados SIP</STRONG>, debe proporcionar el <STRONG>nombre de dominio (o FQDN)</STRONG> para Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="2271f-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="2271f-138">Para Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server, también debe proporcionar un <STRONG>servicio perimetral de acceso (FQDN)</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="2271f-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="2271f-139">Para la Federación de asociados detectados, donde los asociados pueden descubrir el servidor perimetral, se crea un registro SRV en \_el DNS externo sipfederationtls. \_TCP.contoso.com – que apunta al puerto 5061 y al registro host (A) del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="2271f-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="2271f-140">Si admite clientes móviles de Microsoft Lync en Windows Phone o Apple iPhone, iPad u otros dispositivos Apple y usa el servicio de notificaciones de inserción o el servicio de notificaciones de inserción, debe planear _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="2271f-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="2271f-141">&lt;Registros SRV&gt; de dominio SIP para cada dominio SIP que tenga clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="2271f-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="2271f-142">Android y Nokia Symbian Lync Mobile no usan la notificación de inserción y no están sujetos a este requisito.</span><span class="sxs-lookup"><span data-stu-id="2271f-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="2271f-143">Configure las directivas de acceso de los usuarios externos para admitir los dominios federados.</span><span class="sxs-lookup"><span data-stu-id="2271f-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="2271f-144">Abra los puertos del firewall para el protocolo de inicio de sesión (SIP), las conferencias web y los audios y vídeos, con el fin de adaptar la federación o los contactos que está habilitando.</span><span class="sxs-lookup"><span data-stu-id="2271f-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="2271f-145">Para obtener más información, consulte: [determinar los requisitos de puerto y de Firewall a/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="2271f-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="2271f-146">La siguiente información le ayudará a definir el certificado, el puerto o el protocolo, y los requisitos de DNS para la Federación con Microsoft Lync Server 2013 y Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2271f-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="2271f-147">La planeación de certificados, requisitos de firewall y Puerto/protocolo y requisitos de DNS es, por lo general, un proceso directo de reenvío si ha planeado o implementado los servidores perimetrales de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2271f-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="2271f-148">Como la Federación es una característica adicional que usa el servidor perimetral existente, los requisitos de planeación suelen cumplirse con la planeación y la implementación del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="2271f-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="2271f-149">Use las tablas siguientes para determinar si se cumplen los requisitos, y realizar los cambios en el puerto o el protocolo y en el DNS según convenga.</span><span class="sxs-lookup"><span data-stu-id="2271f-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2271f-150">Si tiene un grupo de servidores perimetrales y está federando a los asociados de Lync Server 2013 o Lync Server 2010, puede usar equilibradores de carga de DNS o equilibradores de carga de hardware en los lados orientados internos y externos de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="2271f-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="2271f-151">Si está federando con Office Communications Server 2007 o con Office Communications Server 2007 R2, el equilibrio de carga de hardware proporcionará compatibilidad con la conmutación por error en caso de que se produce un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="2271f-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="2271f-152">Office Communications Server 2007 y Office Communications Server 2007 R2 no tienen en cuenta el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="2271f-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="2271f-153">Los servidores perimetrales asociados establecerán la comunicación con el primer servidor perimetral del grupo que responde.</span><span class="sxs-lookup"><span data-stu-id="2271f-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="2271f-154">Si se produce un error en ese servidor perimetral, la comunicación no realiza la conmutación por error automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2271f-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="2271f-155">Los requisitos de certificado se suelen cumplir mediante la planeación de certificados para el servidor perimetral elegido o el plan de servidor perimetral agrupado.</span><span class="sxs-lookup"><span data-stu-id="2271f-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="2271f-156">Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="2271f-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="2271f-157">La conectividad de mensajería instantánea pública es una clase de Federación y está configurada para permitir que los usuarios internos y externos de Lync Server 2013 puedan agregar contactos desde cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2271f-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="2271f-158">Contactos de Messenger</span><span class="sxs-lookup"><span data-stu-id="2271f-158">Messenger contacts</span></span>

  - <span data-ttu-id="2271f-159">Toolbar\!</span><span class="sxs-lookup"><span data-stu-id="2271f-159">Yahoo\!</span></span> <span data-ttu-id="2271f-160">contacts</span><span class="sxs-lookup"><span data-stu-id="2271f-160">contacts</span></span>

  - <span data-ttu-id="2271f-161">Contactos de America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="2271f-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="2271f-162">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="2271f-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="2271f-163">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="2271f-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="2271f-164">Messenger hasta la fecha de cierre del servicio (la fecha exacta todavía debe decidirse, pero no antes del 2013 de junio).</span><span class="sxs-lookup"><span data-stu-id="2271f-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="2271f-165">La capa de PIC es una licencia por usuario, por mes, que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="2271f-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="2271f-166">Service.</span><span class="sxs-lookup"><span data-stu-id="2271f-166">Messenger.</span></span> <span data-ttu-id="2271f-167">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente que no se renovará.</span><span class="sxs-lookup"><span data-stu-id="2271f-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="2271f-168">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="2271f-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="2271f-169">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="2271f-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="2271f-170">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de mensajería instantánea y voz.</span><span class="sxs-lookup"><span data-stu-id="2271f-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="2271f-171">Esta clase de federación requiere las siguientes consideraciones de planificación:</span><span class="sxs-lookup"><span data-stu-id="2271f-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="2271f-172">Los usuarios de Windows Live Messenger pueden tener comunicación de audio/visual de punto a punto con los usuarios de Lync Server 2013, además de la mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="2271f-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="2271f-173">Los servidores perimetrales deben cumplir unos requisitos de puerto y protocolo específicos.</span><span class="sxs-lookup"><span data-stu-id="2271f-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="2271f-174">Para obtener más información, consulte [determinación de requisitos de firewall y de puerto a/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2271f-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="2271f-175">La mensajería instantánea de Yahoo no tiene requisitos únicos, excepto los que se usan normalmente en la planeación y la implementación del servidor perimetral típico que proporciona la Federación.</span><span class="sxs-lookup"><span data-stu-id="2271f-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="2271f-176">America Online requiere que el certificado del servidor perimetral asignado al servicio perimetral de acceso tenga un uso mejorado de clave (EKU) de cliente.</span><span class="sxs-lookup"><span data-stu-id="2271f-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="2271f-177">Federación de protocolo extensible de mensajería y presencia (XMPP)</span><span class="sxs-lookup"><span data-stu-id="2271f-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="2271f-178">Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="2271f-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="2271f-179">En Microsoft Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica.</span><span class="sxs-lookup"><span data-stu-id="2271f-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="2271f-180">La funcionalidad XMPP se instala en dos partes: un proxy XMPP que se ejecuta en el servidor perimetral y la puerta de enlace XMPP que se ejecuta en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2271f-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="2271f-181">La implementación y la configuración de XMPP se trata en [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) planea admitir XMPP en su organización mediante la definición de reglas de puerto y protocolo en el firewall, la configuración de certificados y la adición de registros DNS.</span><span class="sxs-lookup"><span data-stu-id="2271f-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="2271f-182">En los siguientes temas de esta sección se resume la información necesaria para planear correctamente la Federación XMPP para la implementación.</span><span class="sxs-lookup"><span data-stu-id="2271f-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2271f-183">La capacidad XMPP de Lync Server 2013 se ha probado y es compatible con Microsoft para la Federación de mensajería instantánea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="2271f-183">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="2271f-184">Para cualquier otro sistema XMPP, póngase en contacto con el proveedor de terceros para comprobar que admiten la Federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="2271f-184">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2271f-185">La Federación de XMPP no es compatible con los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="2271f-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="2271f-186">Esto se aplica a ver la información de presencia y a intercambiar mensajes de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="2271f-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="2271f-187">En los siguientes temas se incluyen instrucciones para definir certificados, puertos de firewall y entradas DNS para los tipos de escenarios de Federación admitidos.</span><span class="sxs-lookup"><span data-stu-id="2271f-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="2271f-188">Resumen de certificado: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="2271f-189">Resumen de Puerto-SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="2271f-190">Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2271f-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="2271f-191">See Also</span></span>


[<span data-ttu-id="2271f-192">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="2271f-193">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="2271f-194">Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="2271f-195">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="2271f-196">Administrar la configuración perimetral de acceso para su organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="2271f-197">Administrar dominios federados SIP para la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="2271f-198">Administrar proveedores federados SIP para la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2271f-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

