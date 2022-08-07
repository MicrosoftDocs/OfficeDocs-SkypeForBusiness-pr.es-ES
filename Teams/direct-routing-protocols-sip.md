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
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocolos de enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a4ba1715ccf7b1ea2f0dbf12b58fd5aa6556b24
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271265"
---
# <a name="direct-routing---sip-protocol"></a>Enrutamiento directo: protocolo SIP

En este artículo se describe cómo el Enrutamiento directo implementa el Protocolo de inicio de sesión (SIP). Para redirigir correctamente el tráfico entre un controlador de borde de sesión (SBC) y el proxy SIP, algunos parámetros SIP deben tener valores específicos. Este artículo está destinado a los administradores de voz que son responsables de configurar la conexión entre el SBC local y el servicio proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Procesando la solicitud entrante: buscar el espacio empresarial y el usuario

Antes de que se pueda procesar una llamada entrante o saliente, los mensajes OPTIONS se intercambian entre el proxy SIP y el SBC. Estos mensajes OPTIONS permiten que el proxy SIP proporcione las capacidades permitidas a SBC. Es importante que la negociación OPTIONS tenga éxito (respuesta 200OK), permitiendo una mayor comunicación entre SBC y proxy SIP para establecer llamadas. Los encabezados SIP en un mensaje OPTIONS a proxy SIP se proporcionan como ejemplo a continuación:

| Nombre del parámetro | Ejemplo del valor | 
| :---------------------  |:---------------------- |
| Request-URI | OPCIONES sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| A través del encabezado | A través de: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| encabezado de Max-Forwards | Max-Forwards:68 |
| Desde encabezado | Desde el encabezado de: <sip:sbc1.adatum.biz:5058> |
| Al encabezado | Para: <sip:sip.pstnhub.microsoft.com:5061> |
| Encabezado CSeq | CSeq: 1 INVITACIÓN | 
| Encabezado de contacto | Contacto: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Los encabezados SIP no contienen userinfo en el URI del SIP en uso. Según [RFC 3261, sección 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), la parte userinfo de un URI es opcional y PUEDE estar ausente cuando el host de destino no tiene una noción de usuarios o cuando el propio recurso está siendo identificado. Si el signo @ está presente en un URI de SIP, el campo de usuario NO DEBE estar vacío.
> Tenga en cuenta que el URI del SIPS no debe utilizarse con el Direct Routing ya que no es compatible.
> Compruebe la configuración del controlador de borde de sesión y asegúrese de que no está usando encabezados "Reemplaza" en solicitudes SIP. Enrutamiento directo rechazará solicitudes SIP que tengan los encabezados Replaces definidos.

En una llamada entrante, el proxy SIP necesita encontrar el inquilino al que se destina la llamada y encontrar el usuario específico dentro de este inquilino. El administrador de inquilinos puede configurar números no DID, por ejemplo +1001, en varios espacios empresariales. Por lo tanto, es importante encontrar el inquilino específico en el que realizar la búsqueda de números porque los números que no son DID podrían ser los mismos en varias organizaciones de Microsoft 365 o Office 365.  

Esta sección describe cómo el proxy SIP encuentra el inquilino y el usuario, y realiza la autenticación del SBC en la conexión entrante.

El siguiente es un ejemplo del mensaje de invitación SIP en una llamada entrante:

| Nombre del parámetro | Ejemplo del valor | 
| :---------------------  |:---------------------- |
| Request-URI | INVITAR sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| A través del encabezado | A través de: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| encabezado de Max-Forwards | Max-Forwards:68 |
| Desde encabezado | Desde el encabezado de: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| Al encabezado | Para: sip:+183338006777@sbc1.adatum.biz | 
| Encabezado CSeq | CSeq: 1 INVITACIÓN | 
| Encabezado de contacto | Contacto: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Al recibir la invitación, el proxy SIP realiza los siguientes pasos:

1. Compruebe el certificado. En la conexión inicial, el servicio de enrutamiento directo toma el nombre fqdn presentado en el encabezado del contacto y lo hace coincidir con el nombre común o el nombre alternativo del asunto del certificado presentado. El nombre de SBC debe coincidir con una de las siguientes opciones:

   - Opción 1. El nombre completo del FQDN que se presenta en el encabezado del contacto debe coincidir con el nombre común o el nombre alternativo del asunto del certificado presentado.  

   - Opción 2. La parte del dominio del nombre FQDN que se muestra en el encabezado Contacto (por ejemplo, adatum.biz del nombre FQDN sbc1.adatum.biz) debe coincidir con el valor de comodín en Nombre común o Nombre alternativo del asunto (por ejemplo* .adatum.biz).

2. Intente buscar un inquilino con el nombre completo de FQDN que se muestra en el encabezado Contacto.  

   Compruebe si el nombre fqdn del encabezado de contacto (sbc1.adatum.biz) está registrado como nombre DNS en cualquier Microsoft 365 o Office 365 organización. Si se encuentra, la búsqueda del usuario se realiza en el inquilino que tiene el FQDN de SBC registrado como nombre de dominio. Si no se encuentra, se aplica el paso 3.   

3. El paso 3 solo se aplica si se produce un error en el paso 2. 

   Quite la parte del host del FQDN, que se muestra en el encabezado de contacto (FQDN: sbc12.adatum.biz, después de quitar la parte de host: adatum.biz) y compruebe si este nombre está registrado como nombre DNS en cualquier microsoft 365 o Office 365 organización. Si se encuentra, la búsqueda de usuarios se realiza en este espacio empresarial. Si no se encuentra, se produce un error en la llamada.

4. Con el número de teléfono que se muestra en el URI de solicitud, realice la búsqueda de número inverso dentro del espacio empresarial que se encontró en los pasos 2 o 3. Haga coincidir el número de teléfono presentado con un URI sip de usuario dentro del espacio empresarial que se encontró en el paso anterior.

5. Aplicar la configuración de tronco. Busque los parámetros establecidos por el administrador de inquilinos para este SBC.

   Microsoft no admite tener un proxy SIP o servidor de agente de usuario de terceros entre el proxy SIP de Microsoft y el SBC emparejado, que podría modificar el URI de solicitud creado por el SBC emparejado.

   Los requisitos para las dos búsquedas (pasos 2 y 3) necesarios para el escenario donde un SBC está interconectado a muchos inquilinos (escenario de operador) se tratan más adelante en este artículo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisitos detallados para el encabezado de contacto y el URI de solicitud

#### <a name="contact-header"></a>Encabezado de contacto

Para todos los mensajes SIP entrantes (OPCIONES, INVITAR) al proxy SIP de Microsoft, el encabezado de contacto debe tener el FQDN SBC emparejado en el nombre de host URI de la manera siguiente:

Sintaxis: Contacto: <sip:phone o sip address@FQDN de SBC;transport=tls> 

Como se indica en [RFC 3261, sección 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), un campo de encabezado de contacto puede estar presente en un mensaje OPTIONS. En Enrutamiento directo, el encabezado de contacto es obligatorio. Para los mensajes DE INVITACIÓN en formato anterior, para los mensajes OPTIONS, el userinfo se puede quitar del URI del SIP y solo el FQDN enviado en formato como sigue:

Sintaxis: Contacto: <sip:FQDN del> SBC;transport=tls

Este nombre (FQDN) también debe estar en los campos Nombre común o Nombre alternativo del asunto del certificado presentado. Microsoft admite el uso de valores comodín de los nombres en los campos Nombre común o Nombre alternativo del asunto del certificado.   

La compatibilidad con caracteres comodín se describe en [RFC 2818, sección 3.1](https://tools.ietf.org/html/rfc2818#section-3.1). Específicamente:

*"Los nombres pueden contener el carácter \* comodín que se considera que coincide con cualquier componente de nombre de dominio o fragmento de componente. Por ejemplo, \*las coincidencias de .a.com foo.a.com pero no bar.foo.a.com. f.com\* coinciden foo.com pero no bar.com".*

Si el SBC envía más de un valor en el encabezado de contacto presentado en un mensaje SIP, solo se usa la parte FQDN del primer valor del encabezado de contacto.

Como regla general para el enrutamiento directo, es importante que el FQDN se utilice para rellenar el URI del SIP en lugar de IP. Un mensaje de INVITACIÓN u OPCIONES entrante a proxy SIP con encabezado de contacto donde el nombre de host se representa mediante IP y no FQDN, la conexión se rechazará con 403 Forbidden.

#### <a name="request-uri"></a>Request-URI 

Para todas las llamadas entrantes, el URI de solicitud se usa para hacer coincidir el número de teléfono con un usuario.   

Actualmente, el número de teléfono debe contener un signo más (+) como se muestra en el ejemplo siguiente. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>Desde encabezado

Para todas las llamadas entrantes, el encabezado De se usa para hacer coincidir el número de teléfono del autor de la llamada con la lista de números de teléfono bloqueados del destinatario de la llamada.

El número de teléfono debe contener un signo + como se muestra en el ejemplo siguiente.

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>Consideraciones de encabezados de Record-Route y contactos

El proxy SIP debe calcular el FQDN del próximo salto para las nuevas transacciones de cliente del cuadro de diálogo (por ejemplo, Bye o Re-Invite) y al responder a las opciones sip. Se usan Contacto o Record-Route. 

Según [RFC 3261, sección 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), el encabezado de contacto es obligatorio en cualquier solicitud que pueda dar lugar a un nuevo cuadro de diálogo. El Record-Route solo es necesario si un proxy quiere mantenerse en la ruta de las solicitudes futuras de un cuadro de diálogo. Si se está usando un SBC de proxy con [optimización de medios locales para el enrutamiento directo](./direct-routing-media-optimization.md), será necesario configurar una ruta de registro, ya que el servidor proxy SBC debe permanecer en la ruta. 

Microsoft recomienda usar solo el encabezado Contacto si no se usa un SBC de proxy:

- Por [RFC 3261, sección 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route se usa si un proxy quiere permanecer en la ruta de las solicitudes futuras en un cuadro de diálogo, lo que no es esencial si no se configura ningún proxy SBC, ya que todo el tráfico va entre el proxy SIP de Microsoft y el SBC emparejado. 

- El proxy SIP de Microsoft utiliza solamente el encabezado del contacto (no record-route) para determinar el salto siguiente al enviar las opciones de ping salientes. Configurar solamente un parámetro (contacto) en lugar de dos (contacto y ruta de registro) simplifica la administración si un proxy SBC no está en uso. 

Para calcular el próximo salto, el proxy SIP utiliza:

- Prioridad 1. Ruta de registro de nivel superior. Si la Record-Route de nivel superior contiene el nombre fqdn, el nombre fqdn se usa para realizar la conexión saliente en el cuadro de diálogo.

- Prioridad 2. Encabezado de contacto. Si Record-Route no existe, el proxy SIP buscará el valor del encabezado de contacto para realizar la conexión saliente. (Esta es la configuración recomendada).

Si se usan Contact y Record-Route, el administrador de SBC debe mantener sus valores idénticos, lo que causa una sobrecarga administrativa. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso de nombre FQDN en Contacto o Record-Route

El uso de una dirección IP no se admite en Record-Route ni en Contacto. La única opción compatible es un FQDN, que debe coincidir con el nombre común o el nombre alternativo del asunto del certificado SBC (se admiten valores comodín en el certificado).

- Si se presenta una dirección IP en Ruta de registro o Contacto, se produce un error en la comprobación del certificado y se produce un error en la llamada.

- Si el FQDN no coincide con el valor del nombre alternativo del asunto o común en el certificado presentado, se produce un error en la llamada. 

## <a name="inbound-call-sip-dialog-description"></a>Llamada entrante: descripción del cuadro de diálogo SIP

En la tabla siguiente se resumen las diferencias y similitudes entre los modos de no omisión y de omisión:

| Nombre del parámetro | Modo sin omisión | Modo de omisión
| :---------------------  |:---------------------- |:----------------|
| Candidatos a medios en 183 y 200 mensajes procedentes de | Procesadores multimedia | Clientes | 
| Número de 183 mensajes que puede recibir SBC | Uno por sesión | Múltiples | 
| La llamada puede ser con respuesta provisional (183) | Sí | Sí |
| La llamada puede ser sin respuesta provisional (183) | Sí | Sí |

###  <a name="non-media-bypass-flow"></a>Flujo de omisión no multimedia

Un usuario de Teams puede tener varios puntos de conexión al mismo tiempo. Por ejemplo, Teams para el cliente de Windows, Teams para el cliente de iPhone y Teams Phone (cliente de Teams para Android). Cada punto de conexión podría indicar un descanso HTTP de la siguiente manera:

-   Progreso de la llamada – convertido por el proxy SIP al mensaje SIP 180. Al recibir el mensaje 180, el SBC debe generar llamada local.

-   Respuesta multimedia: convertida por el proxy SIP al mensaje 183 con candidatos multimedia en el Protocolo de descripción de sesión (SDP). Al recibir el mensaje 183, el SBC espera conectarse a los candidatos de medios recibidos en el mensaje SDP. 

    > [!NOTE]
    > En algunos casos, es posible que no se genere la respuesta multimedia y que el punto final responda con el mensaje "Llamada aceptada".

-   Llamada aceptada – convertida por el proxy SIP al mensaje SIP 200 con SDP. Al recibir el mensaje 200, se espera que el SBC envíe y reciba medios hacia y desde los candidatos de SDP proporcionados.

    > [!NOTE]
    > Enrutamiento directo no admite invitación a oferta retrasada (invitación sin SDP).

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Varios puntos de conexión sonando con respuesta provisional

1.  Al recibir la primera invitación del SBC, el proxy SIP envía el mensaje "SIP SIP/2.0 100 Trying" y notifica a todos los puntos de conexión del usuario final sobre la llamada entrante. 

2.  Tras la notificación, cada punto de conexión empezará a llamar y enviar mensajes de "Progreso de llamada" al proxy SIP. Como un usuario de Teams puede tener varios puntos de conexión, el proxy SIP podría recibir varios mensajes de progreso de llamada.

3.  Para cada mensaje de progreso de llamada recibido de los clientes, el proxy SIP convierte el mensaje del progreso de la llamada al mensaje del SIP "SIP SIP/2.0 180 ringing". El intervalo para enviar estos mensajes se define por el intervalo de recepción de mensajes del controlador de llamada. En el siguiente diagrama, hay dos 180 mensajes generados por el proxy SIP. Estos mensajes proceden de los dos puntos de conexión de Teams del usuario. Los clientes tienen un id. de etiqueta único.  Todos los mensajes procedentes de un punto de conexión diferente serán una sesión independiente (la "etiqueta" del parámetro en el campo "Para" será diferente). Pero es posible que un punto de conexión no genere el mensaje 180 y envíe el mensaje 183 inmediatamente, como se muestra en el siguiente diagrama.

4.  Una vez que un punto de conexión genera un mensaje de respuesta multimedia con las direcciones IP de los candidatos multimedia del punto de conexión, el proxy SIP convierte el mensaje recibido en un mensaje "Progreso de sesión SIP 183" con el SDP del cliente reemplazado por el SDP del procesador multimedia. En el siguiente diagrama, el punto de conexión de Bifurcación 2 respondió a la llamada. Si el trunk es non-bypassed, el mensaje del SIP 183 se genera solamente una vez (anillar bot o punto final del cliente). El 183 podría venir en una bifurcación existente o iniciar una nueva.

5.  Se envía un mensaje de Aceptación de llamada con los candidatos finales del punto de conexión que ha aceptado la llamada. El mensaje aceptación de llamadas se convierte en mensaje SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando con respuesta provisional.](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Varios puntos de conexión sonando sin respuesta provisional

1.  Al recibir la primera invitación del SBC, el proxy SIP envía el mensaje "SIP SIP/2.0 100 Trying" y notifica a todos los puntos de conexión del usuario final sobre la llamada entrante. 

2.  Tras la notificación, cada punto de conexión empezará a sonar y enviará el mensaje "Progreso de la llamada" al proxy SIP. Como un usuario de Teams puede tener varios puntos finales, el proxy SIP podría recibir varios mensajes de progreso de llamada.

3.  Para cada mensaje de progreso de llamada recibido de los clientes, el proxy SIP convierte el mensaje del progreso de la llamada al mensaje del SIP "SIP SIP/2.0 180 trying".  El intervalo para enviar los mensajes se define por el intervalo de recepción de los mensajes del controlador de llamada. En la imagen siguiente hay dos 180 mensajes generados por el proxy SIP, lo que significa que el usuario inició sesión en tres clientes de Teams y cada cliente envía el progreso de la llamada. Cada mensaje será una sesión independiente (el parámetro "tag" en el campo "Para" es diferente)

4.  Se envía un mensaje de Aceptación de llamada con los candidatos finales del punto de conexión que ha aceptado la llamada. El mensaje aceptación de llamadas se convierte en mensaje SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión que suenan sin respuesta provisional.](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flujo de omisión de medios

Los mismos mensajes (100 intentos, 180, 183) se usan en el escenario de omisión multimedia. 

El esquema siguiente muestra un ejemplo del flujo de llamada de omisión. 

> [!NOTE]
> Los candidatos a medios pueden proceder de diferentes puntos de conexión. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando con respuesta provisional.](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opción Reemplazar

El SBC debe admitir La invitación con reemplazos.

## <a name="size-of-sdp-considerations"></a>Tamaño de consideraciones de SDP

La interfaz de enrutamiento directo pudo enviar un mensaje SIP que exceda 1,500 bytes.  El tamaño del SDP causa principalmente esto. Sin embargo, si hay un tronco UDP detrás del SBC, podría rechazar el mensaje si se reenvía del proxy SIP de Microsoft al tronco sin modificar. Microsoft recomienda quitar algunos valores en SDP en el SBC al enviar el mensaje a los troncos UDP. Por ejemplo, se pueden quitar los candidatos de ICE o los códecs sin usar.

## <a name="call-transfer"></a>Transferencia de llamada

Enrutamiento directo admite dos métodos para la transferencia de llamadas:

- Opción 1. Procesos del proxy SIP Refiera del cliente localmente y actúa como árbitro tal y como se describe en la sección 7.1 del RFC 3892.

  Con esta opción, el proxy SIP finaliza la transferencia y agrega una nueva invitación. 


- Opción 2. El proxy SIP envía la referencia al SBC y actúa como transferor como describe en la sección 6 de RFC 5589.

  Con esta opción, el proxy SIP envía una referencia al SBC y espera el SBC manejar la transferencia completamente.

El proxy SIP selecciona el método basado en las capacidades notificadas por el SBC. Si el SBC indica que soporta el método "Refer", el proxy SIP usará la opción 2 para las transferencias de llamadas.

El siguiente es un ejemplo de un SBC que envía el mensaje que indica que el método Refer es compatible:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Si el SBC no indica que Refer as a supported method, Direct Routing usará la opción 1 (proxy SIP actúa como árbitro). El SBC también debe indicar que admite el método Notify:

Ejemplo de SBC que indica que no se admite el método Refer:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Procesos del proxy SIP Referir desde el cliente localmente y actúa como árbitro

Si el SBC indica que el método Refer no es compatible, el proxy SIP actúa como árbitro. 

La petición de referencia que viene del cliente se terminará en el proxy DEL SIP. (La petición de referencia del cliente se muestra como "Transferencia de llamada a Dave" en el siguiente diagrama.  Para obtener más información, vea la sección 7.1 de [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando con respuesta provisional.](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>El proxy SIP envía la referencia al SBC y actúa como transferibler

Este es el método preferido para las transferencias de llamadas y es obligatorio para los dispositivos que buscan la certificación de omisión multimedia. Transferencia de llamadas sin que el SBC pueda manejar La referencia no se admite en el modo de omisión de medios. 

El estándar se explica en la sección 6 de RFC 5589. Las RFCs relacionadas son:

- [Control de llamadas del Protocolo de inicio de sesión (SIP): transferencia](https://tools.ietf.org/html/rfc5589)

- [Encabezado "Reemplaza" del Protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3891)

- [Mecanismo "Referido por" del Protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3892)

Esta opción asume que el proxy SIP actúa como transferibler y envía un mensaje de referencia al SBC. El SBC actúa como Cesionario y maneja la Referencia para generar una nueva oferta para transferencia. Hay dos casos posibles:

- La llamada se transfiere a un participante de RTC externo. 
- La llamada se transfiere de un usuario de Teams a otro usuario de Teams en el mismo espacio empresarial a través de SBC. 

Si la llamada se transfiere de un usuario de Teams a otro a través del SBC, se espera que el SBC emita una nueva invitación (iniciar un nuevo cuadro de diálogo) para el destino de transferencia (el usuario de Teams) con la información recibida en el mensaje De referencia. 

Para rellenar los campos To/Transferor para la transacción de la solicitud internamente, el proxy SIP necesita transmitir esta información dentro de los encabezados REFER-TO/REFERRED-BY. 

El proxy SIP formará el REFER-TO como UN URI sip compuesto por un FQDN de proxy SIP en el nombre de host y cualquiera de los siguientes:

- Un número de teléfono E.164 en la parte de nombre de usuario del URI en caso de que el destino de la transferencia sea un número de teléfono, o

- Parámetros x-m y x-t que codifican la MRI de destino de transferencia completa y el id. de inquilino respectivamente 

El encabezado REFERRED-BY es un URI SIP con MRI transferor codificado en él, así como id. del inquilino transferor y otros parámetros de contexto de transferencia como se muestra en la tabla siguiente:

| Parámetro | Valor | Descripción |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | Mri | RMN completa del transferor/destino de transferencia tal y como se rellena con CC |
| x-t | ID. del espacio empresarial | x-t Id. de espacio empresarial opcional rellenado por CC |
| x-ti | Id. de correlación de transferor | Id. de correlación de la llamada al transferibler |
| x-tt | URI de llamada de destino de transferencia | URI de reemplazo de llamada codificado |

El tamaño del encabezado de referencia puede ser de hasta 400 símbolos en este caso. El SBC debe admitir el control De referencia de mensajes con un tamaño de hasta 400 símbolos.

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando con respuesta provisional.](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Temporizador de sesión

El proxy SIP admite (siempre ofrece) el temporizador de sesión en llamadas que no son de derivación, pero no lo ofrece en las llamadas de omisión. El uso del temporizador de sesión por el SBC no es obligatorio.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso del parámetro Request-URI user=phone

El proxy SIP analiza el URI de solicitud y, si el parámetro user=phone está presente, el servicio administrará el URI de solicitud como un número de teléfono, haciendo coincidir el número con un usuario. Si el parámetro no está presente, el proxy SIP aplica heurística para determinar el tipo de usuario request-URI (número de teléfono o una dirección SIP).

Microsoft recomienda aplicar siempre el parámetro user=phone para simplificar el proceso de configuración de la llamada.

## <a name="history-info-header"></a>encabezado de History-Info

El encabezado History-Info se usa para volver a dirigir solicitudes SIP y "proporcionar(s) un mecanismo estándar para capturar la información del historial de solicitudes con el fin de habilitar una amplia variedad de servicios para redes y usuarios finales". Para obtener más información, vea [RFC 4244: sección 1.1](http://www.ietf.org/rfc/rfc4244.txt). Para Microsoft Phone System, este encabezado se usa en escenarios de Desvío de llamadas y Desenlazamiento de llamadas.  

Si se envía, el History-Info se habilita de la siguiente manera:

- El proxy SIP insertará un parámetro que contiene el número de teléfono asociado en entradas de History-Info individuales que comprenden el encabezado de History-Info enviado al controlador RTC.  Usando solamente las entradas que tienen el parámetro del número de teléfono, el regulador RTC reconstruirá un nuevo encabezado de History-Info, y lo pasará al proveedor del tronco SIP vía el proxy SIP.

- History-Info encabezado se agregará para casos de llamada simultánea y desvío de llamadas.

- History-Info encabezado no se agregará para los casos de transferencia de llamadas.

- Una entrada del historial individual en el encabezado de History-Info reconstruido tendrá el parámetro de número de teléfono proporcionado combinado con el FQDN de enrutamiento directo (sip.pstnhub.microsoft.com) establecido como la parte host del URI; se agregará un parámetro de "user=phone" como parte del URI del SIP.  Cualquier otro parámetro asociado con el encabezado de History-Info original, excepto los parámetros de contexto del teléfono, se pasará por el encabezado History-Info reconstruido.  

  > [!NOTE]
  > Las entradas que son privadas (según determinen los mecanismos definidos en la sección 3.3 de RFC 4244) se reenviarán tal y como está porque el proveedor del tronco SIP es un peer de confianza.

- Se omiten los History-Info entrantes.

A continuación se muestra el formato del encabezado History-info enviado por el proxy SIP:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Si la llamada se redirigió varias veces, la información sobre cada redirección se incluye con la razón apropiada en orden cronológico.


Ejemplo de encabezado:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

El History-Info está protegido por un mecanismo TLS obligatorio. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Conexión SBC a enrutamiento directo y mecanismo de conmutación por error

Consulte la sección Mecanismo de conmutación por error para la señalización SIP en [Planear el enrutamiento directo](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Retry-After

Si un centro de datos de enrutamiento directo está ocupado, el servicio puede enviar un mensaje de Retry-After con un intervalo de un segundo a la SBC. Cuando el SBC recibe un mensaje 503 con un encabezado de Retry-After en respuesta a una INVITACIÓN, el SBC debe finalizar esa conexión y probar el siguiente centro de datos de Microsoft disponible.

## <a name="handling-retries-603-response"></a>Control de reintentos (respuesta 603)
Si un usuario final observa varias llamadas perdidas para una llamada después de rechazar la llamada entrante, significa que el mecanismo de reintento del proveedor de tronco RTC o SBC está mal configurado. Es necesario volver a configurar el SBC para detener los esfuerzos de reintento en la respuesta 603.

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Reinicio de ICE: llamada de omisión de medios transferida a un punto de conexión que no admite omisión multimedia

El SBC debe admitir reinicios de ICE como se describe en [RFC 5245, sección 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

El reinicio en enrutamiento directo se implementa de acuerdo con los siguientes párrafos de RFC:

*Para reiniciar ICE, un agente DEBE cambiar tanto el ice-pwd como el ice-ufrag para el flujo de medios en una oferta.  Tenga en cuenta que es permisible utilizar un atributo de nivel de sesión en una oferta, pero proporcionar el mismo ice-pwd o ice-ufrag como un atributo de nivel de medios en una oferta posterior.  No se trata de un cambio en la contraseña, solo un cambio en su representación y no provoca un reinicio de ICE.*

*Un agente establece el resto de los campos en el SDP para esta transmisión multimedia como lo haría en una oferta inicial de esta transmisión multimedia (consulte la sección 4.3).  Por consiguiente, el conjunto de candidatos PUEDE incluir algunos, ninguno o todos los candidatos anteriores para esa transmisión y PUEDE incluir un conjunto totalmente nuevo de candidatos recopilados como se describe en la sección 4.1.1.*

Si la llamada se estableció inicialmente con omisión de medios y la llamada se transfiere a un cliente de Skype for Business, el enrutamiento directo debe insertar un procesador multimedia; esto se debe a que el enrutamiento directo no se puede usar con un cliente de Skype for Business con omisión multimedia. Direct Routing inicia el proceso de reinicio de ICE cambiando el ice-pwd y el ice-ufrag y ofreciendo nuevos candidatos de medios en un revite.
