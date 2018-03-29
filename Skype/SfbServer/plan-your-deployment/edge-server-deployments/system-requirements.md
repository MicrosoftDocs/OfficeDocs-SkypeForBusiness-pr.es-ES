---
title: Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Resumen: Conozca los requisitos del sistema para el servidor perimetral en Skype para Business Server.'
ms.openlocfilehash: d4d195d07b13ccfc294054a811cbd6735b2431cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-system-requirements-in-skype-for-business-server-2015"></a>Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre los requisitos del sistema para el servidor perimetral en Skype para Business Server.
  
En cuanto a su Skype para la implementación de servidor perimetral de Business Server, estas son las cosas que necesita hacer para el servidor o servidores que se encuentran en el entorno de sí mismo, así como planeación de la estructura del entorno. Para más información sobre las topologías, DNS, certificados y otros problemas de la infraestructura, compruebe la documentación sobre los requisitos del entorno.
  
## <a name="components"></a>Components

Al describir el entorno de servidor perimetral, nos estamos haciendo referencia a componentes, en su mayor parte, implementados en una red perimetral (que es para decir es en un grupo de trabajo o un dominio que está fuera de su Skype para la estructura de dominio Business Server).
  
Teniendo eso en cuenta, estos son los componentes que tiene que tener en cuenta para implementar el servidor perimetral correctamente:
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (estos son opcionales y, si se incluyen, estarán en la red interna)
    
- [Equilibradores de carga](system-requirements.md#LoadBalancers) (puede tener equilibrio de carga DNS o un equilibrador de carga de hardware (HLB), pero para un solo servidor de borde, esto no es necesario)
    
Hay más información sobre cada uno de ellos a continuación:
  
### <a name="edge-servers"></a>Servidores perimetrales
<a name="EdgeServers"> </a>

Éstos son el Skype para servidores empresariales implementados en el entorno perimetral. Su función es enviar y recibir tráfico de red a los usuarios externos de los servicios ofrecidos por su Skype para la implementación de Business Server interno. Para hacer esto correctamente, se ejecuta cada servidor perimetral:
  
- **El servicio de servidor perimetral de acceso**: proporciona un punto de conexión único de confianza para el tráfico entrante y saliente de protocolo de inicio de sesión (SIP).
    
- **Servicio perimetral de conferencia Web**: permite a los usuarios externos puedan unirse a reuniones que se hospedan en su Skype para entorno Business Server interno.
    
- **A / servicio perimetral V**: convierte el archivo de audio, vídeo, uso compartido de aplicaciones y transferir usuarios externos disponibles.
    
- **Servicio Proxy XMPP**: acepta y envía mensajes (XMPP) de protocolo extensible de mensajería y presencia y de socios federados XMPP configurados.
    
Los usuarios externos autorizados pueden utilizar sus servidores de borde para conectarse a su Skype interno para la implementación de Business Server, pero en caso contrario, no proporcionan ningún otro acceso a la red interna para cualquier persona.
  
> [!NOTE]
> Se implementan servidores perimetrales para proporcionar conexiones de Skype habilitado para clientes de empresa y otros servidores de borde (en escenarios de federación). No se puede conectar desde otros tipos de cliente o servidor de punto final. El servidor de puerta de enlace de XMPP puede permitir conexiones con socios XMPP configurados. Pero de nuevo, éstos son los únicos tipos de cliente y federación que funcionarán. 
  
### <a name="reverse-proxies"></a>Proxies inversos
<a name="ReverseProxies"> </a>

Un servidor proxy inverso (RP) no tiene ningún Skype para la función de servidor de la empresa, pero es un componente esencial de una implementación de servidor perimetral. Un proxy inverso permite a los usuarios externos:
  
- conectarse a reuniones o conferencias de acceso telefónico local con direcciones URL sencillas.
    
- descargar el contenido de la reunión.
    
- expandir grupos de distribución.
    
- obtener certificados según usuarios para la autenticación según certificados
    
- descargar archivos desde el servidor de libreta de direcciones, o para enviar consultas al servicio de consulta Web de libreta de direcciones.
    
- obtener actualizaciones para software de clientes y dispositivos.
    
Y para dispositivos móviles:
  
- les permite descubrir automáticamente los servidores frontales que ofrece servicios de movilidad.
    
- permite que las notificaciones de inserción desde Office 365 a los dispositivos móviles.
    
Nuestras recomendaciones de proxy inverso actual pueden encontrarse en la página de la [Infraestructura de telefonía de Skype para el negocio](https://technet.microsoft.com/en-us/office/dn947483) . Por lo que el proxy inverso:
  
- necesita poder usar la seguridad de la capa de transporte (TLS) que se introdujo en su entorno a través de certificados públicos para conectarse a los servicios web externos publicados de:
    
  - Director o grupo de directores
    
  - Grupo de servidor o Front-End frontal
    
- tiene que poder publicar sitios web internos con certificados para cifrado, o bien publicarlos con métodos sin cifrar, en caso necesario.
    
- debe poder publicar externamente un sitio web hospedado de forma interna con su nombre de dominio completo (FQDN).
    
- tiene que poder publicar todo el contenido del sitio web hospedado. De forma predeterminada, puede utilizar el ** / ** directiva, que es reconocido por la mayoría de los servidores web para significar "Publicar todo el contenido en el servidor web". También puede modificar la directiva, por ejemplo, **/Uwca/\***, lo que significa "publica todo el contenido del directorio virtual Ucwa".
    
- debe requerir conexiones TLS con los clientes que soliciten contenido desde su sitio web publicado.
    
- debe aceptar certificados con entradas de nombre alternativo del firmante (SAN).
    
- debe poder permitir el enlace de un certificado a una interfaz o agente de escucha a través del que se vaya a resolver el FQDN de servicios web externos. Se prefiere una configuración de agente de escucha a una de interfaz. Se pueden configurar varios agentes de escucha en una sola interfaz.
    
- necesita permitir la configuración de control de encabezados de host. A menudo, el encabezado de host original enviado por el cliente solicitante debe pasarse en forma transparente, en lugar de modificando el proxy inverso.
    
- necesita permitir crear un puente de tráfico TLS desde un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443). El proxy inverso puede descifrar el paquete en el recibo y, a continuación, cifrar de nuevo el paquete de envío.
    
- necesita poder crear un puente para el tráfico TCP no cifrado desde un puerto (TCP 80, por ejemplo) a otro (TCP 8080, por ejemplo).
    
- tiene que permitir la configuración de los tipos de autenticación NTLM, Sin autenticación y Autenticación de paso a través, o aceptar estos tipos de autenticación.
    
Si el proxy inverso puede enfrentar todas las necesidades en esta lista, debe ser de buena a ir, pero tenga en cuenta nuestras recomendaciones en el vínculo anterior.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Necesita poner la implementación perimetral tras un firewall externo, pero le recomendamos tener dos firewall, uno externo y otro interno entre el entorno perimetral y el entorno interno. Toda la documentación en nuestros escenarios tendrá dos firewall. Le recomendamos disponer de dos firewall porque así se asegura un enrutamiento estricto de un perímetro de red a otro y multiplica la protección de firewall para su red interna.
  
### <a name="directors"></a>Directores
<a name="Directors"> </a>

Este es un rol opcional. Puede ser un solo servidor o un grupo de servidores que ejecutan la función de Director. Es una función que se encuentra en el Skype para entorno Business Server interno.
  
El Director es un servidor interno de salto siguiente que recibe el tráfico SIP entrante desde los servidores de borde al que se destina para los servidores internos de Business Server Skype. Autentica previamente las solicitudes de entrada y las redirige a un servidor o grupo de servidores principales de un usuario. Esta autenticación previa le permite eliminar solicitudes de cuenta de usuario no identificadas.
  
¿Por qué importa? Es una función importante para un Director proteger servidores Standard Edition y servidores frontales o agrupaciones de Front-End de tráfico malintencionado, como los ataques de denegación de servicio (DoS). Si la red está desborda por el tráfico externo no válido, el tráfico se detiene en el Director.
  
### <a name="load-balancers"></a>Equilibradores de carga
<a name="LoadBalancers"> </a>

El Skype para Business Server 2015 escala consolidada topología de borde está optimizado para DNS equilibrio de carga para implementaciones nuevas y se recomienda esto. Si necesita alta disponibilidad, se recomienda utilizar un equilibrador de carga de hardware para una situación específica:
  
- Mensajería unificada de Exchange para los usuarios remotos con mensajería unificada de Exchange **anteriores** a Exchange de 2013.
    
> [!IMPORTANT]
> Es fundamental que tenga en cuenta que no puede mezclar equilibradores de carga. En su Skype para entorno Business Server todas las interfaces deben utilizar DNS o HLB. 
  
> [!NOTE]
> Servidor de Direct devolver NAT (DSR) no es compatible para Skype para Business Server 2015. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos de equilibrador de carga de hardware para ejecutar el borde servidores Edge servidores / servicio perimetral V

De cualquier servidor de borde con el servicio de borde V, éstos son los requisitos:
  
- Deshabilite la aplicación del algoritmo de Nagle TCP para los puertos 443 internos y externos. La aplicación del algoritmo de Nagle es la combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.
    
- Deshabilite la aplicación del algoritmo de Nagle TCP para el intervalo de puertos externos 50000 - 59999.
    
- No use la NAT en los firewalls internos ni externos.
    
- La interfaz interna del borde debe estar en una red distinta a la interfaz externa del servidor perimetral y se debe deshabilitar el enrutamiento entre ellos.
    
- La interfaz externa de cualquier servidor perimetral ejecuta el A / servicio V perimetral debe utilizar direcciones IP enrutables públicamente y no NAT o traducción en cualquiera de las direcciones IP externas de borde de puerto.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

Como con Lync Server 2013, Skype para Business Server 2015 no tiene muchos requisitos de afinidad basada en cookies. Por lo que no necesitará utilizar una persistencia basada en cookies **a menos que** va a tener grupos de servidores de fondo frontal de Lync Server 2010 o Front-End en su Skype para entorno Business Server. Tienen afinidad basada en cookies en el método de configuración recomendada para Lync Server 2010.
  
> [!NOTE]
> Si decide activar la afinidad basada en cookies en su HLB, no habrá problemas, incluso si su entorno no la necesita. 
  
Si su entorno **no** necesita la afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, Establece el **encabezado de host directa** en **True**. Esto garantizará que se transfiera la URL original.
    
Para las implementaciones que **sí** necesitan la afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, Establece el **encabezado de host directa** en **True**. Esto garantizará que se transfiera la URL original.
    
- El hardware carga equilibrador cookie **no debe** marcarse httpOnly.
    
- El hardware carga equilibrador cookie **no debe** tener una fecha de caducidad.
    
- El hardware carga equilibrador cookie **debe** denominarse **MS WSMAN** (es decir, el valor que se espera que los servicios Web, y no se puede cambiar).
    
- El hardware carga equilibrador cookie **debe** establecerse en cada respuesta HTTP para que la solicitud HTTP entrante no tiene una cookie, independientemente de si una respuesta HTTP anterior en esa misma conexión TCP ha recibido una cookie. Si el equilibrador de carga de hardware optimiza insertar de cookie para producir sólo una vez por cada conexión TCP, esa optimización **no debe** utilizarse.
    
> [!NOTE]
> Es típico para las configuraciones de HLB utilizar la afinidad de origen y 20 minutos TCP duración de la sesión, que es el adecuado para Skype para Business Server 2015 y sus clientes, ya que se mantiene el estado de sesión mediante el uso del cliente o interacción de la aplicación. 
  
Si se implementan dispositivos móviles, el HLB debe poder equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, debe poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).
  
> [!IMPORTANT]
> Los HLB F5 tienen una característica denominada OneConnect, que garantiza que cada solicitud dentro de una conexión TCP se carga de forma equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor HLB admita la misma característica. Las últimas aplicaciones móviles iOS requieren la versión TLS 1.2. Si necesita más información, F5 proporciona configuración específica para esto. 
  
Aquí son los requisitos de HLB para el Director (opcional) y el grupo de Front-End Web Services (obligatorio):
  
- Para su VIPs interna de servicios Web, establecer persistencia Source_addr (puerto interno 80, 443) en el HLB. Para Skype para Business Server 2015, persistencia Source_addr significa que varias conexiones procedentes de una única dirección IP siempre se envían a un servidor, para mantener el estado de sesión.
    
- Use un tiempo de espera de inactividad TCP de 1.800 segundos.
    
- En el servidor de seguridad entre el proxy inverso y HLB el siguiente salto de la agrupación, cree una regla para permitir https: tráfico en el puerto 4443, desde el proxy inverso para su HLB. El HLB debe configurarse de modo que escuche los puertos 80, 443 y 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumen de los requisitos de afinidad del HLB

|**Ubicación del cliente o usuario**|**Requisitos de afinidad FQDN de los servicios web externo**|**Servicios web interno requisitos de afinidad FQSN**|
|:-----|:-----|:-----|
|Skype para el negocio de la aplicación Web (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Skype para el negocio de la aplicación Web (sólo para usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Skype para el negocio de la aplicación Web (sólo para usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Supervisión de puertos para HLB

Definir la supervisión de puertos en los equilibradores de carga del hardware para determinar cuando ya no están disponibles, debido a un error de hardware o comunicaciones de servicios específicos. Por ejemplo, si se detiene el servicio de servidor Front-End (RTCSRV) porque se produce un error en el grupo de servidor Front-End o Front-End, la supervisión de HLB debe también dejar de recibir tráfico de los servicios Web. Debe implementar la supervisión de puertos en el HLB para supervisar lo siguiente para la interfaz externa del HLB:
  
|**IP/puerto virtual**|**Puerto de nodo**|**Monitor de equipo o nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<grupo\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<grupo\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

Hemos analizado los requisitos de hardware y software de servidor perimetral en nuestra documentación de [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) general.
  
## <a name="collocation"></a>Colocación

Hemos abarcado colocación de servidores de borde en nuestra documentación de [Aspectos básicos de la topología para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

