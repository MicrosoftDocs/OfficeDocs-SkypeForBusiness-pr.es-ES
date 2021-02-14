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

En este artículo se describe cómo el enrutamiento directo admite la omisión de medios con un controlador de borde de sesión (SBC) habilitado para ICE Lite, tal y como se describe en [RFC 5245.](https://tools.ietf.org/html/rfc5245) Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el SBC local y el servicio de proxy SIP.

Este artículo proporciona una descripción general de los escenarios y requisitos de ICE Lite para interoperabilidad. En el artículo se describen los formatos de los mensajes y las transiciones necesarias entre las máquinas de estado para garantizar una llamada y un flujo multimedia confiables.

## <a name="terminology"></a>Terminología

- Primero Hola: las primeras palabras habladas por el autor de la llamada y el destinatario de la llamada. Es importante que todos los esfuerzos se realizan para asegurarse de que los primeros paquetes de los puntos de conexión se entregan de forma fiable en la mayoría de los casos de uso.

- Entrada de teclado: la oferta del autor de la llamada se puede entregar a varios puntos de conexión del destinatario del mensaje si el destinatario está disponible en varios dispositivos (por ejemplo, es posible que un usuario de Teams haya iniciado sesión en Teams para Windows y Teams para Android o iPhone).

- Respuesta provisional (183): los puntos de conexión del destinatario para una configuración de llamada más rápida envían una respuesta con los candidatos y las claves necesarios para establecer el flujo de medios. Esto se realiza con anticipación a que el usuario responda potencialmente a la llamada(200OK) desde esa instancia específica del destinatario. Con la función de ántrate, el autor de la llamada debería estar preparado para recibir varias respuestas provisionales.

- Re-Invite: oferta con candidatos finales seleccionada por el punto de conexión de control de ICE. This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.

- Extremo de Teams: puede ser un servidor (procesador de medios, retransmisión de transporte) o el cliente de Teams.

## <a name="message-format"></a>Formato del mensaje

La infraestructura de Teams sigue RFC 5245 para ICE-Lite. Esto implica que todos los mensajes STUN serán compatibles con [RFC 5389.](https://tools.ietf.org/html/rfc5389)

Los S SBCs, según requiera RFC 5389, deben ignorar cualquier atributos STUN que no reconozcan y continuar procesando los mensajes con los atributos conocidos. 

Si se reciben paquetes con formato noformado, los paquetes se deberán descartar sin afectar al establecimiento de sesión multimedia.

## <a name="ice-lite-requirements"></a>Requisitos de ICE Lite

En esta sección se recogen brevemente los requisitos de ICE Lite.

### <a name="candidate-gathering"></a>Reunión de candidatos

La SBC debe ofrecer solo un candidato que sea públicamente accesible. Actualmente, solo se admiten los candidatos IPV4.


#### <a name="connectivity-checks"></a>Comprobaciones de conectividad

La implementación de ICE Lite debe responder a las comprobaciones de conectividad recibidas. El punto de conexión de ICE Lite no debe enviar ninguna solicitud de comprobación de conectividad. (Si se envían comprobaciones de conectividad infracción, responderá la implementación completa, lo que puede provocar que se descubran candidatos derivados del mismo nivel de forma inesperada y que se puedan producir errores en la llamada).

#### <a name="nominations"></a>Información desde el centro de datos

El punto de conexión de implementación completa de ICE siempre será el punto de conexión de control y seguirá las instrucciones "regulares" para seleccionar los candidatos finales que se usarán para el flujo de medios. El punto de conexión de ICE Lite puede utilizar los resultados para concluir la ruta que se usará para los medios y para el establecimiento de llamadas completo.

Nota: En el caso de la entrada de objetos con puntos de conexión de punto de conexión que envían 183 respuestas provisionales, la SBC debe estar lista para responder a las comprobaciones de varios puntos de conexión y, si las cosas se realizan antes del 200A, las vistas de varios puntos de conexión también se realizan. Según la convergencia del equipo de estado de ICE en la ruta final y los intervalos de respuesta del usuario, las limpiezas pueden producirse antes o después de 200A. La SBC debe ser capaz de controlar ambos casos.

#### <a name="converging-for-forking"></a>Converger para la forking

Si la oferta de la SBC se bifurca para varios puntos de conexión de Teams, los puntos de conexión de Teams pueden responder con una respuesta provisional e iniciar comprobaciones de conectividad. La SBC debe estar preparada para recibir comprobaciones de conectividad y responder a las comprobaciones de conectividad de varios puntos de conexión del mismo nivel. Por ejemplo, el usuario de Teams podría haber iniciado sesión en un equipo de escritorio y en un teléfono móvil. Ambos dispositivos recibirán una notificación de la llamada entrante e intentarán realizar comprobaciones de conectividad con el SBC.

Finalmente, solo uno de los puntos de conexión responderá a la llamada (200OK). Al recibir 200OK, la SBC puede configurar el contexto adecuado para el procesamiento de los paquetes multimedia.

## <a name="scenarios"></a>Escenarios

###  <a name="inbound-call-from-sbc"></a>Llamada entrante de SBC

Para este escenario, hay varios posibles puntos de conexión de punto de conexión que el SBC debe controlar:

- Los puntos de conexión del servidor normalmente responderán directamente con 200OK. Se trata de puntos de conexión completos de ICE que suelen estar implicados en los escenarios del correo de voz, la cola de llamadas y el operador automático.

- Los puntos de conexión del cliente pueden enviar varias respuestas provisionales con etiquetas de origen y destino diferentes (183) seguidas de 200OK desde el punto de conexión que responde a la llamada. Estos son puntos de conexión completos de ICE que normalmente representan los clientes del usuario final.

- Otros puntos de conexión SBC. Estos son puntos de conexión de ICE Lite que suelen estar implicados en el escenario de hacer llamadas simultáneas a puntos de conexión de cliente y otros números de teléfono.

La SBC debe responder a todas las solicitudes válidas de comprobación de conectividad recibidas de los puntos de conexión completos de ICE. Por RFC, los puntos de conexión completos de ICE se convertirán en extremos de control. Los puntos de conexión de Teams (cliente/servidor) realizarán comprobaciones "normales" para completar las comprobaciones de conectividad. La versión final de 200Ok puede ser de un punto de conexión que envió medios anticipados o de otro punto de conexión. Al recibir 200Ok, la SBC debe configurar el contexto adecuado para el flujo de medios. 

###  <a name="early-media"></a>Medios iniciales

Si hay un flujo de medios anticipado, la SBC debe tener acceso al primer punto de conexión que inicia la transmisión multimedia; el flujo multimedia puede empezar antes de que los candidatos se nominan. SBC debe ser compatible con el envío de DTMF durante esta fase para habilitar los escenarios de IVR/correo de voz. La SBC debe usar la ruta de prioridad más alta en la que ha recibido comprobaciones si no se han completado los resultados.

### <a name="outbound-call-to-sbc"></a>Llamada saliente a SBC

Los puntos de conexión de Teams son la persona que llama para este escenario y serán el punto final de control. Al recibir una respuesta provisional (183) o una respuesta final(200OK), el punto de conexión de Teams iniciará las comprobaciones de conectividad y continuará con los resultados "normales" para completar las comprobaciones de conectividad.

Nota: Si la SBC envía una respuesta provisional (183), la SBC debe estar lista para recibir solicitudes de comprobación de conectividad y, posiblemente, completar las peticiones antes de que la SBC envíe la 200OK. Si las comprobaciones o los resultados se completan antes de que se reciba la versión 200OK, las comprobaciones y/o los resultados no se volverán a realizar después de recibir 200OK. La SBC no debe cambiar los candidatos, la contraseña y el ufrag (fragmento de nombre de usuario) de ICE entre 183 y 200.

Para admitir los medios anticipados, la SBC puede iniciar la transmisión de los medios al candidato de ICE del mismo nivel, con la máxima prioridad en función de las comprobaciones de conectividad recibidas, incluso antes de que el punto de conexión de Teams complete las pruebas. La SBC debería esperar los medios de Teams en cualquier candidato hasta que se completen los resultados. Una vez nominado un candidato, la SBC debe restablecerse al contexto adecuado para enviar y recibir paquetes multimedia.

## <a name="srtp-support-requirements"></a>Requisitos de soporte técnico del SRTP

La SBC debe admitir el cifrado de cifrado SRTP AES_CM_128_HMAC_SHA1_80 para ofrecer y responder en el siguiente formato:

```console
"inline:" <key||salt> ["|" lifetime]
```

El siguiente es un ejemplo del atributo crypto de la oferta SDP de la SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Los parámetros MKI y Length no son necesarios.

Para obtener más información, [vea RFC 4568, sección 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)

## <a name="sdes-support-requirements"></a>Requisitos de soporte técnico de SDES

El dispositivo debe poder ofrecer SDES en el formato que se describe a continuación. Los procesadores multimedia de Microsoft siempre prefieren SDES.

- Con omisión no multimedia, incluso si un cliente solo admite DTLS, los procesadores de medios se convertirán en SDES.

- Con la omisión de medios, si un cliente es DTLS solo (estado futuro de Google Chrome), el enrutamiento directo insertará un MP en la ruta de acceso, convirtiendo la llamada de omisión de medios a omisión no multimedia. Entre el componente SBC y el procesador de medios de enrutamiento directo, siempre se utiliza SDES.

Actualmente, no hay ningún cliente de Teams que solo ofrezca DTLS; sin embargo, Google ha anunciado que en algún momento dejarán de admitir SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato de la oferta de SBC en modo de omisión 

La oferta debe contener SDES y puede contener un DTLS opcional en el siguiente formato:

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

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato de la oferta de Teams a SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>El formato para SDES solo ofrece a SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

