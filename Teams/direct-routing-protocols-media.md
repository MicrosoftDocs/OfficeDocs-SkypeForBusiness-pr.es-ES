---
title: Enrutamiento directo del Sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: Protocolos de enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08b022799b2c8bf80ee30cbb0a5ef3e74f0a29e1
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065670"
---
# <a name="overview"></a><span data-ttu-id="51871-103">Información general</span><span class="sxs-lookup"><span data-stu-id="51871-103">Overview</span></span>

<span data-ttu-id="51871-104">En este artículo se describe cómo el enrutamiento directo admite la omisión de elementos multimedia con un controlador de borde de sesión (SBC) habilitado para ICE Lite, como se describe en [RFC 5245](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="51871-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="51871-105">Este artículo está dirigido a los administradores de voz responsables de configurar la conexión entre el SBC local y el servicio de proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="51871-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="51871-106">Este artículo proporciona una descripción general de los escenarios de ICE Lite y los requisitos de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="51871-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="51871-107">En este artículo se describen los formatos de mensaje y las transiciones de equipos de estado necesarias para garantizar una llamada y un flujo de medios confiables.</span><span class="sxs-lookup"><span data-stu-id="51871-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="51871-108">Terminología</span><span class="sxs-lookup"><span data-stu-id="51871-108">Terminology</span></span>

- <span data-ttu-id="51871-109">Primero Hola: las primeras palabras que habla la persona que llama y la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="51871-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="51871-110">Es importante que se realicen todos los esfuerzos para asegurarse de que los primeros paquetes de los puntos de conexión se entreguen de manera confiable para la mayoría de los casos de uso.</span><span class="sxs-lookup"><span data-stu-id="51871-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="51871-111">Bifurcación: la oferta de la persona que llama puede ser entregada a varios puntos de conexión de llamadas si el destinatario de la llamada está disponible en varios dispositivos (por ejemplo, un usuario de equipos puede haber iniciado sesión en Teams para Windows y Teams para Android o iPhone).</span><span class="sxs-lookup"><span data-stu-id="51871-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="51871-112">Respuesta provisional (183): los puntos de conexión de llamadas para acelerar la configuración de llamadas envían una respuesta con los candidatos y claves necesarios para establecer el flujo de medios.</span><span class="sxs-lookup"><span data-stu-id="51871-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="51871-113">Esto se realiza en previsión de que el usuario pueda responder a la llamada (200OK) de esa instancia específica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="51871-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="51871-114">Con la ramificación, la persona que llama debe estar lista para recibir varias respuestas provisionales.</span><span class="sxs-lookup"><span data-stu-id="51871-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="51871-115">Volver a invitar: oferta con candidatos finales seleccionado por el punto final del control de hielo.</span><span class="sxs-lookup"><span data-stu-id="51871-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="51871-116">Esto tendrá el atributo a = candidato a candidatos remotos para resolver las condiciones de carrera y controlar varias bifurcaciones.</span><span class="sxs-lookup"><span data-stu-id="51871-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="51871-117">Punto de conexión de equipos: puede ser un servidor (procesador multimedia, retransmisión de transporte) o el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="51871-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="51871-118">Formato del mensaje</span><span class="sxs-lookup"><span data-stu-id="51871-118">Message format</span></span>

<span data-ttu-id="51871-119">La infraestructura de Teams sigue el RFC 5245 para ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="51871-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="51871-120">Esto implica que todos los mensajes STUN serán compatibles con el [RFC 5389](https://tools.ietf.org/html/rfc5389).</span><span class="sxs-lookup"><span data-stu-id="51871-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="51871-121">El SBCs según lo solicite el RFC 5389 debe omitir los atributos STUN que no reconozcan y continuar procesando los mensajes con los atributos conocidos.</span><span class="sxs-lookup"><span data-stu-id="51871-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="51871-122">Si se reciben paquetes mal formados, los paquetes se deben descartar sin afectar al establecimiento de la sesión de medios.</span><span class="sxs-lookup"><span data-stu-id="51871-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="51871-123">Requisitos de ICE Lite</span><span class="sxs-lookup"><span data-stu-id="51871-123">ICE Lite requirements</span></span>

<span data-ttu-id="51871-124">Esta sección captura brevemente los requisitos de ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="51871-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="51871-125">Recopilación de candidatos</span><span class="sxs-lookup"><span data-stu-id="51871-125">Candidate gathering</span></span>

<span data-ttu-id="51871-126">La SBC debe ofrecer un candidato que sea accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="51871-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="51871-127">Actualmente, solo se admiten los candidatos IPV4.</span><span class="sxs-lookup"><span data-stu-id="51871-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="51871-128">Comprobaciones de conectividad</span><span class="sxs-lookup"><span data-stu-id="51871-128">Connectivity checks</span></span>

<span data-ttu-id="51871-129">La implementación de ICE Lite debe responder a las comprobaciones de conectividad recibidas.</span><span class="sxs-lookup"><span data-stu-id="51871-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="51871-130">El punto final de ICE Lite no debe enviar solicitudes de comprobación de conectividad.</span><span class="sxs-lookup"><span data-stu-id="51871-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="51871-131">(Si se envían infracciones las comprobaciones de conectividad, la implementación completa responderá, lo que puede provocar que se descubran candidatos derivados del mismo nivel inesperados y producir errores de llamadas).</span><span class="sxs-lookup"><span data-stu-id="51871-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="51871-132">Nominaciones</span><span class="sxs-lookup"><span data-stu-id="51871-132">Nominations</span></span>

<span data-ttu-id="51871-133">El extremo de la implementación completa de ICE siempre será el extremo de control y seguirá las nominaciones "normales" para seleccionar los candidatos finales que se usarán para el flujo de medios.</span><span class="sxs-lookup"><span data-stu-id="51871-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="51871-134">El punto final de hielo Lite puede usar las nominaciones para concluir la ruta que se utilizará para los medios y el establecimiento completo de llamadas.</span><span class="sxs-lookup"><span data-stu-id="51871-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="51871-135">Nota: en el caso de bifurcación con puntos de conexión del mismo nivel enviando respuestas provisionales de 183, la SBC debe estar preparada para responder a las comprobaciones de varios puntos finales y también a las nominaciones de varios puntos finales si las nominaciones se producen antes de 200OK.</span><span class="sxs-lookup"><span data-stu-id="51871-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="51871-136">En función de la convergencia de la máquina de estado de hielo en la ruta de acceso final y en el momento de la respuesta del usuario, las nominaciones pueden ocurrir antes o después de la 200OK.</span><span class="sxs-lookup"><span data-stu-id="51871-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="51871-137">La SBC debe poder controlar ambos casos.</span><span class="sxs-lookup"><span data-stu-id="51871-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="51871-138">Convergencia de la ramificación</span><span class="sxs-lookup"><span data-stu-id="51871-138">Converging for forking</span></span>

<span data-ttu-id="51871-139">Si la oferta de la horquilla de SBC para los puntos de conexión de varios equipos, los puntos de conexión de Teams pueden responder con una respuesta provisional y empezar las comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="51871-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="51871-140">El SBC debe estar preparado para recibir comprobaciones de conectividad y responder a las comprobaciones de conectividad de varios puntos de conexión del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="51871-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="51871-141">Por ejemplo, el usuario de Teams podría iniciar sesión en un equipo de escritorio y un teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="51871-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="51871-142">Se notificará a ambos dispositivos de la llamada entrante y se intentarán las comprobaciones de conectividad con el SBC.</span><span class="sxs-lookup"><span data-stu-id="51871-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="51871-143">Hasta el momento, solo uno de los puntos de conexión responderá a la llamada (200OK).</span><span class="sxs-lookup"><span data-stu-id="51871-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="51871-144">Al recibir la 200OK, la SBC puede configurar el contexto adecuado para procesar los paquetes de medios.</span><span class="sxs-lookup"><span data-stu-id="51871-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="51871-145">Escenarios</span><span class="sxs-lookup"><span data-stu-id="51871-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="51871-146">Llamada entrante de SBC</span><span class="sxs-lookup"><span data-stu-id="51871-146">Inbound call from SBC</span></span>

<span data-ttu-id="51871-147">Para este escenario, hay varios puntos de conexión posibles del mismo nivel que el SBC debe controlar:</span><span class="sxs-lookup"><span data-stu-id="51871-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="51871-148">Los puntos de conexión de servidor normalmente responderán directamente con 200OK.</span><span class="sxs-lookup"><span data-stu-id="51871-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="51871-149">Se trata de puntos de conexión de hielo completos que normalmente participan en el buzón de voz, la cola de llamadas y los escenarios de operador automático.</span><span class="sxs-lookup"><span data-stu-id="51871-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="51871-150">Los puntos de conexión de cliente pueden enviar varias respuestas provisionales con diferentes etiquetas from/to (183) seguidas de 200OK desde el extremo que responde a la llamada.</span><span class="sxs-lookup"><span data-stu-id="51871-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="51871-151">Estos son puntos de conexión de hielo completos que suelen representar clientes de usuario final.</span><span class="sxs-lookup"><span data-stu-id="51871-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="51871-152">Otros puntos de conexión de SBC.</span><span class="sxs-lookup"><span data-stu-id="51871-152">Other SBC endpoints.</span></span> <span data-ttu-id="51871-153">Estos son puntos de conexión de ICE Lite generalmente implicados en el escenario de llamadas simultáneas a puntos de conexión de cliente y otro número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="51871-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="51871-154">El SBC debe responder a todas las solicitudes de comprobación de conectividad válidas recibidas de los puntos de conexión de hielo completos.</span><span class="sxs-lookup"><span data-stu-id="51871-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="51871-155">Por RFC, los puntos de conexión de hielo completos se convertirán en el control de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="51871-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="51871-156">Los puntos de conexión de Teams (cliente/servidor) realizarán nominaciones "normales" para completar las comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="51871-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="51871-157">El 200Ok final puede ser de un extremo que envió medios anteriores o de un extremo diferente.</span><span class="sxs-lookup"><span data-stu-id="51871-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="51871-158">Al recibir la 200Ok, el SBC debe configurar el contexto adecuado para el flujo de medios.</span><span class="sxs-lookup"><span data-stu-id="51871-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="51871-159">Primeros medios</span><span class="sxs-lookup"><span data-stu-id="51871-159">Early media</span></span>

<span data-ttu-id="51871-160">Si hay un flujo de medios temprano, el SBC debe aplatchar el primer punto de conexión que empiece a transmitir contenido multimedia; el flujo de medios puede iniciarse antes de que se nominar candidatos.</span><span class="sxs-lookup"><span data-stu-id="51871-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="51871-161">El SBC debería admitir el envío de DTMF durante esta fase para habilitar escenarios de IVR/buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="51871-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="51871-162">La SBC debe usar la ruta de prioridad más alta en la que ha recibido comprobaciones si las nominaciones no se han completado.</span><span class="sxs-lookup"><span data-stu-id="51871-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="51871-163">Llamada saliente a SBC</span><span class="sxs-lookup"><span data-stu-id="51871-163">Outbound call to SBC</span></span>

<span data-ttu-id="51871-164">Los puntos de conexión de Teams son la persona que llama para este escenario y será el extremo de control.</span><span class="sxs-lookup"><span data-stu-id="51871-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="51871-165">Al recibir una respuesta provisional (183) o una respuesta final (200OK), el punto de conexión de Teams iniciará las comprobaciones de conectividad y continuará con las nominaciones "normales" para completar las comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="51871-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="51871-166">Nota: Si la SBC envía una respuesta provisional (183), la SBC debe estar lista para recibir solicitudes de comprobación de conectividad y posiblemente completar las nominaciones antes de que el SBC envíe el 200OK.</span><span class="sxs-lookup"><span data-stu-id="51871-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="51871-167">Si se completan las comprobaciones o nominaciones antes de que se reciba la 200OK, los controles o nominaciones no se volverán a realizar una vez recibida la 200OK.</span><span class="sxs-lookup"><span data-stu-id="51871-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="51871-168">La SBC no debe cambiar los candidatos para hielo, la contraseña y el ufrag (fragmento de nombre de usuario) entre 183 y 200.</span><span class="sxs-lookup"><span data-stu-id="51871-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="51871-169">Para admitir los medios iniciales, la SBC puede iniciar la transmisión de los medios al candidato de ICE del mismo nivel, con la mayor prioridad en función de las comprobaciones de conectividad recibidas, incluso antes de que las noventa se completen mediante el punto de conexión de Teams.</span><span class="sxs-lookup"><span data-stu-id="51871-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="51871-170">La SBC debe esperar medios de los equipos de cualquier candidato hasta que se completen las nominaciones.</span><span class="sxs-lookup"><span data-stu-id="51871-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="51871-171">Una vez que se ha designado a un candidato, el SBC debe restablecer el contexto adecuado para enviar y recibir paquetes de medios.</span><span class="sxs-lookup"><span data-stu-id="51871-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="51871-172">Requisitos de soporte técnico de SRTP</span><span class="sxs-lookup"><span data-stu-id="51871-172">SRTP support requirements</span></span>

<span data-ttu-id="51871-173">La SBC debe admitir el cifrado de cifrado SRTP AES_CM_128_HMAC_SHA1_80 para la oferta y la respuesta en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="51871-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="51871-174">El siguiente es un ejemplo del atributo criptográfico en la oferta de SDP de SBC:</span><span class="sxs-lookup"><span data-stu-id="51871-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="51871-175">Los parámetros MKI y length no son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="51871-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="51871-176">Para obtener más información, consulte la [sección 6,1 de RFC 4568](https://tools.ietf.org/html/rfc4568#section-6.1).</span><span class="sxs-lookup"><span data-stu-id="51871-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="51871-177">Requisitos de asistencia de SDES</span><span class="sxs-lookup"><span data-stu-id="51871-177">SDES support requirements</span></span>

<span data-ttu-id="51871-178">El dispositivo debe poder ofrecer SDES en el formato que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="51871-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="51871-179">Los procesadores de multimedia de Microsoft siempre prefieren SDES.</span><span class="sxs-lookup"><span data-stu-id="51871-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="51871-180">Con la omisión de contenido no multimedia, incluso si un cliente solo admite DTLS, los procesadores multimedia se convertirán en SDES.</span><span class="sxs-lookup"><span data-stu-id="51871-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="51871-181">Con la omisión de elementos multimedia, si un cliente solo se DTLS (el próximo estado de Google Chrome), el enrutamiento directo insertará un módulo de administración en la ruta de acceso, lo que convierte la llamada de la omisión de medios en una omisión no multimedia.</span><span class="sxs-lookup"><span data-stu-id="51871-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="51871-182">Entre el componente de el procesador multimedia y la SBC de enrutamiento directo, siempre se usa SDES.</span><span class="sxs-lookup"><span data-stu-id="51871-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="51871-183">Por el momento, no hay ningún cliente de equipos que solo ofrezca DTLS; sin embargo, Google ha anunciado que, en algún momento, dejarán de admitir SDES.</span><span class="sxs-lookup"><span data-stu-id="51871-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="51871-184">Formato de la oferta de SBC en el modo de omisión</span><span class="sxs-lookup"><span data-stu-id="51871-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="51871-185">La oferta debe contener SDES y puede contener DTLS opcional en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="51871-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="51871-186">Formato de la respuesta que contiene SDES a SBC</span><span class="sxs-lookup"><span data-stu-id="51871-186">Format for answer containing SDES to SBC</span></span>

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="51871-187">Formato de la oferta de Teams a SBC</span><span class="sxs-lookup"><span data-stu-id="51871-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="51871-188">Formato de SDES solo para la oferta de SBC</span><span class="sxs-lookup"><span data-stu-id="51871-188">Format for SDES only offer to SBC</span></span>

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

