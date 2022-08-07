---
title: 'Enrutamiento directo del sistema telefónico de Teams: definiciones y estándares RFC'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Cómo Microsoft Phone System Direct Routing implementa protocolos estándar RFC.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01dbd61748d14ef21a600b2e4f44a306517e46d9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271245"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Enrutamiento directo: definiciones y estándares RFC

En este artículo se describe cómo Enrutamiento directo de Microsoft Phone System implementa protocolos estándar RFC. Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el controlador de borde de sesión local (SBC) y el servicio proxy sip (Protocolo de inicio de sesión).

El cliente SBC se conecta con los siguientes componentes en el back-end de Microsoft Teams: 

- **El proxy SIP** para señalización. Este es el componente orientado a Internet del enrutamiento directo que controla las conexiones SIP (TLS) entre los SBCs y el enrutamiento directo.

- **Procesadores multimedia** para medios. Este es el componente orientado a Internet del enrutamiento directo que controla el tráfico multimedia. Este componente utiliza protocolos SRTP y SRTCP.


Para obtener más información sobre el enrutamiento directo, consulta [Enrutamiento directo del sistema telefónico](direct-routing-landing-page.md).

Para obtener más información sobre cómo Direct Routing implementa el protocolo SIP, vea [Direct Routing - PROTOCOLO SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Estándares RFC

Direct Routing cumple con los estándares RFC.  El SBC conectado al enrutamiento directo también debe cumplir con las siguientes RFCs (o sus sucesoras). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Estándares aplicables a dispositivos que admiten el modo de omisión no multimedia 

Los siguientes estándares son aplicables a los dispositivos que admiten solo el modo de omisión no multimedia:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de inicio de sesión
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extensión privada al Protocolo de inicio de sesión para la identidad aserda dentro de redes de confianza: secciones sobre el tratamiento del encabezado P-Asserted-Identity. Direct Routing envía P-Asserted-Identity con encabezados de Id. de privacidad. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Una extensión al Protocolo de inicio de sesión (SIP) para la información del historial necesaria. Vea también: Descripción del Protocolo SIP de enrutamiento para obtener más información.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Mecanismo de Referred-By del Protocolo de inicio de sesión
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) El encabezado "Reemplaza" del Protocolo de inicio de sesión (SIP) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso del modelo de oferta/respuesta del Protocolo de inicio de sesión (SIP).
  Consulte la sección "Desviaciones de RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) y [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteja el tráfico RTP con SRTP. El SBC debe ser capaz de establecer claves mediante SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Descripción de sesión Protocol (SDP) Oferta/Aclaraciones de respuesta para multiplexación RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Estándares aplicables a dispositivos que admiten el modo de omisión multimedia

Además de los estándares enumerados como aplicables al modo de no derivación, se utilizan los siguientes estándares para el modo de omisión de medios:

- [RFC 5245 Interactive Connectivity Establishment (ICE) para omisión de medios](https://tools.ietf.org/html/rfc5245).  El SBC debe admitir lo siguiente:
  - ICE Lite: los clientes de Teams son clientes de ICE completos
  - [ICE se reinicia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Obtenga más información sobre el caso de uso de los reinicios de ICE y ejemplos en Reinicio de ICE: Llamada de omisión de medios transferida a un punto de conexión que no admite omisión multimedia   
- [Rfc RFC 5589 Control de llamadas del Protocolo de inicio de sesión (SIP): transferencia](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation 
- [Utilidades de recorrido de sesión RFC 5389 para NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal mediante relés alrededor de NAT (TURN): Extensiones de relé a utilidades de recorrido de sesión para NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Estándares aplicables para admitir la transmisión de información de ubicación a proveedores E911

- [RFC 6442, transmisión de ubicación para el protocolo de inicio de sesión](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desviaciones de la RFC

En la tabla siguiente se enumeran las secciones de rfc(s) en las que la implementación de Microsoft de la pila de medios o SIP se desvía del estándar:

| RFC y secciones | Descripción | Desviación |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sección 5.3 Suspensión y currículum vítae de medios](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC permite usar "a=inactive", "a=sendonly", a=recvonly" para poner una llamada en espera. |El proxy SIP solo admite "a=inactivo" y no comprende si el SBC envía "a=sendonly" o "a=recvonly".
| [RFC 6337, sección 5.4 "Comportamiento al recibir SDP con c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requiere que un agente sea capaz de recibir SDP con una dirección de conexión de 0.0.0.0, en cuyo caso significa que ni RTP ni RTCP deben enviarse al par. | El proxy SIP no admite esta opción. |

## <a name="operational-modes"></a>Modos operativos

Existen dos modos operativos para el enrutamiento directo:

- **Sin la omisión de medios** en la que todo el tráfico RTP fluye entre el cliente de Teams, los procesadores multimedia y el SBC.  

- **Con la omisión de medios** en la que todos los medios RTP fluyen entre los puntos de conexión de Teams y el SBC. 

Observe que el tráfico SIP fluye siempre vía el proxy SIP. 

## <a name="dtmf"></a>DTMF
La pila de medios no admite DTMF en banda.
