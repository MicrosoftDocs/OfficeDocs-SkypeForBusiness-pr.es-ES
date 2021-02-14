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
# <a name="overview"></a><span data-ttu-id="04374-103">Información general</span><span class="sxs-lookup"><span data-stu-id="04374-103">Overview</span></span>

<span data-ttu-id="04374-104">En este artículo se describe cómo el enrutamiento directo admite la omisión de medios con un controlador de borde de sesión (SBC) habilitado para ICE Lite, tal y como se describe en [RFC 5245.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="04374-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="04374-105">Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el SBC local y el servicio de proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="04374-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="04374-106">Este artículo proporciona una descripción general de los escenarios y requisitos de ICE Lite para interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="04374-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="04374-107">En el artículo se describen los formatos de los mensajes y las transiciones necesarias entre las máquinas de estado para garantizar una llamada y un flujo multimedia confiables.</span><span class="sxs-lookup"><span data-stu-id="04374-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="04374-108">Terminología</span><span class="sxs-lookup"><span data-stu-id="04374-108">Terminology</span></span>

- <span data-ttu-id="04374-109">Primero Hola: las primeras palabras habladas por el autor de la llamada y el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04374-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="04374-110">Es importante que todos los esfuerzos se realizan para asegurarse de que los primeros paquetes de los puntos de conexión se entregan de forma fiable en la mayoría de los casos de uso.</span><span class="sxs-lookup"><span data-stu-id="04374-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="04374-111">Entrada de teclado: la oferta del autor de la llamada se puede entregar a varios puntos de conexión del destinatario del mensaje si el destinatario está disponible en varios dispositivos (por ejemplo, es posible que un usuario de Teams haya iniciado sesión en Teams para Windows y Teams para Android o iPhone).</span><span class="sxs-lookup"><span data-stu-id="04374-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="04374-112">Respuesta provisional (183): los puntos de conexión del destinatario para una configuración de llamada más rápida envían una respuesta con los candidatos y las claves necesarios para establecer el flujo de medios.</span><span class="sxs-lookup"><span data-stu-id="04374-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="04374-113">Esto se realiza con anticipación a que el usuario responda potencialmente a la llamada(200OK) desde esa instancia específica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="04374-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="04374-114">Con la función de ántrate, el autor de la llamada debería estar preparado para recibir varias respuestas provisionales.</span><span class="sxs-lookup"><span data-stu-id="04374-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="04374-115">Re-Invite: oferta con candidatos finales seleccionada por el punto de conexión de control de ICE.</span><span class="sxs-lookup"><span data-stu-id="04374-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="04374-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span><span class="sxs-lookup"><span data-stu-id="04374-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="04374-117">Extremo de Teams: puede ser un servidor (procesador de medios, retransmisión de transporte) o el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="04374-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="04374-118">Formato del mensaje</span><span class="sxs-lookup"><span data-stu-id="04374-118">Message format</span></span>

<span data-ttu-id="04374-119">La infraestructura de Teams sigue RFC 5245 para ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="04374-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="04374-120">Esto implica que todos los mensajes STUN serán compatibles con [RFC 5389.](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="04374-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="04374-121">Los S SBCs, según requiera RFC 5389, deben ignorar cualquier atributos STUN que no reconozcan y continuar procesando los mensajes con los atributos conocidos.</span><span class="sxs-lookup"><span data-stu-id="04374-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="04374-122">Si se reciben paquetes con formato noformado, los paquetes se deberán descartar sin afectar al establecimiento de sesión multimedia.</span><span class="sxs-lookup"><span data-stu-id="04374-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="04374-123">Requisitos de ICE Lite</span><span class="sxs-lookup"><span data-stu-id="04374-123">ICE Lite requirements</span></span>

<span data-ttu-id="04374-124">En esta sección se recogen brevemente los requisitos de ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="04374-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="04374-125">Reunión de candidatos</span><span class="sxs-lookup"><span data-stu-id="04374-125">Candidate gathering</span></span>

<span data-ttu-id="04374-126">La SBC debe ofrecer solo un candidato que sea públicamente accesible.</span><span class="sxs-lookup"><span data-stu-id="04374-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="04374-127">Actualmente, solo se admiten los candidatos IPV4.</span><span class="sxs-lookup"><span data-stu-id="04374-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="04374-128">Comprobaciones de conectividad</span><span class="sxs-lookup"><span data-stu-id="04374-128">Connectivity checks</span></span>

<span data-ttu-id="04374-129">La implementación de ICE Lite debe responder a las comprobaciones de conectividad recibidas.</span><span class="sxs-lookup"><span data-stu-id="04374-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="04374-130">El punto de conexión de ICE Lite no debe enviar ninguna solicitud de comprobación de conectividad.</span><span class="sxs-lookup"><span data-stu-id="04374-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="04374-131">(Si se envían comprobaciones de conectividad infracción, responderá la implementación completa, lo que puede provocar que se descubran candidatos derivados del mismo nivel de forma inesperada y que se puedan producir errores en la llamada).</span><span class="sxs-lookup"><span data-stu-id="04374-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="04374-132">Información desde el centro de datos</span><span class="sxs-lookup"><span data-stu-id="04374-132">Nominations</span></span>

<span data-ttu-id="04374-133">El punto de conexión de implementación completa de ICE siempre será el punto de conexión de control y seguirá las instrucciones "regulares" para seleccionar los candidatos finales que se usarán para el flujo de medios.</span><span class="sxs-lookup"><span data-stu-id="04374-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="04374-134">El punto de conexión de ICE Lite puede utilizar los resultados para concluir la ruta que se usará para los medios y para el establecimiento de llamadas completo.</span><span class="sxs-lookup"><span data-stu-id="04374-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="04374-135">Nota: En el caso de la entrada de objetos con puntos de conexión de punto de conexión que envían 183 respuestas provisionales, la SBC debe estar lista para responder a las comprobaciones de varios puntos de conexión y, si las cosas se realizan antes del 200A, las vistas de varios puntos de conexión también se realizan.</span><span class="sxs-lookup"><span data-stu-id="04374-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="04374-136">Según la convergencia del equipo de estado de ICE en la ruta final y los intervalos de respuesta del usuario, las limpiezas pueden producirse antes o después de 200A.</span><span class="sxs-lookup"><span data-stu-id="04374-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="04374-137">La SBC debe ser capaz de controlar ambos casos.</span><span class="sxs-lookup"><span data-stu-id="04374-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="04374-138">Converger para la forking</span><span class="sxs-lookup"><span data-stu-id="04374-138">Converging for forking</span></span>

<span data-ttu-id="04374-139">Si la oferta de la SBC se bifurca para varios puntos de conexión de Teams, los puntos de conexión de Teams pueden responder con una respuesta provisional e iniciar comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="04374-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="04374-140">La SBC debe estar preparada para recibir comprobaciones de conectividad y responder a las comprobaciones de conectividad de varios puntos de conexión del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="04374-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="04374-141">Por ejemplo, el usuario de Teams podría haber iniciado sesión en un equipo de escritorio y en un teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="04374-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="04374-142">Ambos dispositivos recibirán una notificación de la llamada entrante e intentarán realizar comprobaciones de conectividad con el SBC.</span><span class="sxs-lookup"><span data-stu-id="04374-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="04374-143">Finalmente, solo uno de los puntos de conexión responderá a la llamada (200OK).</span><span class="sxs-lookup"><span data-stu-id="04374-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="04374-144">Al recibir 200OK, la SBC puede configurar el contexto adecuado para el procesamiento de los paquetes multimedia.</span><span class="sxs-lookup"><span data-stu-id="04374-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="04374-145">Escenarios</span><span class="sxs-lookup"><span data-stu-id="04374-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="04374-146">Llamada entrante de SBC</span><span class="sxs-lookup"><span data-stu-id="04374-146">Inbound call from SBC</span></span>

<span data-ttu-id="04374-147">Para este escenario, hay varios posibles puntos de conexión de punto de conexión que el SBC debe controlar:</span><span class="sxs-lookup"><span data-stu-id="04374-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="04374-148">Los puntos de conexión del servidor normalmente responderán directamente con 200OK.</span><span class="sxs-lookup"><span data-stu-id="04374-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="04374-149">Se trata de puntos de conexión completos de ICE que suelen estar implicados en los escenarios del correo de voz, la cola de llamadas y el operador automático.</span><span class="sxs-lookup"><span data-stu-id="04374-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="04374-150">Los puntos de conexión del cliente pueden enviar varias respuestas provisionales con etiquetas de origen y destino diferentes (183) seguidas de 200OK desde el punto de conexión que responde a la llamada.</span><span class="sxs-lookup"><span data-stu-id="04374-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="04374-151">Estos son puntos de conexión completos de ICE que normalmente representan los clientes del usuario final.</span><span class="sxs-lookup"><span data-stu-id="04374-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="04374-152">Otros puntos de conexión SBC.</span><span class="sxs-lookup"><span data-stu-id="04374-152">Other SBC endpoints.</span></span> <span data-ttu-id="04374-153">Estos son puntos de conexión de ICE Lite que suelen estar implicados en el escenario de hacer llamadas simultáneas a puntos de conexión de cliente y otros números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="04374-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="04374-154">La SBC debe responder a todas las solicitudes válidas de comprobación de conectividad recibidas de los puntos de conexión completos de ICE.</span><span class="sxs-lookup"><span data-stu-id="04374-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="04374-155">Por RFC, los puntos de conexión completos de ICE se convertirán en extremos de control.</span><span class="sxs-lookup"><span data-stu-id="04374-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="04374-156">Los puntos de conexión de Teams (cliente/servidor) realizarán comprobaciones "normales" para completar las comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="04374-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="04374-157">La versión final de 200Ok puede ser de un punto de conexión que envió medios anticipados o de otro punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="04374-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="04374-158">Al recibir 200Ok, la SBC debe configurar el contexto adecuado para el flujo de medios.</span><span class="sxs-lookup"><span data-stu-id="04374-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="04374-159">Medios iniciales</span><span class="sxs-lookup"><span data-stu-id="04374-159">Early media</span></span>

<span data-ttu-id="04374-160">Si hay un flujo de medios anticipado, la SBC debe tener acceso al primer punto de conexión que inicia la transmisión multimedia; el flujo multimedia puede empezar antes de que los candidatos se nominan.</span><span class="sxs-lookup"><span data-stu-id="04374-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="04374-161">SBC debe ser compatible con el envío de DTMF durante esta fase para habilitar los escenarios de IVR/correo de voz.</span><span class="sxs-lookup"><span data-stu-id="04374-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="04374-162">La SBC debe usar la ruta de prioridad más alta en la que ha recibido comprobaciones si no se han completado los resultados.</span><span class="sxs-lookup"><span data-stu-id="04374-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="04374-163">Llamada saliente a SBC</span><span class="sxs-lookup"><span data-stu-id="04374-163">Outbound call to SBC</span></span>

<span data-ttu-id="04374-164">Los puntos de conexión de Teams son la persona que llama para este escenario y serán el punto final de control.</span><span class="sxs-lookup"><span data-stu-id="04374-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="04374-165">Al recibir una respuesta provisional (183) o una respuesta final(200OK), el punto de conexión de Teams iniciará las comprobaciones de conectividad y continuará con los resultados "normales" para completar las comprobaciones de conectividad.</span><span class="sxs-lookup"><span data-stu-id="04374-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="04374-166">Nota: Si la SBC envía una respuesta provisional (183), la SBC debe estar lista para recibir solicitudes de comprobación de conectividad y, posiblemente, completar las peticiones antes de que la SBC envíe la 200OK.</span><span class="sxs-lookup"><span data-stu-id="04374-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="04374-167">Si las comprobaciones o los resultados se completan antes de que se reciba la versión 200OK, las comprobaciones y/o los resultados no se volverán a realizar después de recibir 200OK.</span><span class="sxs-lookup"><span data-stu-id="04374-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="04374-168">La SBC no debe cambiar los candidatos, la contraseña y el ufrag (fragmento de nombre de usuario) de ICE entre 183 y 200.</span><span class="sxs-lookup"><span data-stu-id="04374-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="04374-169">Para admitir los medios anticipados, la SBC puede iniciar la transmisión de los medios al candidato de ICE del mismo nivel, con la máxima prioridad en función de las comprobaciones de conectividad recibidas, incluso antes de que el punto de conexión de Teams complete las pruebas.</span><span class="sxs-lookup"><span data-stu-id="04374-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="04374-170">La SBC debería esperar los medios de Teams en cualquier candidato hasta que se completen los resultados.</span><span class="sxs-lookup"><span data-stu-id="04374-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="04374-171">Una vez nominado un candidato, la SBC debe restablecerse al contexto adecuado para enviar y recibir paquetes multimedia.</span><span class="sxs-lookup"><span data-stu-id="04374-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="04374-172">Requisitos de soporte técnico del SRTP</span><span class="sxs-lookup"><span data-stu-id="04374-172">SRTP support requirements</span></span>

<span data-ttu-id="04374-173">La SBC debe admitir el cifrado de cifrado SRTP AES_CM_128_HMAC_SHA1_80 para ofrecer y responder en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="04374-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="04374-174">El siguiente es un ejemplo del atributo crypto de la oferta SDP de la SBC:</span><span class="sxs-lookup"><span data-stu-id="04374-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="04374-175">Los parámetros MKI y Length no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="04374-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="04374-176">Para obtener más información, [vea RFC 4568, sección 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)</span><span class="sxs-lookup"><span data-stu-id="04374-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="04374-177">Requisitos de soporte técnico de SDES</span><span class="sxs-lookup"><span data-stu-id="04374-177">SDES support requirements</span></span>

<span data-ttu-id="04374-178">El dispositivo debe poder ofrecer SDES en el formato que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="04374-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="04374-179">Los procesadores multimedia de Microsoft siempre prefieren SDES.</span><span class="sxs-lookup"><span data-stu-id="04374-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="04374-180">Con omisión no multimedia, incluso si un cliente solo admite DTLS, los procesadores de medios se convertirán en SDES.</span><span class="sxs-lookup"><span data-stu-id="04374-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="04374-181">Con la omisión de medios, si un cliente es DTLS solo (estado futuro de Google Chrome), el enrutamiento directo insertará un MP en la ruta de acceso, convirtiendo la llamada de omisión de medios a omisión no multimedia.</span><span class="sxs-lookup"><span data-stu-id="04374-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="04374-182">Entre el componente SBC y el procesador de medios de enrutamiento directo, siempre se utiliza SDES.</span><span class="sxs-lookup"><span data-stu-id="04374-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="04374-183">Actualmente, no hay ningún cliente de Teams que solo ofrezca DTLS; sin embargo, Google ha anunciado que en algún momento dejarán de admitir SDES.</span><span class="sxs-lookup"><span data-stu-id="04374-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="04374-184">Formato de la oferta de SBC en modo de omisión</span><span class="sxs-lookup"><span data-stu-id="04374-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="04374-185">La oferta debe contener SDES y puede contener un DTLS opcional en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="04374-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="04374-186">Formato de respuesta que contiene SDES a SBC</span><span class="sxs-lookup"><span data-stu-id="04374-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="04374-187">Formato de la oferta de Teams a SBC</span><span class="sxs-lookup"><span data-stu-id="04374-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="04374-188">El formato para SDES solo ofrece a SBC</span><span class="sxs-lookup"><span data-stu-id="04374-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

