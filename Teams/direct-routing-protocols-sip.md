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
ms.openlocfilehash: 4fe636029c3a058dc1a8d33cc191d7654888ec5e
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278730"
---
# <a name="direct-routing---sip-protocol"></a>Enrutamiento directo - protocolo SIP

En este artículo se describe cómo el enrutamiento directo implementa el Protocolo de inicio de sesión (SIP). Para enrutar correctamente el tráfico entre un controlador de borde de sesión (SBC) y el proxy SIP, algunos parámetros SIP deben tener valores específicos. Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el SBC local y el servicio de proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Procesando la solicitud entrante: buscar el inquilino y el usuario

Antes de que se pueda procesar una llamada entrante o saliente, los mensajes OPCIONES se intercambian entre proxy SIP y SBC. Estos mensajes DE OPCIONES permiten que el proxy SIP proporcione las capacidades permitidas a SBC. Es importante que la negociación OPCIONES tenga éxito (respuesta 200OK), lo que permite una mayor comunicación entre SBC y proxy SIP para establecer llamadas. Los encabezados SIP de los mensajes OPCIONES para proxy SIP se proporcionan como ejemplo a continuación:

| Nombre del parámetro | Ejemplo del valor | 
| :---------------------  |:---------------------- |
| Request-URI | OPCIONES sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| A través del encabezado | A través de: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards encabezado | Reenvíos máximos:68 |
| Desde el encabezado | Desde el encabezado de: <sip:sbc1.adatum.biz:5058> |
| Al encabezado | Para: <sip:sip.pstnhub.microsoft.com:5061> |
| Encabezado CSeq | CSeq: 1 INVITACIÓN | 
| Encabezado de contacto | Contacto: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Los encabezados SIP no contienen información del usuario en el URI del SIP en uso. De acuerdo con [RFC 3261, sección 19.1.1,](https://tools.ietf.org/html/rfc3261#section-19.1.1)la parte de información del usuario de un URI es opcional y puede estar ausente cuando el host de destino no tiene una noción de usuarios o cuando el recurso que se identifica es el recurso en sí. Si el signo @ está presente en un URI del SIP, el campo de usuario NO DEBE estar vacío.

En una llamada entrante, el proxy SIP necesita buscar el inquilino al que se destina la llamada y encontrar el usuario específico dentro de este inquilino. El administrador de inquilinos puede configurar números que no son DID (por ejemplo, +1001) en varios inquilinos. Por lo tanto, es importante encontrar el espacio empresarial específico en el que realizar la búsqueda de números porque los números que no son DID pueden ser los mismos en varias organizaciones de Microsoft 365 u Office 365.  

Esta sección describe cómo el proxy SIP encuentra el inquilino y el usuario, y realiza la autenticación de la SBC en la conexión entrante.

A continuación se muestra un ejemplo del mensaje de invitación SIP en una llamada entrante:

| Nombre del parámetro | Ejemplo del valor | 
| :---------------------  |:---------------------- |
| Request-URI | INVITAR sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| A través del encabezado | A través de: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards encabezado | Reenvíos máximos:68 |
| Desde el encabezado | Desde el encabezado de: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| Al encabezado | Para: sip:+183338006777@sbc1.adatum.biz | 
| Encabezado CSeq | CSeq: 1 INVITACIÓN | 
| Encabezado de contacto | Contacto: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Al recibir la invitación, el proxy SIP realiza los siguientes pasos:

1. Compruebe el certificado. En la conexión inicial, el servicio de enrutamiento directo toma el nombre FQDN que se muestra en el encabezado de contacto y lo coincide con el nombre común o el nombre alternativo del asunto del certificado presentado. El nombre de SBC debe coincidir con una de las siguientes opciones:

   - Opción 1. El nombre completo del FQDN que se presenta en el encabezado de contacto debe coincidir con el nombre común/asunto alternativo del certificado presentado.  

   - Opción 2. La parte del dominio del nombre FQDN que se muestra en el encabezado de contacto (por ejemplo adatum.biz del nombre de FQDN sbc1.adatum.biz) debe coincidir con el valor comodín de Nombre común/Asunto nombre alternativo (por ejemplo *.adatum.biz).

2. Intente buscar un inquilino con el nombre completo del FQDN que se muestra en el encabezado de contacto.  

   Compruebe si el nombre FQDN del encabezado de contacto (sbc1.adatum.biz) está registrado como nombre DNS en cualquier organización de Microsoft 365 u Office 365. Si se encuentra, la búsqueda del usuario se realiza en el espacio empresarial que tiene el FQDN de SBC registrado como nombre de dominio. Si no se encuentra, se aplica el paso 3.   

3. El paso 3 solo se aplica si el paso 2 falla. 

   Quite la parte de host del FQDN, que se muestra en el encabezado de contacto (FQDN: sbc12.adatum.biz, después de quitar la parte de host: adatum.biz) y compruebe si este nombre está registrado como nombre DNS en cualquier organización de Microsoft 365 u Office 365. Si se encuentra, la búsqueda de usuarios se realiza en este espacio empresarial. Si no se encuentra, se produce un error en la llamada.

4. Con el número de teléfono presentado en el URI de solicitud, realice la búsqueda inversa de números dentro del espacio empresarial que se encontró en los pasos 2 o 3. Hacer coincidir el número de teléfono presentado con un URI del SIP del usuario dentro del espacio empresarial que se encontró en el paso anterior.

5. Aplique la configuración de tronco. Busque los parámetros establecidos por el administrador de inquilinos para este SBC.

   Microsoft no admite tener un proxy SIP de terceros o un servidor de agente de usuario entre el proxy SIP de Microsoft y el SBC emparejado, lo que podría modificar el URI de solicitud creado por la SBC emparejada.

   Los requisitos para las dos búsquedas (pasos 2 y 3) necesarios para el escenario en el que un SBC está interconectado con muchos inquilinos (escenario de operadores) se tratan más adelante en este artículo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisitos detallados para el encabezado de contacto y el URI de solicitud

#### <a name="contact-header"></a>Encabezado de contacto

Para todos los mensajes SIP entrantes (OPCIONES, INVITAR) al proxy SIP de Microsoft, el encabezado del contacto debe tener el FQDN de SBC emparejado en el nombre de host URI de la siguiente manera:

Sintaxis: Contacto: <sip:phone o sip address@FQDN de la SBC;transport=tls> 

Según [RFC 3261, sección 11.1,](https://tools.ietf.org/html/rfc3261#section-11.1)puede haber un campo de encabezado de contacto en un mensaje DE OPCIONES. En Enrutamiento directo es necesario el encabezado de contacto. Para los mensajes INVITAR en formato anterior, para los mensajes OPCIONES el info. usuario se puede quitar del URI del SIP y solo se puede enviar FQDN en formato como se muestra a continuación:

Sintaxis: Contacto: <sip:FQDN de la cadena SBC;transport=tls>

Este nombre (FQDN) también debe estar en los campos Nombre común o Nombre alternativo del certificado presentado. Microsoft admite el uso de valores comodín de los nombres en los campos Nombre común o Nombre alternativo del asunto del certificado.   

La compatibilidad con los caracteres comodín se describe [en RFC 2818, sección 3.1.](https://tools.ietf.org/html/rfc2818#section-3.1) En concreto:

*"Los nombres pueden contener el carácter comodín que se considera que coincide con cualquier componente o componente de un nombre \* de dominio único. Por ejemplo, .a.com coincide foo.a.com pero no bar.foo.a.com. f.com coincide con \* foo.com pero no \* bar.com".*

Si la SBC envía más de un valor en el encabezado de contacto que aparece en un mensaje SIP, solo se utiliza la parte del FQDN del primer valor del encabezado de contacto.

Como regla general del enrutamiento directo, es importante que se utilice FQDN para rellenar uri de SIP en lugar de IP. Un mensaje entrante INVITAR u OPCIONES al proxy SIP con encabezado de contacto donde el nombre de host está representado por IP y no FQDN, la conexión se rechazará con 403 Prohibido.

#### <a name="request-uri"></a>Request-URI 

Para todas las llamadas entrantes, el URI de solicitud se usa para hacer coincidir el número de teléfono con un usuario.   

Actualmente, el número de teléfono debe contener un signo más (+), tal y como se muestra en el ejemplo siguiente. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Consideraciones sobre los Record-Route contacto y los encabezados de página

El proxy SIP necesita calcular el FQDN del próximo salto para las nuevas transacciones del cliente en el cuadro de diálogo (por ejemplo, Bye o Re-Invite) y al responder a opciones SIP. Se usan las Record-Route contacto o las Record-Route contactos. 

Según [RFC 3261, sección 8.1.1.8,](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)el encabezado de contacto es necesario en cualquier solicitud que puede dar como resultado un nuevo cuadro de diálogo. La Record-Route es necesaria si un proxy desea permanecer en la ruta de acceso a solicitudes futuras en un cuadro de diálogo. Si un SBC proxy está en uso con la optimización de medios locales para enrutamiento [directo,](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)se tendrá que configurar una ruta de registro ya que el SBC del proxy debe permanecer en la ruta. 

Microsoft recomienda usar solo el encabezado de contacto si no se usa un SBC proxy:

- Por [RFC 3261, sección 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route se usa si un proxy quiere seguir la ruta de solicitudes futuras en un cuadro de diálogo, lo que no es esencial si no se configura SBC del proxy ya que todo el tráfico pasa entre el proxy SIP de Microsoft y el SBC emparejado. 

- El proxy SIP de Microsoft solo usa el encabezado de contacto (no Record-Route) para determinar el próximo salto al enviar opciones de ping salientes. Configurar solo un parámetro (Contacto) en lugar de dos (Contacto y Ruta de registro) simplifica la administración si no está en uso un SBC proxy. 

Para calcular el próximo salto, el proxy SIP usa:

- Prioridad 1. Ruta de registro de nivel superior. Si el nombre de nivel Record-Route contiene el nombre de FQDN, el nombre de FQDN se usa para realizar la conexión saliente en el cuadro de diálogo.

- Prioridad 2. Encabezado de contacto. Si Record-Route no existe, el proxy SIP buscará el valor del encabezado de contacto para realizar la conexión saliente. (Esta es la configuración recomendada).

Si se usan tanto contactos como Record-Route, el administrador de SBC debe mantener sus valores idénticos, lo que provoca una sobrecarga administrativa. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso del nombre FQDN en Contacto o Record-Route

El uso de una dirección IP no se admite en el servicio Record-Route o contacto. La única opción admitida es un FQDN, que debe coincidir con el nombre común o el nombre alternativo del asunto del certificado SBC (se admiten los valores comodín del certificado).

- Si se presenta una dirección IP en La ruta del registro o contacto, la comprobación del certificado produce errores y la llamada produce errores.

- Si el FQDN no coincide con el valor del nombre alternativo Común o Asunto en el certificado presentado, se produce un error en la llamada. 

## <a name="inbound-call-sip-dialog-description"></a>Llamada entrante: descripción del cuadro de diálogo SIP

La siguiente tabla resume las diferencias y similitudes entre los modos de no omisión y omisión:

| Nombre del parámetro | Modo de no omisión | Modo de omisión
| :---------------------  |:---------------------- |:----------------|
| Candidatos multimedia en 183 y 200 mensajes procedentes de | Procesadores multimedia | Clientes | 
| Número de 183 mensajes que puede recibir SBC | Uno por sesión | Múltiplo | 
| La llamada puede tener respuesta provisional (183) | Sí | Sí |
| La llamada puede no tener respuesta provisional (183) | Sí | Sí |

###  <a name="non-media-bypass-flow"></a>Flujo de omisión no multimedia

Un usuario de Teams puede tener varios puntos de conexión al mismo tiempo. Por ejemplo, El cliente de Teams para Windows, Teams para iPhone y Teams Phone (cliente de Teams para Android). Cada punto de conexión podría indicar un reposo HTTP de la siguiente manera:

-   Progreso de la llamada: convertido por el proxy SIP en el mensaje SIP 180. Al recibir el mensaje 180, la SBC debe generar una llamada local.

-   Respuesta multimedia: convertida por el proxy SIP en el mensaje 183 con candidatos a medios en el Protocolo de descripción de sesión (SDP). Al recibir el mensaje 183, el SBC espera conectarse a los medios candidatos recibidos en el mensaje SDP. 

    > [!NOTE]
    > En algunos casos, es posible que no se genere la respuesta multimedia y que el punto final responda con el mensaje "Llamada aceptada".

-   Llamada aceptada: convertida por el proxy SIP en el mensaje SIP 200 con SDP. Al recibir el mensaje 200, se espera que SBC envíe y reciba medios a los candidatos del SDP proporcionados.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Varios puntos de conexión sonando con respuesta provisional

1.  Al recibir la primera invitación del SBC, el proxy SIP envía el mensaje "SIP SIP/2.0 100 Trying" (SIP SIP/2.0 100 Trying) y notifica a todos los puntos de conexión del usuario final acerca de la llamada entrante. 

2.  Tras la notificación, cada punto de conexión comenzará a sonar y a enviar mensajes de "Progreso de la llamada" al proxy SIP. Como un usuario de Teams puede tener varios puntos de conexión, el proxy SIP podría recibir varios mensajes de progreso de la llamada.

3.  Por cada mensaje de progreso de la llamada recibido de los clientes, el proxy SIP convierte el mensaje de progreso de la llamada en el mensaje SIP "SIP/2.0 180 Trying". El intervalo para enviar estos mensajes se define por el intervalo de los mensajes recibidos desde el controlador de llamada. En el siguiente diagrama, hay dos 180 mensajes generados por el proxy SIP. Estos mensajes proceden de los dos puntos de conexión de Teams del usuario. Cada uno de los clientes tiene un id. de etiqueta único.  Cada mensaje procedente de un punto de conexión diferente será una sesión independiente (el parámetro "tag" del campo "Para" será diferente). Pero es posible que un punto de conexión no genere el mensaje 180 y envíe el mensaje 183 inmediatamente como se muestra en el siguiente diagrama.

4.  Una vez que un punto de conexión genera un mensaje de Respuesta multimedia con las direcciones IP de los candidatos multimedia del punto de conexión, el proxy SIP convierte el mensaje recibido en un mensaje "Progreso de sesión SIP 183" con el SDP del cliente reemplazado por el SDP desde el procesador de medios. En el siguiente diagrama, el punto de conexión de bifurcación 2 ha respondido a la llamada. Si el tronco no se omite, el mensaje SIP 183 solo se genera una vez (anillo bot o punto final del cliente). La 183 podría venir en una bifurcación existente o iniciar una nueva.

5.  Se envía un mensaje de aceptación de llamada con los candidatos finales del punto de conexión que ha aceptado la llamada. El mensaje aceptación de la llamada se convierte en mensaje SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando con respuesta provisional](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Varios puntos de conexión sonando sin respuesta provisional

1.  Al recibir la primera invitación del SBC, el proxy SIP envía el mensaje "SIP SIP/2.0 100 Trying" (SIP SIP/2.0 100 Trying) y notifica a todos los puntos de conexión del usuario final acerca de la llamada entrante. 

2.  Tras la notificación, cada punto de conexión comenzará a sonar y a enviar el mensaje "Progreso de la llamada" al proxy SIP. Como un usuario de Teams puede tener varios puntos de conexión, el proxy SIP podría recibir varios mensajes de progreso de la llamada.

3.  Por cada mensaje de progreso de la llamada recibido de los clientes, el proxy SIP convierte el mensaje de progreso de la llamada en el mensaje SIP "SIP/2.0 180 Trying".  El intervalo para enviar los mensajes se define por el intervalo de recepción de los mensajes desde el controlador de llamada. En la imagen siguiente hay dos 180 mensajes generados por el proxy SIP, lo que significa que el usuario inició sesión en tres clientes de Teams y cada cliente envía el progreso de la llamada. Cada mensaje será una sesión independiente (el parámetro "etiqueta" del campo "Para" es diferente)

4.  Se envía un mensaje de aceptación de llamada con los candidatos finales del punto de conexión que ha aceptado la llamada. El mensaje aceptación de la llamada se convierte en mensaje SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando sin respuesta provisional](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flujo de omisión de medios

En el escenario de omisión de medios se usan los mismos mensajes (100 Trying, 180, 183). 

El esquema siguiente muestra un ejemplo del flujo de llamadas de omisión. 

> [!NOTE]
> Los candidatos a medios pueden venir de distintos puntos de conexión. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando con respuesta provisional](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opción De reemplazo

La SBC debe admitir la invitación con sustituciones.

## <a name="size-of-sdp-considerations"></a>Tamaño de las consideraciones del SDP

La interfaz de enrutamiento directo puede enviar un mensaje SIP que supere los 1.500 bytes.  El tamaño de SDP provoca principalmente esto. Sin embargo, si hay un tronco UDP detrás de la SBC, es posible que rechace el mensaje si se reenvía desde el proxy SIP de Microsoft al tronco sin modificar. Microsoft recomienda eliminar algunos valores en SDP en el SBC al enviar el mensaje a los troncos UDP. Por ejemplo, los candidatos de ICE o los códecs sin usar se pueden quitar.

## <a name="call-transfer"></a>Transferencia de llamadas

El enrutamiento directo admite dos métodos para la transferencia de llamadas:

- Opción 1. Los procesos de proxy SIP se refieren localmente al cliente y actúan como árbitro, tal y como se describe en la sección 7.1 de RFC 3892.

  Con esta opción, el proxy SIP finaliza la transferencia y agrega una nueva invitación. 


- Opción 2. El proxy SIP envía la referencia a la SBC y actúa como transferor como se describe en la sección 6 de RFC 5589.

  Con esta opción, el proxy SIP envía un refer a la SBC y espera que SBC controle la transferencia por completo.

El proxy SIP selecciona el método en función de las capacidades que el SBC ha notificado. Si el SBC indica que admite el método "Consultar", el proxy SIP usará la opción 2 para las transferencias de llamadas.

El siguiente es un ejemplo de un SBC que envía el mensaje de que el método de referencia es compatible:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Si el SBC no indica que hacer referencia como un método admitido, el enrutamiento directo usará la opción 1 (proxy SIP actúa como árbitro). La SBC también debe indicar que admite el método de notificación:

Ejemplo de SBC que indica que el método Refer no es compatible:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Los procesos de proxy SIP se refieren localmente al cliente y actúan como árbitro

Si el SBC indica que el método de referencia no es compatible, el proxy SIP actúa como árbitro. 

La solicitud de referencia que procede del cliente finalizará en el proxy SIP. (La solicitud de referencia del cliente se muestra como "Transferencia de llamada a David" en el siguiente diagrama.  Para obtener más información, consulte la sección 7.1 de [RFC 3892.](https://www.ietf.org/rfc/rfc3892.txt) 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando con respuesta provisional](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>Proxy SIP envía la referencia a la SBC y actúa como transferor

Este es el método preferido para las transferencias de llamadas y es obligatorio para los dispositivos que den omisión a los medios. La transferencia de llamadas sin que la SBC pueda controlar la referencia no se admite en el modo de omisión de medios. 

El estándar se explica en la sección 6 de RFC 5589. Las RFC relacionadas son:

- [Control de llamada del Protocolo de inicio de sesión (SIP): transferencia](https://tools.ietf.org/html/rfc5589)

- [Encabezado "Reemplaza" del Protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3891)

- [Mecanismo "Referred-By" del Protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3892)

Esta opción asume que el proxy SIP actúa como transferor y envía un mensaje de referencia a la SBC. La SBC actúa como transferible y controla la referencia para generar una nueva oferta de transferencia. Hay dos casos posibles:

- La llamada se transfiere a un participante externo de RTC. 
- La llamada se transfiere de un usuario de Teams a otro usuario de Teams en el mismo espacio empresarial a través de SBC. 

Si la llamada se transfiere de un usuario de Teams a otro a través del SBC, se espera que el SBC emita una nueva invitación (iniciar un nuevo cuadro de diálogo) para el destino de la transferencia (el usuario de Teams) con la información recibida en el mensaje de referencia. 

Para rellenar los campos Para/Transferir de la transacción de la solicitud internamente, el proxy SIP necesita transmitir esta información dentro de los encabezados REFER-TO/REFERRED-BY. 

El proxy SIP formará el URI de REFER-TO como un URI de SIP compuesto por un FQDN de proxy SIP en el nombre de host y cualquiera de los siguientes:

- Un número de teléfono E.164 en la parte de nombre de usuario del URI en caso de que el destino de la transferencia sea un número de teléfono o

- Los parámetros x-m y x-t codifican la MRI de destino de transferencia completa y el id. de inquilino, respectivamente 

El encabezado REFERRED-BY es un URI de SIP con MRI transferor codificado en él, así como un id. de inquilino del transferor y otros parámetros de contexto de transferencia, tal y como se muestra en la tabla siguiente:

| Parámetro | Valor | Descripción |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | MRI completa del destino del transferor o la transferencia rellenado por CC |
| x-t | ID. del espacio empresarial | Id. de inquilino opcional de x-t rellenado por CC |
| x-ti | Id. de correlación de transferor | Id. de correlación de la llamada al transferor |
| x-tt | URI de transferencia de llamada de destino | URI de sustitución de llamada codificada |

El tamaño del encabezado de referencia puede tener hasta 400 símbolos en este caso. La SBC debe admitir la gestión de mensajes de referencia con tamaños de hasta 400 símbolos.

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión sonando con respuesta provisional](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Temporizador de sesión

El proxy SIP admite (siempre ofrece) el temporizador de sesión en llamadas que no se omitan, pero no lo ofrece en llamadas de omisión. El uso del temporizador de sesión por parte del SBC no es obligatorio.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso del parámetro Request-URI user=phone

El proxy SIP analiza el URI de la solicitud y, si el parámetro user=phone está presente, el servicio administrará el URI de solicitud como un número de teléfono, haciendo coincidir el número con un usuario. Si el parámetro no está presente, el proxy SIP aplica heurismo para determinar el tipo de usuario de URI de solicitud (número de teléfono o dirección SIP).

Microsof recomienda aplicar siempre el parámetro user=phone para simplificar el proceso de configuración de llamadas.

## <a name="history-info-header"></a>History-Info encabezado

El encabezado History-Info se usa para volver a segmentar las solicitudes SIP y "proporcionar o proporcionar un mecanismo estándar para capturar la información del historial de solicitudes para habilitar una amplia variedad de servicios para redes y usuarios finales". Para obtener más información, [vea RFC 4244 - Sección 1.1.](http://www.ietf.org/rfc/rfc4244.txt) Para Microsoft Phone System, este encabezado se usa en escenarios de simultánea y desviado de llamadas.  

Si se envía, el History-Info está habilitado de la siguiente manera:

- El proxy SIP insertará un parámetro que contiene el número de teléfono asociado en entradas de History-Info que componen el encabezado History-Info electrónico enviado al controlador RTC.  Usando solo las entradas que tienen el parámetro de número de teléfono, el controlador RTC reconstruirá un nuevo encabezado History-Info y lo pasará al proveedor de troncos SIP a través de proxy SIP.

- History-Info encabezado se agregará para los casos de llamadas y de llamadas simultáneas.

- History-Info encabezado no se agregará para los casos de transferencia de llamadas.

- Una entrada de historial individual en el encabezado History-Info reconstruir tendrá el parámetro de número de teléfono combinado con el FQDN de enrutamiento directo (sip.pstnhub.microsoft.com) establecido como la parte host del URI; un parámetro de "user=phone" se agregará como parte del URI del SIP.  Cualquier otro parámetro asociado con el encabezado History-Info original, excepto los parámetros contextuales del teléfono, se pasará por el encabezado de History-Info nueva construcción.  

  > [!NOTE]
  > Las entradas que son privadas (según determinen los mecanismos definidos en la sección 3.3 de RFC 4244) se reenviarán como se hace porque el proveedor de tronco SIP es un punto de confianza.

- Los History-Info entrantes se pasan por alto.

A continuación se muestra el formato del encabezado de información del historial enviado por el proxy SIP:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Si la llamada se redirija varias veces, la información sobre cada redirección se incluye por el motivo adecuado en orden cronológico.


Ejemplo de encabezado:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

El History-Info está protegido por un mecanismo obligatorio de TLS. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Conexión SBC al mecanismo de enrutamiento directo y conmutación por error

Consulte la sección Mecanismo de conmutación por error para la señalización SIP en [Plan de enrutamiento directo.](direct-routing-plan.md#failover-mechanism-for-sip-signaling)

## <a name="retry-after"></a>Retry-After

Si un centro de datos de enrutamiento directo está ocupado, el servicio puede enviar un mensaje de Retry-After con un intervalo de un segundo a la SBC. Cuando la SBC recibe un mensaje 503 con un encabezado Retry-After en respuesta a una INVITACIÓN, la SBC debe finalizar esa conexión y probar el siguiente centro de datos de Microsoft disponible. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Reinicio de ICE: llamada de omisión de medios transferida a un punto de conexión que no admite la omisión de medios

La SBC debe admitir los reinicios de ICE, como se describe en [RFC 5245, sección 9.1.1.1.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)

El reinicio en Enrutamiento directo se implementa según los siguientes párrafos del RFC:

*Para reiniciar ICE, un agente DEBE cambiar tanto el ice-pwd como el ice-ufrag de la transmisión multimedia en una oferta.  Tenga en cuenta que es opcional usar un atributo de nivel de sesión en una oferta, pero proporcionar los mismos atributos de nivel de hielo o ice-ufrag que en una oferta posterior.  Esto no es un cambio de contraseña, solo un cambio en su representación, y no provoca un reinicio de ICE.*

*Un agente establece el resto de los campos en el SDP para esta transmisión multimedia como lo haría en una oferta inicial de esta transmisión multimedia (vea la sección 4.3).  Por lo tanto, el conjunto de candidatos PUEDE incluir algunos, ninguno o todos los candidatos anteriores para esa transmisión y PUEDE incluir un conjunto totalmente nuevo de candidatos recopilados, como se describe en la sección 4.1.1.*

Si la llamada se estableció inicialmente con omisión de medios y la llamada se transfiere a un cliente de Skype Empresarial, el enrutamiento directo tiene que insertar un procesador de medios, esto se debe a que el enrutamiento directo no se puede usar con un cliente de Skype Empresarial con omisión de medios. El enrutamiento directo inicia el proceso de reinicio de ICE cambiando el ice-pwd y ice-ufrag y ofreciendo nuevos candidatos a medios en un cambio de color. 


