---
title: Requisitos del sistema del servidor perimetral en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Resumen: Obtenga información sobre los requisitos del sistema para el servidor perimetral en Skype empresarial Server.'
ms.openlocfilehash: 4ef2feeb2b486bc9be9f4eb59136d74ef542dd31
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803320"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos del sistema del servidor perimetral en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre los requisitos del sistema para el servidor perimetral en Skype empresarial Server.
  
En lo que respecta a la implementación de su servidor perimetral de Skype empresarial Server, estas son las cosas que debe hacer para el servidor o los servidores que están en el propio entorno, así como para planear la estructura de entorno. Para más información sobre las topologías, DNS, certificados y otros problemas de la infraestructura, compruebe la documentación sobre los requisitos del entorno.
  
## <a name="components"></a>Components

Al hablar el entorno de servidor perimetral, hacemos referencia a componentes que, en la mayoría de los casos, se implementan en una red perimetral (es decir, se encuentran en un grupo de trabajo o un dominio que está fuera de la estructura de dominios de Skype empresarial Server).
  
Teniendo eso en cuenta, estos son los componentes que tiene que tener en cuenta para implementar el servidor perimetral correctamente:
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (estos son opcionales y, si se incluyen, estarán en la red interna)
    
- [Equilibradores de carga](system-requirements.md#LoadBalancers) (puede tener el equilibrio de carga de DNS o un equilibrador de carga de hardware (HLB), pero para un solo servidor perimetral, esto no es necesario).
    
Hay más información sobre cada uno de ellos a continuación:
  
### <a name="edge-servers"></a>Servidores perimetrales
<a name="EdgeServers"> </a>

Estos son los servidores de Skype empresarial implementados en su entorno perimetral. Su rol es enviar y recibir tráfico de red a usuarios externos para los servicios ofrecidos por su implementación interna de Skype empresarial Server. Para hacerlo correctamente, se ejecuta cada servidor perimetral:
  
- **Servicio perimetral de acceso**: proporciona un único punto de conexión de confianza para el tráfico SIP (Protocolo de inicio de sesión) entrante y saliente.
    
- **Servicio perimetral de conferencias web**: permite a los usuarios externos unirse a reuniones hospedadas en su entorno interno de Skype empresarial Server.
    
- **Servicio perimetral a/V**: hace que el audio, el vídeo, el uso compartido de aplicaciones y la transferencia de archivos estén disponibles para los usuarios externos.
    
- **Servicio de proxy XMPP**: acepta y envía mensajes de protocolo de presencia y mensajería extensible (XMPP) a los socios de XMPP federados configurados.
    
Los usuarios externos autorizados pueden usar sus servidores perimetrales para conectarse a su implementación interna de Skype empresarial Server, pero por el contrario, no proporcionan ningún otro acceso a su red interna para nadie.
  
> [!NOTE]
> Los servidores perimetrales se implementan para proporcionar conexiones para clientes de Skype empresarial habilitados y otros servidores perimetrales (en escenarios de Federación). No puede conectarse desde otros tipos de clientes o servidores de punto final. El servidor de puerta de enlace XMPP puede permitir conexiones con socios XMPP configurados. Pero, de nuevo, son los únicos tipos de Federación y de clientes que funcionarán. 

> [!NOTE]
> Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Para obtener más información, consulte [migrar la Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Proxies inversos
<a name="ReverseProxies"> </a>

Un servidor proxy inverso (RP) no tiene el rol de servidor de Skype empresarial, pero es un componente esencial de una implementación de servidor perimetral. Un proxy inverso permite a los usuarios externos:
  
- conectarse a reuniones o conferencias de acceso telefónico local con direcciones URL sencillas.
    
- descargar el contenido de la reunión.
    
- expandir grupos de distribución.
    
- obtener certificados según usuarios para la autenticación según certificados
    
- descargar archivos desde el servidor de la libreta de direcciones o para enviar consultas al servicio de consultas Web de la libreta de direcciones.
    
- obtener actualizaciones para software de clientes y dispositivos.
    
Y para dispositivos móviles:
  
- permite que descubran automáticamente los servidores front-end que ofrecen servicios de movilidad.
    
- permite notificaciones push de Office 365 a dispositivos móviles.
    
Nuestras recomendaciones actuales de proxy inverso pueden encontrarse en la [infraestructura de telefonía para la página de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Por lo tanto, el proxy inverso:
  
- necesita poder usar la seguridad de la capa de transporte (TLS) que se introdujo en su entorno a través de certificados públicos para conectarse a los servicios web externos publicados de:
    
  - Grupo de directores o directores
    
  - Servidor front-end o grupo front-end
    
- tiene que poder publicar sitios web internos con certificados para cifrado, o bien publicarlos con métodos sin cifrar, en caso necesario.
    
- debe poder publicar externamente un sitio web hospedado de forma interna con su nombre de dominio completo (FQDN).
    
- tiene que poder publicar todo el contenido del sitio web hospedado. De forma predeterminada, puede usar la ** / **Directiva *, que es reconocida por la mayoría de los servidores web para que signifiquen "publicar todo el contenido en el servidor Web". También puede modificar la Directiva, por ejemplo, * */Uwca/\\* * *, lo que significa "publicar todo el contenido bajo el directorio virtual de Ucwa".
    
- debe requerir conexiones TLS con los clientes que soliciten contenido desde su sitio web publicado.
    
- debe aceptar certificados con entradas de nombre alternativo del firmante (SAN).
    
- debe poder permitir el enlace de un certificado a una interfaz o agente de escucha a través del que se vaya a resolver el FQDN de servicios web externos. Se prefiere una configuración de agente de escucha a una de interfaz. Se pueden configurar varios agentes de escucha en una sola interfaz.
    
- necesita permitir la configuración de control de encabezados de host. A menudo, el encabezado de host original enviado por el cliente solicitante debe transferirse de forma transparente, en lugar de ser modificado por el proxy inverso.
    
- necesita permitir crear un puente de tráfico TLS desde un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443). El proxy inverso puede descifrar el paquete en el recibo y, a continuación, volver a cifrar el paquete en el envío.
    
- necesita poder crear un puente para el tráfico TCP no cifrado desde un puerto (TCP 80, por ejemplo) a otro (TCP 8080, por ejemplo).
    
- tiene que permitir la configuración de los tipos de autenticación NTLM, Sin autenticación y Autenticación de paso a través, o aceptar estos tipos de autenticación.
    
Si el proxy inverso puede cubrir todas las necesidades de esta lista, deberás estar de viaje, pero ten en cuenta nuestras recomendaciones en el vínculo que figura anteriormente.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Necesita poner la implementación perimetral tras un firewall externo, pero le recomendamos tener dos firewall, uno externo y otro interno entre el entorno perimetral y el entorno interno. Toda la documentación en nuestros escenarios tendrá dos firewall. Le recomendamos disponer de dos firewall porque así se asegura un enrutamiento estricto de un perímetro de red a otro y multiplica la protección de firewall para su red interna.
  
### <a name="directors"></a>Directores
<a name="Directors"> </a>

Este es un rol opcional. Puede ser un solo servidor o un grupo de servidores que ejecuten el rol de director. Es una función que se encuentra en el entorno interno de Skype empresarial Server.
  
El director es un servidor interno del próximo salto que recibe tráfico SIP entrante de los servidores perimetrales destinados a los servidores internos de Skype empresarial Server. Autentica previamente las solicitudes de entrada y las redirige a un servidor o grupo de servidores principales de un usuario. Esta autenticación previa le permite eliminar solicitudes de cuenta de usuario no identificadas.
  
¿Por qué importa? Una función importante para un director es proteger los servidores Standard Edition y los servidores front-end o las agrupaciones front end contra tráfico malintencionado, como ataques de denegación de servicio (DoS). Si su red está inundada con tráfico externo no válido, el tráfico se detiene en el director.
  
### <a name="load-balancers"></a>Equilibradores de carga
<a name="LoadBalancers"> </a>

La topología de Edge consolidado escalado de Skype empresarial Server está optimizada para el equilibrio de carga de DNS para implementaciones nuevas y le recomendamos esto. Si necesita una alta disponibilidad, le recomendamos que use un equilibrador de carga de hardware para una situación específica:
  
- Mensajería unificada de Exchange para usuarios remotos que usen Exchange UM **antes** de Exchange 2013.
    
> [!IMPORTANT]
> Es fundamental que tenga en cuenta que no puede mezclar equilibradores de carga. En su entorno de Skype empresarial Server, todas las interfaces deben usar DNS o HLB. 
  
> [!NOTE]
> Direct Server Return (DSR) NAT no es compatible con Skype empresarial Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos del equilibrador de carga de hardware para servidores perimetrales servidores perimetrales con el servicio de borde A/V

Para cualquier servidor perimetral que ejecute el servicio perimetral A/V, estos son los requisitos:
  
- Deshabilite la aplicación del algoritmo de Nagle TCP para los puertos 443 internos y externos. La aplicación del algoritmo de Nagle es la combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.
    
- Deshabilite la aplicación del algoritmo de Nagle TCP para el intervalo de puertos externos 50000 - 59999.
    
- No use la NAT en los firewalls internos ni externos.
    
- La interfaz interna de Edge debe estar en una red diferente a la de la interfaz externa del servidor perimetral y el enrutamiento entre ellos debe estar deshabilitado.
    
- La interfaz externa de cualquier servidor perimetral que ejecute el servicio perimetral A/V debe usar direcciones IP que se puedan enrutar públicamente y sin traducción de puertos ni NAT en ninguna de las direcciones IP externas de Edge.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

Skype empresarial Server no tiene muchos requisitos de afinidad basados en cookies. Por lo tanto, no es necesario usar una persistencia basada en cookies **, a menos** que (y sea Skype empresarial Server 2015-específico) va a tener servidores front-end de Lync Server 2010 o grupos front-end en su entorno de Skype empresarial Server. Necesitarían afinidad basada en cookies en el método de configuración recomendado para Lync Server 2010.
  
> [!NOTE]
> Si decide activar la afinidad basada en cookies en su HLB, no habrá problemas, incluso si su entorno no la necesita. 
  
Si su entorno **no** necesita la afinidad basada en cookies:
  
- En la regla de publicación de proxy invertida para el puerto 443, establezca el **encabezado de host de reenvío** en **true**. Esto garantizará que se transfiera la URL original.
    
Para las implementaciones que **sí** necesitan la afinidad basada en cookies:
  
- En la regla de publicación de proxy invertida para el puerto 443, establezca el **encabezado de host de reenvío** en **true**. Esto garantizará que se transfiera la URL original.
    
- La cookie del equilibrador de carga del hardware **no se debe** marcar como httpOnly.
    
- La cookie del equilibrador de carga de hardware **no debe** tener una fecha de expiración.
    
- La cookie del equilibrador de carga del hardware **debe** tener el nombre **MS-WSMAN** (este es el valor que esperan los servicios web y no se puede cambiar).
    
- La cookie del equilibrador de carga de hardware **debe** establecerse en todas las respuestas http en las que la solicitud HTTP entrante no tiene una cookie, independientemente de si una respuesta http anterior en esa misma conexión TCP ha recibido una cookie. Si su equilibrador de carga de hardware optimiza la inserción de cookies para que solo se produzca una vez por conexión TCP, esa optimización **no debe** usarse.
    
> [!NOTE]
> Es habitual que las configuraciones de HLB usen la afinidad de origen y la duración de la sesión TCP de 20 minutos, que es adecuada para Skype empresarial Server y sus clientes, ya que el estado de la sesión se mantiene a través del uso del cliente o la interacción de la aplicación. 
  
Si se implementan dispositivos móviles, el HLB debe poder equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, debe poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).
  
> [!IMPORTANT]
> Los HLB F5 tienen una característica denominada OneConnect, que garantiza que cada solicitud dentro de una conexión TCP se carga de forma equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor HLB admita la misma característica. Las últimas aplicaciones móviles iOS requieren la versión TLS 1.2. Si necesita más información, F5 proporciona configuración específica para esto. 
  
Estos son los requisitos de HLB para el director (opcional) y los servicios web del grupo de servidores front-end (obligatorio):
  
- Para los VIP de servicios Web internos, establezca la persistencia de Source_addr (puerto interno 80, 443) en su HLB. En el caso de Skype empresarial Server, la persistencia de la Source_addr significa que todas las conexiones provenientes de una única dirección IP siempre se envían a un servidor, para mantener el estado de la sesión.
    
- Use un tiempo de espera de inactividad TCP de 1.800 segundos.
    
- En el Firewall entre el proxy inverso y el HLB del grupo de próximos saltos, cree una regla para permitir https: tráfico en el puerto 4443, desde su proxy inverso hasta su HLB. El HLB debe configurarse de modo que escuche los puertos 80, 443 y 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumen de los requisitos de afinidad del HLB

|**Ubicación de cliente/usuario**|**Requisitos de afinidad del FQDN de servicios web externos**|**Requisitos de afinidad del FQDN de servicios web internos**|
|:-----|:-----|:-----|
|Aplicación Web de Skype empresarial (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Aplicación Web de Skype empresarial (solo para usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Aplicación Web de Skype empresarial (solo para usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Supervisión de puertos para HLB

Puede definir la supervisión de puertos en sus equilibradores de carga de hardware para determinar cuándo ya no están disponibles determinados servicios, debido a errores de hardware o de comunicaciones. Por ejemplo, si se detiene el servicio servidor front-end (RTCSRV) porque se produce un error en el servidor front-end o en la agrupación front end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios Web. Debe implementar la supervisión de puertos en el HLB para supervisar lo siguiente para la interfaz externa del HLB:
  
|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs\>de grupo  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs\>de grupo  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

Hemos cubierto los requisitos de hardware y software de los servidores perimetrales en [los requisitos generales del servidor para Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y [los requisitos del sistema para la documentación de Skype empresarial 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Colocación

Hemos cubierto el servidor EDGE de collocation en los [conceptos básicos de la topología para la documentación de Skype empresarial Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

