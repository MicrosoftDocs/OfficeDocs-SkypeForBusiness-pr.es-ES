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
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835030"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Enrutamiento directo: definiciones y estándares RFC

En este artículo se describe cómo El enrutamiento directo de Microsoft Phone System implementa los protocolos estándar RFC. Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el controlador de borde de sesión local (SBC) y el servicio proxy de Protocolo de inicio de sesión (SIP).

El cliente SBC se interface con los siguientes componentes del back-end de Microsoft Teams: 

- **Proxy SIP para** señalización. Este es el componente de enrutamiento directo orientado a Internet que controla las conexiones SIP (TLS) entre las TDC y el enrutamiento directo.

- **Los procesadores multimedia** de los medios. Este es el componente de enrutamiento directo orientado a Internet que controla el tráfico multimedia. Este componente usa protocolos SRTP y SRTCP.


Para obtener más información sobre el enrutamiento directo, vea [Enrutamiento directo de sistema telefónico.](direct-routing-landing-page.md)

Para obtener más información sobre cómo el enrutamiento directo implementa el protocolo SIP, consulte [Enrutamiento directo - protocolo SIP.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>Estándares RFC

El enrutamiento directo cumple con los estándares RFC.  El SBC conectado a enrutamiento directo también debe cumplir con las siguientes RFCs (o sus sucesores). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Estándares aplicables a los dispositivos que admiten el modo de omisión de medios no multimedia 

Los siguientes estándares se aplican a los dispositivos que solo admiten el modo de omisión de medios:

- [RFC 3261 SIP:](https://tools.ietf.org/html/rfc3261)protocolo de inicio de sesión
- [RFC 3325.](https://www.ietf.org/rfc/rfc3325) Extensión privada del Protocolo de inicio de sesión para una identidad autenticada dentro de redes de confianza : secciones sobre la gestión de encabezados P-Identityed-Identity. El enrutamiento directo envía P-A-Identity con encabezados de id. de privacidad. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Una extensión del Protocolo de inicio de sesión (SIP) para obtener información necesaria sobre el historial. Vea también: Descripción del protocolo SIP de enrutamiento para obtener más información.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Mecanismo de configuración del protocolo Referred-By sesión
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Encabezado "Reemplaza" el Protocolo de inicio de sesión (SIP) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso del protocolo de inicio de sesión (SIP) del modelo de oferta y respuesta.
  Vea la sección "Desviaciones de RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) y [RFC 4771.](https://tools.ietf.org/html/rfc4771) Proteja el tráfico RTP con SRTP. La SBC debe poder establecer claves mediante SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Aclaraciones de oferta y respuesta de Protocolo de descripción de sesión (SDP) para la multiplexación RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Estándares aplicables a los dispositivos que admiten el modo de omisión de medios

Además de los estándares enumerados como aplicables al modo de no omisión, se utilizan los siguientes estándares para el modo de omisión de medios:

- [RFC 5245 Interactive Connectivity Fi (ICE) para la omisión de medios.](https://tools.ietf.org/html/rfc5245)  La SBC debe admitir lo siguiente:
  - ICE Lite: los clientes de Teams son clientes completos de ICE
  - [Se reinicia ICE.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1) Ver más en caso de uso de reinicios de ICE y ejemplos en reiniciar ICE: llamada de omisión de medios transferida a un punto de conexión que no admite la omisión de medios   
- [RFC RFC 5589 Control](https://tools.ietf.org/html/rfc5589)de llamadas del Protocolo de inicio de sesión (SIP): transferencia. 
- [RFC 3960 Early Media and Ringing Tone Generation](https://tools.ietf.org/html/rfc3960)en el Protocolo de inicio de sesión (SIP), vea las secciones 3.1, Forking y 3.2, Ringing Tone Generation 
- [Rfc 5389 Utilidades de recorrido de sesión para NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal mediante retransmisión alrededor de NAT (TURN): Extensiones de retransmisión a utilidades de recorrido de sesión para NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Estándares aplicables que admiten transmitir información de ubicación a proveedores de E911

- [RFC 6442, Transmisión de ubicación para el protocolo de inicio de sesión](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desviaciones del RFC

En la tabla siguiente se enumeran las secciones de los RFC en las que la implementación de Microsoft del SIP o la pila de medios se desvía del estándar:

| RFC y secciones | Descripción | Desviación |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sección 5.3, retención y currículo de medios](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC permite usar "a=inactive", "a=sendonly", a=recvonly" para poner una llamada en espera. |El proxy SIP solo admite "a=inactivo" y no comprende si la SBC envía "a=sendonly" o "a=recvonly".
| [RFC 6337, sección 5.4 "Comportamiento al recibir SDP con c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requiere que un agente pueda recibir SDP con una dirección de conexión de 0.0.0.0, en cuyo caso significa que ni RTP ni RTCP deben enviarse al mismo nivel. | El proxy SIP no admite esta opción. |

## <a name="operational-modes"></a>Modos de funcionamiento

Hay dos modos de funcionamiento del enrutamiento directo:

- **Sin omisión de medios** en la que todo el tráfico RTP fluye entre el cliente de Teams, los procesadores multimedia y la SBC.  

- **Con la omisión de** medios en la que todos los medios RTP fluyen entre los puntos de conexión de Teams y la SBC. 

Tenga en cuenta que el tráfico SIP siempre fluye a través del proxy SIP.   
