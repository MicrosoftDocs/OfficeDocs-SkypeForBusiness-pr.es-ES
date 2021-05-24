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
# <a name="direct-routing---definitions-and-rfc-standards"></a>Enrutamiento directo: definiciones y estándares RFC

En este artículo se describe cómo Teléfono Microsoft System Direct Routing implementa protocolos estándar RFC. Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el controlador de borde de sesión local (SBC) y el servicio de proxy protocolo de inicio de sesión (SIP).

El SBC del cliente interfaces con los siguientes componentes en el back-end Microsoft Teams cliente: 

- **El proxy SIP** para señalización. Este es el componente orientado a Internet de Enrutamiento directo que controla las conexiones SIP (TLS) entre los SBC y el enrutamiento directo.

- **Los procesadores multimedia** para medios. Este es el componente orientado a Internet de Enrutamiento directo que controla el tráfico multimedia. Este componente usa protocolos SRTP y SRTCP.


Para obtener más información sobre enrutamiento directo, [vea Sistema telefónico enrutamiento directo.](direct-routing-landing-page.md)

Para obtener más información sobre cómo enrutamiento directo implementa el protocolo SIP, vea [Enrutamiento directo : protocolo SIP.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>Estándares RFC

El enrutamiento directo cumple con los estándares RFC.  El SBC conectado a Enrutamiento directo también debe cumplir con las siguientes RFC (o sus sucesores). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Estándares aplicables a dispositivos que admiten el modo de omisión no multimedia 

Los siguientes estándares se aplican a los dispositivos que solo admiten el modo de omisión no multimedia:

- [RFC 3261 SIP:](https://tools.ietf.org/html/rfc3261)Protocolo de inicio de sesión
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extensión privada al protocolo de inicio de sesión para la identidad afirmada en redes de confianza: secciones sobre cómo administrar el encabezado P-Asserted-Identity. Enrutamiento directo envía P-Asserted-Identity con encabezados de id. de privacidad. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Una extensión al Protocolo de inicio de sesión (SIP) para obtener la información de historial necesaria. Vea también: Descripción del protocolo SIP de enrutamiento para obtener más información.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) El protocolo de inicio de sesión Referred-By mecanismo
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Encabezado "Reemplaza" del Protocolo de inicio de sesión (SIP) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso del protocolo de inicio de sesión (SIP) del modelo de oferta y respuesta.
  Vea la sección "Desviaciones de RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) y [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteja el tráfico RTP con SRTP. El SBC debe poder establecer claves con SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Ofertas y respuestas del Protocolo de descripción de sesión (SDP) para multiplexación RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Estándares aplicables a dispositivos compatibles con el modo de omisión multimedia

Además de los estándares enumerados como aplicables al modo de no omisión, se usan los siguientes estándares para el modo de omisión de medios:

- [Rfc 5245 Interactive Connectivity Establishment (ICE) para la omisión de medios.](https://tools.ietf.org/html/rfc5245)  El SBC debe admitir lo siguiente:
  - ICE Lite: los Teams son clientes completos de ICE
  - [Ice Reinicia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Más información sobre los casos de uso y ejemplos de los reinicios del ICE: Llamada de omisión de medios transferida a un punto de conexión que no admite la omisión de medios   
- [Rfc RFC 5589 Session Initiation Protocol (SIP) Control de llamadas : Transferir](https://tools.ietf.org/html/rfc5589). 
- [Rfc 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)vea las secciones 3.1, Forking y 3.2, Ringing Tone Generation 
- [Utilidades de recorrido de sesión RFC 5389 para NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [Rfc 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Estándares aplicables para admitir el transporte de información de ubicación a proveedores de E911

- [RFC 6442, Transporte de ubicación para el protocolo de inicio de sesión](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desviaciones de la RFC

En la tabla siguiente se enumeran las secciones de las RFC en las que la implementación de Microsoft de la pila sip o multimedia se desvía del estándar:

| RFC y secciones | Descripción | Desviación |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sección 5.3 Retención y currículo de medios](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC permite usar "a=inactivo", "a=sendonly", a=recvonly" para poner una llamada en espera. |El proxy SIP solo admite "a=inactivo" y no comprende si el SBC envía "a=sendonly" o "a=recvonly".
| [RFC 6337, sección 5.4 "Comportamiento al recibir SDP con c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requiere que un agente pueda recibir SDP con una dirección de conexión de 0.0.0.0, en cuyo caso significa que no se deben enviar ni RTP ni RTCP al par. | El proxy SIP no admite esta opción. |

## <a name="operational-modes"></a>Modos operativos

Hay dos modos operativos para enrutamiento directo:

- **Sin omisión** de medios en la que todo el tráfico RTP fluye entre el cliente Teams, los procesadores multimedia y el SBC.  

- **Con la omisión** de medios en la que todos los medios RTP fluyen entre los puntos de conexión Teams y el SBC. 

Tenga en cuenta que el tráfico SIP siempre fluye a través del proxy SIP. 

## <a name="dtmf"></a>DTMF
DTMF en banda no es compatible con la pila de medios.
