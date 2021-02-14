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
ms.openlocfilehash: e066249498febbd5e622546533f49422320c7c87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813770"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisitos del sistema del servidor perimetral en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre los requisitos del sistema para el servidor perimetral en Skype Empresarial Server.
  
En lo que respecta a la implementación del servidor perimetral de Skype Empresarial Server, estas son las cosas que debe hacer para el servidor o los servidores que están en el propio entorno, así como la planeación de la estructura del entorno. Para obtener más información sobre topología, DNS, certificados y otros problemas de infraestructura, consulte la documentación de requisitos del entorno.
  
## <a name="components"></a>Componentes

Al analizar el entorno del servidor perimetral, estamos haciendo referencia a componentes que, en su mayoría, están implementados en una red perimetral (es decir, está en un grupo de trabajo o en un dominio que está fuera de la estructura de dominio de Skype Empresarial Server).
  
Teniendo esto en cuenta, estos son los componentes que debes tener en cuenta para implementar el servidor perimetral correctamente:
  
- [Servidores perimetrales](system-requirements.md#EdgeServers)
    
- [Proxy inversos](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directores](system-requirements.md#Directors) (estos son opcionales y, si se incluyen, se ubicarán en la red interna)
    
- [Equilibradores de carga](system-requirements.md#LoadBalancers) (puede tener equilibrio de carga dns o un equilibrador de carga de hardware (HLB), pero para un único servidor perimetral, esto no es necesario)
    
A continuación, tenemos más detalles sobre cada uno de estos:
  
### <a name="edge-servers"></a>Servidores perimetrales
<a name="EdgeServers"> </a>

Estos son los servidores de Skype Empresarial implementados en su entorno perimetral. Su función es enviar y recibir tráfico de red a usuarios externos para los servicios ofrecidos por la implementación interna de Skype Empresarial Server. Para hacerlo correctamente, cada servidor perimetral ejecuta:
  
- **Servicio perimetral de** acceso: proporciona un único punto de conexión de confianza para el tráfico de protocolo de inicio de sesión (SIP) entrante y saliente.
    
- **Servicio perimetral de conferencia web:** permite a los usuarios externos unirse a reuniones hospedadas en su entorno interno de Skype Empresarial Server.
    
- **Servicio perimetral A/V:** hace que el audio, el vídeo, el uso compartido de aplicaciones y la transferencia de archivos estén disponibles para los usuarios externos.
    
- **Servicio de proxy XMPP:** acepta y envía mensajes de protocolo extensible de mensajería y presencia (XMPP) a socios federados XMPP configurados y desde estos.
    
Los usuarios externos autorizados pueden usar los servidores perimetrales para conectarse a la implementación interna de Skype Empresarial Server, pero, de lo contrario, no proporcionan ningún otro acceso a la red interna para nadie.
  
> [!NOTE]
> Los servidores perimetrales se implementan para proporcionar conexiones para clientes de Skype Empresarial habilitados y otros servidores perimetrales (en escenarios de federación). No puede conectarse desde otros tipos de cliente o servidor de extremo. El servidor de puerta de enlace XMPP puede permitir conexiones con socios XMPP configurados. Pero de nuevo, estos son los únicos tipos de cliente y federación que funcionarán. 

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de la federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.
  
### <a name="reverse-proxies"></a>Proxy inversos
<a name="ReverseProxies"> </a>

Un servidor de proxy inverso (RP) no tiene rol de Skype Empresarial Server, pero es un componente esencial de una implementación de servidor perimetral. Un proxy inverso permite a los usuarios externos:
  
- conectarse a reuniones o conferencias de acceso telefónico mediante direcciones URL sencillas.
    
- descargar contenido de la reunión.
    
- expandir grupos de distribución.
    
- obtener certificados basados en el usuario para la autenticación basada en certificados de cliente
    
- descargar archivos desde el servidor de libreta de direcciones o enviar consultas al servicio de consulta web de libreta de direcciones.
    
- obtener actualizaciones de software de cliente y dispositivo.
    
Y para dispositivos móviles:
  
- les permite detectar automáticamente los servidores front-end que ofrecen servicios de movilidad.
    
- habilita las notificaciones de inserción de Microsoft 365 u Office 365 a dispositivos móviles.
    
Nuestras recomendaciones actuales de proxy inverso se pueden encontrar en la página [Infraestructura de telefonía para Skype](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) Empresarial. Por lo tanto, el proxy inverso:
  
- debe poder usar la seguridad de la capa de transporte (TLS) que se introduce en su entorno a través de certificados públicos para conectarse a los servicios web externos publicados de:
    
  - Director o grupo de directores
    
  - Servidor front-end o grupo de servidores front-end
    
- debe poder publicar sitios web internos con certificados para el cifrado o publicarlos por medios no cifrados, si es necesario.
    
- debe poder publicar un sitio web hospedado internamente externamente mediante un nombre de dominio completo (FQDN).
    
- debe poder publicar todo el contenido del sitio web hospedado. De forma predeterminada, puede usar la directiva _, que la mayoría de los servidores web reconocen como "Publicar todo el contenido **/\\** en el servidor web". También puede modificar la directiva, por ejemplo, _*/Uwca/, \\* *_ que significa "Publicar todo el contenido en el directorio virtual Ucwa".
    
- debe requerir conexiones TLS con clientes que solicitan contenido de su sitio web publicado.
    
- tiene que aceptar certificados con entradas de nombre alternativo de sujeto (SAN).
    
- debe poder permitir el enlace de un certificado a una escucha o interfaz a través de la cual se resolverá el FQDN de los servicios web externos. Las configuraciones de escucha son preferibles a las interfaces. Muchos agentes de escucha se pueden configurar en una sola interfaz.
    
- debe permitir la configuración del control de encabezados de host. A menudo, el encabezado host original enviado por el cliente solicitante debe pasarse de forma transparente, en lugar de ser modificado por el proxy inverso.
    
- debe permitir el puente del tráfico TLS desde un puerto definido externamente (por ejemplo, TCP 443) a otro puerto definido (por ejemplo, TCP 4443). El proxy inverso puede descifrar el paquete al recibirlo y, a continuación, cifrar el paquete al enviarlo.
    
- debe permitir el puente de tráfico TCP sin cifrar desde un puerto (por ejemplo, TCP 80) a otro (por ejemplo, TCP 8080).
    
- debe permitir la configuración o aceptación de autenticación NTLM, sin autenticación y autenticación de paso a través.
    
Si su proxy inverso puede satisfacer todas las necesidades de esta lista, debería estar lista, pero tenga en cuenta nuestras recomendaciones en el vínculo proporcionado anteriormente.
  
### <a name="firewalls"></a>Firewalls
<a name="Firewalls"> </a>

Debes colocar la implementación perimetral detrás de un firewall externo, pero te recomendamos tener dos firewalls, uno externo y otro interno entre el entorno perimetral y el entorno interno. Toda nuestra documentación en nuestros escenarios tendrá dos firewalls. Se recomiendan dos firewalls porque garantiza un enrutamiento estricto de un perímetro de red al otro y duplica la protección de firewall para la red interna.
  
### <a name="directors"></a>Directores
<a name="Directors"> </a>

Este es un rol opcional. Puede ser un único servidor o un grupo de servidores que ejecuten el rol director. Es un rol que se encuentra en el entorno interno de Skype Empresarial Server.
  
El director es un servidor interno del próximo salto que recibe tráfico SIP entrante de los servidores perimetrales destinados a los servidores internos de Skype Empresarial Server. Autentica previamente las solicitudes entrantes y las redirige al servidor o grupo de servidores principal de un usuario. Esta autenticación previa le permite quitar solicitudes de cuenta de usuario no identificadas.
  
¿Por qué es importante? Una función importante para un director es proteger los servidores Standard Edition y los servidores front-end o grupos de servidores front-end contra el tráfico malintencionado, como los ataques por denegación de servicio (DoS). Si la red está saturada de tráfico externo no válido, el tráfico se detiene en el director.
  
### <a name="load-balancers"></a>Equilibradores de carga
<a name="LoadBalancers"> </a>

La topología perimetral consolidada a escala de Skype Empresarial Server está optimizada para el equilibrio de carga de DNS para nuevas implementaciones, y se recomienda esto. Si necesita alta disponibilidad, se recomienda usar un equilibrador de carga de hardware para una situación específica:
  
- Mensajería unificada de Exchange para usuarios remotos que usan mensajería unificada de Exchange _ *anterior** a Exchange 2013.
    
> [!IMPORTANT]
> Es fundamental tener en cuenta que no puede mezclar equilibradores de carga. En su entorno de Skype Empresarial Server, todas las interfaces deben usar DNS o HLB. 
  
> [!NOTE]
> Nat de retorno directo del servidor (DSR) no es compatible con Skype Empresarial Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Requisitos del equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V

Para cualquier servidor perimetral que ejecute el servicio perimetral A/V, estos son los requisitos:
  
- Desactive el algoritmo de naje TCP para los puertos internos y externos 443 (la naginación es el proceso de combinar varios paquetes pequeños en un único paquete más grande para una transmisión más eficiente).
    
- Desactive el algoritmo de naje TCP para el intervalo de puertos externos 50000 - 59999.
    
- No use NAT en los firewalls internos o externos.
    
- La interfaz perimetral interna debe estar en una red diferente a la interfaz externa del servidor perimetral y el enrutamiento entre ellos debe deshabilitarse.
    
- La interfaz externa de cualquier servidor perimetral que ejecute el servicio perimetral A/V debe usar direcciones IP enrutables públicamente y ninguna NAT o traducción de puertos en ninguna de las direcciones IP externas perimetrales.
    
#### <a name="hlb-requirements"></a>Requisitos de HLB

Skype Empresarial Server no tiene muchos requisitos de afinidad basados en cookies. Por lo tanto, no necesita usar una persistencia basada en cookies a menos **que** (y esto es específico de Skype Empresarial Server 2015) vaya a tener servidores front-end de Lync Server 2010 o grupos de servidores front-end en su entorno de Skype Empresarial Server. Necesitarán afinidad basada en cookies en el método de configuración recomendado para Lync Server 2010.
  
> [!NOTE]
> Si decide activar la afinidad basada en cookies para su HLB, no habrá ningún problema al hacerlo, incluso si su entorno no la necesita. 
  
Si su entorno **no necesita afinidad** basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, establezca **el encabezado de host forward** en **True**. Esto garantizará que se reenvía la dirección URL original.
    
Para implementaciones que **necesitan** afinidad basada en cookies:
  
- En la regla de publicación de proxy inverso para el puerto 443, establezca **el encabezado de host forward** en **True**. Esto garantizará que se reenvía la dirección URL original.
    
- La cookie del equilibrador de carga de hardware **no debe** marcarse como httpOnly.
    
- La cookie del equilibrador de carga de hardware **no debe** tener una fecha de expiración.
    
- La cookie del equilibrador de carga de **hardware** debe llamarse **MS-WSMAN** (este es el valor que esperan los servicios web y no se puede cambiar).
    
- La cookie del  equilibrador de carga de hardware debe establecerse en cada respuesta HTTP para la que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en esa misma conexión TCP había recibido una cookie. Si el equilibrador de carga de hardware optimiza la inserción de cookies para que solo se produzca una vez por conexión TCP, no se **debe usar esa** optimización.
    
> [!NOTE]
> Es habitual que las configuraciones de HLB usen afinidad de origen y duración de sesión TCP de 20 minutos, lo que es adecuado para Skype Empresarial Server y sus clientes, ya que el estado de sesión se mantiene a través del uso del cliente o la interacción de la aplicación. 
  
Si implementa dispositivos móviles, el HLB debe ser capaz de equilibrar la carga de solicitudes individuales en una sesión TCP (en efecto, debe poder equilibrar la carga de una solicitud individual en función de la dirección IP de destino).
  
> [!IMPORTANT]
> Los HAB F5 tienen una característica llamada OneConnect. Garantiza que cada solicitud dentro de una conexión TCP tiene equilibrio de carga individual. Si va a implementar dispositivos móviles, asegúrese de que su proveedor de HLB admite la misma funcionalidad. Las aplicaciones móviles de iOS más recientes requieren TLS versión 1.2. Si necesitas saber más, F5 proporciona una configuración específica para esto. 
  
Estos son los requisitos de HLB para el director (opcional) y los servicios web del grupo de servidores front-end (obligatorios):
  
- Para las VIP de servicios web internos, establezca Source_addr persistente (puerto interno 80, 443) en el HLB. Para Skype Empresarial Server, Source_addr persistencia significa que se envían siempre varias conexiones procedentes de una única dirección IP a un servidor, para mantener el estado de sesión.
    
- Use un tiempo de espera de inactividad TCP de 1800 segundos.
    
- En el firewall entre el proxy inverso y el HLB del grupo de servidores del próximo salto, cree una regla para permitir el tráfico https: en el puerto 4443, desde el proxy inverso al HLB. El HLB debe configurarse para escuchar en los puertos 80, 443 y 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Resumen de los requisitos de afinidad de HLB

|**Ubicación de cliente/usuario**|**Requisitos de afinidad del FQDN de servicios web externos**|**Requisitos de afinidad FQSN de servicios web internos**|
|:-----|:-----|:-----|
|Aplicación web de Skype Empresarial (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Aplicación web de Skype Empresarial (solo usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Aplicación web de Skype Empresarial (solo usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Supervisión de puertos para HAB

La supervisión de puertos se define en los equilibradores de carga de hardware para determinar cuándo determinados servicios ya no están disponibles, debido a errores de hardware o comunicaciones. Por ejemplo, si el servicio de servidor front-end (RTCSRV) se detiene porque se produce un error en el servidor front-end o el grupo de servidores front-end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios web. Debe implementar la supervisión de puertos en el HLB para supervisar lo siguiente para la interfaz externa de HLB:
  
|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

Hemos cubierto los requisitos de hardware y software del servidor perimetral en nuestros requisitos generales del servidor para [Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y los requisitos del sistema para la documentación de [Skype Empresarial Server 2019.](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="collocation"></a>Colocación

Hemos cubierto la colocación del servidor perimetral en nuestra documentación [de Topology Basics for Skype for Business Server.](../../plan-your-deployment/topology-basics/topology-basics.md)
  

