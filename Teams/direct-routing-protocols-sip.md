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
ms.openlocfilehash: 26d6555b82db1939b879ecafc113ced186528f80
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50837007"
---
# <a name="direct-routing---sip-protocol"></a>Enrutamiento directo: protocolo SIP

En este artículo se describe cómo enrutamiento directo implementa el Protocolo de inicio de sesión (SIP). Para enrutar correctamente el tráfico entre un controlador de borde de sesión (SBC) y el proxy SIP, algunos parámetros SIP deben tener valores específicos. Este artículo está destinado a los administradores de voz responsables de configurar la conexión entre el SBC local y el servicio de proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Procesar la solicitud entrante: buscar el inquilino y el usuario

Antes de que se pueda procesar una llamada entrante o saliente, los mensajes OPTIONS se intercambian entre el proxy SIP y el SBC. Estos mensajes OPTIONS permiten que el proxy SIP proporcione las capacidades permitidas a SBC. Es importante que la negociación DE OPCIONES tenga éxito (respuesta 200OK), lo que permite una mayor comunicación entre SBC y proxy SIP para establecer llamadas. Los encabezados SIP de un mensaje OPTIONS para proxy SIP se proporcionan como ejemplo a continuación:

| Nombre del parámetro | Ejemplo del valor | 
| :---------------------  |:---------------------- |
| Request-URI | OPCIONES sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| A través del encabezado | A través de: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards encabezado | Max-Forwards:68 |
| Desde encabezado | Desde el encabezado desde: <sip:sbc1.adatum.biz:5058> |
| A Encabezado | Para: <sip:sip.pstnhub.microsoft.com:5061> |
| Encabezado CSeq | CSeq: 1 INVITACIÓN | 
| Encabezado de contacto | Contacto: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Los encabezados SIP no contienen userinfo en el URI de SIP en uso. Según [RFC 3261, sección 19.1.1,](https://tools.ietf.org/html/rfc3261#section-19.1.1)la parte userinfo de un URI es opcional y puede estar ausente cuando el host de destino no tiene un concepto de usuarios o cuando el propio recurso está identificado. Si el signo @ está presente en un URI SIP, el campo de usuario NO DEBE estar vacío.

En una llamada entrante, el proxy SIP debe buscar el espacio empresarial al que está destinada la llamada y encontrar el usuario específico dentro de este espacio empresarial. El administrador de inquilinos puede configurar números que no son DID, por ejemplo +1001, en varios inquilinos. Por lo tanto, es importante buscar el espacio empresarial específico en el que realizar la búsqueda de números porque los números que no son DID pueden ser los mismos en varias organizaciones de Microsoft 365 u Office 365.  

En esta sección se describe cómo el proxy SIP encuentra el inquilino y el usuario, y realiza la autenticación del SBC en la conexión entrante.

A continuación se muestra un ejemplo del mensaje Invitar SIP en una llamada entrante:

| Nombre del parámetro | Ejemplo del valor | 
| :---------------------  |:---------------------- |
| Request-URI | INVITAR sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| A través del encabezado | A través de: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards encabezado | Max-Forwards:68 |
| Desde encabezado | Del encabezado de: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| A Encabezado | Para: sip:+183338006777@sbc1.adatum.biz | 
| Encabezado CSeq | CSeq: 1 INVITACIÓN | 
| Encabezado de contacto | Contacto: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Al recibir la invitación, el proxy SIP realiza los pasos siguientes:

1. Compruebe el certificado. En la conexión inicial, el servicio enrutamiento directo toma el nombre FQDN que se muestra en el encabezado contacto y lo hace con el nombre común o el nombre alternativo del asunto del certificado presentado. El nombre de SBC debe coincidir con una de las siguientes opciones:

   - Opción 1. El nombre completo fqdn que se presenta en el encabezado de contacto debe coincidir con el nombre común o el nombre alternativo del asunto del certificado presentado.  

   - Opción 2. La parte de dominio del nombre FQDN que se presenta en el encabezado Contacto (por ejemplo, adatum.biz del nombre FQDN sbc1.adatum.biz) debe coincidir con el valor comodín en Nombre común/Nombre alternativo del asunto (por ejemplo, *.adatum.biz).

2. Intente buscar un inquilino con el nombre completo fqdn que se muestra en el encabezado Contacto.  

   Compruebe si el nombre FQDN del encabezado de contacto (sbc1.adatum.biz) está registrado como nombre DNS en cualquier organización de Microsoft 365 u Office 365. Si se encuentra, la búsqueda del usuario se realiza en el espacio empresarial que tiene el FQDN de SBC registrado como nombre de dominio. Si no se encuentra, se aplica el paso 3.   

3. El paso 3 solo se aplica si se ha fallado el paso 2. 

   Quite la parte del host del FQDN, que se muestra en el encabezado De contacto (FQDN: sbc12.adatum.biz, después de quitar la parte del host: adatum.biz) y compruebe si este nombre está registrado como nombre DNS en cualquier organización de Microsoft 365 u Office 365. Si se encuentra, la búsqueda de usuario se realiza en este espacio empresarial. Si no se encuentra, se produce un error en la llamada.

4. Con el número de teléfono presentado en el URI de solicitud, realice la búsqueda de número inverso dentro del espacio empresarial que se encuentra en los pasos 2 o 3. Coincida con el número de teléfono presentado con un URI SIP de usuario dentro del espacio empresarial encontrado en el paso anterior.

5. Aplicar la configuración del tronco. Busque los parámetros establecidos por el administrador de inquilinos para este SBC.

   Microsoft no admite tener un proxy SIP de terceros o un servidor de agente de usuario entre el proxy SIP de Microsoft y el SBC emparejado, lo que podría modificar el URI de solicitud creado por el SBC emparejado.

   Los requisitos para las dos búsquedas (pasos 2 y 3) necesarios para el escenario en el que un SBC está interconectado con muchos inquilinos (escenario de operador) se tratan más adelante en este artículo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisitos detallados para encabezado de contacto y Solicitud-URI

#### <a name="contact-header"></a>Encabezado de contacto

Para todos los mensajes SIP entrantes (OPCIONES, INVITAR) al proxy SIP de Microsoft, el encabezado de contacto debe tener el FQDN de SBC emparejado en el nombre de host uri como se muestra a continuación:

Sintaxis: Contacto: <sip:phone o sip address@FQDN del SBC;transport=tls> 

Según [RFC 3261, sección 11.1,](https://tools.ietf.org/html/rfc3261#section-11.1)un campo de encabezado de contacto puede estar presente en un mensaje OPTIONS. En Enrutamiento directo, el encabezado de contacto es obligatorio. Para los mensajes INVITE en formato anterior, para los mensajes OPTIONS, el userinfo se puede quitar del URI de SIP y solo el FQDN enviado en formato como se muestra a continuación:

Sintaxis: Contacto: <sip:FQDN del SBC;transport=tls>

Este nombre (FQDN) también debe estar en los campos Nombre común o Nombre alternativo del asunto del certificado presentado. Microsoft admite el uso de valores comodín de los nombres en los campos Nombre común o Nombre alternativo del asunto del certificado.   

La compatibilidad con caracteres comodín se describe [en RFC 2818, sección 3.1.](https://tools.ietf.org/html/rfc2818#section-3.1) Específicamente:

*"Los nombres pueden contener el carácter comodín que se considera que coincide con cualquier único componente de nombre de dominio \* o fragmento de componente. Por ejemplo, .a.com coincide foo.a.com pero no bar.foo.a.com. f .com coincide foo.com \* \* pero no bar.com".*

Si el SBC envía más de un valor en el encabezado Contacto presentado en un mensaje SIP, solo se usa la parte FQDN del primer valor del encabezado de contacto.

Como regla general para enrutamiento directo, es importante que el FQDN se utilice para rellenar URI DE SIP en lugar de IP. Un mensaje DE INVITACIÓN o OPCIONES entrante a Proxy SIP con encabezado de contacto en el que el nombre de host se representa mediante IP y no FQDN, la conexión se rechazará con 403 Prohibido.

#### <a name="request-uri"></a>Request-URI 

Para todas las llamadas entrantes, el URI de solicitud se usa para hacer coincidir el número de teléfono con un usuario.   

Actualmente, el número de teléfono debe contener un signo más (+) como se muestra en el ejemplo siguiente. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Consideraciones de Record-Route de contacto y encabezados

El proxy SIP necesita calcular el FQDN de salto siguiente para las nuevas transacciones de cliente en el cuadro de diálogo (por ejemplo, Bye o Re-Invite) y al responder a Opciones SIP. Se usan las Record-Route contacto o las Record-Route. 

Según [RFC 3261, sección 8.1.1.8,](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)el encabezado de contacto es necesario en cualquier solicitud que pueda dar como resultado un nuevo cuadro de diálogo. El Record-Route solo es necesario si un proxy desea mantenerse en la ruta de acceso de las solicitudes futuras en un cuadro de diálogo. Si un SBC proxy está en uso con optimización de medios [locales](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)para enrutamiento directo, deberá configurarse una ruta de registro ya que el SBC proxy debe permanecer en la ruta. 

Microsoft recomienda usar solo el encabezado de contacto si no se usa un SBC proxy:

- Por [RFC 3261, sección 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route se usa si un proxy quiere mantenerse en la ruta de las solicitudes futuras en un cuadro de diálogo, lo que no es esencial si no se configura ningún SBC proxy ya que todo el tráfico va entre el proxy SIP de Microsoft y el SBC emparejado. 

- El proxy SIP de Microsoft usa solo encabezado de contacto (no Ruta de registro) para determinar el siguiente salto al enviar opciones de ping salientes. Configurar solo un parámetro (Contacto) en lugar de dos (Contacto y Ruta de registro) simplifica la administración si no se usa un SBC proxy. 

Para calcular el salto siguiente, el proxy SIP usa:

- Prioridad 1. Ruta de registro de nivel superior. Si el nombre de Record-Route nivel superior contiene el nombre FQDN, el nombre FQDN se usa para realizar la conexión saliente en el cuadro de diálogo.

- Prioridad 2. Encabezado de contacto. Si Record-Route no existe, el proxy SIP buscará el valor del encabezado Contacto para realizar la conexión saliente. (Esta es la configuración recomendada).

Si se usan contact y Record-Route, el administrador de SBC debe mantener sus valores idénticos, lo que causa sobrecarga administrativa. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso del nombre FQDN en Contacto o Record-Route

El uso de una dirección IP no es compatible ni en Record-Route ni en Contacto. La única opción compatible es un FQDN, que debe coincidir con el nombre común o el nombre alternativo del asunto del certificado SBC (se admiten valores comodín en el certificado).

- Si se presenta una dirección IP en Ruta de registro o Contacto, se produce un error en la comprobación del certificado y se produce un error en la llamada.

- Si el FQDN no coincide con el valor del nombre alternativo común o del asunto en el certificado presentado, se produce un error en la llamada. 

## <a name="inbound-call-sip-dialog-description"></a>Llamada entrante: descripción del cuadro de diálogo SIP

En la siguiente tabla se resumen las diferencias y similitudes de flujo de llamada entre los modos de no omisión y omisión:

| Nombre del parámetro | Modo sin omisión | Modo de omisión
| :---------------------  |:---------------------- |:----------------|
| Candidatos multimedia en 183 y 200 mensajes procedentes de | Procesadores multimedia | Clientes | 
| Número de 183 mensajes que SBC puede recibir | Uno por sesión | Múltiplo | 
| La llamada puede ser con respuesta provisional (183) | Sí | Sí |
| La llamada puede no tener respuesta provisional (183) | Sí | Sí |

###  <a name="non-media-bypass-flow"></a>Flujo de omisión no multimedia

Un usuario de Teams puede tener varios puntos de conexión al mismo tiempo. Por ejemplo, cliente de Teams para Windows, cliente de Teams para iPhone y Teams Phone (cliente Android de Teams). Cada punto de conexión puede indicar un reposo HTTP de la siguiente manera:

-   Progreso de la llamada: convertido por el proxy SIP al mensaje SIP 180. Al recibir el mensaje 180, el SBC debe generar una llamada local.

-   Respuesta multimedia: convertida por el proxy SIP en el mensaje 183 con candidatos multimedia en el Protocolo de descripción de sesión (SDP). Al recibir el mensaje 183, el SBC espera conectarse a los candidatos multimedia recibidos en el mensaje SDP. 

    > [!NOTE]
    > En algunos casos, es posible que no se genere la respuesta multimedia y que el punto final responda con el mensaje "Llamada aceptada".

-   Llamada aceptada: convertida por el proxy SIP en el mensaje SIP 200 con SDP. Al recibir el mensaje 200, se espera que el SBC envíe y reciba los medios a y desde los candidatos del SDP proporcionados.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Varios puntos de conexión que suenan con respuesta provisional

1.  Al recibir la primera invitación desde el SBC, el proxy SIP envía el mensaje "SIP SIP/2.0 100 Trying" y notifica a todos los extremos del usuario final sobre la llamada entrante. 

2.  Tras la notificación, cada punto de conexión empezará a sonar y a enviar mensajes de "Progreso de llamada" al proxy SIP. Como un usuario de Teams puede tener varios puntos finales, el proxy SIP puede recibir varios mensajes de progreso de llamada.

3.  Por cada mensaje de progreso de llamada recibido de los clientes, el proxy SIP convierte el mensaje de progreso de llamada en el mensaje SIP "SIP SIP/2.0 180 Trying". El intervalo para enviar estos mensajes se define por el intervalo de los mensajes de recepción desde el controlador de llamadas. En el siguiente diagrama, hay dos 180 mensajes generados por el proxy SIP. Estos mensajes proceden de los dos puntos de conexión de Teams del usuario. Cada uno de los clientes tiene un id. de etiqueta único.  Cada mensaje procedente de un punto de conexión diferente será una sesión independiente (el parámetro "etiqueta" en el campo "Para" será diferente). Sin embargo, es posible que un punto de conexión no genere el mensaje 180 y envíe el mensaje 183 inmediatamente, como se muestra en el siguiente diagrama.

4.  Una vez que un punto de conexión genera un mensaje de respuesta multimedia con las direcciones IP de los candidatos multimedia del punto de conexión, el proxy SIP convierte el mensaje recibido en un mensaje "Progreso de sesión SIP 183" con el SDP del cliente reemplazado por el SDP desde el procesador multimedia. En el siguiente diagrama, el punto de conexión de Bifurcación 2 respondió a la llamada. Si el tronco no se omite, el mensaje SIP 183 solo se genera una vez (anillo bot o punto final del cliente). El 183 puede venir en una bifurcación existente o iniciar una nueva.

5.  Se envía un mensaje de aceptación de llamadas con los candidatos finales del punto de conexión que aceptaron la llamada. El mensaje Aceptación de llamadas se convierte en mensaje SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión que suenan con respuesta provisional](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Varios puntos de conexión que suenan sin respuesta provisional

1.  Al recibir la primera invitación desde el SBC, el proxy SIP envía el mensaje "SIP SIP/2.0 100 Trying" y notifica a todos los extremos del usuario final sobre la llamada entrante. 

2.  Tras la notificación, cada punto de conexión empezará a sonar y a enviar el mensaje "Progreso de la llamada" al proxy SIP. Como un usuario de Teams puede tener varios puntos finales, el proxy SIP puede recibir varios mensajes de progreso de llamada.

3.  Por cada mensaje de progreso de llamada recibido de los clientes, el proxy SIP convierte el mensaje de progreso de llamada en el mensaje SIP "SIP SIP/2.0 180 Trying".  El intervalo para enviar los mensajes se define por el intervalo de recepción de los mensajes desde el controlador de llamadas. En la imagen siguiente hay dos 180 mensajes generados por el proxy SIP, lo que significa que el usuario ha iniciado sesión en tres clientes de Teams y cada cliente envía el progreso de la llamada. Cada mensaje será una sesión independiente (el parámetro "etiqueta" en el campo "Para" es diferente)

4.  Se envía un mensaje de aceptación de llamadas con los candidatos finales del punto de conexión que aceptaron la llamada. El mensaje Aceptación de llamadas se convierte en mensaje SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión que suenan sin respuesta provisional](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flujo de omisión de medios

Los mismos mensajes (100 Intentando, 180, 183) se usan en el escenario de omisión de medios. 

En el esquema siguiente se muestra un ejemplo del flujo de llamadas de omisión. 

> [!NOTE]
> Los candidatos multimedia pueden venir de distintos puntos de conexión. 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión que suenan con respuesta provisional](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opción Reemplazar

El SBC debe admitir Invitar con reemplazos.

## <a name="size-of-sdp-considerations"></a>Tamaño de las consideraciones de SDP

La interfaz de enrutamiento directo puede enviar un mensaje SIP que supere los 1.500 bytes.  El tamaño de SDP causa principalmente esto. Sin embargo, si hay un tronco UDP detrás del SBC, puede rechazar el mensaje si se reenvía desde el proxy SIP de Microsoft al tronco sin modificar. Microsoft recomienda quitar algunos valores de SDP en el SBC al enviar el mensaje a los troncos UDP. Por ejemplo, los candidatos del ICE o los códecs sin usar se pueden quitar.

## <a name="call-transfer"></a>Transferencia de llamadas

Enrutamiento directo admite dos métodos para la transferencia de llamadas:

- Opción 1. Procesos de proxy SIP Refiérase del cliente localmente y actúa como árbitro como se describe en la sección 7.1 de RFC 3892.

  Con esta opción, el proxy SIP finaliza la transferencia y agrega una nueva invitación. 


- Opción 2. El proxy SIP envía la referencia al SBC y actúa como transferor como se describe en la sección 6 de RFC 5589.

  Con esta opción, el proxy SIP envía una referencia al SBC y espera que el SBC controle la transferencia por completo.

El proxy SIP selecciona el método en función de las capacidades notificadas por el SBC. Si el SBC indica que admite el método "Referencia", el proxy SIP usará la opción 2 para las transferencias de llamadas.

A continuación se muestra un ejemplo de un SBC que envía el mensaje de que el método Refer es compatible:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Si el SBC no indica que Hacer referencia como un método compatible, enrutamiento directo usará la opción 1 (proxy SIP actúa como árbitro). El SBC también debe indicar que es compatible con el método Notify:

Ejemplo de SBC que indica que no se admite el método Refer:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Procesos de proxy SIP Refiérase del cliente localmente y actúa como árbitro

Si el SBC indicaba que el método Refer no es compatible, el proxy SIP actúa como árbitro. 

La solicitud de referencia que proviene del cliente se finalizará en el proxy SIP. (La solicitud De referencia del cliente se muestra como "Transferencia de llamadas a Dave" en el siguiente diagrama.  Para obtener más información, vea la sección 7.1 de [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión que suenan con respuesta provisional](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>El proxy SIP envía la referencia al SBC y actúa como transferor

Este es el método preferido para las transferencias de llamadas y es obligatorio para los dispositivos que buscan la certificación de omisión de medios. La transferencia de llamadas sin que el SBC pueda controlar La referencia no es compatible con el modo de omisión de medios. 

El estándar se explica en la sección 6 de RFC 5589. Las RFC relacionadas son:

- [Control de llamadas del Protocolo de inicio de sesión (SIP): transferencia](https://tools.ietf.org/html/rfc5589)

- [Encabezado "Reemplaza" del Protocolo de inicio de sesión (SIP)](https://tools.ietf.org/html/rfc3891)

- [Mecanismo de protocolo de inicio de sesión (SIP) "Referido por".](https://tools.ietf.org/html/rfc3892)

Esta opción supone que el proxy SIP actúa como transferor y envía un mensaje De referencia al SBC. El SBC actúa como transferible y controla la referencia para generar una nueva oferta de transferencia. Hay dos casos posibles:

- La llamada se transfiere a un participante RTC externo. 
- La llamada se transfiere de un usuario de Teams a otro usuario de Teams en el mismo espacio empresarial a través del SBC. 

Si la llamada se transfiere de un usuario de Teams a otro a través del SBC, se espera que el SBC emita una nueva invitación (iniciar un nuevo cuadro de diálogo) para el destino de transferencia (el usuario de Teams) con la información recibida en el mensaje Referencia. 

Para rellenar los campos Para/Transferir para la transacción de la solicitud internamente, el proxy SIP debe transmitir esta información dentro de los encabezados REFER-TO/REFERRED-BY. 

El proxy SIP formará el URI REFER-TO como SIP compuesto de un FQDN de proxy SIP en el nombre de host y uno de los siguientes:

- Un número de teléfono E.164 en la parte de nombre de usuario del URI en caso de que el destino de la transferencia sea un número de teléfono o

- parámetros x-m y x-t que codifican la MRI de destino de transferencia completa y el id. de inquilino respectivamente 

El encabezado REFERRED-BY es un URI SIP con MRI transferor codificado en él, así como id. de inquilino de transferor y otros parámetros de contexto de transferencia como se muestra en la tabla siguiente:

| Parámetro | Valor | Descripción |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | MRI completa del destino de transferencia o transferencia rellenada por CC |
| x-t | ID. del espacio empresarial | id. de inquilino opcional de x-t rellenado por CC |
| x-ti | Id. de correlación del transferor | Id. de correlación de la llamada al transferor |
| x-tt | Transferir uri de llamada de destino | URI de reemplazo de llamadas codificado |

En este caso, el tamaño del encabezado Referencia puede ser de hasta 400 símbolos. El SBC debe admitir la administración de mensajes De referencia con un tamaño de hasta 400 símbolos.

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra varios puntos de conexión que suenan con respuesta provisional](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Temporizador de sesión

El proxy SIP admite (siempre ofrece) el temporizador de sesión en llamadas que no se omiten, pero no lo ofrece en llamadas de omisión. El uso del temporizador de sesión por el SBC no es obligatorio.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso del parámetro Request-URI user=phone

El proxy SIP analiza el URI de solicitud y, si el parámetro user=phone está presente, el servicio controlará el URI de solicitud como un número de teléfono, haciendo coincidir el número con un usuario. Si el parámetro no está presente, el proxy SIP aplica heurística para determinar el tipo de usuario De solicitud-URI (número de teléfono o dirección SIP).

Microsoft recomienda aplicar siempre el parámetro user=phone para simplificar el proceso de configuración de la llamada.

## <a name="history-info-header"></a>History-Info encabezado

El encabezado History-Info se usa para volver a dirigir solicitudes SIP y "proporcionar un mecanismo estándar para capturar la información del historial de solicitudes para habilitar una amplia variedad de servicios para redes y usuarios finales". Para obtener más información, [vea RFC 4244 - Sección 1.1](http://www.ietf.org/rfc/rfc4244.txt). Para Microsoft Phone System, este encabezado se usa en escenarios de simulring y reenvío de llamadas.  

Si envía, el History-Info está habilitado de la siguiente manera:

- El proxy SIP insertará un parámetro que contiene el número de teléfono asociado en entradas individuales History-Info que componen el encabezado de History-Info enviado al controlador RTC.  Con solo las entradas que tienen el parámetro de número de teléfono, el controlador RTC reconstruirá un nuevo encabezado de History-Info y lo pasará al proveedor de troncos SIP a través del proxy SIP.

- History-Info encabezado se agregará para los casos de llamada y reenvío de llamadas simultáneas.

- History-Info encabezado no se agregará para los casos de transferencia de llamadas.

- Una entrada de historial individual en el encabezado History-Info reconstruido tendrá el parámetro de número de teléfono proporcionado combinado con el FQDN de enrutamiento directo (sip.pstnhub.microsoft.com) establecido como la parte host del URI; se agregará un parámetro de "user=phone" como parte del URI de SIP.  Cualquier otro parámetro asociado con el encabezado de History-Info original, excepto los parámetros de contexto del teléfono, se pasarán por el encabezado History-Info nuevo.  

  > [!NOTE]
  > Las entradas que son privadas (según lo determinado por los mecanismos definidos en la sección 3.3 de RFC 4244) se reenviarán tal y como se debe a que el proveedor de troncos SIP es un punto de confianza.

- Las History-Info entrantes se pasan por alto.

A continuación se muestra el formato del encabezado History-info enviado por el proxy SIP:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Si la llamada se redirija varias veces, la información sobre cada redirección se incluye con el motivo adecuado en orden cronológico.


Ejemplo de encabezado:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

El History-Info está protegido por un mecanismo TLS obligatorio. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Conexión SBC al mecanismo de enrutamiento directo y conmutación por error

Vea la sección Mecanismo de conmutación por error para la señalización SIP en [Plan de enrutamiento directo.](direct-routing-plan.md#failover-mechanism-for-sip-signaling)

## <a name="retry-after"></a>Retry-After

Si un centro de datos de enrutamiento directo está ocupado, el servicio puede enviar un mensaje de Retry-After con un intervalo de un segundo al SBC. Cuando el SBC recibe un mensaje 503 con un encabezado Retry-After en respuesta a una INVITACIÓN, el SBC debe finalizar esa conexión y probar el siguiente centro de datos de Microsoft disponible. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Reinicio de ICE: llamada de omisión de medios transferida a un punto de conexión que no admite la omisión de medios

El SBC debe admitir los reinicios de ICE como se describe en [RFC 5245, sección 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

El reinicio en Enrutamiento directo se implementa según los párrafos siguientes de la RFC:

*Para reiniciar ICE, un agente DEBE cambiar tanto el ice-pwd como el ice-ufrag para la transmisión multimedia en una oferta.  Tenga en cuenta que es permisible usar un atributo de nivel de sesión en una oferta, pero para proporcionar el mismo ice-pwd o ice-ufrag que un atributo de nivel multimedia en una oferta posterior.  Esto no es un cambio en la contraseña, solo un cambio en su representación y no causa un reinicio del ICE.*

*Un agente establece el resto de los campos del SDP para esta transmisión multimedia como lo haría en una oferta inicial de esta transmisión multimedia (vea sección 4.3).  Por lo tanto, el conjunto de candidatos PUEDE incluir algunos, ninguno o todos los candidatos anteriores para esa transmisión y PUEDE incluir un conjunto totalmente nuevo de candidatos reunidos como se describe en la Sección 4.1.1.*

Si la llamada se estableció inicialmente con omisión multimedia y la llamada se transfiere a un cliente de Skype Empresarial, enrutamiento directo debe insertar un procesador multimedia, esto se debe a que el enrutamiento directo no se puede usar con un cliente de Skype Empresarial con omisión de medios. Enrutamiento directo inicia el proceso de reinicio del ICE cambiando el ice-pwd y ice-ufrag y ofreciendo nuevos candidatos a medios en un revite. 


