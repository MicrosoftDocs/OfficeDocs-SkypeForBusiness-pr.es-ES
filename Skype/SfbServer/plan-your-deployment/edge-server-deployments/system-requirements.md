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
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221030"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos del sistema del servidor perimetral en Skype empresarial Server
 
**Resumen:** Obtenga información sobre los requisitos del sistema para el servidor perimetral en Skype empresarial Server.
  
En lo que respecta a la implementación del servidor perimetral de Skype empresarial Server, estas son las cosas que debe realizar para el servidor o los servidores que están en el propio entorno, así como para planear la estructura del entorno. Para obtener más información acerca de la topología, los certificados DNS y otros aspectos relacionados con la infraestructura, consulte la documentación sobre los requisitos del entorno.
  
## <a name="components"></a>Componentes

Al hablar del entorno del servidor perimetral, hacemos referencia a componentes que, en la mayoría de los casos, se implementan en una red perimetral (es decir, se encuentra en un grupo de trabajo o en un dominio que está fuera de la estructura de dominios de Skype empresarial Server).
  
Teniendo esto en cuenta, estos son los componentes que va a tener en cuenta para implementar el servidor perimetral correctamente:
  
- [Servidores perimetrales](system-requirements.md#EdgeServers)
    
- [Proxies inversos](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directores](system-requirements.md#Directors) (estos son opcionales y, si están incluidos, se ubicarán en la red interna)
    
- [Equilibradores de carga](system-requirements.md#LoadBalancers) (puede tener el equilibrio de carga de DNS o un equilibrador de carga de hardware (HLB), pero para un solo servidor perimetral, esto no es necesario)
    
Tenemos más detalles en cada una de las siguientes opciones:
  
### <a name="edge-servers"></a>Servidores perimetrales
<a name="EdgeServers"> </a>

Estos son los servidores de Skype empresarial que se implementan en el entorno perimetral. Su rol es enviar y recibir tráfico de red a usuarios externos para los servicios ofrecidos por su implementación de Skype empresarial Server interna. Para hacer esto correctamente, se ejecutará cada servidor perimetral:
  
- **Servicio perimetral de acceso**: proporciona un único punto de conexión de confianza para el tráfico SIP (Protocolo de inicio de sesión) saliente y entrante.
    
- **Servicio perimetral de conferencia web**: permite a los usuarios externos unirse a reuniones hospedadas en su entorno interno de Skype empresarial Server.
    
- **Servicio perimetral a/V**: hace que el audio, vídeo, uso compartido de aplicaciones y transferencia de archivos estén disponibles para los usuarios externos.
    
- **Servicio de proxy XMPP**: acepta y envía mensajes del protocolo extensible de mensajería y presencia (XMPP) a y desde socios federados de XMPP configurados.
    
Los usuarios externos autorizados pueden usar los servidores perimetrales para conectarse a la implementación de Skype empresarial Server interna, pero, de lo contrario, no proporcionan ningún otro acceso a la red interna para nadie.
  
> [!NOTE]
> Los servidores perimetrales se implementan para proporcionar conexiones para clientes de Skype empresarial habilitados y otros servidores perimetrales (en escenarios de Federación). No puede conectarse desde otros tipos de cliente o de servidor de punto final. El servidor de puerta de enlace XMPP puede permitir conexiones con socios XMPP configurados. Pero, de nuevo, son los únicos tipos de cliente y de Federación que funcionarán. 

> [!NOTE]
> Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019. Consulte [migrar la Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.
  
### <a name="reverse-proxies"></a>Proxies inversos
<a name="ReverseProxies"> </a>

Un servidor de proxy inverso (RP) no tiene rol de servidor de Skype empresarial, pero es un componente esencial de una implementación de servidor perimetral. Un proxy inverso permite a los usuarios externos:
  
- Conéctese a reuniones o conferencias de acceso telefónico local con direcciones URL sencillas.
    
- Descargue el contenido de la reunión.
    
- Expanda grupos de distribución.
    
- obtener certificados basados en usuario para la autenticación basada en certificados de cliente
    
- descargar archivos desde el servidor de la libreta de direcciones o para enviar consultas al servicio de consulta Web de la libreta de direcciones.
    
- Obtenga actualizaciones para el software de cliente y de dispositivos.
    
Y para dispositivos móviles:
  
- permite detectar automáticamente los servidores front-end que ofrecen servicios de movilidad.
    
- permite las notificaciones de inserción de Microsoft 365 u Office 365 a dispositivos móviles.
    
Puede encontrar nuestras recomendaciones actuales de proxy inverso en la página [infraestructura de telefonía para Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Por lo tanto, el proxy inverso:
  
- debe poder usar la seguridad de la capa de transporte (TLS) que se ha agregado a su entorno a través de certificados públicos para conectarse a los servicios web externos publicados de:
    
  - Director o grupo de directores
    
  - Servidor front-end o grupo de servidores front-end
    
- debe ser capaz de publicar sitios Web internos con certificados para cifrado o publicarlos a través de un medio sin cifrar, si es necesario.
    
- debe poder publicar un sitio web hospedado internamente de forma externa mediante un nombre de dominio completo (FQDN).
    
- debe ser capaz de publicar todo el contenido de su sitio web hospedado. De forma predeterminada, puede usar la **/\\** Directiva *, que es reconocida por la mayoría de los servidores web para indicar "publicar todo el contenido en el servidor Web". También puede modificar la Directiva (por ejemplo, * */Uwca/ \\ * * *), lo que significa "publicar todo el contenido en el directorio virtual Ucwa".
    
- debe requerir conexiones TLS con los clientes que soliciten contenido de su sitio Web publicado.
    
- tiene que aceptar certificados con entradas de nombre alternativo de sujeto (SAN).
    
- debe ser capaz de permitir el enlace de un certificado a un agente de escucha o a una interfaz a través de la cual se resolverá el FQDN de servicios web externos. Las configuraciones de la escucha son preferibles a las interfaces. Se pueden configurar varios agentes de escucha en una sola interfaz.
    
- debe permitir la configuración de la administración del encabezado de host. A menudo, el encabezado de host original enviado por el cliente que realiza la solicitud debe pasar de forma transparente, en lugar de ser modificado por el proxy inverso.
    
- debe permitir el puente de tráfico TLS desde un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443). El proxy inverso puede descifrar el paquete en su recepción y, a continuación, volver a cifrar el paquete en el envío.
    
- debe permitir el puente de tráfico TCP no cifrado desde un puerto (por ejemplo, TCP 80) a otro (por ejemplo, TCP 8080).
    
- debe permitir la configuración de autenticación NTLM, o aceptarla, sin autenticación y autenticación de paso a través.
    
Si el proxy inverso puede satisfacer todas las necesidades de esta lista, debe estar listo, pero tenga en cuenta las recomendaciones que se indican en el vínculo anterior.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Debe colocar la implementación perimetral detrás de un firewall externo, pero se recomienda tener dos firewalls, uno externo y otro interno entre el entorno perimetral y el entorno interno. Toda nuestra documentación en nuestros escenarios tendrá dos firewalls. Le recomendamos dos firewalls, ya que garantiza un enrutamiento estricto desde un perímetro de red al otro y dobla la protección del firewall de la red interna.
  
### <a name="directors"></a>Reparto
<a name="Directors"> </a>

Este es un rol opcional. Puede ser un solo servidor o un grupo de servidores que ejecuten el rol de director. Se trata de un rol que se encuentra en el entorno de Skype empresarial Server interno.
  
El director es un servidor interno del próximo salto que recibe tráfico SIP entrante de los servidores perimetrales destinados a los servidores internos de Skype empresarial Server. Realiza la autenticación previa de las solicitudes entrantes y las redirige a un servidor o grupo de servidores principales de un usuario. Esta autenticación previa permite quitar las solicitudes de cuenta de usuario no identificadas.
  
¿Por qué importa? Una función importante para un director es proteger los servidores Standard Edition y los servidores front-end o los grupos de servidores front-end del tráfico malintencionado, como los ataques de denegación de servicio (DoS). Si la red está inundada con tráfico externo no válido, el tráfico se detiene en el director.
  
### <a name="load-balancers"></a>Equilibradores de carga
<a name="LoadBalancers"> </a>

La topología perimetral consolidada escalada de Skype empresarial Server está optimizada para el equilibrio de carga de DNS para implementaciones nuevas y se recomienda esto. Si necesita alta disponibilidad, se recomienda usar un equilibrador de carga de hardware para una situación específica:
  
- Mensajería unificada de Exchange para usuarios remotos mediante la mensajería unificada de Exchange **antes** de Exchange 2013.
    
> [!IMPORTANT]
> Es fundamental tener en cuenta que no se pueden mezclar equilibradores de carga. En su entorno de Skype empresarial Server, todas las interfaces deben usar DNS o HLB. 
  
> [!NOTE]
> La NAT de Direct Server Return (DSR) no es compatible con Skype empresarial Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos del equilibrador de carga de hardware para servidores perimetrales servidores perimetrales que ejecutan el servicio perimetral A/V

Para cualquier servidor perimetral que ejecute el servicio perimetral A/V, estos son los requisitos:
  
- Desactive TCP Nagle para los puertos internos y externos 443 (Nagle es el proceso de combinar varios paquetes pequeños en un único paquete más grande para una transmisión más eficaz).
    
- Desactive TCP Nagle para el intervalo de puertos externo 50000-59999.
    
- No use NAT en los firewalls internos o externos.
    
- La interfaz perimetral interna debe estar en una red distinta a la interfaz externa del servidor perimetral y el enrutamiento entre ellas debe estar deshabilitado.
    
- La interfaz externa de todos los servidores perimetrales que ejecutan el servicio perimetral A/V debe usar direcciones IP enrutables públicamente y no NAT o traducción de puerto en ninguna de las direcciones IP externas del servidor perimetral.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

Skype empresarial Server no tiene muchos requisitos de afinidad basada en cookies. Por lo tanto, no es necesario usar una persistencia basada en cookies **a menos** que (y esto es Skype empresarial Server 2015-específico), tendrá Lync Server 2010 servidores front-end o grupos de servidores front-end en su entorno de Skype empresarial Server. Necesitarían la afinidad basada en cookies en el método de configuración recomendado para Lync Server 2010.
  
> [!NOTE]
> Si decide activar la afinidad basada en cookies en su HLB, no habrá un problema, incluso si su entorno no la necesita. 
  
Si su entorno **no** necesita la afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, establezca el **encabezado de host de reenvío** en **true**. Esto garantizará que se reenviará la dirección URL original.
    
Para las implementaciones que **sí** necesitan la afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, establezca el **encabezado de host de reenvío** en **true**. Esto garantizará que se reenviará la dirección URL original.
    
- La cookie del equilibrador de carga de hardware **no debe** marcarse httpOnly.
    
- La cookie del equilibrador de carga de hardware **no debe** tener una fecha de expiración.
    
- La cookie del equilibrador de carga de hardware **debe** tener el nombre **MS-WSMAN** (este es el valor esperado por los servicios web y no se puede cambiar).
    
- La cookie del equilibrador de carga de hardware **debe** establecerse en todas las respuestas http para las que la solicitud HTTP entrante no tiene una cookie, independientemente de si una respuesta http anterior de la misma conexión TCP ha recibido una cookie. Si su equilibrador de carga de hardware optimiza la inserción de cookies para que solo ocurra una vez por cada conexión TCP, esa optimización **no debe** usarse.
    
> [!NOTE]
> Es habitual que las configuraciones de HLB usen la afinidad de origen y la duración de sesión TCP de 20 minutos, que es adecuada para Skype empresarial Server y sus clientes, ya que el estado de sesión se mantiene a través del uso del cliente o la interacción de la aplicación. 
  
Si está implementando dispositivos móviles, su HLB debe poder equilibrar la carga de solicitudes individuales dentro de una sesión TCP (de hecho, debe poder equilibrar la carga de una solicitud individual en función de la dirección IP de destino).
  
> [!IMPORTANT]
> F5 HLB tener una característica denominada OneConnect. Garantiza que cada solicitud dentro de una conexión TCP se carga con equilibrio individual. Si está implementando dispositivos móviles, asegúrese de que el proveedor de HLB admite la misma funcionalidad. Las aplicaciones móviles de iOS más recientes requieren la versión 1,2 de TLS. Si necesita saber más, F5 proporciona una configuración específica para este. 
  
Estos son los requisitos de HLB para los servicios web del grupo de servidores front-end (opcional) y director (obligatorio):
  
- Para los VIP de servicios Web internos, establezca la persistencia de Source_addr (puerto interno 80, 443) en su HLB. En el caso de Skype empresarial Server, la persistencia de la Source_addr significa que se envían siempre varias conexiones procedentes de una única dirección IP a un servidor para mantener el estado de la sesión.
    
- Use un tiempo de espera de inactividad de TCP de 1800 segundos.
    
- En el Firewall entre el proxy inverso y el HLB del grupo de servidores del próximo salto, cree una regla para permitir el tráfico https: en el puerto 4443, desde el proxy inverso hasta su HLB. Su HLB debe estar configurada para escuchar en los puertos 80, 443 y 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumen de los requisitos de afinidad de HLB

|**Ubicación de cliente/usuario**|**Requisitos de afinidad del FQDN de servicios web externos**|**Requisitos de afinidad de FQSN de servicios Web internos**|
|:-----|:-----|:-----|
|Aplicación Web de Skype empresarial (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Aplicación Web de Skype empresarial (solo usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Aplicación Web de Skype empresarial (solo usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Supervisión de puertos para HLB

La supervisión de puertos se define en los equilibradores de carga de hardware para determinar cuándo los servicios específicos ya no están disponibles, debido a errores de hardware o de comunicaciones. Por ejemplo, si el servicio de servidor front-end (RTCSRV) se detiene debido a un error en el servidor front-end o en el grupo de servidores front-end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios Web. Debe implementar la supervisión de puertos en el HLB para supervisar lo siguiente para la interfaz externa de HLB:
  
|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs de grupo \>  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs de grupo \>  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

Hemos cubierto los requisitos de hardware y software del servidor perimetral en los requisitos generales del [servidor para Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y [los requisitos del sistema para la documentación de skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Combinación

Hemos cubierto el servidor perimetral combinación en nuestra documentación [básica sobre la topología de Skype empresarial Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

