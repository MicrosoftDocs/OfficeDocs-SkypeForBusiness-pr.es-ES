---
title: Enrutamiento directo del sistema telefónico
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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888579"
---
# <a name="overview"></a>Información general

En este artículo se describe cómo el enrutamiento directo admite la omisión de medios con un controlador de borde de sesión (SBC) habilitado para ICE Lite como se describe en [RFC 5245.](https://tools.ietf.org/html/rfc5245) Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el SBC local y el servicio de proxy SIP.

En este artículo se proporciona información general sobre los escenarios y los requisitos de interoperabilidad de ICE Lite. En el artículo se describen los formatos de mensaje y las transiciones de máquina de estado necesarias para garantizar un flujo de llamadas y medios confiables.

## <a name="terminology"></a>Terminología

- First Hello: las primeras palabras pronunciadas por el autor de la llamada y el destinatario. Es importante que se realizan todos los esfuerzos para asegurarse de que los primeros paquetes de los puntos de conexión se entregan de forma confiable en la mayoría de los casos de uso.

- Forking: la oferta del autor de la llamada podría entregarse a varios puntos de conexión de la llamada si el destinatario está disponible en varios dispositivos (por ejemplo, un usuario de Teams podría haber iniciado sesión en Teams para Windows y Teams para Android o iPhone).

- Respuesta provisional (183): los puntos de conexión del destinatario para una configuración de llamada más rápida envían una respuesta con los candidatos y las claves necesarias para establecer el flujo multimedia. Esto se hace en previsión de que el usuario pueda responder a la llamada(200OK) desde esa instancia específica del destinatario. Con la tención, el autor de la llamada debe estar listo para recibir varias respuestas provisionales.

- Re-Invite: oferta con candidatos finales seleccionados por el punto de conexión de control del ICE. Esto tendrá el atributo a=remote-candidate para resolver cualquier condición de carrera al manipular varias bifurcaciones.

- Teams Punto de conexión: podría ser un servidor (procesador multimedia, retransmisión de transporte) o el Teams usuario.

## <a name="message-format"></a>Formato de mensaje

La Teams de datos sigue RFC 5245 para ICE-Lite. Esto implica que todos los mensajes de STUN serán compatibles con [RFC 5389.](https://tools.ietf.org/html/rfc5389)

Los SBC requeridos por RFC 5389 deben ignorar los atributos de STUN que no reconozcan y continuar procesando los mensajes con los atributos conocidos. 

Si se reciben paquetes malformados, los paquetes deben descartarse sin afectar al establecimiento de la sesión multimedia.

## <a name="ice-lite-requirements"></a>Requisitos de ICE Lite

En esta sección se capturan brevemente los requisitos de ICE Lite.

### <a name="candidate-gathering"></a>Reunión de candidatos

El SBC debe ofrecer solo un candidato accesible públicamente. Actualmente, solo se admiten candidatos IPV4.


#### <a name="connectivity-checks"></a>Comprobaciones de conectividad

La implementación de ICE Lite debe responder a las comprobaciones de conectividad recibidas. El punto de conexión ice lite no debe enviar ninguna solicitud de comprobación de conectividad. (Si se envían comprobaciones de conectividad en infracción, la implementación completa responderá, lo que puede provocar que se descubran candidatos derivados por pares inesperados y que puedan producir errores de llamada).

#### <a name="nominations"></a>Nominaciones

El punto de conexión de implementación completa del ICE siempre será el punto de conexión de Control y seguirá las nominaciones "regulares" para seleccionar los candidatos finales que se usarán para el flujo de medios. El punto de conexión de ICE Lite puede usar las nominaciones para concluir la ruta que se usará para los medios y completar el establecimiento de llamadas.

Nota: En el caso de que los puntos de conexión del mismo nivel envíen 183 respuestas provisionales, el SBC debe estar listo para responder a las comprobaciones de varios puntos de conexión y también a las nominaciones de varios puntos de conexión si las nominaciones se realizan antes del 200OK. Dependiendo de la convergencia de la máquina de estado ice en la ruta final y los intervalos del usuario que responde, las nominaciones pueden ocurrir antes o después del 200OK. El SBC debe poder controlar ambos casos.

#### <a name="converging-for-forking"></a>Converger para la forking

Si la oferta de SBC se bifurca a varios puntos de conexión Teams, los puntos de conexión Teams pueden responder con una respuesta provisional e iniciar comprobaciones de conectividad. El SBC debe estar preparado para recibir comprobaciones de conectividad y responder a las comprobaciones de conectividad de varios puntos de conexión del mismo nivel. Por ejemplo, el Teams usuario podría haber iniciado sesión tanto en un escritorio como en un teléfono móvil. Ambos dispositivos recibirán una notificación de la llamada entrante e intentarán realizar comprobaciones de conectividad con el SBC.

Finalmente, solo uno de los puntos de conexión responderá a la llamada (200OK). Al recibir el 200OK, el SBC puede configurar el contexto adecuado para procesar los paquetes multimedia.

## <a name="scenarios"></a>Escenarios

###  <a name="inbound-call-from-sbc"></a>Llamada entrante desde SBC

Para este escenario, hay varios puntos de conexión de punto de conexión posibles que el SBC debe controlar:

- Los puntos de conexión del servidor normalmente responderán directamente con 200OK. Estos son puntos de conexión completos de ICE que suelen estar implicados en el correo de voz, la cola de llamadas y los escenarios de operador automático.

- Los puntos de conexión de cliente pueden enviar varias respuestas provisionales con distintas etiquetas De/A (183) seguidas de un 200OK desde el punto de conexión que responde a la llamada. Estos son puntos de conexión completos de ICE que suelen representar clientes de usuario final.

- Otros puntos de conexión de SBC. Estos son puntos de conexión de ICE Lite que suelen estar implicados en el escenario de llamar simultáneamente a puntos de conexión de cliente y a otros números de teléfono.

El SBC debe responder a todas las solicitudes de comprobación de conectividad válidas recibidas de los puntos de conexión completos de ICE. Por RFC, los puntos de conexión completos de ICE se convertirán en puntos de conexión de Control. Los Teams (cliente/servidor) realizarán nominaciones "regulares" para completar las comprobaciones de conectividad. El 200Ok final puede ser de un punto de conexión que envió medios anticipados o de otro punto de conexión. Al recibir el 200Ok, el SBC debe configurar el contexto adecuado para el flujo multimedia. 

###  <a name="early-media"></a>Medios anticipados

Si hay un flujo de medios anticipado, el SBC debe estar en el primer punto de conexión que inicia la transmisión de contenido multimedia; el flujo de medios puede comenzar antes de que se nomina a los candidatos. El SBC debe ser compatible con el envío de DTMF durante esta fase para habilitar escenarios de IVR/correo de voz. El SBC debe usar la ruta de prioridad más alta en la que ha recibido comprobaciones si las nominaciones no se han completado.

### <a name="outbound-call-to-sbc"></a>Llamada saliente a SBC

Los Teams de conexión son el autor de la llamada para este escenario y será el punto de conexión de control. Al recibir una respuesta provisional (183) o una respuesta final(200OK), el punto de conexión de Teams iniciará las comprobaciones de conectividad y procederá a las nominaciones "Normales" para completar las comprobaciones de conectividad.

Nota: Si el SBC envía una respuesta provisional (183), el SBC debe estar listo para recibir solicitudes de comprobación de conectividad y, posiblemente, completar las nominaciones antes de que el SBC envíe el 200OK. Si las comprobaciones y/o las nominaciones se completan antes de que se reciba el 200OK, los controles y/o las nominaciones no se volverán a realizar después de recibir 200OK. El SBC no debe cambiar los candidatos del ICE, la contraseña y el ufrag (fragmento de nombre de usuario) entre 183 y 200.

Para admitir los primeros medios, es posible que el SBC empiece a transmitir los medios al candidato de ICE del mismo nivel, con la prioridad más alta en función de las comprobaciones de conectividad recibidas, incluso antes de que las nominaciones se completen Teams punto de conexión. El SBC debe esperar que los medios Teams en cualquier candidato hasta que se completen las nominaciones. Una vez que se nomina a un candidato, el SBC debe restablecerse al contexto adecuado para enviar y recibir paquetes multimedia.

## <a name="srtp-support-requirements"></a>Requisitos de soporte técnico srtp

El SBC debe admitir el cifrado SRTP AES_CM_128_HMAC_SHA1_80 para ofrecer y responder en el siguiente formato:

```console
"inline:" <key||salt> ["|" lifetime]
```

A continuación se muestra un ejemplo del atributo crypto en la oferta de SDP del SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Los parámetros MKI y Longitud no son necesarios.

Para obtener más información, vea [RFC 4568, sección 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)

## <a name="sdes-support-requirements"></a>Requisitos de soporte técnico de SDES

El dispositivo debe poder ofrecer SDES en el formato que se describe a continuación. Los procesadores multimedia de Microsoft siempre prefieren SDES.

- Con la omisión no multimedia, incluso si un cliente solo admite DTLS, los procesadores multimedia se convertirán en SDES.

- Con la omisión de medios, si un cliente solo es DTLS (futuro estado de Google Chrome), enrutamiento directo insertará un MP en la ruta de acceso, convirtiendo la llamada de omisión multimedia a omisión no multimedia. Entre el SBC y el componente de procesador multimedia de Enrutamiento directo, sdes siempre se usa.

Actualmente, no hay ningún Teams que solo ofrezca DTLS; sin embargo, Google ha anunciado que en algún momento dejarán de admitir SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato de oferta de SBC en modo de omisión 

Oferta debe contener SDES y puede contener DTLS opcional en el siguiente formato:

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

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato de oferta de Teams a SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Formato para SDES solo ofrece para SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

