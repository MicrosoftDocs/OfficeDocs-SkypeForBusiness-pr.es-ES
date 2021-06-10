---
title: Enrutamiento directo del sistema telefónico
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
f1.keywords:
- NOCSH
description: Protocolos de enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888579"
---
# <a name="overview"></a><span data-ttu-id="3fe78-103">Información general</span><span class="sxs-lookup"><span data-stu-id="3fe78-103">Overview</span></span>

<span data-ttu-id="3fe78-104">En este artículo se describe cómo el enrutamiento directo admite la omisión de medios con un controlador de borde de sesión (SBC) habilitado para ICE Lite como se describe en [RFC 5245.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="3fe78-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="3fe78-105">Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el SBC local y el servicio de proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="3fe78-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="3fe78-106">En este artículo se proporciona información general sobre los escenarios y los requisitos de interoperabilidad de ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="3fe78-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="3fe78-107">En el artículo se describen los formatos de mensaje y las transiciones de máquina de estado necesarias para garantizar un flujo de llamadas y medios confiables.</span><span class="sxs-lookup"><span data-stu-id="3fe78-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="3fe78-108">Terminología</span><span class="sxs-lookup"><span data-stu-id="3fe78-108">Terminology</span></span>

- <span data-ttu-id="3fe78-109">First Hello: las primeras palabras pronunciadas por el autor de la llamada y el destinatario.</span><span class="sxs-lookup"><span data-stu-id="3fe78-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="3fe78-110">Es importante que se realizan todos los esfuerzos para asegurarse de que los primeros paquetes de los puntos de conexión se entregan de forma confiable en la mayoría de los casos de uso.</span><span class="sxs-lookup"><span data-stu-id="3fe78-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="3fe78-111">Forking: la oferta del autor de la llamada podría entregarse a varios puntos de conexión de la llamada si el destinatario está disponible en varios dispositivos (por ejemplo, un usuario de Teams podría haber iniciado sesión en Teams para Windows y Teams para Android o iPhone).</span><span class="sxs-lookup"><span data-stu-id="3fe78-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="3fe78-112">Respuesta provisional (183): los puntos de conexión del destinatario para una configuración de llamada más rápida envían una respuesta con los candidatos y las claves necesarias para establecer el flujo multimedia.</span><span class="sxs-lookup"><span data-stu-id="3fe78-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="3fe78-113">Esto se hace en previsión de que el usuario pueda responder a la llamada(200OK) desde esa instancia específica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3fe78-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="3fe78-114">Con la tención, el autor de la llamada debe estar listo para recibir varias respuestas provisionales.</span><span class="sxs-lookup"><span data-stu-id="3fe78-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="3fe78-115">Re-Invite: oferta con candidatos finales seleccionados por el punto de conexión de control del ICE.</span><span class="sxs-lookup"><span data-stu-id="3fe78-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="3fe78-116">Esto tendrá el atributo a=remote-candidate para resolver cualquier condición de carrera al manipular varias bifurcaciones.</span><span class="sxs-lookup"><span data-stu-id="3fe78-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="3fe78-117">Teams Punto de conexión: podría ser un servidor (procesador multimedia, retransmisión de transporte) o el Teams usuario.</span><span class="sxs-lookup"><span data-stu-id="3fe78-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="3fe78-118">Formato de mensaje</span><span class="sxs-lookup"><span data-stu-id="3fe78-118">Message format</span></span>

<span data-ttu-id="3fe78-119">La Teams de datos sigue RFC 5245 para ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="3fe78-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="3fe78-120">Esto implica que todos los mensajes de STUN serán compatibles con [RFC 5389.](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="3fe78-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="3fe78-121">Los SBC requeridos por RFC 5389 deben ignorar los atributos de STUN que no reconozcan y continuar procesando los mensajes con los atributos conocidos.</span><span class="sxs-lookup"><span data-stu-id="3fe78-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="3fe78-122">Si se reciben paquetes malformados, los paquetes deben descartarse sin afectar al establecimiento de la sesión multimedia.</span><span class="sxs-lookup"><span data-stu-id="3fe78-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="3fe78-123">Requisitos de ICE Lite</span><span class="sxs-lookup"><span data-stu-id="3fe78-123">ICE Lite requirements</span></span>

<span data-ttu-id="3fe78-124">En esta sección se capturan brevemente los requisitos de ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="3fe78-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="3fe78-125">Reunión de candidatos</span><span class="sxs-lookup"><span data-stu-id="3fe78-125">Candidate gathering</span></span>

<span data-ttu-id="3fe78-126">El SBC debe ofrecer solo un candidato accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="3fe78-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="3fe78-127">Actualmente, solo se admiten candidatos IPV4.</span><span class="sxs-lookup"><span data-stu-id="3fe78-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="3fe78-128">Comprobaciones de conectividad</span><span class="sxs-lookup"><span data-stu-id="3fe78-128">Connectivity checks</span></span>

<span data-ttu-id="3fe78-129">La implementación de ICE Lite debe responder a las comprobaciones de conectividad recibidas.</span><span class="sxs-lookup"><span data-stu-id="3fe78-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="3fe78-130">El punto de conexión ice lite no debe enviar ninguna solicitud de comprobación de conectividad.</span><span class="sxs-lookup"><span data-stu-id="3fe78-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="3fe78-131">(Si se envían comprobaciones de conectividad en infracción, la implementación completa responderá, lo que puede provocar que se descubran candidatos derivados por pares inesperados y que puedan producir errores de llamada).</span><span class="sxs-lookup"><span data-stu-id="3fe78-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="3fe78-132">Nominaciones</span><span class="sxs-lookup"><span data-stu-id="3fe78-132">Nominations</span></span>

<span data-ttu-id="3fe78-133">El punto de conexión de implementación completa del ICE siempre será el punto de conexión de Control y seguirá las nominaciones "regulares" para seleccionar los candidatos finales que se usarán para el flujo de medios.</span><span class="sxs-lookup"><span data-stu-id="3fe78-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="3fe78-134">El punto de conexión de ICE Lite puede usar las nominaciones para concluir la ruta que se usará para los medios y completar el establecimiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3fe78-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="3fe78-135">Nota: En el caso de que los puntos de conexión del mismo nivel envíen 183 respuestas provisionales, el SBC debe estar listo para responder a las comprobaciones de varios puntos de conexión y también a las nominaciones de varios puntos de conexión si las nominaciones se realizan antes del 200OK.</span><span class="sxs-lookup"><span data-stu-id="3fe78-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="3fe78-136">Dependiendo de la convergencia de la máquina de estado ice en la ruta final y los intervalos del usuario que responde, las nominaciones pueden ocurrir antes o después del 200OK.</span><span class="sxs-lookup"><span data-stu-id="3fe78-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="3fe78-137">El SBC debe poder controlar ambos casos.</span><span class="sxs-lookup"><span data-stu-id="3fe78-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="3fe78-138">Converger para la forking</span><span class="sxs-lookup"><span data-stu-id="3fe78-138">Converging for forking</span></span>

<span data-ttu-id="3fe78-139">Si la oferta de SBC se bifurca a varios puntos de conexión Teams, los puntos de conexión Teams pueden responder con una respuesta provisional e iniciar comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="3fe78-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="3fe78-140">El SBC debe estar preparado para recibir comprobaciones de conectividad y responder a las comprobaciones de conectividad de varios puntos de conexión del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3fe78-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="3fe78-141">Por ejemplo, el Teams usuario podría haber iniciado sesión tanto en un escritorio como en un teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="3fe78-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="3fe78-142">Ambos dispositivos recibirán una notificación de la llamada entrante e intentarán realizar comprobaciones de conectividad con el SBC.</span><span class="sxs-lookup"><span data-stu-id="3fe78-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="3fe78-143">Finalmente, solo uno de los puntos de conexión responderá a la llamada (200OK).</span><span class="sxs-lookup"><span data-stu-id="3fe78-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="3fe78-144">Al recibir el 200OK, el SBC puede configurar el contexto adecuado para procesar los paquetes multimedia.</span><span class="sxs-lookup"><span data-stu-id="3fe78-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="3fe78-145">Escenarios</span><span class="sxs-lookup"><span data-stu-id="3fe78-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="3fe78-146">Llamada entrante desde SBC</span><span class="sxs-lookup"><span data-stu-id="3fe78-146">Inbound call from SBC</span></span>

<span data-ttu-id="3fe78-147">Para este escenario, hay varios puntos de conexión de punto de conexión posibles que el SBC debe controlar:</span><span class="sxs-lookup"><span data-stu-id="3fe78-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="3fe78-148">Los puntos de conexión del servidor normalmente responderán directamente con 200OK.</span><span class="sxs-lookup"><span data-stu-id="3fe78-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="3fe78-149">Estos son puntos de conexión completos de ICE que suelen estar implicados en el correo de voz, la cola de llamadas y los escenarios de operador automático.</span><span class="sxs-lookup"><span data-stu-id="3fe78-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="3fe78-150">Los puntos de conexión de cliente pueden enviar varias respuestas provisionales con distintas etiquetas De/A (183) seguidas de un 200OK desde el punto de conexión que responde a la llamada.</span><span class="sxs-lookup"><span data-stu-id="3fe78-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="3fe78-151">Estos son puntos de conexión completos de ICE que suelen representar clientes de usuario final.</span><span class="sxs-lookup"><span data-stu-id="3fe78-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="3fe78-152">Otros puntos de conexión de SBC.</span><span class="sxs-lookup"><span data-stu-id="3fe78-152">Other SBC endpoints.</span></span> <span data-ttu-id="3fe78-153">Estos son puntos de conexión de ICE Lite que suelen estar implicados en el escenario de llamar simultáneamente a puntos de conexión de cliente y a otros números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="3fe78-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="3fe78-154">El SBC debe responder a todas las solicitudes de comprobación de conectividad válidas recibidas de los puntos de conexión completos de ICE.</span><span class="sxs-lookup"><span data-stu-id="3fe78-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="3fe78-155">Por RFC, los puntos de conexión completos de ICE se convertirán en puntos de conexión de Control.</span><span class="sxs-lookup"><span data-stu-id="3fe78-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="3fe78-156">Los Teams (cliente/servidor) realizarán nominaciones "regulares" para completar las comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="3fe78-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="3fe78-157">El 200Ok final puede ser de un punto de conexión que envió medios anticipados o de otro punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3fe78-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="3fe78-158">Al recibir el 200Ok, el SBC debe configurar el contexto adecuado para el flujo multimedia.</span><span class="sxs-lookup"><span data-stu-id="3fe78-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="3fe78-159">Medios anticipados</span><span class="sxs-lookup"><span data-stu-id="3fe78-159">Early media</span></span>

<span data-ttu-id="3fe78-160">Si hay un flujo de medios anticipado, el SBC debe estar en el primer punto de conexión que inicia la transmisión de contenido multimedia; el flujo de medios puede comenzar antes de que se nomina a los candidatos.</span><span class="sxs-lookup"><span data-stu-id="3fe78-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="3fe78-161">El SBC debe ser compatible con el envío de DTMF durante esta fase para habilitar escenarios de IVR/correo de voz.</span><span class="sxs-lookup"><span data-stu-id="3fe78-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="3fe78-162">El SBC debe usar la ruta de prioridad más alta en la que ha recibido comprobaciones si las nominaciones no se han completado.</span><span class="sxs-lookup"><span data-stu-id="3fe78-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="3fe78-163">Llamada saliente a SBC</span><span class="sxs-lookup"><span data-stu-id="3fe78-163">Outbound call to SBC</span></span>

<span data-ttu-id="3fe78-164">Los Teams de conexión son el autor de la llamada para este escenario y será el punto de conexión de control.</span><span class="sxs-lookup"><span data-stu-id="3fe78-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="3fe78-165">Al recibir una respuesta provisional (183) o una respuesta final(200OK), el punto de conexión de Teams iniciará las comprobaciones de conectividad y procederá a las nominaciones "Normales" para completar las comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="3fe78-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="3fe78-166">Nota: Si el SBC envía una respuesta provisional (183), el SBC debe estar listo para recibir solicitudes de comprobación de conectividad y, posiblemente, completar las nominaciones antes de que el SBC envíe el 200OK.</span><span class="sxs-lookup"><span data-stu-id="3fe78-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="3fe78-167">Si las comprobaciones y/o las nominaciones se completan antes de que se reciba el 200OK, los controles y/o las nominaciones no se volverán a realizar después de recibir 200OK.</span><span class="sxs-lookup"><span data-stu-id="3fe78-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="3fe78-168">El SBC no debe cambiar los candidatos del ICE, la contraseña y el ufrag (fragmento de nombre de usuario) entre 183 y 200.</span><span class="sxs-lookup"><span data-stu-id="3fe78-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="3fe78-169">Para admitir los primeros medios, es posible que el SBC empiece a transmitir los medios al candidato de ICE del mismo nivel, con la prioridad más alta en función de las comprobaciones de conectividad recibidas, incluso antes de que las nominaciones se completen Teams punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3fe78-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="3fe78-170">El SBC debe esperar que los medios Teams en cualquier candidato hasta que se completen las nominaciones.</span><span class="sxs-lookup"><span data-stu-id="3fe78-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="3fe78-171">Una vez que se nomina a un candidato, el SBC debe restablecerse al contexto adecuado para enviar y recibir paquetes multimedia.</span><span class="sxs-lookup"><span data-stu-id="3fe78-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="3fe78-172">Requisitos de soporte técnico srtp</span><span class="sxs-lookup"><span data-stu-id="3fe78-172">SRTP support requirements</span></span>

<span data-ttu-id="3fe78-173">El SBC debe admitir el cifrado SRTP AES_CM_128_HMAC_SHA1_80 para ofrecer y responder en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="3fe78-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="3fe78-174">A continuación se muestra un ejemplo del atributo crypto en la oferta de SDP del SBC:</span><span class="sxs-lookup"><span data-stu-id="3fe78-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="3fe78-175">Los parámetros MKI y Longitud no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="3fe78-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="3fe78-176">Para obtener más información, vea [RFC 4568, sección 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)</span><span class="sxs-lookup"><span data-stu-id="3fe78-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="3fe78-177">Requisitos de soporte técnico de SDES</span><span class="sxs-lookup"><span data-stu-id="3fe78-177">SDES support requirements</span></span>

<span data-ttu-id="3fe78-178">El dispositivo debe poder ofrecer SDES en el formato que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="3fe78-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="3fe78-179">Los procesadores multimedia de Microsoft siempre prefieren SDES.</span><span class="sxs-lookup"><span data-stu-id="3fe78-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="3fe78-180">Con la omisión no multimedia, incluso si un cliente solo admite DTLS, los procesadores multimedia se convertirán en SDES.</span><span class="sxs-lookup"><span data-stu-id="3fe78-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="3fe78-181">Con la omisión de medios, si un cliente solo es DTLS (futuro estado de Google Chrome), enrutamiento directo insertará un MP en la ruta de acceso, convirtiendo la llamada de omisión multimedia a omisión no multimedia.</span><span class="sxs-lookup"><span data-stu-id="3fe78-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="3fe78-182">Entre el SBC y el componente de procesador multimedia de Enrutamiento directo, sdes siempre se usa.</span><span class="sxs-lookup"><span data-stu-id="3fe78-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="3fe78-183">Actualmente, no hay ningún Teams que solo ofrezca DTLS; sin embargo, Google ha anunciado que en algún momento dejarán de admitir SDES.</span><span class="sxs-lookup"><span data-stu-id="3fe78-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="3fe78-184">Formato de oferta de SBC en modo de omisión</span><span class="sxs-lookup"><span data-stu-id="3fe78-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="3fe78-185">Oferta debe contener SDES y puede contener DTLS opcional en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="3fe78-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="3fe78-186">Formato de respuesta que contiene SDES a SBC</span><span class="sxs-lookup"><span data-stu-id="3fe78-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="3fe78-187">Formato de oferta de Teams a SBC</span><span class="sxs-lookup"><span data-stu-id="3fe78-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="3fe78-188">Formato para SDES solo ofrece para SBC</span><span class="sxs-lookup"><span data-stu-id="3fe78-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

