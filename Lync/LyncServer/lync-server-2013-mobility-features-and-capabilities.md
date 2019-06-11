---
title: 'Lync Server 2013: Características y funcionalidad de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="beec7-102">Características y funcionalidad de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beec7-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beec7-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="beec7-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="beec7-104">La característica de movilidad introducida en las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero admite Lync 2010 para móviles y la funcionalidad de clientes móviles de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="beec7-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="beec7-105">Al implementar el servicio de movilidad de Lync Server 2013, los usuarios pueden usar Apple iOS, Android y Windows Phone compatibles, o dispositivos móviles Nokia Symbian para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver presencia.</span><span class="sxs-lookup"><span data-stu-id="beec7-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="beec7-106">Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y llamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="beec7-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="beec7-107">Las nuevas características introducidas en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 incluyen capacidad de voz sobre IP (VoIP) y vídeo (H. 264) para el Asistente de la reunión.</span><span class="sxs-lookup"><span data-stu-id="beec7-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="beec7-108">La característica de movilidad introducida en las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero es compatible con la funcionalidad de cliente móvil de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="beec7-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="beec7-109">Las actualizaciones acumulativas para Lync Server 2013: febrero 2013 Instale la API Web de comunicaciones unificadas, o UCWA.</span><span class="sxs-lookup"><span data-stu-id="beec7-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="beec7-110">UCWA es el componente que se usa para clientes móviles de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="beec7-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="beec7-111">En Lync Server 2013, MCX se usa para clientes móviles de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="beec7-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="beec7-112">Actualizaciones acumulativas para Lync Server 2013: febrero de 2013 introduce UCWA como el nuevo punto de entrada para los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="beec7-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="beec7-113">Lync Server 2013 implementa de forma simultánea el servicio de movilidad (MCX), presentado en las actualizaciones acumulativas para Lync Server 2010:2011 de noviembre, y proporciona soporte técnico para Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="beec7-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="beec7-114">Al implementar las actualizaciones acumulativas para Lync Server 2013: febrero de 2013, los usuarios pueden usar dispositivos móviles compatibles con Apple iOS, Android y Windows Phone para realizar estas actividades, como:</span><span class="sxs-lookup"><span data-stu-id="beec7-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="beec7-115">Características compatibles con el servicio de movilidad de las actualizaciones acumulativas para Lync Server 2010: el 2011 de noviembre se indica con (MCX).</span><span class="sxs-lookup"><span data-stu-id="beec7-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="beec7-116">UCWA admite todas las características de la lista, que se incluyen en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="beec7-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="beec7-117">Enviar y recibir mensajes instantáneos (MCX)</span><span class="sxs-lookup"><span data-stu-id="beec7-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="beec7-118">Ver presencia (MCX)</span><span class="sxs-lookup"><span data-stu-id="beec7-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="beec7-119">Ver contactos (MCX)</span><span class="sxs-lookup"><span data-stu-id="beec7-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="beec7-120">Haga clic para unirse a una conferencia (MCX)</span><span class="sxs-lookup"><span data-stu-id="beec7-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="beec7-121">Llamar a través del trabajo (MCX)</span><span class="sxs-lookup"><span data-stu-id="beec7-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="beec7-122">Alcance de un solo número (MCX)</span><span class="sxs-lookup"><span data-stu-id="beec7-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="beec7-123">Correo de voz (MCX)</span><span class="sxs-lookup"><span data-stu-id="beec7-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="beec7-124">Notificación de llamada perdida (MCX)</span><span class="sxs-lookup"><span data-stu-id="beec7-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="beec7-125">Voz sobre IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="beec7-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="beec7-126">Vídeo para asistentes (H.264)</span><span class="sxs-lookup"><span data-stu-id="beec7-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beec7-127">Lync 2010 Mobile proporcionó un cliente para dispositivos Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="beec7-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="beec7-128">Lync 2013 Mobile no tendrá un cliente para dispositivos basados en Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="beec7-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="beec7-129">Los usuarios de Apple iPad tendrán acceso a capacidades mejoradas.</span><span class="sxs-lookup"><span data-stu-id="beec7-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="beec7-130">Después de unirse a una reunión con la devolución de llamada de audio, un usuario de iPad podrá ver las presentaciones cargadas de Microsoft PowerPoint en una reunión, compartir aplicaciones y escritorios, ver la lista de participantes de la reunión y recibir notificaciones de otros tipos de contenido. que se comparten dentro de la reunión.</span><span class="sxs-lookup"><span data-stu-id="beec7-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="beec7-131">Con un único número, un usuario recibe llamadas en un teléfono móvil que se marcaron en el número del trabajo.</span><span class="sxs-lookup"><span data-stu-id="beec7-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="beec7-132">Con la llamada a través del trabajo, el usuario realiza una llamada saliente desde el cliente móvil de Lync usando un número de teléfono del trabajo en lugar del número de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="beec7-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="beec7-133">Con el marcado, el cliente envía una solicitud a MCX o UCWA (en función de la versión de Lync Mobile) para hacer la llamada.</span><span class="sxs-lookup"><span data-stu-id="beec7-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="beec7-134">El servidor inicia la llamada y, a continuación, vuelve a llamar al usuario en el teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="beec7-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="beec7-135">Cuando el usuario responde, el servidor completa la llamada marcando a la otra parte.</span><span class="sxs-lookup"><span data-stu-id="beec7-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="beec7-136">Al usar las llamadas a través del trabajo, los usuarios pueden mantener su identidad de trabajo durante una llamada, lo que significa que el destinatario de la llamada no verá el número de teléfono móvil de la persona que llama, y la persona que llama evitará los cargos de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="beec7-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="beec7-137">No todas las características funcionan exactamente igual en todos los dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="beec7-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="beec7-138">Para obtener más información sobre las características compatibles con dispositivos móviles, vea las tablas de <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>comparación de clientes móviles en.</span><span class="sxs-lookup"><span data-stu-id="beec7-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="beec7-139">Para obtener más información sobre los dispositivos y sistemas operativos compatibles, consulte los temas de requisitos en <A href="lync-server-2013-planning-for-mobile-clients.md">planificación de clientes móviles en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="beec7-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="beec7-140">Cuando usa la característica de detección automática de Lync Server 2013, las aplicaciones móviles pueden ubicar automáticamente los servicios Web de Lync Server 2013 sin que los usuarios tengan que introducir manualmente las direcciones URL en la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="beec7-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="beec7-141">También se admite la especificación manual de direcciones URL en la configuración de dispositivos móviles, principalmente para propósitos de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="beec7-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="beec7-142">MCX y UCWA son servicios complementarios y ambos se implementan para admitir clientes móviles de Lync 2010 Mobile y Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="beec7-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="beec7-143">Lync 2013 Mobile no podrá iniciar sesión en implementaciones de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="beec7-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="beec7-144">Lync 2010 Mobile y Lync 2013 Mobile podrán usar una implementación de Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013:2013 de febrero aplicado.</span><span class="sxs-lookup"><span data-stu-id="beec7-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="beec7-145">La característica de movilidad también admite las *notificaciones de inserción* en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="beec7-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="beec7-146">Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.</span><span class="sxs-lookup"><span data-stu-id="beec7-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="beec7-147">Por ejemplo, una invitación de mensajería instantánea (mi) perdida puede dar lugar a una notificación push.</span><span class="sxs-lookup"><span data-stu-id="beec7-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="beec7-148">MCX, UCWA, el servicio Detección automática y la compatibilidad con las notificaciones push se proporcionan en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="beec7-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="beec7-149">Las características de cliente actualizadas, las capacidades y el uso de UCWA como punto de entrada de movilidad se incluyen en las actualizaciones acumulativas para Lync Server 2013:2013 de febrero.</span><span class="sxs-lookup"><span data-stu-id="beec7-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

