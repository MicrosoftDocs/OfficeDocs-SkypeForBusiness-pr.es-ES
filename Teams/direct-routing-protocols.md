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
# <a name="direct-routing---definitions-and-rfc-standards"></a>Enrutamiento directo: definiciones y estándares de RFC

Este artículo describe cómo el enrutamiento directo de Microsoft Phone System implementa protocolos RFC estándar. Este artículo está dirigido a los administradores de voz responsables de configurar la conexión entre el controlador de borde de sesión (SBC) local y el servicio proxy del Protocolo de inicio de sesión (SIP).

El SBC del cliente se une a los siguientes componentes en el back-end de Microsoft Teams: 

- **El proxy SIP para la** señalización. Este es el componente orientado a Internet de enrutamiento directo que controla las conexiones SIP (TLS) entre el enrutamiento de SBCs y el enrutamiento directo.

- **Los procesadores multimedia para los** medios. Este es el componente de Internet de enrutamiento directo que maneja el tráfico de medios. Este componente usa los protocolos SRTP y SRTCP.


Para obtener más información sobre el enrutamiento directo, consulte [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md).

Para obtener más información acerca de cómo el enrutamiento directo implementa el protocolo SIP, consulte [protocolo SIP de enrutamiento directo](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Estándares de RFC

El enrutamiento directo cumple con los estándares de RFC.  La SBC conectada al enrutamiento directo también debe cumplir con los siguientes documentos RFC (o sus sucesoras). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Estándares aplicables a dispositivos que admiten el modo de omisión no multimedia 

Los siguientes estándares se aplican a los dispositivos que admiten solo el modo de omisión no multimedia:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de inicio de sesión
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extensión privada para el protocolo de inicio de sesión para la identidad afirmada dentro de redes de confianza: secciones sobre el tratamiento del encabezado de identidad declarada en P. El enrutamiento directo envía la identidad confirmada por P con encabezados de identificación de privacidad. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Extensión del Protocolo de inicio de sesión (SIP) para información del historial requerida. Consulte también: Descripción del protocolo SIP de enrutamiento para obtener más información.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) El protocolo de inicio de sesión denominado mecanismo
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) El encabezado "reemplazar" del Protocolo de inicio de sesión (SIP) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso del Protocolo de inicio de sesión (SIP) del modelo de oferta/respuesta.
  Consulte la sección "desviaciones de RFC".
- [Rfc 3711](https://tools.ietf.org/html/rfc3711) y [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteger el tráfico RTP con SRTP. La SBC debe poder establecer teclas mediante SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocolo de descripción de sesión (SDP) oferta/respuesta aclaraciones para multiplexación de RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Estándares aplicables a dispositivos que admiten el modo de omisión de medios

Además de los estándares indicados en el modo de no omisión, se usan los siguientes estándares para el modo de omisión de medios:

- El [establecimiento de conectividad interactiva de RFC 5245 para la omisión de medios](https://tools.ietf.org/html/rfc5245).  La SBC debe admitir lo siguiente:
  - ICE Lite: los clientes de Teams son clientes completos de ICE
  - Se [reiniciará el hielo](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Ver más en el ICE reinicia caso de uso y ejemplos en reinicio de ICE: llamada de omisión de medios transferida a un extremo que no admite omisión de medios   
- [RFC rfc 5589 control de llamadas de protocolo de inicio de sesión (SIP) – transferencia](https://tools.ietf.org/html/rfc5589). 
- [Generación de tono de timbre y medios iniciales de RFC 3960 en el protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3960), consulte las secciones 3,1, fork y 3,2, generación de tono de timbre 
- [Utilidades de recorrido de sesión de RFC 5389 para NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [Recorridos de RFC 5766 con retransmisión por NAT (TURN): retransmisión de extensiones a utilidades de recorrido de sesión para NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Normas aplicables para permitir la transmisión de información sobre la ubicación a proveedores de E911

- [RFC 6442, transporte de ubicación para el protocolo de inicio de sesión](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desviaciones de las RFC

En la siguiente tabla se enumeran las secciones de RFC en las que se desvía la implementación de Microsoft de la pila de medios o SIP desde el estándar:

| RFC y secciones | Descripción | Funcion |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sección 5,3, suspensión y reanudación de los medios](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC permite usar "a = inactivo", "a = sendonly", a = recvonly "para poner una llamada en espera. |El proxy SIP solo admite "a = inactivo" y no entiende si el SBC envía "a = sendonly" o "a = recvonly".
| [El comportamiento de RFC 6337, sección 5,4 "para recibir SDP con c = 0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requiere que un agente pueda recibir SDP con una dirección de conexión de 0.0.0.0, en cuyo caso significa que no debe enviarse ni RTP ni RTCP al interlocutor. | El proxy SIP no admite esta opción. |

## <a name="operational-modes"></a>Modos operativos

Existen dos modos operativos para el enrutamiento directo:

- **Sin omisión de medios** en el que todo el tráfico de RTP fluye entre el cliente de Teams, los procesadores de medios y el SBC.  

- **Con la omisión de elementos multimedia** en la que todos los medios RTP fluyen entre los puntos de conexión y SBC de los equipos. 

Ten en cuenta que el tráfico SIP siempre fluye a través del proxy SIP.   
