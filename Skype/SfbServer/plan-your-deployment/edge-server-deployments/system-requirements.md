---
title: Requisitos del sistema del servidor perimetral en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre los requisitos del sistema para el servidor perimetral en Skype Empresarial Server.'
ms.openlocfilehash: dc1541604a4a26c9af3c184282648ef2f96469fa4346a6b6cc379eed2f5f023f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306981"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos del sistema del servidor perimetral en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre los requisitos del sistema para el servidor perimetral en Skype Empresarial Server.
  
Cuando se trata de la implementación del servidor perimetral de Skype Empresarial Server, estas son las cosas que deberá hacer para el servidor o los servidores que se encuentran en el propio entorno, así como la planeación de la estructura del entorno. Para obtener más información sobre topología, DNS, certificados y otros problemas de infraestructura, consulte la documentación de requisitos del entorno.
  
## <a name="components"></a>Componentes

Al hablar del entorno de servidor perimetral, estamos haciendo referencia a componentes que, en su mayoría, están implementados en una red perimetral (es decir, en un grupo de trabajo o un dominio que está fuera de la estructura de dominio de Skype Empresarial Server).
  
Teniendo esto en cuenta, estos son los componentes que tendrá que tener en cuenta para implementar el servidor perimetral correctamente:
  
- [Servidores perimetrales](system-requirements.md#EdgeServers)
    
- [Proxy inversos](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directores](system-requirements.md#Directors) (estos son opcionales y, si se incluyen, se ubicarán en la red interna)
    
- [Equilibradores de carga](system-requirements.md#LoadBalancers) (puede tener equilibrio de carga DNS o un equilibrador de carga de hardware (HLB), pero para un solo servidor perimetral, esto no es necesario)
    
A continuación, tenemos más detalles sobre cada uno de estos:
  
### <a name="edge-servers"></a>Servidores perimetrales
<a name="EdgeServers"> </a>

Estos son los Skype Empresarial implementados en el entorno perimetral. Su función es enviar y recibir tráfico de red a usuarios externos para los servicios ofrecidos por la implementación Skype Empresarial Server interna. Para hacerlo correctamente, cada servidor perimetral se ejecuta:
  
- **Servicio perimetral de** acceso: proporciona un único punto de conexión de confianza para el tráfico de protocolo de inicio de sesión (SIP) saliente y entrante.
    
- **Servicio perimetral de conferencia web:** permite a los usuarios externos unirse a reuniones hospedadas en el entorno Skype Empresarial Server interno.
    
- **Servicio perimetral A/V:** hace que el audio, el vídeo, el uso compartido de aplicaciones y la transferencia de archivos estén disponibles para usuarios externos.
    
- **Servicio de proxy XMPP:** acepta y envía mensajes de protocolo extensible de mensajería y presencia (XMPP) a y desde socios federados XMPP configurados.
    
Los usuarios externos autorizados pueden usar los servidores perimetrales para conectarse a la implementación Skype Empresarial Server interna, pero, de lo contrario, no proporcionan ningún otro acceso a la red interna para nadie.
  
> [!NOTE]
> Los servidores perimetrales se implementan para proporcionar conexiones para clientes Skype Empresarial y otros servidores perimetrales (en escenarios de federación). No puede conectarse desde otros tipos de cliente o servidor de punto final. El servidor de puerta de enlace XMPP puede permitir conexiones con socios XMPP configurados. Pero, de nuevo, estos son los únicos tipos de cliente y federación que funcionarán. 

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.
  
### <a name="reverse-proxies"></a>Proxy inversos
<a name="ReverseProxies"> </a>

Un servidor de proxy inverso (RP) no tiene Skype Empresarial Server función, pero es un componente esencial de una implementación de servidor perimetral. Un proxy inverso permite a los usuarios externos:
  
- conectarse a reuniones o conferencias de acceso telefónico mediante direcciones URL sencillas.
    
- descargar contenido de la reunión.
    
- expandir grupos de distribución.
    
- obtener certificados basados en usuario para la autenticación basada en certificados de cliente
    
- descargar archivos desde el servidor de libreta de direcciones o enviar consultas al servicio de consulta web de libreta de direcciones.
    
- obtener actualizaciones del software del cliente y del dispositivo.
    
Y para dispositivos móviles:
  
- les permite detectar automáticamente los servidores front-end que ofrecen servicios de movilidad.
    
- habilita las notificaciones de inserción desde Microsoft 365 o Office 365 a dispositivos móviles.
    
Nuestras recomendaciones de proxy inverso actuales se pueden encontrar en la página Infraestructura de telefonía [para Skype Empresarial](../../../SfbPartnerCertification/certification/infra-gateways.md) servidor. Por lo tanto, el proxy inverso:
  
- debe poder usar la seguridad de la capa de transporte (TLS) que se introduce en el entorno a través de certificados públicos para conectarse a los servicios web externos publicados de:
    
  - Director o grupo de directores
    
  - Servidor front-end o grupo de servidores front-end
    
- debe poder publicar sitios web internos con certificados para el cifrado o publicarlos en un medio sin cifrar, si es necesario.
    
- debe poder publicar un sitio web hospedado internamente externamente mediante un nombre de dominio completo (FQDN).
    
- debe poder publicar todo el contenido del sitio web hospedado. De forma predeterminada, puede usar la directiva _, que reconoce la mayoría de los servidores web para significar "Publicar todo el **/\\** contenido en el servidor web". También puede modificar la directiva, por ejemplo, _*/Uwca/ ***, que significa "Publicar todo el contenido en el directorio \\ virtual Ucwa".
    
- debe requerir conexiones TLS con clientes que soliciten contenido del sitio web publicado.
    
- debe aceptar certificados con entradas de nombre alternativo de sujeto (SAN).
    
- debe poder permitir el enlace de un certificado a una escucha o interfaz a través de la cual se resolverá el FQDN de los servicios web externos. Las configuraciones de escucha son preferibles a las interfaces. Muchos agentes de escucha se pueden configurar en una sola interfaz.
    
- debe permitir la configuración del control de encabezados de host. A menudo, el encabezado host original enviado por el cliente solicitante debe pasarse de forma transparente, en lugar de ser modificado por el proxy inverso.
    
- debe permitir el puente del tráfico TLS desde un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443). El proxy inverso puede descifrar el paquete al recibirlo y, a continuación, volver a cifrar el paquete al enviar.
    
- debe permitir el puente del tráfico TCP sin cifrar de un puerto (por ejemplo, TCP 80) a otro (por ejemplo, TCP 8080).
    
- debe permitir la configuración de la autenticación NTLM, sin autenticación y la autenticación de paso a través, o aceptarla.
    
Si su proxy inverso puede satisfacer todas las necesidades de esta lista, debe estar bien, pero tenga en cuenta nuestras recomendaciones en el vínculo proporcionado anteriormente.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Debe colocar la implementación perimetral detrás de un firewall externo, pero se recomienda tener dos firewalls, uno externo y otro interno entre el entorno perimetral y el entorno interno. Toda la documentación de nuestros escenarios tendrá dos firewalls. Se recomiendan dos firewalls porque garantiza el enrutamiento estricto de un borde de red al otro y duplica la protección del firewall para la red interna.
  
### <a name="directors"></a>Directores
<a name="Directors"> </a>

Este es un rol opcional. Puede ser un único servidor o un grupo de servidores que ejecuten el rol Director. Es un rol que se encuentra en el entorno Skype Empresarial Server interno.
  
El Director es un servidor interno del próximo salto que recibe tráfico SIP entrante de los servidores perimetrales destinados a Skype Empresarial Server servidores internos. Autentica previamente las solicitudes entrantes y las redirige al servidor o grupo de servidores principal de un usuario. Esta autenticación previa permite colocar solicitudes de cuenta de usuario no identificadas.
  
¿Por qué es importante? Una función importante para un director es proteger Standard Edition servidores y servidores front-end o grupos de servidores front-end contra tráfico malintencionado, como ataques de denegación de servicio (DoS). Si la red está inundada de tráfico externo no válido, el tráfico se detiene en el Director.
  
### <a name="load-balancers"></a>Equilibradores de carga
<a name="LoadBalancers"> </a>

La Skype Empresarial Server perimetral consolidada a escala está optimizada para el equilibrio de carga DNS para las implementaciones nuevas, y se recomienda esto. Si necesita alta disponibilidad, se recomienda usar un equilibrador de carga de hardware para una situación específica:
  
- Exchange Mensajería unificada para usuarios remotos que usan Exchange um **antes** de Exchange 2013.
    
> [!IMPORTANT]
> Es fundamental tener en cuenta que no puede mezclar equilibradores de carga. En el Skype Empresarial Server todas las interfaces deben usar DNS o HLB. 
  
> [!NOTE]
> Nat de devolución directa de servidor (DSR) no se admite para Skype Empresarial Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisitos del equilibrador de carga de hardware para servidores perimetrales servidores perimetrales que ejecutan el servicio perimetral A/V

Para cualquier servidor perimetral que ejecute el servicio perimetral A/V, estos son los requisitos:
  
- Desactivar la nagling TCP para los puertos internos y externos 443 (la nagling es el proceso de combinar varios paquetes pequeños en un único paquete más grande para una transmisión más eficiente).
    
- Desactivar la nagling TCP para el intervalo de puertos externos 50000 - 59999.
    
- No use NAT en los firewalls internos o externos.
    
- La interfaz interna perimetral debe estar en una red diferente a la interfaz externa del servidor perimetral y el enrutamiento entre ellos debe deshabilitarse.
    
- La interfaz externa de cualquier servidor perimetral que ejecute el servicio perimetral A/V debe usar direcciones IP enrutables públicamente y ninguna nat o traducción de puertos en ninguna de las direcciones IP externas perimetrales.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

Skype Empresarial Server no tiene muchos requisitos de afinidad basados en cookies. Por lo tanto, no es necesario usar una persistencia basada en cookies a menos que **(y** esto es Skype Empresarial Server específico de 2015) vaya a tener servidores front-end de Lync Server 2010 o grupos de servidores front-end en su entorno Skype Empresarial Server. Necesitarán afinidad basada en cookies en el método de configuración recomendado para Lync Server 2010.
  
> [!NOTE]
> Si decide activar la afinidad basada en cookies para su HLB, no habrá ningún problema al hacerlo, incluso si el entorno no lo necesita. 
  
Si el entorno **no necesita** afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, establezca **Forward host header** en **True**. Esto garantizará que se reenvía la dirección URL original.
    
Para implementaciones que **necesitan** afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, establezca **Forward host header** en **True**. Esto garantizará que se reenvía la dirección URL original.
    
- La cookie del equilibrador **de carga de** hardware no debe marcarse httpOnly.
    
- La cookie del equilibrador de carga de hardware **no debe** tener una fecha de expiración.
    
- La cookie del equilibrador de carga de **hardware** debe llamarse **MS-WSMAN** (este es el valor que esperan los servicios web y no se puede cambiar).
    
- La cookie del  equilibrador de carga de hardware debe establecerse en todas las respuestas HTTP para las que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en esa misma conexión TCP había obtenido una cookie. Si el equilibrador de carga de hardware optimiza la inserción de cookies para que solo se produzca una vez por conexión TCP, no se debe usar **esa** optimización.
    
> [!NOTE]
> Es típico que las configuraciones de HLB usen afinidad de origen y duración de sesión TCP de 20 minutos, lo que es bueno para Skype Empresarial Server y sus clientes, ya que el estado de sesión se mantiene a través del uso del cliente o la interacción de la aplicación. 
  
Si va a implementar dispositivos móviles, el HLB debe poder equilibrar la carga de las solicitudes individuales dentro de una sesión TCP (en efecto, debe ser capaz de equilibrar la carga de una solicitud individual en función de la dirección IP de destino).
  
> [!IMPORTANT]
> Los HLB F5 tienen una característica llamada OneConnect. Garantiza que cada solicitud dentro de una conexión TCP esté equilibrada de forma individual. Si va a implementar dispositivos móviles, asegúrese de que el proveedor de HLB admite la misma funcionalidad. Las últimas aplicaciones móviles de iOS requieren TLS versión 1.2. Si necesita saber más, F5 proporciona una configuración específica para esto. 
  
Estos son los requisitos de HLB para los servicios web de grupo de servidores front-end (opcionales) y (obligatorios):
  
- Para las VIP internas de servicios web, establezca Source_addr persistencia (puerto interno 80, 443) en el HLB. Por Skype Empresarial Server, Source_addr persistencia significa que varias conexiones procedentes de una única dirección IP siempre se envían a un servidor, para mantener el estado de sesión.
    
- Use un tiempo de espera de inactividad tcp de 1800 segundos.
    
- En el firewall entre el proxy inverso y el HLB del grupo de servidores de próximo salto, cree una regla para permitir https: tráfico en el puerto 4443, desde el proxy inverso a su HLB. El HLB debe configurarse para escuchar en los puertos 80, 443 y 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumen de los requisitos de afinidad de HLB

|**Ubicación de cliente/usuario**|**Requisitos de afinidad del FQDN de servicios web externos**|**Requisitos de afinidad FQSN de servicios web internos**|
|:-----|:-----|:-----|
|aplicación web de Skype Empresarial (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|aplicación web de Skype Empresarial (solo usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|aplicación web de Skype Empresarial (solo usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Supervisión de puertos para HLB

Se define la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo los servicios específicos ya no están disponibles, debido a errores de hardware o comunicaciones. Por ejemplo, si el servicio de servidor front-end (RTCSRV) se detiene porque se produce un error en el servidor front-end o el grupo de servidores front-end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios web. Debe implementar la supervisión de puertos en el HLB para supervisar lo siguiente para la interfaz externa de HLB:
  
|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

Hemos cubierto los requisitos de hardware y software del servidor perimetral en nuestros requisitos generales de servidor para [Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y requisitos del sistema para Skype Empresarial Server documentación de [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="collocation"></a>Colocación

Hemos cubierto la colocación de servidores perimetrales en nuestros [conceptos](../../plan-your-deployment/topology-basics/topology-basics.md) básicos de topología para obtener Skype Empresarial Server documentación.
