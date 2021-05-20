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
# <a name="direct-routing---definitions-and-rfc-standards"></a>Enrutamiento directo - Definiciones y estándares RFC

En este artículo se describe cómo Teléfono Microsoft enrutamiento directo del sistema implementa los protocolos estándar RFC. Este artículo está destinado a administradores de voz que son responsables de configurar la conexión entre el controlador de borde de sesión local (SBC) y el servicio proxy del Protocolo de inicio de sesión (SIP).

El cliente SBC interactúa con los siguientes componentes en el back-end Microsoft Teams: 

- **El proxy SIP** para la señalización. Este es el componente orientado a Internet del enrutamiento directo que maneja las conexiones SIP (TLS) entre los SBC y el enrutamiento directo.

- **Los procesadores de medios** para medios. Este es el componente orientado a Internet de enrutamiento directo que controla el tráfico de medios. Este componente utiliza los protocolos SRTP y SRTCP.


Para obtener más información acerca del enrutamiento directo, consulte [Sistema telefónico enrutamiento directo](direct-routing-landing-page.md).

Para obtener más información acerca de cómo el enrutamiento directo implementa el protocolo SIP, consulte [Enrutamiento directo - Protocolo SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Estándares RFC

Enrutamiento directo cumple con los estándares RFC.  El SBC conectado al enrutamiento directo también debe cumplir con los siguientes RFC (o sus sucesores). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Estándares aplicables a los dispositivos que admiten el modo de derivación no multimedia 

Los siguientes estándares son aplicables a los dispositivos que solo admiten el modo de omisión no multimedia:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocolo de iniciación de sesión
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extensión privada al protocolo de inicio de sesión para la identidad afirmada dentro de redes de confianza: secciones sobre el control del encabezado P-Asserted-Identity. Enrutamiento directo envía P-Asserted-Identity con encabezados de ID de privacidad. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Una extensión al Protocolo de inicio de sesión (SIP) para la información de historial requerida. Vea también: Descripción del Protocolo SIP de ruteo para más información.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) El mecanismo de Referred-By del Protocolo de Iniciación de Sesiones
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) El encabezado "Reemplaza" del Protocolo de inicio de sesión (SIP) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso del Protocolo de inicio de sesión (SIP) del modelo de oferta/respuesta.
  Consulte la sección "Desviaciones de RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) y [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteja el tráfico RTP usando el SRTP. El SBC debe poder establecer claves mediante SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocolo de descripción de sesión (SDP) Ofrecer/Responder aclaraciones para rtp/RTCP multiplexing

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Estándares aplicables a los dispositivos que admiten el modo de derivación de medios

Además de los estándares enumerados como aplicables al modo de no derivación, se utilizan los siguientes estándares para el modo de derivación de medios:

- [RFC 5245 Establecimiento interactivo de conectividad (ICE) para la omisión de medios](https://tools.ietf.org/html/rfc5245).  El SBC debe admitir lo siguiente:
  - ICE Lite: los clientes Teams son clientes completos del ICE
  - [El ICE reinicia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Vea más sobre los reinicios del ICE caso de uso y ejemplos en ice restart: Media bypass call transferida a un punto final que no admite la omisión de medios   
- [RFC RFC 5589 Protocolo de inicio de sesión (SIP) Control de llamadas – Transferencia](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation en el Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)ver secciones 3.1, Forking, y 3.2, Ringing Tone Generation 
- [Utilidades de recorrido de sesión RFC 5389 para NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Usando relés alrededor de NAT (TURN): Extensiones de relé a utilidades de recorrido de sesión para NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Normas aplicables a la ayuda para transmitir información de ubicación a proveedores de E911

- [RFC 6442, Transporte de ubicación para el Protocolo de iniciación de sesión](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Desviaciones de la RFC

En la tabla siguiente se enumeran las secciones de las RFC en las que la implementación de Microsoft de la pila sip o media se desvía del estándar:

| RFC y secciones | Descripción | desviación |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sección 5.3 Retención y reanudación de medios](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC permite utilizar "a=inactive", "a=sendonly", a=recvonly" para realizar una llamada en espera. |El proxy SIP solo admite "a=inactive" y no entiende si el SBC envía "a=sendonly" o "a=recvonly".
| [RFC 6337, sección 5.4 "Comportamiento al recibir SDP con c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) requiere que un agente sea capaz de recibir el SDP con una dirección de conexión de 0.0.0.0, en cuyo caso significa que ni rtp ni RTCP deben ser enviados al par. | El proxy SIP no admite esta opción. |

## <a name="operational-modes"></a>Modos operativos

Hay dos modos operativos para el enrutamiento directo:

- **Sin la omisión de medios** en la que todo el tráfico RTP fluye entre el cliente Teams, los procesadores de medios, y el SBC.  

- **Con el desvío de medios** en el cual todos los medios RTP fluyen entre los puntos finales Teams y el SBC. 

Observe que el tráfico SIP fluye siempre vía el proxy DEL SORBO. 

## <a name="dtmf"></a>Dtmf
La pila de medios no admite DTMF en banda.
