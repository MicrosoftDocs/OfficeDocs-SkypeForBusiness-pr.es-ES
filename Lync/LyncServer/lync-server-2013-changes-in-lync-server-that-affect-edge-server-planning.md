---
title: 'Lync Server 2013: Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="862e8-102">Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="862e8-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="862e8-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="862e8-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="862e8-104">Lync Server 2013 presenta nuevas características que amplían las características y los métodos de comunicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="862e8-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="862e8-105">Además, Lync Server 2013 introduce cambios en los servicios existentes para mejorar la integración y la ampliación de los servicios que están disponibles para su organización.</span><span class="sxs-lookup"><span data-stu-id="862e8-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="862e8-106">A continuación se resume un resumen de los cambios que pueden afectar a la planificación y la implementación de los servicios del servidor perimetral 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="862e8-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="862e8-107">Compatibilidad con direcciones IPv6</span><span class="sxs-lookup"><span data-stu-id="862e8-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="862e8-108">Lync Server 2013 admite el direccionamiento IPv6 para todos los servicios de servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="862e8-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="862e8-109">Si ha proporcionado direcciones IPv6 para las interfaces mediante la configuración de Windows Server, puede usar direcciones IPv6 en la configuración de su servidor perimetral a través de la configuración de dirección IP en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="862e8-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="862e8-110">Además, el protocolo de presencia y mensajería extensible (XMPP) admite IPv6.</span><span class="sxs-lookup"><span data-stu-id="862e8-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="862e8-111">No se necesita ninguna configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="862e8-111">No additional configuration is required.</span></span> <span data-ttu-id="862e8-112">Si IPv6 está configurado en la topología, XMPP usará IPv6 (donde sea necesario).</span><span class="sxs-lookup"><span data-stu-id="862e8-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="862e8-113">Un requisito adicional para admitir IPv6 en Lync Server 2013 es crear registros del sistema de nombres de dominio para los registros que deben detectarse y resolverse en una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="862e8-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="862e8-114">IPv6 DNS usa registros de host que se definen como **AAAA** y se denomina "Quad-a".</span><span class="sxs-lookup"><span data-stu-id="862e8-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="862e8-115">Otros tipos de registro son coherentes con sus homólogos IPv4.</span><span class="sxs-lookup"><span data-stu-id="862e8-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="862e8-116">Compatibilidad con la implementación de protocolo de presencia y mensajería extensible (XMPP)</span><span class="sxs-lookup"><span data-stu-id="862e8-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="862e8-117">Edge Server presenta un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP (implementada en los servidores front-end).</span><span class="sxs-lookup"><span data-stu-id="862e8-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="862e8-118">Puede implementar la Federación XMPP como un componente opcional.</span><span class="sxs-lookup"><span data-stu-id="862e8-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="862e8-119">Al agregar y configurar el proxy XMPP y la puerta de enlace XMPP, puede habilitar a los usuarios de Microsoft Lync 2013 para que agreguen contactos de socios basados en XMPP para la mensajería instantánea (mi) y la presencia.</span><span class="sxs-lookup"><span data-stu-id="862e8-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="862e8-120">Por el momento, los servicios XMPP en el servidor perimetral solo proporcionan la mensajería instantánea y la presencia entre los clientes de Lync Server y los contactos basados en XMPP.</span><span class="sxs-lookup"><span data-stu-id="862e8-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="862e8-121">Además, XMPP está hospedado en un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="862e8-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="862e8-p106">La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="862e8-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="862e8-124">Compatibilidad con la autenticación de audio/vídeo y los certificados de autenticación de servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="862e8-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="862e8-125">Un certificado se usa para generar tokens emitidos para clientes y otros consumidores del servicio de autenticación A/V y para la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="862e8-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="862e8-126">El certificado de autenticación de audio y vídeo es de tipo *AudioVideoAuthentication* y el certificado de autenticación de servidor a servidor es de tipo *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="862e8-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="862e8-127">Para la autenticación de audio y vídeo, los tokens se usan para autenticar las solicitudes de asignación de puertos y los tokens se almacenan en la memoria caché durante un máximo de 8 horas, es decir, la duración predeterminada del token.</span><span class="sxs-lookup"><span data-stu-id="862e8-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="862e8-128">Bajo el funcionamiento normal, este es un método muy confiable para crear y distribuir material de autenticación a los consumidores a/V.</span><span class="sxs-lookup"><span data-stu-id="862e8-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="862e8-129">Sin embargo, los certificados tienen una duración finita y vencen en una fecha y hora predefinidas (según la fecha de creación y las directivas que se aplican en la entidad emisora de certificados que creó el certificado, normalmente 2 años para este tipo de certificado).</span><span class="sxs-lookup"><span data-stu-id="862e8-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="862e8-130">Cuando el certificado expira, todos los tokens creados por el certificado expirado y almacenados en caché por consumidores no son válidos.</span><span class="sxs-lookup"><span data-stu-id="862e8-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="862e8-131">Si los intentos de usar un token creado con un certificado caducado, se producía un error en las asignaciones de retransmisión multimedia y se producirá un error en las sesiones de audio o vídeo actuales.</span><span class="sxs-lookup"><span data-stu-id="862e8-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="862e8-132">El cliente necesitaría adquirir un nuevo token creado por un certificado válido para reanudar la funcionalidad de audio y vídeo normal.</span><span class="sxs-lookup"><span data-stu-id="862e8-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="862e8-133">La autenticación de servidor a servidor se administra mediante un certificado global que se solicita y se aplica a todos los servidores de la implementación.</span><span class="sxs-lookup"><span data-stu-id="862e8-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="862e8-134">El certificado es responsable de autenticar los servidores en Lync Server 2013, así como de autenticar a Exchange 2013 y Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="862e8-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="862e8-135">Para obtener más información sobre cómo funciona la autenticación de servidor a servidor, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="862e8-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="862e8-136">Una diferencia muy importante entre el proceso de autenticación de audio y vídeo y el proceso de autenticación de servidor a servidor es la duración de la autenticación o los tokens.</span><span class="sxs-lookup"><span data-stu-id="862e8-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="862e8-137">Para la autenticación de audio y vídeo, la autenticación vence después de ocho horas.</span><span class="sxs-lookup"><span data-stu-id="862e8-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="862e8-138">La autenticación de servidor a servidor tiene una duración de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="862e8-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="862e8-139">Debe planificar según corresponda para cada uno de los tipos de certificados.</span><span class="sxs-lookup"><span data-stu-id="862e8-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="862e8-140">Novedades de Lync Server 2013 es la capacidad de ensayar un certificado de autenticación de audio y vídeo de reemplazo y un certificado de autenticación de servidor a servidor antes de la fecha de expiración del certificado actual.</span><span class="sxs-lookup"><span data-stu-id="862e8-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="862e8-141">El nuevo certificado se usa para generar nuevos tokens o solicitudes de autenticación nuevas.</span><span class="sxs-lookup"><span data-stu-id="862e8-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="862e8-142">pero conserva el certificado antiguo para comprobar las sesiones actuales y las autenticaciones..</span><span class="sxs-lookup"><span data-stu-id="862e8-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="862e8-143">Lo que logra es evitar de forma eficaz casi todos los errores debido a la expiración de los tokens y los certificados.</span><span class="sxs-lookup"><span data-stu-id="862e8-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="862e8-144">Para obtener más información sobre esta característica y cómo configurarla, consulte [almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usar-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="862e8-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="862e8-145">Disminución de la dependencia de afinidad basada en cookies</span><span class="sxs-lookup"><span data-stu-id="862e8-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="862e8-146">En versiones anteriores de Lync Server y Office Communications Server, los servicios web usaban la afinidad basada en cookies para garantizar que se mantuvo el estado de la sesión de los servicios web y del cliente.</span><span class="sxs-lookup"><span data-stu-id="862e8-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="862e8-147">Los servicios Web de Lync Server 2013 usan un mecanismo de afinidad integrado que elimina la mayoría de los requisitos de afinidad basada en cookies.</span><span class="sxs-lookup"><span data-stu-id="862e8-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="862e8-148">El cliente móvil de Microsoft Lync 2010 aún debe usar afinidad basada en cookies y necesitará la configuración de la afinidad basada en cookies hasta que haya migrado todos los clientes al próximo cliente móvil de Microsoft Lync (fecha de lanzamiento no establecida aún).</span><span class="sxs-lookup"><span data-stu-id="862e8-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="862e8-149">Para obtener detalles sobre la afinidad basada en cookies en Lync Server 2013, vea [componentes necesarios para el acceso de usuarios externos en Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="862e8-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="862e8-150">Mejoras de detección automática</span><span class="sxs-lookup"><span data-stu-id="862e8-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="862e8-151">La característica de detección automática de Lync Server 2013 permite a los clientes localizar características adicionales que estén disponibles para la comunicación.</span><span class="sxs-lookup"><span data-stu-id="862e8-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="862e8-152">Detección automática se presentó por primera vez en la actualización acumulativa para Lync Server 2010:2011 de noviembre para movilidad y Microsoft Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="862e8-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="862e8-153">La característica de detección automática (también conocida por los nombres de registros DNS LyncDiscover y LyncDiscoverInternal) permite a los clientes ubicar y usar los servicios de movilidad (para clientes móviles de Microsoft Lync 2010), Microsoft Lync Web App y Lync web Scheduler, así como comunicaciones con Microsoft Exchange Server y SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="862e8-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="862e8-154">Detección automática se instala como parte normal de la configuración e implementación de su infraestructura y los servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="862e8-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="862e8-155">El generador de topología y el Asistente para la implementación de Lync Server eliminan la mayoría de las tareas de configuración que se requirieron en la actualización acumulativa para Lync Server 2010:2011 de noviembre.</span><span class="sxs-lookup"><span data-stu-id="862e8-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="862e8-156">Servicios para clientes móviles</span><span class="sxs-lookup"><span data-stu-id="862e8-156">Services for Mobile Clients</span></span>

<span data-ttu-id="862e8-157">Presentado en la actualización acumulativa para Lync Server 2010:2011 de noviembre, servicios de movilidad en Lync Server 2013 habilitar teléfonos móviles con dispositivos móviles y tabletas Lync compatibles con Apple iOS, Android, Windows Phone o dispositivos móviles Nokia para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver presencia.</span><span class="sxs-lookup"><span data-stu-id="862e8-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="862e8-158">Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y notificación de llamada perdida.</span><span class="sxs-lookup"><span data-stu-id="862e8-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="862e8-159">Los servicios de movilidad usan el proxy inverso y los servicios publicados que se implementan en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="862e8-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="862e8-160">No es necesario realizar cambios en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="862e8-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="862e8-161">En el servidor que ejecuta el servicio perimetral de acceso de Lync Server, lo mínimo que se necesita es SIP/TCP/5061from.</span><span class="sxs-lookup"><span data-stu-id="862e8-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="862e8-162">El rol de director es opcional</span><span class="sxs-lookup"><span data-stu-id="862e8-162">Director Role is Optional</span></span>

<span data-ttu-id="862e8-163">La función del servidor Director en la topología de Lync Server 2013 no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="862e8-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="862e8-164">Aún, hospeda servicios Web, preautentica las solicitudes de usuario entrantes y dirige a los usuarios externos a su grupo de servidores principales.</span><span class="sxs-lookup"><span data-stu-id="862e8-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="862e8-165">Al cambiar el director de un rol recomendado a un rol opcional, Microsoft no pretende disminuir el valor del director.</span><span class="sxs-lookup"><span data-stu-id="862e8-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="862e8-166">La intención es reducir el número de servidores y otros requisitos de hardware (por ejemplo, los equilibradores de carga de hardware del Director) sin comprometer las características ni la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="862e8-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="862e8-167">Como los servidores de aplicaciones para el usuario pueden hacer el mismo trabajo que el director sin impacto alguno en los servicios proporcionados, puede implementar directores si así lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="862e8-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="862e8-168">Puede excluir sin riesgos al director con la confianza de que los servidores front-end proporcionarán los mismos servicios en lugar de un director.</span><span class="sxs-lookup"><span data-stu-id="862e8-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

