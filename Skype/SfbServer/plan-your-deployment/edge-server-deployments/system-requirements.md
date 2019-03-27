---
title: Requisitos del sistema del servidor de bordes en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Resumen: Obtenga información sobre los requisitos del sistema para el servidor perimetral en Skype para Business Server.'
ms.openlocfilehash: 34114833b516f49fb36742cbde9361e1bb1d3be3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879929"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos del sistema del servidor de bordes en Skype para Business Server
 
**Resumen:** Obtenga información sobre los requisitos del sistema para el servidor perimetral en Skype para Business Server.
  
Lo que respecta a su Skype para la implementación de servidor perimetral de Business Server, estos son las cosas que debe hacer para el servidor o servidores que se encuentran en el entorno de sí mismo, así como planeación de la estructura del entorno. Para más información sobre las topologías, DNS, certificados y otros problemas de la infraestructura, compruebe la documentación sobre los requisitos del entorno.
  
## <a name="components"></a>Components

Cuando trate el entorno de servidor perimetral, nos estamos hacer referencia a componentes, la mayor parte implementadas en una red perimetral (es para decir, está en un grupo de trabajo o en un dominio que se encuentra fuera de su Skype para la estructura de dominios de Business Server).
  
Teniendo eso en cuenta, estos son los componentes que tiene que tener en cuenta para implementar el servidor perimetral correctamente:
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (estos son opcionales y, si se incluyen, estarán en la red interna)
    
- [Equilibradores de carga](system-requirements.md#LoadBalancers) (puede tener un equilibrador de carga de hardware (HLB) o el equilibrio de carga DNS, pero para un solo servidor perimetral, esto no es necesario)
    
Hay más información sobre cada uno de ellos a continuación:
  
### <a name="edge-servers"></a>Servidores perimetrales
<a name="EdgeServers"> </a>

Estos son los Skype para servidores empresariales implementados en el entorno perimetral. Su función es enviar y recibir tráfico de red a los usuarios externos para los servicios ofrecidos por su Skype interno para la implementación de Business Server. Para hacer esto correctamente, se ejecuta cada servidor perimetral:
  
- **Servicio perimetral de acceso**: proporciona un punto de conexión de confianza solo para el tráfico de protocolo de inicio de sesión (SIP) entrante y saliente.
    
- **Servicio perimetral de conferencia Web**: permite a los usuarios externos unirse a reuniones que se hospedan en su Skype interna para el entorno de servidor empresarial.
    
- **A / servicio perimetral A/v**: realiza audio, vídeo, uso compartido de aplicaciones y los usuarios disponibles externos de transferencia de archivos.
    
- **El servicio Proxy XMPP**: acepta y envía mensajes (XMPP) de protocolo extensible de mensajería y presencia a y desde socios federados XMPP configurados.
    
Los usuarios externos autorizados pueden usar los servidores perimetrales para conectarse a su Skype interno para la implementación de Business Server pero, de lo contrario, que proporcionan no hay otro acceso a la red interna para cualquier persona.
  
> [!NOTE]
> Los servidores perimetrales se implementan para proporcionar conexiones de Skype habilitado para los clientes empresariales y otros servidores perimetrales (en escenarios de federación). No se puede conectar desde otros tipos de cliente o servidor de punto final. El servidor de puerta de enlace XMPP puede permitir conexiones con socios XMPP configurados. Pero de nuevo, éstos son los únicos tipos de cliente y de federación que funcionarán. 

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019. Para obtener más información, vea [la federación XMPP migrar](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Proxies inversos
<a name="ReverseProxies"> </a>

Un servidor proxy inverso (RP) no tiene ningún Skype para el rol de servidor empresarial, pero es un componente esencial de una implementación de servidor perimetral. Un proxy inverso permite a los usuarios externos:
  
- conectarse a reuniones o conferencias de acceso telefónico local con direcciones URL sencillas.
    
- descargar el contenido de la reunión.
    
- expandir grupos de distribución.
    
- obtener certificados según usuarios para la autenticación según certificados
    
- descargar archivos desde el servidor de la libreta de direcciones, o para enviar consultas al servicio de consulta Web de libreta de direcciones.
    
- obtener actualizaciones para software de clientes y dispositivos.
    
Y para dispositivos móviles:
  
- les permite detectar automáticamente los servidores Front-End que ofrece servicios de movilidad.
    
- permite que las notificaciones de inserción de Office 365 a los dispositivos móviles.
    
Nuestras recomendaciones actual de proxy inverso pueden encontrarse en la página de la [Infraestructura de telefonía de Skype para la empresa](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Por lo que el proxy inverso:
  
- necesita poder usar la seguridad de la capa de transporte (TLS) que se introdujo en su entorno a través de certificados públicos para conectarse a los servicios web externos publicados de:
    
  - Director o grupo de directores
    
  - Front-End Server o Front-End de grupo
    
- tiene que poder publicar sitios web internos con certificados para cifrado, o bien publicarlos con métodos sin cifrar, en caso necesario.
    
- debe poder publicar externamente un sitio web hospedado de forma interna con su nombre de dominio completo (FQDN).
    
- tiene que poder publicar todo el contenido del sitio web hospedado. De forma predeterminada, puede usar el ** / *** directiva, que es reconocido por la mayoría de los servidores web a Media "Publicar todo el contenido en el servidor web". También puede modificar la directiva, por ejemplo, ** /Uwca/\\***, lo que significa "publica todo el contenido en el directorio virtual de Ucwa".
    
- debe requerir conexiones TLS con los clientes que soliciten contenido desde su sitio web publicado.
    
- debe aceptar certificados con entradas de nombre alternativo del firmante (SAN).
    
- debe poder permitir el enlace de un certificado a una interfaz o agente de escucha a través del que se vaya a resolver el FQDN de servicios web externos. Se prefiere una configuración de agente de escucha a una de interfaz. Se pueden configurar varios agentes de escucha en una sola interfaz.
    
- necesita permitir la configuración de control de encabezados de host. A menudo, el encabezado de host original enviado por el cliente solicitante debe pasarse transparente, en lugar de modificando el proxy inverso.
    
- necesita permitir crear un puente de tráfico TLS desde un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443). El proxy inverso puede descifrar el paquete en la recepción y, a continuación, cifre el paquete en enviar.
    
- necesita poder crear un puente para el tráfico TCP no cifrado desde un puerto (TCP 80, por ejemplo) a otro (TCP 8080, por ejemplo).
    
- tiene que permitir la configuración de los tipos de autenticación NTLM, Sin autenticación y Autenticación de paso a través, o aceptar estos tipos de autenticación.
    
Si el proxy inverso puede satisfacer todas las necesidades de esta lista, debe ser una buena vaya, pero tenga en cuenta nuestras recomendaciones en el vínculo proporcionado por encima.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Necesita poner la implementación perimetral tras un firewall externo, pero le recomendamos tener dos firewall, uno externo y otro interno entre el entorno perimetral y el entorno interno. Toda la documentación en nuestros escenarios tendrá dos firewall. Le recomendamos disponer de dos firewall porque así se asegura un enrutamiento estricto de un perímetro de red a otro y multiplica la protección de firewall para su red interna.
  
### <a name="directors"></a>Directores
<a name="Directors"> </a>

Este es un rol opcional. Puede ser un solo servidor o un grupo de servidores que ejecutan el rol de Director. Es una función que se encuentra en la Skype interna para el entorno de servidor empresarial.
  
El Director es un servidor interno de salto siguiente que recibe el tráfico SIP entrante de los servidores perimetrales que está dirigido a Skype para los servidores internos Business Server. Autentica previamente las solicitudes de entrada y las redirige a un servidor o grupo de servidores principales de un usuario. Esta autenticación previa le permite eliminar solicitudes de cuenta de usuario no identificadas.
  
¿Por qué importa? Es una función importante para un Director proteger los servidores Standard Edition y servidores Front-End o grupos de servidores Front-End del tráfico malintencionado, como los ataques de denegación de servicio (DoS). Si la red se desborda con el tráfico externo no válido, el tráfico se detiene en el Director.
  
### <a name="load-balancers"></a>Equilibradores de carga
<a name="LoadBalancers"> </a>

El Skype para la topología perimetral consolidada escalada de Business Server está optimizado para DNS equilibrio de carga para las implementaciones de nuevo, y se recomienda esto. Si necesita una alta disponibilidad, se recomienda usar un equilibrador de carga de hardware para una situación específica:
  
- Mensajería unificada de Exchange para los usuarios remotos con mensajería unificada de Exchange **anterior** a Exchange 2013.
    
> [!IMPORTANT]
> Es fundamental que tenga en cuenta que no puede mezclar equilibradores de carga. En su Skype para entorno Business Server deben usar todas las interfaces de DNS o HLB. 
  
> [!NOTE]
> Servidor directo devolver NAT (DSR) no se admite para Skype para Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos de equilibrador de carga de hardware para servidores de borde de los servidores perimetrales que ejecuta el / servicio perimetral A/v

Para cualquier servidor perimetral que ejecuta el servicio perimetral A/v, estos son los requisitos:
  
- Deshabilite la aplicación del algoritmo de Nagle TCP para los puertos 443 internos y externos. La aplicación del algoritmo de Nagle es la combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.
    
- Deshabilite la aplicación del algoritmo de Nagle TCP para el intervalo de puertos externos 50000 - 59999.
    
- No use la NAT en los firewalls internos ni externos.
    
- La interfaz perimetral interna debe estar en una red distinta a la interfaz externa del servidor perimetral, y debe deshabilitar el enrutamiento entre ellas.
    
- La interfaz externa de cualquier servidor perimetral que ejecuta el servicio perimetral A/v debe usar direcciones IP enrutables públicamente y ninguna NAT o traducción de puerto en cualquiera de las direcciones IP de servidor perimetral externas.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

Skype para Business Server no tiene una gran cantidad de requisitos de afinidad basada en cookies. Por lo que no es necesario utilizar un persistencia basada en cookies **a menos que** (y se trata de Skype para servidor 2015-específicos de su negocio) que va a tener grupos de servidores Front-End o de Lync Server 2010 Front End Servers en su Skype para el entorno de servidor empresarial. Tienen afinidad basada en cookies en el método de configuración recomendado para Lync Server 2010.
  
> [!NOTE]
> Si decide activar la afinidad basada en cookies en su HLB, no habrá problemas, incluso si su entorno no la necesita. 
  
Si su entorno **no** necesita la afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, establezca el **encabezado de host hacia delante** en **True**. Esto garantizará que se transfiera la URL original.
    
Para las implementaciones que **sí** necesitan la afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, establezca el **encabezado de host hacia delante** en **True**. Esto garantizará que se transfiera la URL original.
    
- El hardware carga equilibrador cookie **no debe** estar marcada como httpOnly.
    
- El hardware carga equilibrador cookie **no debe** tener un tiempo de expiración.
    
- El hardware carga equilibrador cookie **debe** tener el nombre **MS-WSMAN** (este es el valor que se espera que los servicios Web, y no se puede cambiar).
    
- El hardware carga equilibrador cookie **debe** establecerse en cada respuesta HTTP para la que la solicitud HTTP entrante no tiene una cookie, independientemente de si una respuesta HTTP anterior en esa misma conexión TCP ha recibido una cookie. Si el equilibrador de carga de hardware optimiza insertar cookie para que sólo se produzca una vez por cada conexión TCP, esa optimización **no debe** usarse.
    
> [!NOTE]
> Es habitual que el de las configuraciones de HLB utilizar la afinidad de origen y 20 minutos TCP duración de la sesión, que es el adecuado para Skype para Business Server y sus clientes, porque se mantiene el estado de sesión a través de uso del cliente o la interacción de aplicaciones. 
  
Si se implementan dispositivos móviles, el HLB debe poder equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, debe poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).
  
> [!IMPORTANT]
> Los HLB F5 tienen una característica denominada OneConnect, que garantiza que cada solicitud dentro de una conexión TCP se carga de forma equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor HLB admita la misma característica. Las últimas aplicaciones móviles iOS requieren la versión TLS 1.2. Si necesita más información, F5 proporciona configuración específica para esto. 
  
Estos son los requisitos de HLB para el Director (opcional) y el grupo de servidores Front-End (obligatorio) servicios Web:
  
- Para la VIP de servicios Web internos, establezca Source_addr persistencia (interno puerto 80, 443) en su HLB. Para Skype para Business Server, persistencia Source_addr significa que varias conexiones procedentes de una sola dirección IP siempre se envían a un servidor, para mantener el estado de sesión.
    
- Use un tiempo de espera de inactividad TCP de 1.800 segundos.
    
- En el firewall entre el proxy inverso y HLB el próximo salto del grupo de servidores, cree una regla para permitir https: el tráfico en el puerto 4443, desde el proxy inverso para su HLB. El HLB debe configurarse de modo que escuche los puertos 80, 443 y 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumen de los requisitos de afinidad del HLB

|**Ubicación de cliente/usuario**|**Requisitos de afinidad del FQDN de servicios web externos**|**Requisitos de afinidad del FQDN de servicios web internos**|
|:-----|:-----|:-----|
|Skype para la aplicación empresarial de Web (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Skype para la aplicación empresarial de Web (sólo para usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Skype para la aplicación empresarial de Web (solo usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Supervisión de puertos para HLB

Definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuando ya no están disponibles, debido a errores de hardware o comunicaciones de servicios específicos. Por ejemplo, si el servicio de servidor Front-End (RTCSRV) se detiene debido a que se produce un error en el grupo de servidores Front-End o de servidor Front-End, la supervisión de HLB debe también dejar de recibir tráfico de los servicios Web. Debe implementar la supervisión de puertos en el HLB para supervisar lo siguiente para la interfaz externa del HLB:
  
|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<grupo de servidores\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<grupo de servidores\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

Hemos analizado los requisitos de hardware y software de servidor perimetral en nuestra documentación general de [los requisitos de servidor de Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y [requisitos del sistema para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Colocación

Hemos analizado colocación de servidor perimetral en nuestra documentación de [Conceptos básicos de la topología de Skype para Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

