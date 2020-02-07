---
title: Enrutamiento directo del Sistema telefónico
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
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835030"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="2c0b9-103">Enrutamiento directo: definiciones y estándares de RFC</span><span class="sxs-lookup"><span data-stu-id="2c0b9-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="2c0b9-104">Este artículo describe cómo el enrutamiento directo de Microsoft Phone System implementa protocolos RFC estándar.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="2c0b9-105">Este artículo está dirigido a los administradores de voz responsables de configurar la conexión entre el controlador de borde de sesión (SBC) local y el servicio proxy del Protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="2c0b9-106">El SBC del cliente se une a los siguientes componentes en el back-end de Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="2c0b9-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="2c0b9-107">**El proxy SIP para la** señalización.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="2c0b9-108">Este es el componente orientado a Internet de enrutamiento directo que controla las conexiones SIP (TLS) entre el enrutamiento de SBCs y el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="2c0b9-109">**Los procesadores multimedia para los** medios.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-109">**The media processors** for media.</span></span> <span data-ttu-id="2c0b9-110">Este es el componente de Internet de enrutamiento directo que maneja el tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="2c0b9-111">Este componente usa los protocolos SRTP y SRTCP.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="2c0b9-112">Para obtener más información sobre el enrutamiento directo, consulte [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="2c0b9-113">Para obtener más información acerca de cómo el enrutamiento directo implementa el protocolo SIP, consulte [protocolo SIP de enrutamiento directo](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="2c0b9-114">Estándares de RFC</span><span class="sxs-lookup"><span data-stu-id="2c0b9-114">RFC standards</span></span>

<span data-ttu-id="2c0b9-115">El enrutamiento directo cumple con los estándares de RFC.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="2c0b9-116">La SBC conectada al enrutamiento directo también debe cumplir con los siguientes documentos RFC (o sus sucesoras).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="2c0b9-117">Estándares aplicables a dispositivos que admiten el modo de omisión no multimedia</span><span class="sxs-lookup"><span data-stu-id="2c0b9-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="2c0b9-118">Los siguientes estándares se aplican a los dispositivos que admiten solo el modo de omisión no multimedia:</span><span class="sxs-lookup"><span data-stu-id="2c0b9-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="2c0b9-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="2c0b9-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="2c0b9-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="2c0b9-121">Extensión privada para el protocolo de inicio de sesión para la identidad afirmada dentro de redes de confianza: secciones sobre el tratamiento del encabezado de identidad declarada en P.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="2c0b9-122">El enrutamiento directo envía la identidad confirmada por P con encabezados de identificación de privacidad.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="2c0b9-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Extensión del Protocolo de inicio de sesión (SIP) para información del historial requerida.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="2c0b9-124">Consulte también: Descripción del protocolo SIP de enrutamiento para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="2c0b9-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) El protocolo de inicio de sesión denominado mecanismo</span><span class="sxs-lookup"><span data-stu-id="2c0b9-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="2c0b9-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) El encabezado "reemplazar" del Protocolo de inicio de sesión (SIP)</span><span class="sxs-lookup"><span data-stu-id="2c0b9-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="2c0b9-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Uso del Protocolo de inicio de sesión (SIP) del modelo de oferta/respuesta.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="2c0b9-128">Consulte la sección "desviaciones de RFC".</span><span class="sxs-lookup"><span data-stu-id="2c0b9-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="2c0b9-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711) y [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="2c0b9-130">Proteger el tráfico RTP con SRTP.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="2c0b9-131">La SBC debe poder establecer teclas mediante SDES.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="2c0b9-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocolo de descripción de sesión (SDP) oferta/respuesta aclaraciones para multiplexación de RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="2c0b9-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="2c0b9-133">Estándares aplicables a dispositivos que admiten el modo de omisión de medios</span><span class="sxs-lookup"><span data-stu-id="2c0b9-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="2c0b9-134">Además de los estándares indicados en el modo de no omisión, se usan los siguientes estándares para el modo de omisión de medios:</span><span class="sxs-lookup"><span data-stu-id="2c0b9-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="2c0b9-135">El [establecimiento de conectividad interactiva de RFC 5245 para la omisión de medios](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="2c0b9-136">La SBC debe admitir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c0b9-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="2c0b9-137">ICE Lite: los clientes de Teams son clientes completos de ICE</span><span class="sxs-lookup"><span data-stu-id="2c0b9-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="2c0b9-138">Se [reiniciará el hielo](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="2c0b9-139">Ver más en el ICE reinicia caso de uso y ejemplos en reinicio de ICE: llamada de omisión de medios transferida a un extremo que no admite omisión de medios</span><span class="sxs-lookup"><span data-stu-id="2c0b9-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="2c0b9-140">[RFC rfc 5589 control de llamadas de protocolo de inicio de sesión (SIP) – transferencia](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="2c0b9-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="2c0b9-141">[Generación de tono de timbre y medios iniciales de RFC 3960 en el protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3960), consulte las secciones 3,1, fork y 3,2, generación de tono de timbre</span><span class="sxs-lookup"><span data-stu-id="2c0b9-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="2c0b9-142">Utilidades de recorrido de sesión de RFC 5389 para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="2c0b9-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="2c0b9-143">Recorridos de RFC 5766 con retransmisión por NAT (TURN): retransmisión de extensiones a utilidades de recorrido de sesión para NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="2c0b9-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="2c0b9-144">Normas aplicables para permitir la transmisión de información sobre la ubicación a proveedores de E911</span><span class="sxs-lookup"><span data-stu-id="2c0b9-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="2c0b9-145">RFC 6442, transporte de ubicación para el protocolo de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="2c0b9-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="2c0b9-146">Desviaciones de las RFC</span><span class="sxs-lookup"><span data-stu-id="2c0b9-146">Deviations from the RFC's</span></span>

<span data-ttu-id="2c0b9-147">En la siguiente tabla se enumeran las secciones de RFC en las que se desvía la implementación de Microsoft de la pila de medios o SIP desde el estándar:</span><span class="sxs-lookup"><span data-stu-id="2c0b9-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="2c0b9-148">RFC y secciones</span><span class="sxs-lookup"><span data-stu-id="2c0b9-148">RFC and sections</span></span> | <span data-ttu-id="2c0b9-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c0b9-149">Description</span></span> | <span data-ttu-id="2c0b9-150">Funcion</span><span class="sxs-lookup"><span data-stu-id="2c0b9-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="2c0b9-151">RFC 6337, sección 5,3, suspensión y reanudación de los medios</span><span class="sxs-lookup"><span data-stu-id="2c0b9-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="2c0b9-152">RFC permite usar "a = inactivo", "a = sendonly", a = recvonly "para poner una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="2c0b9-153">El proxy SIP solo admite "a = inactivo" y no entiende si el SBC envía "a = sendonly" o "a = recvonly".</span><span class="sxs-lookup"><span data-stu-id="2c0b9-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="2c0b9-154">El comportamiento de RFC 6337, sección 5,4 "para recibir SDP con c = 0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="2c0b9-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="2c0b9-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requiere que un agente pueda recibir SDP con una dirección de conexión de 0.0.0.0, en cuyo caso significa que no debe enviarse ni RTP ni RTCP al interlocutor.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="2c0b9-156">El proxy SIP no admite esta opción.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="2c0b9-157">Modos operativos</span><span class="sxs-lookup"><span data-stu-id="2c0b9-157">Operational modes</span></span>

<span data-ttu-id="2c0b9-158">Existen dos modos operativos para el enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="2c0b9-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="2c0b9-159">**Sin omisión de medios** en el que todo el tráfico de RTP fluye entre el cliente de Teams, los procesadores de medios y el SBC.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="2c0b9-160">**Con la omisión de elementos multimedia** en la que todos los medios RTP fluyen entre los puntos de conexión y SBC de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="2c0b9-161">Ten en cuenta que el tráfico SIP siempre fluye a través del proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="2c0b9-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
