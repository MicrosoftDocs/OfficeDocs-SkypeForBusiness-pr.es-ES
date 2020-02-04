---
title: 'Lync Server 2013: Topologías y componentes para movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739deecf47e25e57ca0175c29a2721e509f8dbe2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="0157f-102">Topologías y componentes para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0157f-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0157f-103">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="0157f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="0157f-104">Para admitir las aplicaciones móviles de Lync en dispositivos móviles, Lync Server 2013 proporciona tres servicios: Lync Server 2013 MCX Mobility Service, servicio Detección automática de Lync Server 2013 y servicio de notificaciones push de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0157f-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="0157f-105">Las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 agrega un servicio gratuito, pero avanzado, para clientes móviles de Lync 2013, soporte de movilidad mediante el uso de la API Web de comunicaciones unificadas, o UCWA.</span><span class="sxs-lookup"><span data-stu-id="0157f-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="0157f-106">En esta sección se describen brevemente estos componentes y se identifican las topologías de Lync Server 2013 que admiten movilidad.</span><span class="sxs-lookup"><span data-stu-id="0157f-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0157f-107">Los servicios de movilidad también están disponibles en implementaciones híbridas.</span><span class="sxs-lookup"><span data-stu-id="0157f-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="0157f-108">No es necesario implementar servicios para admitir la movilidad si los usuarios están conectados.</span><span class="sxs-lookup"><span data-stu-id="0157f-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="0157f-109">Debe definir una configuración para que el servicio de detección automática permita que los usuarios móviles encuentren su identidad en línea.</span><span class="sxs-lookup"><span data-stu-id="0157f-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0157f-110">Si planea una conectividad de usuario externa (por ejemplo, Federación, acceso de usuarios externos o características de movilidad), debe usar servidores perimetrales con servidor Standard Edition y el servidor front-end o grupo front-end.</span><span class="sxs-lookup"><span data-stu-id="0157f-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="0157f-111">El servidor Standard Edition y el servidor front-end o el grupo front-end no tienen los componentes necesarios para permitir a los usuarios externos el acceso a su implementación interna o para que la implementación interna se comunique con los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="0157f-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="0157f-112">Para todos los escenarios en los que se incluyen usuarios externos que colaboran o comunican con usuarios internos, incluida la movilidad, debe implementar al menos un servidor perimetral y un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="0157f-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="0157f-113">La <EM>notificación de inserción</EM> usa un tipo de Federación a los servicios de Lync Online, que hospeda el centro de enrutamiento de notificaciones de inserción (PNCH).</span><span class="sxs-lookup"><span data-stu-id="0157f-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="0157f-114">La notificación push hace referencia a las alertas de sonido, las alertas en pantalla (texto) y los insignias que las aplicaciones envían a Apple iPhone, iPad y Windows Phone, cuando el dispositivo móvil está inactivo.</span><span class="sxs-lookup"><span data-stu-id="0157f-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="0157f-115">PNCH recibe notificaciones push de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0157f-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="0157f-116">Cuando PNCH recibe una notificación de un mensaje, PNCH reenvía una notificación a los clientes móviles a través del servicio de notificaciones push de Apple push Notification Services o Lync Server 2013, en función del cliente móvil al que se destina el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0157f-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="0157f-117">PNCH es un servicio necesario para estos clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="0157f-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="0157f-118">Para federarse a Lync Online, PNCH usa servidores perimetrales y certificados para garantizar la confidencialidad, la autenticación, las directivas y los registros del sistema de nombres de dominio (DNS) correctamente configurado.</span><span class="sxs-lookup"><span data-stu-id="0157f-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="0157f-119">Nokia Symbian y los clientes de Lync Mobile basados en Android no usan PNCH.</span><span class="sxs-lookup"><span data-stu-id="0157f-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="0157f-120">Para obtener más información sobre la planeación y la implementación de servidores perimetrales, vea <A href="lync-server-2013-planning-for-external-user-access.md">planear el acceso de usuarios externos en Lync server 2013</A> e <A href="lync-server-2013-deploying-external-user-access.md">implementar el acceso de usuarios externos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0157f-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="0157f-121">Los clientes móviles de Lync 2013 para dispositivos Apple se introdujeron con las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 ya no usan la notificación de inserción o el centro de enrutamiento de notificaciones de inserción (PNCH).</span><span class="sxs-lookup"><span data-stu-id="0157f-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="0157f-122">Los clientes móviles de Lync 2013 en Windows Phone siguen usando la notificación de inserción y (PNCH).</span><span class="sxs-lookup"><span data-stu-id="0157f-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="0157f-123">Componentes de movilidad</span><span class="sxs-lookup"><span data-stu-id="0157f-123">Mobility Components</span></span>

<span data-ttu-id="0157f-124">Los servicios que admiten la movilidad son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0157f-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="0157f-125">**La API Web de comunicaciones unificadas de Lync Server 2013 (UCWA)**   proporciona servicios para las comunicaciones en tiempo real con clientes móviles y Web en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0157f-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="0157f-126">Al implementar las actualizaciones acumulativas para Lync Server 2013:2013 de febrero al servidor front-end y el director, la instalación crea un directorio virtual en los servicios Web internos y externos (Ucwa).</span><span class="sxs-lookup"><span data-stu-id="0157f-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="0157f-127">Un componente web que forma parte del directorio virtual Ucwa acepta llamadas de clientes habilitados en UCWA.</span><span class="sxs-lookup"><span data-stu-id="0157f-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="0157f-128">Las aplicaciones cliente se comunican a través de una interfaz REST de presencia, contactos, mensajería instantánea, VoIP, videoconferencias y colaboración.</span><span class="sxs-lookup"><span data-stu-id="0157f-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="0157f-129">UCWA usa un canal basado en P-GET para enviar eventos, como una llamada entrante, un mensaje instantáneo entrante o un mensaje a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="0157f-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0157f-130">El <EM>resto</EM> de la transferencia del estado de la presentación, es un estilo arquitectónico de software para sistemas distribuidos que se ha adoptado ampliamente en muchas formas y es muy adecuado para los requisitos de los servicios web en general.</span><span class="sxs-lookup"><span data-stu-id="0157f-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="0157f-131">**Lync Server 2013 Mobility Service (MCX)**   este servicio admite la funcionalidad de Lync, como la mensajería instantánea (mi), la presencia y los contactos, en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="0157f-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="0157f-132">El servicio de movilidad se instala en todos los servidores front-end de cada grupo para admitir la funcionalidad de Lync en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="0157f-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="0157f-133">Al instalar Lync Server 2013, se crea un nuevo directorio virtual (MCX) en el sitio Web interno y en el sitio web externo de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="0157f-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0157f-134">Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero es compatible con el servicio de movilidad introducido en la actualización acumulativa para Lync Server 2010:2011 de noviembre (conocido comúnmente como MCX y el componente Web de UCWA).</span><span class="sxs-lookup"><span data-stu-id="0157f-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="0157f-135">La combinación de estos dos servicios de movilidad proporciona interoperabilidad y uso por parte de los usuarios con Lync 2010 Mobile y clientes móviles de Lync 2013 en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0157f-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="0157f-136">**Servicio Detección automática de Lync Server 2013**   este servicio identifica la ubicación del usuario y permite que los dispositivos móviles y otros clientes de Lync encuentren recursos, como las direcciones URL internas y externas para los servicios Web de Lync Server 2013 y la dirección URL de MCX o UCWA, independientemente de la ubicación de red.</span><span class="sxs-lookup"><span data-stu-id="0157f-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="0157f-137">El descubrimiento automático usa nombres de host codificados (lyncdiscoverinternal para los usuarios de la red; lyncdiscover para usuarios ajenos a la red) y el dominio SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="0157f-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="0157f-138">Admite conexiones de cliente con HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0157f-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="0157f-139">El servicio de detección automática se instala en todos los servidores front-end y en cada director de cada grupo que sea compatible con la funcionalidad de Lync en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="0157f-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="0157f-140">Al instalar el servicio Detección automática, se crea un nuevo directorio virtual (detección automática) en el sitio Web interno y en el sitio web externo, tanto en servidores de aplicaciones para el usuario como en directores.</span><span class="sxs-lookup"><span data-stu-id="0157f-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0157f-141">El servicio Detección automática aparece aquí porque sigue siendo un componente crítico al proporcionar servicios de cliente móvil.</span><span class="sxs-lookup"><span data-stu-id="0157f-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="0157f-142">El rol de detección automática en Lync Server 2013 se ha expandido para proporcionar servicios para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="0157f-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="0157f-143">Para obtener más información sobre cómo planear el servicio de detección automática, consulte <A href="lync-server-2013-planning-for-autodiscover.md">planificación de la detección automática en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0157f-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="0157f-144">**Servicio de notificaciones push**   este servicio es un servicio basado en la nube que se encuentra en el centro de datos de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0157f-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="0157f-145">Cuando la aplicación móvil de Lync en un dispositivo iOS de Apple compatible o en Windows Phone no está activa, no puede responder a eventos nuevos, como una nueva invitación de mensajería instantánea (mi), un mensaje instantáneo perdido, una llamada perdida o correo de voz, porque estos dispositivos no son compatibles aplicaciones móviles que se ejecutan en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="0157f-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="0157f-146">En estos casos, se envía al dispositivo móvil una notificación del nuevo evento (denominado *notificación de inserción*).</span><span class="sxs-lookup"><span data-stu-id="0157f-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="0157f-147">El servicio de movilidad envía la notificación al servicio de notificaciones de inserción basado en la nube, que después envía la notificación al servicio de notificaciones push de Apple (APN) (para dispositivos Apple iOS compatibles) o al servicio de notificaciones push de Microsoft (MPNS ) (para Windows Phone), que a su vez la envía al dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="0157f-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="0157f-148">Después, el usuario puede responder a la notificación en el dispositivo móvil para activar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0157f-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="0157f-149">Lync 2010 Mobile en dispositivos Apple y Windows Phone usa notificaciones Push.</span><span class="sxs-lookup"><span data-stu-id="0157f-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="0157f-150">El cliente móvil de Lync 2013 para dispositivos Apple introducido con las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero ya no usa la notificación de inserción ni el centro de enrutamiento de notificaciones de inserción (PNCH).</span><span class="sxs-lookup"><span data-stu-id="0157f-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="0157f-151">En el siguiente diagrama se muestra cómo el servicio de notificaciones de inserción encaja en una topología de Lync Server 2013 que usa UCWA y clientes móviles de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0157f-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="0157f-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="0157f-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="0157f-153">Introducido en la actualización acumulativa para Lync Server 2010:2011 de noviembre, el servicio MCX ofrece servicios a clientes móviles de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="0157f-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="0157f-154">En el siguiente diagrama se muestra el servicio de notificaciones push tal y como se aplica a una topología mediante MCX y clientes móviles de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="0157f-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="0157f-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="0157f-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="0157f-156">Topologías admitidas</span><span class="sxs-lookup"><span data-stu-id="0157f-156">Supported Topologies</span></span>

<span data-ttu-id="0157f-157">Aplicar las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero agrega los componentes Web de UCWA para admitir la movilidad de las características de cliente móvil de Lync 2013 en las siguientes topologías:</span><span class="sxs-lookup"><span data-stu-id="0157f-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="0157f-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0157f-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="0157f-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="0157f-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="0157f-160">El servidor perimetral puede ser un servidor perimetral de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0157f-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="0157f-161">Una implementación de Lync Server 2013 sin las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero usará el servicio de movilidad MCX y solo puede proporcionar servicios para Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="0157f-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0157f-162">El servicio de movilidad es compatible con los servidores front-end que se colocan con la función de servidor de mediación con dos interfaces de red, pero debe seguir los pasos adecuados para configurar las interfaces.</span><span class="sxs-lookup"><span data-stu-id="0157f-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="0157f-163">Debe asignar las direcciones IP a la interfaz específica que se comunicará como el servidor de mediación y la IP de la interfaz de red que se comunicará como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="0157f-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="0157f-164">Puede hacerlo en el generador de topología seleccionando la dirección IP correcta para cada servicio, en lugar de <STRONG>usar las direcciones IP configuradas</STRONG>de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0157f-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0157f-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="0157f-165">See Also</span></span>


[<span data-ttu-id="0157f-166">Planear acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0157f-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="0157f-167">Implementar el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0157f-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="0157f-168">Planificación de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0157f-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

