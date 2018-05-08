---
title: Requisitos del equilibrio de carga para Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/21/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Resumen: Revise la carga equilibrio consideraciones antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: 5d5c1c58746fe9656a0eb123d211ed5b3f330063
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Requisitos del equilibrio de carga para Skype Empresarial
 
**Resumen:** Revise la carga equilibrio consideraciones antes de implementar Skype para Business Server 2015.
  
El equilibrio de carga distribuye el tráfico entre los servidores en un grupo de servidores. Si tiene grupos de servidores Front-End, grupos de servidores de mediación o grupos de servidores perimetrales, necesita implementar el equilibrio de carga para estos grupos de servidores.
  
Skype para Business Server admite dos tipos de soluciones para el tráfico de cliente a servidor de equilibrio de carga: equilibrio de carga de sistema de nombres de dominio (DNS) y a menudo (abreviado como HLB) de equilibrio de carga de hardware. Carga de DNS equilibrio ofrece varias ventajas, incluyendo administración más sencilla, más eficaz solución de problemas y la capacidad de aislar gran parte de su Skype para el tráfico de servidor empresarial de los posibles problemas de equilibrador de carga de hardware.
  
Decidir por sí mismo qué solución de equilibrio de carga es adecuada para cada grupo de servidores en la implementación, pero tenga en cuenta las siguientes restricciones: 
  
- La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz y el equilibrio de carga de hardware en la otra.
    
- Algunos tipos de tráfico requieren un equilibrador de carga de hardware. Por ejemplo, el tráfico HTTP requiere un equilibrador de carga de hardware en lugar del equilibrio de carga de DNS. El equilibrio de carga de DNS no funciona con tráfico web del cliente al servidor.
    
Si decide usar el equilibrio de carga de DNS para un grupo, pero aún tiene que implementar equilibradores de carga de hardware para el tráfico, como el tráfico HTTP, la administración de los equilibradores de carga de hardware será mucho más sencilla. Por ejemplo, configurar el equilibrador de carga de hardware será más sencillo, pues solamente administrará el tráfico HTTPS y HTTP, mientras que el equilibrio de carga de DNS administrará todos los demás protocolos. Para obtener información detallada, vea [El equilibrio de carga de DNS](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Para el tráfico de servidor a servidor, Skype para Business Server usa el equilibrio de carga conscientes de la topología. Servidores leen la topología publicada en el almacén de Administración Central para obtener los FQDN de los servidores de la topología y distribuyen automáticamente el tráfico entre los servidores. Los administradores no necesitan configurar ni administrar este tipo de equilibrio de carga. 
  
Si utiliza el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente con solo quitar las entradas de direcciones IP del FQDN del grupo de servidores. También es preciso quitar la entrada de DNS para el equipo. 
  
## <a name="hardware-load-balancer-requirements"></a>Requisitos del equilibrador de carga de hardware

El Skype para Business Server escalada consolidada perimetral topología está optimizada para el equilibrio de carga DNS para las nuevas implementaciones federar principalmente con otras organizaciones con Skype para Business Server o Lync Server. Si la alta disponibilidad es necesaria para cualquiera de los siguientes escenarios, se debe usar un equilibrador de carga de hardware en grupos de servidores perimetrales para lo siguiente: 
  
- Federación con organizaciones que ejecutan Office Communications Server 2007 R2 u Office Communications Server 2007
    
- Mensajería unificada de Exchange para los usuarios remotos con mensajería unificada de Exchange antes de Exchange 2010 con SP1
    
- Conectividad con usuarios de mensajería instantánea (MI) pública
    
> [!IMPORTANT]
> No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Necesita utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces. 
  
> [!NOTE]
> Si usa un equilibrador de carga de hardware, el equilibrador de carga que se haya implementado para las conexiones con la red interna necesitará configurarse para que solo equilibre la carga del tráfico de los servidores que ejecuten el servicio perimetral de acceso y el servicio perimetral A/V. No puede equilibrar la carga del tráfico al servicio perimetral de conferencia web interno o al servicio proxy XMPP interno. 
  
> [!NOTE]
> Retorno de servidor directo (DSR) NAT no es compatible con Skype para Business Server. 
  
Para determinar si el equilibrador de carga de hardware admite las características necesarias requeridas por Skype para Business Server, vea [infraestructura de Skype para la empresa](https://technet.microsoft.com/en-us/office/dn947483).
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V

A continuación se muestran los requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el / servicio perimetral A/v:
  
- Deshabilitar el algoritmo de Nagle de TCP para los puertos 443 internos y externos. El algoritmo de Nagle es el proceso de combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.
    
- Activar Nagle TCP para el intervalo de puertos externos 50.000-59.999. 
    
- No utilizar NAT en el firewall interno o externo. 
    
- La interfaz perimetral interna debe estar en una red distinta a la interfaz externa del servidor perimetral y debe deshabilitar el enrutamiento entre ellas. 
    
- La interfaz externa del servidor perimetral que ejecuta el servicio perimetral A/v debe usar públicamente direcciones IP enrutables y ninguna NAT o traducción de puerto en cualquiera de las direcciones IP de servidor perimetral externas. 
    
- El equilibrador de carga no necesita cambiar la dirección de origen del cliente.
    
### <a name="other-hardware-load-balancer-requirements"></a>Otros requisitos de equilibrador de carga de Hardware

Requisitos de afinidad basada en cookies se reducen en gran medida en Skype para Business Server para servicios Web. Si va a implementar Skype para Business Server y no se conservará ningún grupo de servidores Front End Servers de Lync Server 2010 o Front-End, no es necesario persistencia basada en cookies. Sin embargo, si va a temporalmente o conservar permanentemente cualquier grupo de servidores Front End Servers de Lync Server 2010 o Front-End, todavía utilizará la persistencia basada en cookies tal y como se ha implementado y configurado para Lync Server 2010. 
  
> [!NOTE]
> **La utilización de la afinidad basada en cookies pese a que su implementación no la necesite** no tiene repercusiones. 
  
Para las implementaciones que **no utilizarán** la afinidad basada en cookies:
  
- En la regla de publicación del proxy inverso para el puerto 4443, establezca **Reenviar encabezado de host** en True. Esto garantizará que se reenviará la dirección URL original.
    
Para las implementaciones que **utilizarán** la afinidad basada en cookies:
  
- En la regla de publicación del proxy inverso para el puerto 4443, establezca **Reenviar encabezado de host** en True. Esto garantizará que se reenviará la dirección URL original.
    
- La cookie del equilibrador de carga de hardware NO NECESITA estar marcada como httpOnly
    
- La cookie del equilibrador de carga de hardware NO NECESITA tener tiempo de expiración
    
- La cookie del equilibrador de carga de hardware NECESITA tener el nombre **MS-WSMAN** (este es el valor esperado por los servicios web y no puede modificarse)
    
- La cookie del equilibrador de carga de hardware NECESITA estar establecida en cada respuesta HTTP para la que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en la misma conexión TCP ya había obtenido una cookie. Si el equilibrador de carga optimiza la inserción de cookies para que solo ocurra una vez por conexión TCP, la optimización NO NECESITA usarse.
    
> [!NOTE]
> Las configuraciones de equilibrador de carga de hardware típicos usan afinidad de dirección de origen y un mínimo de 20 TCP duración de la sesión, que es el adecuado para los clientes de Lync Server y Lync 2013 debido a que se mantiene el estado de sesión a través del uso de cliente o y la interacción de aplicaciones. 
  
Si se implementan dispositivos móviles, es preciso que el equilibrador de carga de hardware pueda equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, necesita poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).
  
> [!CAUTION]
> Los equilibradores de carga de hardware F5 tienen una característica llamada OneConnect que asegura que cada solicitud dentro de una conexión TCP tenga carga equilibrada individualmente. Si va a implementar dispositivos móviles, asegúrese de que su proveedor del equilibrador de carga de hardware admita la misma función. Las últimas aplicaciones móviles que utilizan Apple iOS requieren la versión 1.2 de la seguridad de la capa de transporte (TLS). Para ellos, F5 proporciona una configuración específica. 
  
> [!CAUTION]
> Para obtener información detallada en los equilibradores de carga de hardware de terceros, vea [infraestructura de Skype para la empresa](https://technet.microsoft.com/en-us/office/dn947483). 
  
A continuación, se muestran los requisitos del equilibrador de carga de hardware para los servicios web del grupo de servidores front-end y de directores:
  
- Para VIP de los servicios web internos, configure la persistencia Source_addr (puerto interno 80, 443) en el equilibrador de carga de hardware. Para Skype para Business Server, persistencia Source_addr significa que varias conexiones procedentes de una sola dirección IP siempre se envían a un servidor para mantener el estado de sesión.
    
- Use un tiempo de espera de inactividad de TCP de 1800 segundos.
    
- En el firewall entre el servidor proxy inverso y el equilibrador de carga de hardware de servidores del próximo salto, cree una regla para permitir https: tráfico en el puerto 4443, desde el proxy inverso para el hardware de equilibrador de carga. El equilibrador de carga de hardware necesita configurarse para que escuche los puertos 80, 443 y 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumen de los requisitos de afinidad del equilibrador de carga de hardware

|**Ubicación de cliente/usuario**|**Requisitos de afinidad del FQDN de servicios web externos**|**Requisitos de afinidad del FQDN de servicios web internos**|
|:-----|:-----|:-----|
|Lync Web App (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Lync Web App (solo usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Lync Web App (solo usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Supervisión de puertos para los equilibradores de carga de hardware

Es necesario definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo determinados servicios dejan de estar disponibles por errores de comunicaciones o de hardware. Por ejemplo, si el servicio de servidor Front-End (RTCSRV) se detiene debido a que se produce un error en el grupo de servidores Front-End o de servidor Front-End, la supervisión de HLB debe también dejar de recibir tráfico de los servicios Web. La supervisión de puertos en ECH tiene que implementarse para supervisar lo siguiente:
  
**Grupo de usuario de servidor Front-End - interfaz interna de HLB**

|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<grupo de servidores\>web int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-end  <br/> 5061  <br/> |Origen  <br/> |HTTPS  <br/> |
|\<grupo de servidores\>web int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-end  <br/> 5061  <br/> |Origen  <br/> |HTTP  <br/> |
   
**Grupo de usuario de servidor Front-End - interfaz externa de HLB**

|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<grupo de servidores\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<grupo de servidores\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="BKMK_DNSLoadBalancing"> </a>

Skype Business Server habilita DNS para equilibrio de carga, una solución de software que puede reducir considerablemente la sobrecarga de administración para equilibrio de carga en la red. Equilibrio de carga DNS equilibra el tráfico de red que es exclusivo de Skype para Business Server, como el tráfico SIP y el tráfico de medios.
  
Si implementa el equilibrio de carga DNS, se reducirán sobrecarga de administración su organización para equilibradores de carga de hardware. Además, se evitará la solución de problemas complejos asociados a errores de configuración de equilibradores de carga del tráfico SIP. También puede impedir que se establezcan conexiones de servidores para poder desconectar servidores. El equilibrio de carga de DNS también garantiza que los problemas relacionados con los equilibradores de carga de hardware no afecten a elementos de tráfico SIP, como el enrutamiento de llamadas básico.
  
Si se utiliza el equilibrio de carga de DNS también podrá adquirir equilibradores de carga de hardware a un precio más económico que si usa equilibradores de carga de hardware para todos los tipos de tráfico. Debe usar los equilibradores de carga que han transcurrido calificación de interoperabilidad de las pruebas con Skype para Business Server. Para obtener información detallada acerca de pruebas de interoperabilidad de equilibrador de carga, vea [Socios de equilibrador de carga de Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452). El contenido se aplica a Skype para Business Server.
  
El equilibrio de carga de DNS es compatible con grupos de servidores front-end, grupos de servidores perimetrales, grupos de servidores de director y grupos de servidores de mediación independientes.
  
El equilibrio de carga de DNS suele implementarse en la aplicación. La aplicación (por ejemplo, un cliente que ejecuta Skype para la empresa), intenta conectarse a un servidor en un grupo de servidores mediante la conexión a una de las direcciones IP devueltas desde el DNS A y AAAA (si se usa el direccionamiento IPv6) de registro de consulta para el nombre de dominio completo (FQDN) de grupo de servidores. 
  
Por ejemplo, si hay tres servidores front-end en un grupo denominado pool01.contoso.com, pasará lo siguiente:
  
- Los clientes que ejecutan Skype para la empresa de consulta DNS para pool01.contoso.com. La consulta devuelve direcciones IP tres y se almacena en caché como se muestra a continuación (no necesariamente en este orden):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Luego, el cliente intenta establecer una conexión del Protocolo de control de transmisión (TCP) con una de las direcciones IP. Si no funciona, lo intenta con la siguiente dirección IP almacenada en caché.
    
- Si la conexión TCP se establece correctamente, el cliente negocia con el TLS para conectarse con el registrador principal en pool01.contoso.com.
    
- Si el cliente intenta todas las entradas almacenadas en caché sin una conexión correctamente, se notificará al usuario que ningún servidor que ejecute Skype para Business Server está disponibles en ese momento.
    
> [!NOTE]
> El equilibrio de carga basado en DNS es distinto al round robin de DNS (RR de DNS), que normalmente hace referencia al equilibrio de carga usando el DNS para proporcionar un orden distinto de direcciones IP correspondientes a los servidores de un grupo de servidores. Por lo general, RR de DNS solo habilita la distribución de carga, pero no habilita la conmutación por error. Por ejemplo, si no se consigue establecer la conexión con una de las direcciones IP devueltas por la consulta A y AAAA (si está usando el direccionamiento IPv6) de DNS, la conexión será errónea. Por tanto, el round robin de DNS por sí solo es menos fiable que el equilibrio de carga basado en DNS. Puede usar el round robin de DNS junto con el equilibrio de carga de DNS. 
  
El equilibrio de carga de DNS se usa para lo siguiente:
  
- Equilibrar la carga SIP de servidor a servidor con los servidores perimetrales
    
- Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS) como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas
    
- Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (proceso también conocido como "purga").
    
- Equilibrar la carga de todo el tráfico desde el servidor al cliente entre clientes y servidores perimetrales
    
El equilibrio de carga de DNS no puede usarse para:
  
- Tráfico web de cliente a servidor al director o a los servidores front-end
    
Equilibrio de carga de DNS y tráfico federado:
  
Si una consulta SRV de DNS devuelve varios registros de DNS, el servicio perimetral de acceso siempre selecciona el registro SRV de DNS con la prioridad numérica más baja y con el peso numérico más alto. El grupo de trabajo de ingeniería de Internet "Un RR DNS para especificar la ubicación de los servicios (DNS SRV)" del documento [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) especifica que si hay varios DNS SRV registros definidos, la prioridad se utiliza en primer lugar y, a continuación, weight. Por ejemplo, el registro A de SRV de DNS tiene un peso de 20 y una prioridad de 40, y el registro B de SRV de DNS tiene un peso de 10 y una prioridad de 50. Se seleccionará el registro A de SRV de DNS con una prioridad de 40. Las siguientes reglas se aplican a la selección de registros SRV de DNS:
  
- La prioridad se considera primero. Un cliente TIENE QUE intentar contactar con el host de destino definido por el registro SRV de DNS con la menor prioridad numerada que pueda alcanzar. Los destinos con la misma prioridad NECESITAN intentarse siguiendo el orden definido por el campo de peso.
    
- El campo de peso especifica un peso relativo para las entradas que tienen la misma prioridad. Es PRECISO que a los pesos más grandes se les otorgue una probabilidad proporcionalmente mayor para ser seleccionados. Los administradores de DNS deben utilizar peso 0 cuando no hay ninguna selección de servidor para hacer. Cuando existen registros con pesos superiores a 0, los registros con peso 0 necesitan tener una oportunidad muy pequeña de ser elegidos.
    
Si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso, el servicio perimetral de acceso seleccionará el registro SRV que se haya obtenido en primer lugar del servidor DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director

Puede usar el equilibrio de carga de DNS para el tráfico SIP de los grupos de servidores front-end y los grupos de servidores de director. Con el equilibrio de carga de DNS implementado, seguirá necesitando usar también equilibradores de carga de hardware para esos grupos de servidores, pero solo para el tráfico HTTPS de cliente a servidor. El equilibrador de carga de hardware se usa para el tráfico HTTPS de los clientes en los puertos 443 y 80. 
  
A pesar de que seguirá necesitando equilibradores de carga de hardware para esos grupos de servidores, su instalación y administración será fundamentalmente para el tráfico HTTPS, al que están habituados los administradores de equilibradores de carga de hardware.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Equilibrio de carga de DNS y compatibilidad con clientes y servidores más antiguos

Carga de DNS equilibrio admite la conmutación por error automática sólo para los servidores que ejecutan Skype para Business Server o de Lync Server 2010 y para Lync 2013 y Skype para clientes empresariales. Las versiones anteriores de los clientes y Office Communications Server aún pueden conectarse a los grupos de servidores que ejecuta el equilibrio de carga DNS, pero si no pueden realizar una conexión con el primer servidor que Equilibrio de carga de DNS refiere a ellos a, no son capaces de conmutación por error a otro servidor del grupo de servidores . 
  
Además, si está utilizando mensajería unificada de Exchange, debe usar un mínimo de Exchange 2010 SP1 para obtener soporte técnico para Skype para equilibrio de carga de DNS del servidor de negocio. Si usa alguna versión anterior de Exchange, los usuarios no tendrán capacidades de conmutación por error para estos escenarios de la mensajería unificada de Exchange:
  
- Reproducir el correo de voz de Enterprise en el teléfono
    
- Transferir llamadas de un operador automático de la mensajería unificada de Exchange
    
Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director
<a name="BK_FE_Dir"> </a>

Para implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director, es necesario realizar un par de pasos adicionales con los registros de DNS y los FQDN.
  
- Un grupo de servidores que usa el equilibrio de carga DNS debe tener dos FQDN: el FQDN que se usa en DNS del grupo regular equilibrio de carga (por ejemplo, pool01.contoso.com) y resuelve a las direcciones IP física de los servidores del grupo de servidores, y otro FQDN para Web el grupo de servidores (como servicios Web01.contoso.com), que se resuelve en la dirección IP virtual del grupo de servidores. 
    
    En el generador, si desea implementar DNS equilibrio de carga para un grupo de servidores, para crear este FQDN adicional para los servicios Web del grupo de servidores debe Active la casilla de verificación **FQDN de grupo de servicios Web internos de reemplazo** y escriba el FQDN, en la **especificar las direcciones URL de servicios Web para Este grupo de servidores** página.
    
- Para admitir el FQDN que usa el equilibrio de carga de DNS, necesita aprovisionar el DNS, de modo que resuelva el FQDN del grupo (como, por ejemplo, pool01.contoso.com) en las direcciones IP de todos los servidores del grupo (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Necesita incluir solo las direcciones IP de los servidores implementados actualmente.
    
    > [!CAUTION]
    > Si tiene más de un grupo de servidores Front-End o servidor Front-End los servicios Web externos FQDN debe ser único. Por ejemplo, si define el FQDN de un servidor Front-End de servicios Web externos como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores Front-End o servidor Front-End. Si va a implementar también los directores, la externa FQDN definido para cualquier Director de los servicios Web o debe ser único de cualquier otro grupo de directores Director o Director del grupo de servidores, así como cualquier otro grupo de servidores Front-End o un servidor Front-End. Si decide reemplazar los servicios web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores Front-End, Director o un grupo de directores.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Equilibrio de carga de DNS en grupos de servidores perimetrales
<a name="BK_Edge"> </a>

Puede implementar el equilibrio de carga de DNS en grupos de servidores perimetrales. Si lo hace, necesita tener en cuenta varias consideraciones.
  
El uso del equilibrio de carga de DNS en los servidores perimetrales provoca una pérdida en la capacidad de conmutación por error, en los siguientes escenarios:
  
- Federación con organizaciones que ejecutan versiones de Skype para Business Server publicado antes de Lync Server 2010.
    
- Intercambio de mensajes instantáneos con los usuarios de servicios de mensajería instantánea pública (IM) AOL y Yahoo!, además de los proveedores basados en XMPP y servidores, como Google Talk, actualmente el único socio XMPP compatible.
    
Estos escenarios funcionarán siempre que se ejecuten correctamente todos los servidores perimetrales del grupo pero, si un servidor perimetral no está disponible, fallarán todas las solicitudes de estos escenarios que se envíen a él, en lugar de redirigirse a otro servidor perimetral.
  
 Si está utilizando mensajería unificada de Exchange, debe usar un mínimo de Exchange 2013 para obtener soporte técnico para Skype Business Server DNS para equilibrio de carga en el borde. Si usa alguna versión anterior de Exchange, los usuarios remotos no tendrán capacidades de conmutación por error para estos escenarios de mensajería unificada de Exchange:
  
- Reproducir el correo de voz de Enterprise en el teléfono
    
- Transferir llamadas de un operador automático de la mensajería unificada de Exchange
    
Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.
  
La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga de DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implementar el equilibrio de carga de DNS en grupos de servidores perimetrales

Para implementar el equilibrio de carga de DNS en la interfaz externa del grupo de servidores perimetrales, necesita las siguientes entradas de DNS:
  
- Para el servicio perimetral de acceso, necesita una entrada por cada servidor del grupo. Cada entrada necesita resolver el FQDN del servicio perimetral de acceso (por ejemplo, sip.contoso.com) en la dirección IP del servicio perimetral de acceso de uno de los servidores perimetrales del grupo.
    
- Para el servicio perimetral de conferencia web, necesita una entrada por cada servidor del grupo. Cada entrada necesita resolver el FQDN del servicio perimetral de conferencia web (por ejemplo, webconf.contoso.com) en la dirección IP del servicio perimetral de conferencia web de uno de los servidores perimetrales del grupo.
    
- Para el servicio perimetral de audio y vídeo, necesita una entrada por cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de Audio y vídeo (por ejemplo, av.contoso.com) en la dirección IP del servicio perimetral A/v en uno de los servidores perimetrales en el grupo de servidores.
    
Para implementar el equilibrio de carga de DNS en la interfaz interna del grupo de servidores perimetrales, necesita agregar un registro A de DNS que resuelva el FQDN interno del grupo de servidores perimetrales en la dirección IP de cada servidor del grupo.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Usar el equilibrio de carga de DNS en grupos de servidores de mediación
<a name="BK_Mediation"> </a>

Puede usar el equilibrio de carga de DNS en grupos de servidores de mediación independientes. Todo el tráfico de medios y SIP se equilibra con el equilibrio de carga de DNS.
  
Para implementar el equilibrio de carga de DNS en un grupo de servidores de mediación, necesita aprovisionar el DNS, de modo que resuelva el FQDN del grupo (por ejemplo, mediationpool1.contoso.com) en las direcciones IP de todos los servidores del grupo (por ejemplo, 192.168.1.1, 192.168.1.2, etc.).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloquear tráfico a un servidor con equilibrio de carga de DNS
<a name="BK_Mediation"> </a>

Si utiliza el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente con solo quitar las entradas de direcciones IP del FQDN del grupo de servidores. También es preciso quitar la entrada de DNS para el equipo. 
  
Tenga en cuenta que para el tráfico de servidor a servidor, Skype para Business Server usa el equilibrio de carga conscientes de la topología. Servidores leen la topología publicada en el almacén de Administración Central para obtener los FQDN de los servidores de la topología y distribuyen automáticamente el tráfico entre los servidores. Para bloquear un servidor para que no reciba tráfico de servidor a servidor, necesita quitar el servidor de la topología. 
  

