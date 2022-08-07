---
title: Información general de enrutamiento directo del sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: El enrutamiento directo hHw admite la omisión de medios con un controlador de borde de sesión habilitado para ICE Lite.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59ea283069c6fc37590d6329aeac46e40484f8ca
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267765"
---
# <a name="overview"></a>Información general

En este artículo se describe cómo Direct Routing admite la omisión de medios con un controlador de borde de sesión (SBC) habilitado para ICE Lite, como se describe en [RFC 5245](https://tools.ietf.org/html/rfc5245). Este artículo está destinado a los administradores de voz que son responsables de configurar la conexión entre el SBC local y el servicio proxy SIP.

En este artículo se proporciona información general sobre los escenarios y requisitos de ICE Lite para la interoperabilidad. En el artículo se describen los formatos de mensaje y las transiciones necesarias de la máquina de estado para garantizar un flujo de llamadas y multimedia confiable.

## <a name="terminology"></a>Terminología

- First Hello: las primeras palabras habladas por el autor de la llamada y el destinatario de la llamada. Es importante que se realicen todos los esfuerzos para garantizar que los primeros paquetes de los puntos de conexión se entreguen de forma confiable para la mayoría de los casos de uso.

- Entrada manuscrita: la oferta del autor de la llamada se puede entregar a varios puntos de conexión si el destinatario de la llamada está disponible en varios dispositivos (por ejemplo, un usuario de Teams podría haber iniciado sesión en Teams para Windows y Teams para Android o iPhone).

- Respuesta provisional (183): los puntos de conexión del destinatario de la llamada para una configuración de llamada más rápida envían una respuesta con los candidatos y las claves necesarias para establecer el flujo de medios. Esto se hace anticipando que el usuario pueda responder a la llamada(200OK) desde esa instancia específica del destinatario de la llamada. Con la entrada manuscrita, el autor de la llamada debe estar listo para recibir varias respuestas provisionales.

- Re-Invite: oferta con candidatos finales seleccionados por el punto de conexión de control de ICE. Esto tendrá el atributo a=remote-candidate para resolver cualquier condición de carrera a partir de la manipulación de varias horquillas.

- Punto de conexión de Teams: puede ser un servidor (procesador multimedia, retransmisión de transporte) o el cliente de Teams.

## <a name="message-format"></a>Formato del mensaje

La infraestructura de Teams sigue a RFC 5245 para ICE-Lite. Esto implica que todos los mensajes stun cumplirán con [RFC 5389](https://tools.ietf.org/html/rfc5389).

Los S SBC según lo requerido por RFC 5389 deben ignorar los atributos stun que no reconocen y continúan procesando los mensajes con los atributos conocidos. 

Si se reciben paquetes con formato incorrecto, estos deben descartarse sin que esto afecte al establecimiento de la sesión multimedia.

## <a name="ice-lite-requirements"></a>Requisitos de ICE Lite

En esta sección se capturan brevemente los requisitos de ICE Lite.

### <a name="candidate-gathering"></a>Reunión de candidatos

El SBC debe ofrecer solo un candidato que sea públicamente accesible. Actualmente, solo se admiten candidatos IPV4.


#### <a name="connectivity-checks"></a>Comprobaciones de conectividad

La implementación de ICE Lite debe responder a las comprobaciones de conectividad recibidas. El punto de conexión de ICE Lite no debe enviar ninguna solicitud de comprobación de conectividad. (Si se envían comprobaciones de conectividad en caso de infracción, la implementación completa responderá, lo que puede provocar la detección de candidatos derivados del mismo nivel inesperados y, potencialmente, errores de llamada).

#### <a name="nominations"></a>Nominaciones

El punto final de implementación completa de ICE siempre será el punto final de Controlling y seguirá las nominaciones "regulares" para seleccionar los candidatos finales que se usarán para el flujo de medios. El punto de conexión de ICE Lite puede usar las nominaciones para concluir la ruta que se usará para los medios y el establecimiento completo de llamadas.

Nota: En el caso de la entrada manuscrita con puntos de conexión del mismo nivel que envían 183 respuestas provisionales, el SBC debe estar listo para responder a las comprobaciones de varios puntos de conexión y también las nominaciones de varios puntos de conexión si las nominaciones se producen antes del 200OK. Dependiendo de la convergencia de la máquina del estado ice en el camino final y el tiempo del usuario que responde, las nominaciones pueden ocurrir antes o después del 200OK. El SBC debe ser capaz de controlar ambos casos.

#### <a name="converging-for-forking"></a>Convergente para la entrada manuscrita

Si la oferta de las bifurcaciones de SBC a varios puntos de conexión de Teams, los puntos de conexión de Teams pueden responder con una respuesta provisional e iniciar las comprobaciones de conectividad. El SBC debe estar preparado para recibir comprobaciones de conectividad y responder a las comprobaciones de conectividad de varios puntos de conexión del mismo nivel. Por ejemplo, el usuario de Teams podría haber iniciado sesión en un equipo de escritorio y en un teléfono móvil. Ambos dispositivos recibirán una notificación de la llamada entrante e intentarán realizar comprobaciones de conectividad con el SBC.

Finalmente, solo uno de los puntos de conexión responderá a la llamada (200OK). Al recibir el 200OK, el SBC puede configurar el contexto adecuado para procesar los paquetes multimedia.

## <a name="scenarios"></a>Escenarios

###  <a name="inbound-call-from-sbc"></a>Llamada entrante desde SBC

Para este escenario, hay varios puntos de conexión del mismo nivel posibles que el SBC debe controlar:

- Los puntos de conexión del servidor suelen responder directamente con 200OK. Se trata de puntos de conexión completos de ICE que suelen estar implicados en los escenarios de correo de voz, cola de llamadas y operador automático.

- Los puntos de conexión del cliente pueden enviar varias respuestas provisionales con etiquetas de origen y destino diferentes (183), seguidas de un 200OK desde el punto de conexión que responde a la llamada. Estos son puntos de conexión completos de ICE que normalmente representan clientes de usuarios finales.

- Otros puntos de conexión de SBC. Estos son puntos de conexión de ICE Lite que suelen estar implicados en el escenario de llamadas simultáneas de puntos de conexión de cliente y otros números de teléfono.

El SBC debe responder a todas las solicitudes de comprobación de conectividad válidas recibidas de los puntos de conexión completos de ICE. Por RFC, los puntos de conexión de ICE completos se convertirán en puntos de conexión de Controlling. Los puntos de conexión de Teams (cliente/servidor) realizarán nominaciones "periódicas" para completar las comprobaciones de conectividad. El final 200Ok puede ser de un punto de conexión que envió medios anticipados o desde un punto de conexión diferente. Al recibir el 200Ok, el SBC debe configurar el contexto adecuado para el flujo multimedia. 

###  <a name="early-media"></a>Elementos multimedia iniciales

Si hay un flujo de medios anticipado, el SBC debe estar en contacto con el primer punto de conexión que inicia el streaming multimedia; el flujo de medios puede comenzar antes de que se designe a los candidatos. El SBC debe tener soporte para enviar DTMF durante esta fase para habilitar escenarios de IVR/correo de voz. El SBC debe utilizar la ruta de prioridad más alta en la que ha recibido cheques si las nominaciones no se han completado.

### <a name="outbound-call-to-sbc"></a>Llamada saliente a SBC

Los puntos de conexión de Teams son los autores de llamadas de este escenario y serán el punto final de control. Al recibir una respuesta provisional (183) o una respuesta final(200OK), el punto de conexión de Teams iniciará comprobaciones de conectividad y continuará con las nominaciones "periódicas" para completar las comprobaciones de conectividad.

Nota: Si el SBC envía una respuesta provisional (183), el SBC debe estar listo para recibir solicitudes de comprobación de conectividad y potencialmente completar las nominaciones antes de que el 200OK sea enviado por el SBC. Si los cheques y/o nominaciones se completan antes de que se reciba el 200OK, las comprobaciones y/o nominaciones no se volverán a realizar después de que se reciba 200OK. El SBC no debe cambiar los candidatos de ICE, la contraseña y el ufrag (fragmento de nombre de usuario) entre 183 y 200.

Para admitir medios anticipados, el SBC puede iniciar la transmisión de los medios al candidato de ICE del mismo nivel, con la máxima prioridad en función de las comprobaciones de conectividad recibidas, incluso antes de que el punto de conexión de Teams complete las nominaciones. El SBC debe esperar que los medios de Teams sobre cualquier candidato hasta que se completen las nominaciones. Una vez que se nomina un candidato, el SBC debe restablecer al contexto correcto para enviar y recibir paquetes multimedia.

## <a name="srtp-support-requirements"></a>Requisitos de soporte de SRTP

El SBC debe admitir AES_CM_128_HMAC_SHA1_80 de cifrado SRTP para ofrecer y responder en el siguiente formato:

```console
"inline:" <key||salt> ["|" lifetime]
```

El siguiente es un ejemplo del atributo crypto en la oferta SDP desde el SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Los parámetros MKI y Length no son necesarios.

Para obtener más información, vea [RFC 4568, sección 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>Requisitos de soporte de SDES

El dispositivo debe poder ofrecer SDES en el formato que se describe a continuación. Los procesadores multimedia de Microsoft siempre prefieren SDES.

- Con la omisión no multimedia, incluso si un cliente solo admite DTLS, los procesadores multimedia se convertirán en SDES.

- Con la omisión de medios, si un cliente es solo DTLS (futuro estado de Google Chrome), Enrutamiento directo insertará un MP en la ruta de acceso, convirtiendo la llamada de la omisión multimedia en omisión no multimedia. Entre el componente SBC y el componente de procesador multimedia de enrutamiento directo, siempre se usa SDES.

Actualmente, no hay ningún cliente de Teams que ofrezca solo DTLS; sin embargo, Google ha anunciado que en algún momento en el tiempo dejarán de admitir SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato para la oferta de SBC en modo de omisión 

La oferta debe contener SDES y puede contener DTLS opcional en el siguiente formato:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Formato de respuesta que contiene SDES a SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato para la oferta de Teams a SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>El formato de SDES solo ofrece a SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

