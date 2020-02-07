---
title: Enrutamiento directo del Sistema telefónico
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
ms.openlocfilehash: 3f21a4532a841a23f6bbb78a57e223616ae539fa
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835140"
---
# <a name="overview"></a>Información general

En este artículo se describe cómo el enrutamiento directo admite la omisión de elementos multimedia con un controlador de borde de sesión (SBC) habilitado para ICE Lite, como se describe en [RFC 5245](https://tools.ietf.org/html/rfc5245). Este artículo está dirigido a los administradores de voz responsables de configurar la conexión entre el SBC local y el servicio de proxy SIP.

Este artículo proporciona una descripción general de los escenarios de ICE Lite y los requisitos de interoperabilidad. En este artículo se describen los formatos de mensaje y las transiciones de equipos de estado necesarias para garantizar una llamada y un flujo de medios confiables.

## <a name="terminology"></a>Terminología

- Primero Hola: las primeras palabras que habla la persona que llama y la persona que llama. Es importante que se realicen todos los esfuerzos para asegurarse de que los primeros paquetes de los puntos de conexión se entreguen de manera confiable para la mayoría de los casos de uso.

- Bifurcación: la oferta de la persona que llama puede ser entregada a varios puntos de conexión de llamadas si el destinatario de la llamada está disponible en varios dispositivos (por ejemplo, un usuario de equipos puede haber iniciado sesión en Teams para Windows y Teams para Android o iPhone).

- Respuesta provisional (183): los puntos de conexión de llamadas para acelerar la configuración de llamadas envían una respuesta con los candidatos y claves necesarios para establecer el flujo de medios. Esto se realiza en previsión de que el usuario pueda responder a la llamada (200OK) de esa instancia específica del destinatario. Con la ramificación, la persona que llama debe estar lista para recibir varias respuestas provisionales.

- Volver a invitar: oferta con candidatos finales seleccionado por el punto final del control de hielo. Esto tendrá el atributo a = candidato a candidatos remotos para resolver las condiciones de carrera y controlar varias bifurcaciones.

- Punto de conexión de equipos: puede ser un servidor (procesador multimedia, retransmisión de transporte) o el cliente de Teams.

## <a name="message-format"></a>Formato del mensaje

La infraestructura de Teams sigue el RFC 5245 para ICE-Lite. Esto implica que todos los mensajes STUN serán compatibles con el [RFC 5389](https://tools.ietf.org/html/rfc5389).

El SBCs según lo solicite el RFC 5389 debe omitir los atributos STUN que no reconozcan y continuar procesando los mensajes con los atributos conocidos. 

Si se reciben paquetes mal formados, los paquetes se deben descartar sin afectar al establecimiento de la sesión de medios.

## <a name="ice-lite-requirements"></a>Requisitos de ICE Lite

Esta sección captura brevemente los requisitos de ICE Lite.

### <a name="candidate-gathering"></a>Recopilación de candidatos

La SBC debe ofrecer un candidato que sea accesible públicamente. Actualmente, solo se admiten los candidatos IPV4.


#### <a name="connectivity-checks"></a>Comprobaciones de conectividad

La implementación de ICE Lite debe responder a las comprobaciones de conectividad recibidas. El punto final de ICE Lite no debe enviar solicitudes de comprobación de conectividad. (Si se envían infracciones las comprobaciones de conectividad, la implementación completa responderá, lo que puede provocar que se descubran candidatos derivados del mismo nivel inesperados y producir errores de llamadas).

#### <a name="nominations"></a>Nominaciones

El extremo de la implementación completa de ICE siempre será el extremo de control y seguirá las nominaciones "normales" para seleccionar los candidatos finales que se usarán para el flujo de medios. El punto final de hielo Lite puede usar las nominaciones para concluir la ruta que se utilizará para los medios y el establecimiento completo de llamadas.

Nota: en el caso de bifurcación con puntos de conexión del mismo nivel enviando respuestas provisionales de 183, la SBC debe estar preparada para responder a las comprobaciones de varios puntos finales y también a las nominaciones de varios puntos finales si las nominaciones se producen antes de 200OK. En función de la convergencia de la máquina de estado de hielo en la ruta de acceso final y en el momento de la respuesta del usuario, las nominaciones pueden ocurrir antes o después de la 200OK. La SBC debe poder controlar ambos casos.

#### <a name="converging-for-forking"></a>Convergencia de la ramificación

Si la oferta de la horquilla de SBC para los puntos de conexión de varios equipos, los puntos de conexión de Teams pueden responder con una respuesta provisional y empezar las comprobaciones de conectividad. El SBC debe estar preparado para recibir comprobaciones de conectividad y responder a las comprobaciones de conectividad de varios puntos de conexión del mismo nivel. Por ejemplo, el usuario de Teams podría iniciar sesión en un equipo de escritorio y un teléfono móvil. Se notificará a ambos dispositivos de la llamada entrante y se intentarán las comprobaciones de conectividad con el SBC.

Hasta el momento, solo uno de los puntos de conexión responderá a la llamada (200OK). Al recibir la 200OK, la SBC puede configurar el contexto adecuado para procesar los paquetes de medios.

## <a name="scenarios"></a>Escenarios

###  <a name="inbound-call-from-sbc"></a>Llamada entrante de SBC

Para este escenario, hay varios puntos de conexión posibles del mismo nivel que el SBC debe controlar:

- Los puntos de conexión de servidor normalmente responderán directamente con 200OK. Se trata de puntos de conexión de hielo completos que normalmente participan en el buzón de voz, la cola de llamadas y los escenarios de operador automático.

- Los puntos de conexión de cliente pueden enviar varias respuestas provisionales con diferentes etiquetas from/to (183) seguidas de 200OK desde el extremo que responde a la llamada. Estos son puntos de conexión de hielo completos que suelen representar clientes de usuario final.

- Otros puntos de conexión de SBC. Estos son puntos de conexión de ICE Lite generalmente implicados en el escenario de llamadas simultáneas a puntos de conexión de cliente y otro número de teléfono.

El SBC debe responder a todas las solicitudes de comprobación de conectividad válidas recibidas de los puntos de conexión de hielo completos. Por RFC, los puntos de conexión de hielo completos se convertirán en el control de los puntos de conexión. Los puntos de conexión de Teams (cliente/servidor) realizarán nominaciones "normales" para completar las comprobaciones de conectividad. El 200Ok final puede ser de un extremo que envió medios anteriores o de un extremo diferente. Al recibir la 200Ok, el SBC debe configurar el contexto adecuado para el flujo de medios. 

###  <a name="early-media"></a>Primeros medios

Si hay un flujo de medios temprano, el SBC debe aplatchar el primer punto de conexión que empiece a transmitir contenido multimedia; el flujo de medios puede iniciarse antes de que se nominar candidatos. El SBC debería admitir el envío de DTMF durante esta fase para habilitar escenarios de IVR/buzón de voz. La SBC debe usar la ruta de prioridad más alta en la que ha recibido comprobaciones si las nominaciones no se han completado.

### <a name="outbound-call-to-sbc"></a>Llamada saliente a SBC

Los puntos de conexión de Teams son la persona que llama para este escenario y será el extremo de control. Al recibir una respuesta provisional (183) o una respuesta final (200OK), el punto de conexión de Teams iniciará las comprobaciones de conectividad y continuará con las nominaciones "normales" para completar las comprobaciones de conectividad.

Nota: Si la SBC envía una respuesta provisional (183), la SBC debe estar lista para recibir solicitudes de comprobación de conectividad y posiblemente completar las nominaciones antes de que el SBC envíe el 200OK. Si se completan las comprobaciones o nominaciones antes de que se reciba la 200OK, los controles o nominaciones no se volverán a realizar una vez recibida la 200OK. La SBC no debe cambiar los candidatos para hielo, la contraseña y el ufrag (fragmento de nombre de usuario) entre 183 y 200.

Para admitir los medios iniciales, la SBC puede iniciar la transmisión de los medios al candidato de ICE del mismo nivel, con la mayor prioridad en función de las comprobaciones de conectividad recibidas, incluso antes de que las noventa se completen mediante el punto de conexión de Teams. La SBC debe esperar medios de los equipos de cualquier candidato hasta que se completen las nominaciones. Una vez que se ha designado a un candidato, el SBC debe restablecer el contexto adecuado para enviar y recibir paquetes de medios.

## <a name="srtp-support-requirements"></a>Requisitos de soporte técnico de SRTP

La SBC debe admitir el cifrado de cifrado SRTP AES_CM_128_HMAC_SHA1_80 para la oferta y la respuesta en el siguiente formato:

```
"inline:" <key||salt> ["|" lifetime]
```

El siguiente es un ejemplo del atributo criptográfico en la oferta de SDP de SBC:

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Los parámetros MKI y length no son obligatorios.

Para obtener más información, consulte la [sección 6,1 de RFC 4568](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>Requisitos de asistencia de SDES

El dispositivo debe poder ofrecer SDES en el formato que se describe a continuación. Los procesadores de multimedia de Microsoft siempre prefieren SDES.

- Con la omisión de contenido no multimedia, incluso si un cliente solo admite DTLS, los procesadores multimedia se convertirán en SDES.

- Con la omisión de elementos multimedia, si un cliente solo se DTLS (el próximo estado de Google Chrome), el enrutamiento directo insertará un módulo de administración en la ruta de acceso, lo que convierte la llamada de la omisión de medios en una omisión no multimedia. Entre el componente de el procesador multimedia y la SBC de enrutamiento directo, siempre se usa SDES.

Por el momento, no hay ningún cliente de equipos que solo ofrezca DTLS; sin embargo, Google ha anunciado que, en algún momento, dejarán de admitir SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato de la oferta de SBC en el modo de omisión 

La oferta debe contener SDES y puede contener DTLS opcional en el siguiente formato:

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Formato de la respuesta que contiene SDES a SBC

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato de la oferta de Teams a SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Formato de SDES solo para la oferta de SBC

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

