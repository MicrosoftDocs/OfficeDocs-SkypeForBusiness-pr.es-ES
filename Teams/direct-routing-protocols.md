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
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="86a9c-103">Enrutamiento directo - Definiciones y estándares RFC</span><span class="sxs-lookup"><span data-stu-id="86a9c-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="86a9c-104">En este artículo se describe cómo Teléfono Microsoft enrutamiento directo del sistema implementa los protocolos estándar RFC.</span><span class="sxs-lookup"><span data-stu-id="86a9c-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="86a9c-105">Este artículo está destinado a administradores de voz que son responsables de configurar la conexión entre el controlador de borde de sesión local (SBC) y el servicio proxy del Protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="86a9c-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="86a9c-106">El cliente SBC interactúa con los siguientes componentes en el back-end Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="86a9c-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="86a9c-107">**El proxy SIP** para la señalización.</span><span class="sxs-lookup"><span data-stu-id="86a9c-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="86a9c-108">Este es el componente orientado a Internet del enrutamiento directo que maneja las conexiones SIP (TLS) entre los SBC y el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="86a9c-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="86a9c-109">**Los procesadores de medios** para medios.</span><span class="sxs-lookup"><span data-stu-id="86a9c-109">**The media processors** for media.</span></span> <span data-ttu-id="86a9c-110">Este es el componente orientado a Internet de enrutamiento directo que controla el tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="86a9c-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="86a9c-111">Este componente utiliza los protocolos SRTP y SRTCP.</span><span class="sxs-lookup"><span data-stu-id="86a9c-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="86a9c-112">Para obtener más información acerca del enrutamiento directo, consulte [Sistema telefónico enrutamiento directo](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="86a9c-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="86a9c-113">Para obtener más información acerca de cómo el enrutamiento directo implementa el protocolo SIP, consulte [Enrutamiento directo - Protocolo SIP](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="86a9c-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="86a9c-114">Estándares RFC</span><span class="sxs-lookup"><span data-stu-id="86a9c-114">RFC standards</span></span>

<span data-ttu-id="86a9c-115">Enrutamiento directo cumple con los estándares RFC.</span><span class="sxs-lookup"><span data-stu-id="86a9c-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="86a9c-116">El SBC conectado al enrutamiento directo también debe cumplir con los siguientes RFC (o sus sucesores).</span><span class="sxs-lookup"><span data-stu-id="86a9c-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="86a9c-117">Estándares aplicables a los dispositivos que admiten el modo de derivación no multimedia</span><span class="sxs-lookup"><span data-stu-id="86a9c-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="86a9c-118">Los siguientes estándares son aplicables a los dispositivos que solo admiten el modo de omisión no multimedia:</span><span class="sxs-lookup"><span data-stu-id="86a9c-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="86a9c-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de iniciación de sesión</span><span class="sxs-lookup"><span data-stu-id="86a9c-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="86a9c-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="86a9c-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="86a9c-121">Extensión privada al protocolo de inicio de sesión para la identidad afirmada dentro de redes de confianza: secciones sobre el control del encabezado P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="86a9c-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="86a9c-122">Enrutamiento directo envía P-Asserted-Identity con encabezados de ID de privacidad.</span><span class="sxs-lookup"><span data-stu-id="86a9c-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="86a9c-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Una extensión al Protocolo de inicio de sesión (SIP) para la información de historial requerida.</span><span class="sxs-lookup"><span data-stu-id="86a9c-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="86a9c-124">Vea también: Descripción del Protocolo SIP de ruteo para más información.</span><span class="sxs-lookup"><span data-stu-id="86a9c-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="86a9c-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) El mecanismo de Referred-By del Protocolo de Iniciación de Sesiones</span><span class="sxs-lookup"><span data-stu-id="86a9c-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="86a9c-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) El encabezado "Reemplaza" del Protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="86a9c-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="86a9c-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Uso del Protocolo de inicio de sesión (SIP) del modelo de oferta/respuesta.</span><span class="sxs-lookup"><span data-stu-id="86a9c-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="86a9c-128">Consulte la sección "Desviaciones de RFC".</span><span class="sxs-lookup"><span data-stu-id="86a9c-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="86a9c-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) y [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="86a9c-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="86a9c-130">Proteja el tráfico RTP usando el SRTP.</span><span class="sxs-lookup"><span data-stu-id="86a9c-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="86a9c-131">El SBC debe poder establecer claves mediante SDES.</span><span class="sxs-lookup"><span data-stu-id="86a9c-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="86a9c-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocolo de descripción de sesión (SDP) Ofrecer/Responder aclaraciones para rtp/RTCP multiplexing</span><span class="sxs-lookup"><span data-stu-id="86a9c-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="86a9c-133">Estándares aplicables a los dispositivos que admiten el modo de derivación de medios</span><span class="sxs-lookup"><span data-stu-id="86a9c-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="86a9c-134">Además de los estándares enumerados como aplicables al modo de no derivación, se utilizan los siguientes estándares para el modo de derivación de medios:</span><span class="sxs-lookup"><span data-stu-id="86a9c-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="86a9c-135">[RFC 5245 Establecimiento interactivo de conectividad (ICE) para la omisión de medios](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="86a9c-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="86a9c-136">El SBC debe admitir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="86a9c-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="86a9c-137">ICE Lite: los clientes Teams son clientes completos del ICE</span><span class="sxs-lookup"><span data-stu-id="86a9c-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="86a9c-138">[El ICE reinicia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="86a9c-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="86a9c-139">Vea más sobre los reinicios del ICE caso de uso y ejemplos en ice restart: Media bypass call transferida a un punto final que no admite la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="86a9c-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="86a9c-140">[RFC RFC 5589 Protocolo de inicio de sesión (SIP) Control de llamadas – Transferencia](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="86a9c-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="86a9c-141">[RFC 3960 Early Media and Ringing Tone Generation en el Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)ver secciones 3.1, Forking, y 3.2, Ringing Tone Generation</span><span class="sxs-lookup"><span data-stu-id="86a9c-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="86a9c-142">Utilidades de recorrido de sesión RFC 5389 para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="86a9c-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="86a9c-143">RFC 5766 Traversal Usando relés alrededor de NAT (TURN): Extensiones de relé a utilidades de recorrido de sesión para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="86a9c-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="86a9c-144">Normas aplicables a la ayuda para transmitir información de ubicación a proveedores de E911</span><span class="sxs-lookup"><span data-stu-id="86a9c-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="86a9c-145">RFC 6442, Transporte de ubicación para el Protocolo de iniciación de sesión</span><span class="sxs-lookup"><span data-stu-id="86a9c-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="86a9c-146">Desviaciones de la RFC</span><span class="sxs-lookup"><span data-stu-id="86a9c-146">Deviations from the RFC's</span></span>

<span data-ttu-id="86a9c-147">En la tabla siguiente se enumeran las secciones de las RFC en las que la implementación de Microsoft de la pila sip o media se desvía del estándar:</span><span class="sxs-lookup"><span data-stu-id="86a9c-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="86a9c-148">RFC y secciones</span><span class="sxs-lookup"><span data-stu-id="86a9c-148">RFC and sections</span></span> | <span data-ttu-id="86a9c-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="86a9c-149">Description</span></span> | <span data-ttu-id="86a9c-150">desviación</span><span class="sxs-lookup"><span data-stu-id="86a9c-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="86a9c-151">RFC 6337, sección 5.3 Retención y reanudación de medios</span><span class="sxs-lookup"><span data-stu-id="86a9c-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="86a9c-152">RFC permite utilizar "a=inactive", "a=sendonly", a=recvonly" para realizar una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="86a9c-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="86a9c-153">El proxy SIP solo admite "a=inactive" y no entiende si el SBC envía "a=sendonly" o "a=recvonly".</span><span class="sxs-lookup"><span data-stu-id="86a9c-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="86a9c-154">RFC 6337, sección 5.4 "Comportamiento al recibir SDP con c=0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="86a9c-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="86a9c-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requiere que un agente sea capaz de recibir el SDP con una dirección de conexión de 0.0.0.0, en cuyo caso significa que ni rtp ni RTCP deben ser enviados al par.</span><span class="sxs-lookup"><span data-stu-id="86a9c-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="86a9c-156">El proxy SIP no admite esta opción.</span><span class="sxs-lookup"><span data-stu-id="86a9c-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="86a9c-157">Modos operativos</span><span class="sxs-lookup"><span data-stu-id="86a9c-157">Operational modes</span></span>

<span data-ttu-id="86a9c-158">Hay dos modos operativos para el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="86a9c-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="86a9c-159">**Sin la omisión de medios** en la que todo el tráfico RTP fluye entre el cliente Teams, los procesadores de medios, y el SBC.</span><span class="sxs-lookup"><span data-stu-id="86a9c-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="86a9c-160">**Con el desvío de medios** en el cual todos los medios RTP fluyen entre los puntos finales Teams y el SBC.</span><span class="sxs-lookup"><span data-stu-id="86a9c-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="86a9c-161">Observe que el tráfico SIP fluye siempre vía el proxy DEL SORBO.</span><span class="sxs-lookup"><span data-stu-id="86a9c-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="86a9c-162">Dtmf</span><span class="sxs-lookup"><span data-stu-id="86a9c-162">DTMF</span></span>
<span data-ttu-id="86a9c-163">La pila de medios no admite DTMF en banda.</span><span class="sxs-lookup"><span data-stu-id="86a9c-163">In-band DTMF is not supported by media stack.</span></span>
