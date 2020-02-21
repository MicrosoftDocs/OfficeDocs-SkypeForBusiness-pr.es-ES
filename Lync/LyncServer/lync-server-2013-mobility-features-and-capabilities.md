---
title: 'Lync Server 2013: funciones y características de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c534aa912e2564f8a8934aafa75bc52b76600795
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="9a999-102">Características y capacidades de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a999-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a999-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="9a999-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="9a999-104">La característica de movilidad que se incluye en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 admite Lync 2010 para móviles y la funcionalidad de clientes móviles de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9a999-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="9a999-105">Al implementar el servicio de movilidad de Lync Server 2013, los usuarios pueden usar dispositivos móviles Apple iOS, Android y Windows Phone compatibles, o dispositivos móviles Nokia Symbian para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver la presencia.</span><span class="sxs-lookup"><span data-stu-id="9a999-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="9a999-106">Asimismo, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y llamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="9a999-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="9a999-107">Las nuevas características presentadas en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 incluyen la capacidad de voz sobre IP (VoIP) y el vídeo (H. 264) para los asistentes a la reunión.</span><span class="sxs-lookup"><span data-stu-id="9a999-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="9a999-108">La característica de movilidad que se ha incluido en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013 admite la funcionalidad de cliente móvil de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9a999-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="9a999-109">Las actualizaciones acumulativas para Lync Server 2013: febrero 2013 instalar la API Web de comunicaciones unificadas, o UCWA.</span><span class="sxs-lookup"><span data-stu-id="9a999-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="9a999-110">UCWA es el componente usado para clientes móviles de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9a999-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="9a999-111">En Lync Server 2013, MCX se usa para clientes móviles de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="9a999-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="9a999-112">Actualizaciones acumulativas para Lync Server 2013: febrero de 2013 introduce UCWA como el nuevo punto de entrada para los servicios de movilidad.</span><span class="sxs-lookup"><span data-stu-id="9a999-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="9a999-113">Lync Server 2013 implementa de forma concurrente el servicio de movilidad (MCX), que se ha incluido en las actualizaciones acumulativas para Lync Server 2010:2011 de noviembre y proporciona soporte técnico para Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="9a999-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="9a999-114">Al implementar las actualizaciones acumulativas para Lync Server 2013: febrero de 2013, los usuarios pueden usar dispositivos móviles Apple iOS, Android y Windows Phone compatibles para realizar actividades como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a999-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a999-115">Las características admitidas por el servicio de movilidad de las actualizaciones acumulativas para Lync Server 2010: el 2011 de noviembre se indican con (MCX).</span><span class="sxs-lookup"><span data-stu-id="9a999-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="9a999-116">Las características enumeradas son compatibles con UCWA, que se incluyen en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="9a999-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="9a999-117">Enviar y recibir mensajes instantáneos (MCX)</span><span class="sxs-lookup"><span data-stu-id="9a999-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="9a999-118">Ver presencia (MCX)</span><span class="sxs-lookup"><span data-stu-id="9a999-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="9a999-119">Ver contactos (MCX)</span><span class="sxs-lookup"><span data-stu-id="9a999-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="9a999-120">Haga clic para unirse a una conferencia (MCX)</span><span class="sxs-lookup"><span data-stu-id="9a999-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="9a999-121">Llamar a través del trabajo (MCX)</span><span class="sxs-lookup"><span data-stu-id="9a999-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="9a999-122">Alcance de un solo número (MCX)</span><span class="sxs-lookup"><span data-stu-id="9a999-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="9a999-123">Correo de voz (MCX)</span><span class="sxs-lookup"><span data-stu-id="9a999-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="9a999-124">Notificación de llamada perdida (MCX)</span><span class="sxs-lookup"><span data-stu-id="9a999-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="9a999-125">Voz sobre IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="9a999-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="9a999-126">Vídeo de asistente (H. 264)</span><span class="sxs-lookup"><span data-stu-id="9a999-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a999-127">Lync 2010 Mobile proporcionó un cliente para dispositivos Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="9a999-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="9a999-128">Lync 2013 Mobile no tendrá un cliente para dispositivos basados en Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="9a999-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="9a999-129">Los usuarios de Apple iPad tendrán acceso a funciones mejoradas.</span><span class="sxs-lookup"><span data-stu-id="9a999-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="9a999-130">Después de unirse a una reunión mediante la devolución de llamada de audio, un usuario de iPad podrá ver las presentaciones cargadas de Microsoft PowerPoint en una reunión, compartir aplicaciones y escritorios, ver la lista de participantes de la reunión y recibir notificaciones de otros tipos de contenido. que se comparten en la reunión.</span><span class="sxs-lookup"><span data-stu-id="9a999-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9a999-131">Con un número único alcance, un usuario recibe llamadas en un teléfono móvil que se marcaron en el número de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9a999-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="9a999-132">Con llamar a través del trabajo, el usuario realiza una llamada saliente desde el cliente móvil de Lync mediante un número de teléfono del trabajo en lugar del número de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="9a999-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="9a999-133">Con las llamadas salientes, el cliente envía una solicitud a MCX o UCWA (en función de la versión de Lync Mobile) para realizar la llamada.</span><span class="sxs-lookup"><span data-stu-id="9a999-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="9a999-134">El servidor inicia la llamada y, a continuación, vuelve a llamar al usuario en el teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="9a999-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="9a999-135">Cuando el usuario responde, el servidor completa la llamada al llamar a la otra parte.</span><span class="sxs-lookup"><span data-stu-id="9a999-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="9a999-136">Mediante el uso de llamadas vía trabajo, los usuarios pueden mantener su identidad de trabajo durante una llamada, lo que significa que el destinatario de la llamada no ve el número de teléfono móvil del autor de la llamada, y el autor de la llamada evita los gastos de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="9a999-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9a999-137">No todas las características funcionan exactamente igual en todos los dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="9a999-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="9a999-138">Para obtener más información sobre las características admitidas en los dispositivos móviles, consulte las <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>tablas de comparación de clientes móviles en.</span><span class="sxs-lookup"><span data-stu-id="9a999-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="9a999-139">Para más detalles sobre los dispositivos compatibles y los dispositivos compatibles, consulte los temas de requisitos en <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for Mobile clients in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9a999-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9a999-140">Cuando se usa la característica detección automática de Lync Server 2013, las aplicaciones móviles pueden ubicar automáticamente los servicios Web de Lync Server 2013 sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9a999-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="9a999-141">También se admite la introducción manual de direcciones URL en la configuración de dispositivo móvil, principalmente con fines de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="9a999-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a999-142">MCX y UCWA son servicios complementarios que se implementan para admitir clientes móviles de Lync 2010 y Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9a999-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="9a999-143">Lync 2013 Mobile no podrá iniciar sesión en implementaciones de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9a999-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="9a999-144">Lync 2010 Mobile y Lync 2013 Mobile podrán usar una implementación de Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013:2013 de febrero aplicado.</span><span class="sxs-lookup"><span data-stu-id="9a999-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="9a999-145">La característica de movilidad también admite las *notificaciones de inserción* en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9a999-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="9a999-146">Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.</span><span class="sxs-lookup"><span data-stu-id="9a999-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="9a999-147">Por ejemplo, una invitación de mensajería instantánea (mi) perdida puede dar como resultado una notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="9a999-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="9a999-148">MCX, UCWA, el servicio Detección automática y la compatibilidad con notificaciones de inserción se proporcionan en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a999-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="9a999-149">Las características de cliente actualizadas, las capacidades y el uso de UCWA como punto de entrada de movilidad se incluyen en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="9a999-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

