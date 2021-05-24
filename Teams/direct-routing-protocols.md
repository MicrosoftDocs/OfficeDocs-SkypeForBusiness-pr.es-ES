---
title: Enrutamiento directo del sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
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
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569208"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="02981-103">Enrutamiento directo: definiciones y estándares RFC</span><span class="sxs-lookup"><span data-stu-id="02981-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="02981-104">En este artículo se describe cómo Teléfono Microsoft System Direct Routing implementa protocolos estándar RFC.</span><span class="sxs-lookup"><span data-stu-id="02981-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="02981-105">Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el controlador de borde de sesión local (SBC) y el servicio de proxy protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="02981-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="02981-106">El SBC del cliente interfaces con los siguientes componentes en el back-end Microsoft Teams cliente:</span><span class="sxs-lookup"><span data-stu-id="02981-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="02981-107">**El proxy SIP** para señalización.</span><span class="sxs-lookup"><span data-stu-id="02981-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="02981-108">Este es el componente orientado a Internet de Enrutamiento directo que controla las conexiones SIP (TLS) entre los SBC y el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="02981-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="02981-109">**Los procesadores multimedia** para medios.</span><span class="sxs-lookup"><span data-stu-id="02981-109">**The media processors** for media.</span></span> <span data-ttu-id="02981-110">Este es el componente orientado a Internet de Enrutamiento directo que controla el tráfico multimedia.</span><span class="sxs-lookup"><span data-stu-id="02981-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="02981-111">Este componente usa protocolos SRTP y SRTCP.</span><span class="sxs-lookup"><span data-stu-id="02981-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="02981-112">Para obtener más información sobre enrutamiento directo, [vea Sistema telefónico enrutamiento directo.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="02981-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="02981-113">Para obtener más información sobre cómo enrutamiento directo implementa el protocolo SIP, vea [Enrutamiento directo : protocolo SIP.](direct-routing-protocols-sip.md)</span><span class="sxs-lookup"><span data-stu-id="02981-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="02981-114">Estándares RFC</span><span class="sxs-lookup"><span data-stu-id="02981-114">RFC standards</span></span>

<span data-ttu-id="02981-115">El enrutamiento directo cumple con los estándares RFC.</span><span class="sxs-lookup"><span data-stu-id="02981-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="02981-116">El SBC conectado a Enrutamiento directo también debe cumplir con las siguientes RFC (o sus sucesores).</span><span class="sxs-lookup"><span data-stu-id="02981-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="02981-117">Estándares aplicables a dispositivos que admiten el modo de omisión no multimedia</span><span class="sxs-lookup"><span data-stu-id="02981-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="02981-118">Los siguientes estándares se aplican a los dispositivos que solo admiten el modo de omisión no multimedia:</span><span class="sxs-lookup"><span data-stu-id="02981-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="02981-119">[RFC 3261 SIP:](https://tools.ietf.org/html/rfc3261)Protocolo de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="02981-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="02981-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="02981-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="02981-121">Extensión privada al protocolo de inicio de sesión para la identidad afirmada en redes de confianza: secciones sobre cómo administrar el encabezado P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="02981-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="02981-122">Enrutamiento directo envía P-Asserted-Identity con encabezados de id. de privacidad.</span><span class="sxs-lookup"><span data-stu-id="02981-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="02981-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Una extensión al Protocolo de inicio de sesión (SIP) para obtener la información de historial necesaria.</span><span class="sxs-lookup"><span data-stu-id="02981-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="02981-124">Vea también: Descripción del protocolo SIP de enrutamiento para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="02981-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="02981-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) El protocolo de inicio de sesión Referred-By mecanismo</span><span class="sxs-lookup"><span data-stu-id="02981-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="02981-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Encabezado "Reemplaza" del Protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="02981-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="02981-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Uso del protocolo de inicio de sesión (SIP) del modelo de oferta y respuesta.</span><span class="sxs-lookup"><span data-stu-id="02981-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="02981-128">Vea la sección "Desviaciones de RFC".</span><span class="sxs-lookup"><span data-stu-id="02981-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="02981-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) y [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="02981-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="02981-130">Proteja el tráfico RTP con SRTP.</span><span class="sxs-lookup"><span data-stu-id="02981-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="02981-131">El SBC debe poder establecer claves con SDES.</span><span class="sxs-lookup"><span data-stu-id="02981-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="02981-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Ofertas y respuestas del Protocolo de descripción de sesión (SDP) para multiplexación RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="02981-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="02981-133">Estándares aplicables a dispositivos compatibles con el modo de omisión multimedia</span><span class="sxs-lookup"><span data-stu-id="02981-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="02981-134">Además de los estándares enumerados como aplicables al modo de no omisión, se usan los siguientes estándares para el modo de omisión de medios:</span><span class="sxs-lookup"><span data-stu-id="02981-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="02981-135">[Rfc 5245 Interactive Connectivity Establishment (ICE) para la omisión de medios.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="02981-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="02981-136">El SBC debe admitir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="02981-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="02981-137">ICE Lite: los Teams son clientes completos de ICE</span><span class="sxs-lookup"><span data-stu-id="02981-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="02981-138">[Ice Reinicia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="02981-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="02981-139">Más información sobre los casos de uso y ejemplos de los reinicios del ICE: Llamada de omisión de medios transferida a un punto de conexión que no admite la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="02981-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="02981-140">[Rfc RFC 5589 Session Initiation Protocol (SIP) Control de llamadas : Transferir](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="02981-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="02981-141">[Rfc 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)vea las secciones 3.1, Forking y 3.2, Ringing Tone Generation</span><span class="sxs-lookup"><span data-stu-id="02981-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="02981-142">Utilidades de recorrido de sesión RFC 5389 para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="02981-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="02981-143">Rfc 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="02981-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="02981-144">Estándares aplicables para admitir el transporte de información de ubicación a proveedores de E911</span><span class="sxs-lookup"><span data-stu-id="02981-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="02981-145">RFC 6442, Transporte de ubicación para el protocolo de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="02981-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="02981-146">Desviaciones de la RFC</span><span class="sxs-lookup"><span data-stu-id="02981-146">Deviations from the RFC's</span></span>

<span data-ttu-id="02981-147">En la tabla siguiente se enumeran las secciones de las RFC en las que la implementación de Microsoft de la pila sip o multimedia se desvía del estándar:</span><span class="sxs-lookup"><span data-stu-id="02981-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="02981-148">RFC y secciones</span><span class="sxs-lookup"><span data-stu-id="02981-148">RFC and sections</span></span> | <span data-ttu-id="02981-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="02981-149">Description</span></span> | <span data-ttu-id="02981-150">Desviación</span><span class="sxs-lookup"><span data-stu-id="02981-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="02981-151">RFC 6337, sección 5.3 Retención y currículo de medios</span><span class="sxs-lookup"><span data-stu-id="02981-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="02981-152">RFC permite usar "a=inactivo", "a=sendonly", a=recvonly" para poner una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="02981-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="02981-153">El proxy SIP solo admite "a=inactivo" y no comprende si el SBC envía "a=sendonly" o "a=recvonly".</span><span class="sxs-lookup"><span data-stu-id="02981-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="02981-154">RFC 6337, sección 5.4 "Comportamiento al recibir SDP con c=0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="02981-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="02981-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requiere que un agente pueda recibir SDP con una dirección de conexión de 0.0.0.0, en cuyo caso significa que no se deben enviar ni RTP ni RTCP al par.</span><span class="sxs-lookup"><span data-stu-id="02981-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="02981-156">El proxy SIP no admite esta opción.</span><span class="sxs-lookup"><span data-stu-id="02981-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="02981-157">Modos operativos</span><span class="sxs-lookup"><span data-stu-id="02981-157">Operational modes</span></span>

<span data-ttu-id="02981-158">Hay dos modos operativos para enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="02981-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="02981-159">**Sin omisión** de medios en la que todo el tráfico RTP fluye entre el cliente Teams, los procesadores multimedia y el SBC.</span><span class="sxs-lookup"><span data-stu-id="02981-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="02981-160">**Con la omisión** de medios en la que todos los medios RTP fluyen entre los puntos de conexión Teams y el SBC.</span><span class="sxs-lookup"><span data-stu-id="02981-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="02981-161">Tenga en cuenta que el tráfico SIP siempre fluye a través del proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="02981-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="02981-162">DTMF</span><span class="sxs-lookup"><span data-stu-id="02981-162">DTMF</span></span>
<span data-ttu-id="02981-163">DTMF en banda no es compatible con la pila de medios.</span><span class="sxs-lookup"><span data-stu-id="02981-163">In-band DTMF is not supported by media stack.</span></span>
