---
title: Requisitos del equilibrio de carga para Skype Empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Resumen: Revise las consideraciones de equilibrio de carga antes de implementar Skype empresarial Server.'
ms.openlocfilehash: 2db9b7aa37f71d445feb3cfd9a09e49f44ca48f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297060"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Requisitos del equilibrio de carga para Skype Empresarial
 
**Resumen:** Revise las consideraciones de equilibrio de carga antes de implementar Skype empresarial Server.
  
El equilibrio de carga distribuye el tráfico entre los servidores de un grupo. Si tiene grupos de front-end, grupos de servidores de mediación o grupos de servidores perimetrales, necesita implementar el equilibrio de carga para estos grupos.
  
Skype empresarial Server admite dos tipos de soluciones de equilibrio de carga para el tráfico de cliente a servidor: equilibrio de carga del sistema de nombres de dominio (DNS) y equilibrio de carga de hardware (a menudo abreviado como HLB). El equilibrio de carga de DNS ofrece varias ventajas, como la administración más sencilla, la solución de problemas más eficaz y la capacidad de aislar gran parte del tráfico de Skype empresarial Server de cualquier problema potencial de equilibrado de carga de hardware.
  
Decida usted mismo qué solución de equilibrio de carga es adecuada para cada grupo de la implementación, pero tenga en cuenta las siguientes restricciones: 
  
- La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz y el equilibrio de carga de hardware en la otra.
    
- Algunos tipos de tráfico requieren un equilibrador de carga de hardware. Por ejemplo, el tráfico HTTP requiere un equilibrador de carga de hardware en lugar del equilibrio de carga de DNS. El equilibrio de carga de DNS no funciona con tráfico web del cliente al servidor.
    
Si decide usar el equilibrio de carga de DNS para un grupo, pero aún tiene que implementar equilibradores de carga de hardware para el tráfico, como el tráfico HTTP, la administración de los equilibradores de carga de hardware será mucho más sencilla. Por ejemplo, configurar el equilibrador de carga de hardware será más sencillo, pues solamente administrará el tráfico HTTPS y HTTP, mientras que el equilibrio de carga de DNS administrará todos los demás protocolos. Para más detalles, consulte [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Para el tráfico de servidor a servidor, Skype empresarial Server usa el equilibrio de carga que reconoce la topología. Los servidores leen la topología Publicada en el almacén central de administración para obtener los FQDN de los servidores de la topología y distribuyen automáticamente el tráfico entre los servidores. Los administradores no necesitan configurar ni administrar este tipo de equilibrio de carga. 
  
Si utiliza el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente con solo quitar las entradas de direcciones IP del FQDN del grupo de servidores. También es preciso quitar la entrada de DNS para el equipo. 
  
## <a name="hardware-load-balancer-requirements"></a>Requisitos del equilibrador de carga de hardware

La topología de la escalabilidad perimetral consolidada de Skype empresarial Server está optimizada para el equilibrio de carga de DNS para implementaciones nuevas que se federan principalmente con otras organizaciones que usan Skype empresarial Server o Lync Server. Si se requiere una alta disponibilidad para cualquiera de los siguientes escenarios, se debe usar un equilibrador de carga de hardware en los grupos de servidores perimetrales para lo siguiente: 
  
- Federación con organizaciones que usan Office Communications Server 2007 R2 u Office Communications Server 2007
    
- Mensajería unificada de Exchange para usuarios remotos que usan la mensajería unificada de Exchange antes de Exchange 2010 con SP1
    
- Conectividad con usuarios de mensajería instantánea (MI) pública
    
> [!IMPORTANT]
> No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Necesita utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces. 
  
> [!NOTE]
> Si usa un equilibrador de carga de hardware, el equilibrador de carga que se haya implementado para las conexiones con la red interna necesitará configurarse para que solo equilibre la carga del tráfico de los servidores que ejecuten el servicio perimetral de acceso y el servicio perimetral A/V. No puede equilibrar la carga del tráfico al servicio perimetral de conferencia web interno o al servicio proxy XMPP interno. 
  
> [!NOTE]
> El NAT de Return de servidor directo (DSR) no es compatible con Skype empresarial Server. 
  
Para determinar si su equilibrador de carga de hardware admite las características necesarias para Skype empresarial Server, consulte [infraestructura de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V

Estos son los requisitos del equilibrador de carga de hardware para los servidores perimetrales que ejecutan el servicio perimetral A/V:
  
- Deshabilitar el algoritmo de Nagle de TCP para los puertos 443 internos y externos. El algoritmo de Nagle es el proceso de combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.
    
- Desactive la Nagling TCP para el intervalo de puertos externo 50.000-59.999. 
    
- No utilizar NAT en el firewall interno o externo. 
    
- La interfaz interna de Edge debe estar en una red diferente a la de la interfaz externa del servidor perimetral y el enrutamiento entre ellas debe estar deshabilitado. 
    
- La interfaz externa del servidor perimetral que ejecuta el servicio de borde A/V debe usar direcciones IP enrutables públicamente y sin traducción de NAT o puerto en ninguna de las direcciones IP externas de Edge. 
    
- El equilibrador de carga no necesita cambiar la dirección de origen del cliente.
    
### <a name="other-hardware-load-balancer-requirements"></a>Otros requisitos del equilibrador de carga de hardware

Los requisitos de afinidad basados en cookies se reducen enormemente en Skype empresarial Server para servicios Web. Si va a implementar Skype empresarial Server y no va a conservar ninguno de los servidores front-end de Lync Server 2010 o de las agrupaciones front end, no necesita persistencia basada en cookies. Sin embargo, si conservará de forma temporal o permanente los servidores front-end de Lync Server 2010 o las agrupaciones front end, seguirá usando la persistencia basada en cookies a medida que se implemente y se configure para Lync Server 2010. 
  
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
> Las configuraciones típicas de equilibrado de carga de hardware usan afinidad de dirección de origen y 20 minutos de duración de la sesión TCP, lo cual es adecuado para clientes de Lync Server y Lync 2013 porque se mantiene el estado de la sesión a través del uso del cliente o la interacción de la aplicación. 
  
Si se implementan dispositivos móviles, es preciso que el equilibrador de carga de hardware pueda equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, necesita poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).
  
> [!CAUTION]
> Si está implementando dispositivos móviles, su equilibrador de carga de hardware debe poder equilibrar cada solicitud individualmente dentro de una conexión TCP. Las últimas aplicaciones móviles que utilizan Apple iOS requieren la versión 1.2 de la seguridad de la capa de transporte (TLS).  
  
> [!CAUTION]
> Para obtener más información sobre los equilibradores de carga de hardware de terceros, consulte [infraestructura de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
A continuación, se muestran los requisitos del equilibrador de carga de hardware para los servicios web del grupo de servidores front-end y de directores:
  
- Para VIP de los servicios web internos, configure la persistencia Source_addr (puerto interno 80, 443) en el equilibrador de carga de hardware. En el caso de Skype empresarial Server, la persistencia de Source_addr significa que varias conexiones provenientes de una única dirección IP siempre se envían a un servidor para mantener el estado de la sesión.
    
- Use un tiempo de espera de inactividad de TCP de 1800 segundos.
    
- En el Firewall entre el proxy inverso y el equilibrador de carga de hardware del grupo siguiente, cree una regla para permitir https: tráfico en el puerto 4443, desde el proxy inverso al equilibrador de carga del hardware. El equilibrador de carga de hardware necesita configurarse para que escuche los puertos 80, 443 y 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumen de los requisitos de afinidad del equilibrador de carga de hardware

|**Ubicación de cliente/usuario**|**Requisitos de afinidad del FQDN de servicios web externos**|**Requisitos de afinidad del FQDN de servicios web internos**|
|:-----|:-----|:-----|
|Lync Web App (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Lync Web App (solo usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Lync Web App (solo para usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Supervisión de puertos para los equilibradores de carga de hardware

Es necesario definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo determinados servicios dejan de estar disponibles por errores de comunicaciones o de hardware. Por ejemplo, si se detiene el servicio servidor front-end (RTCSRV) porque se produce un error en el servidor front-end o en la agrupación front end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios Web. La supervisión de puertos en ECH tiene que implementarse para supervisar lo siguiente:
  
**Grupo de usuarios del servidor front-end-interfaz interna de HLB**

|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<Web\>de Pool-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-end  <br/> 5061  <br/> |Origen  <br/> |HTTPS  <br/> |
|\<Web\>de Pool-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-end  <br/> 5061  <br/> |Origen  <br/> |HTTP  <br/> |
   
**Grupo de usuarios del servidor front-end-interfaz externa de HLB**

|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<Grupo\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<Grupo\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="BKMK_DNSLoadBalancing"> </a>

Skype empresarial Server habilita el equilibrio de carga de DNS, una solución de software que puede reducir en gran medida la sobrecarga de administración para el equilibrio de carga en la red. El equilibrio de carga de DNS equilibra el tráfico de red que es exclusivo de Skype empresarial Server, como el tráfico SIP y el tráfico de medios.
  
Si implementa el equilibrio de carga de DNS, la sobrecarga de administración de la organización para los equilibradores de carga de hardware se minimizará. Además, se evitará la solución de problemas complejos asociados a errores de configuración de equilibradores de carga del tráfico SIP. También puede impedir que se establezcan conexiones de servidores para poder desconectar servidores. El equilibrio de carga de DNS también garantiza que los problemas relacionados con los equilibradores de carga de hardware no afecten a elementos de tráfico SIP, como el enrutamiento de llamadas básico.

En el siguiente diagrama se muestra un ejemplo que incluye el equilibrio de carga de DNS interno y externo: 
  
**Diagrama de red perimetral con direcciones IPv4 públicas**

![ejemplo de diagrama de red DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Si se utiliza el equilibrio de carga de DNS también podrá adquirir equilibradores de carga de hardware a un precio más económico que si usa equilibradores de carga de hardware para todos los tipos de tráfico. Debe usar equilibradores de carga que hayan superado las pruebas de calificación de interoperabilidad con Skype empresarial Server. Para obtener detalles sobre las pruebas de interoperabilidad de equilibrador de carga, consulte [Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452)de equilibrador de carga. El contenido que se aplica a Skype empresarial Server.
  
El equilibrio de carga de DNS es compatible con grupos de servidores front-end, grupos de servidores perimetrales, grupos de servidores de director y grupos de servidores de mediación independientes.
  
El equilibrio de carga de DNS suele implementarse en la aplicación. La aplicación (por ejemplo, un cliente con Skype empresarial) intenta conectarse a un servidor de un grupo conectándose a una de las direcciones IP devueltas desde el DNS a y AAAA (si se usa el direccionamiento IPv6) consulta de registro para el nombre de dominio completo (FQDN) del grupo. 
  
Por ejemplo, si hay tres servidores front-end en un grupo denominado pool01.contoso.com, pasará lo siguiente:
  
- Los clientes que ejecutan DNS de consultas de Skype empresarial para pool01.contoso.com. La consulta devuelve tres direcciones IP y las almacena en caché como sigue (no necesariamente en este orden):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Luego, el cliente intenta establecer una conexión del Protocolo de control de transmisión (TCP) con una de las direcciones IP. Si no funciona, lo intenta con la siguiente dirección IP almacenada en caché.
    
- Si la conexión TCP se establece correctamente, el cliente negocia con el TLS para conectarse con el registrador principal en pool01.contoso.com.
    
- Si el cliente prueba todas las entradas almacenadas en caché sin una conexión correcta, el usuario recibirá una notificación de que en este momento no hay servidores con Skype empresarial Server disponibles.
    
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
  
Si una consulta SRV de DNS devuelve varios registros de DNS, el servicio perimetral de acceso siempre selecciona el registro SRV de DNS con la prioridad numérica más baja y con el peso numérico más alto. El documento del grupo de tareas de ingeniería de Internet "un registro de registros de DNS para especificar la ubicación de los servicios (DNS SRV)" [RFC 2782, RR SRV de DNS](https://www.ietf.org/rfc/rfc2782.txt) especifica que si hay varios registros SRV de DNS definidos, primero se usa la prioridad y luego el peso. Por ejemplo, el registro A de SRV de DNS tiene un peso de 20 y una prioridad de 40, y el registro B de SRV de DNS tiene un peso de 10 y una prioridad de 50. Se seleccionará el registro A de SRV de DNS con una prioridad de 40. Las siguientes reglas se aplican a la selección de registros SRV de DNS:
  
- La prioridad se considera primero. Un cliente TIENE QUE intentar contactar con el host de destino definido por el registro SRV de DNS con la menor prioridad numerada que pueda alcanzar. Los destinos con la misma prioridad NECESITAN intentarse siguiendo el orden definido por el campo de peso.
    
- El campo de peso especifica un peso relativo para las entradas que tienen la misma prioridad. Es PRECISO que a los pesos más grandes se les otorgue una probabilidad proporcionalmente mayor para ser seleccionados. Los administradores de DNS deben usar Weight 0 cuando no hay ninguna selección de servidor para hacer. Cuando existen registros con pesos superiores a 0, los registros con peso 0 necesitan tener una oportunidad muy pequeña de ser elegidos.
    
Si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso, el servicio perimetral de acceso seleccionará el registro SRV que se haya obtenido en primer lugar del servidor DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director

Puede usar el equilibrio de carga de DNS para el tráfico SIP de los grupos de servidores front-end y los grupos de servidores de director. Con el equilibrio de carga de DNS implementado, seguirá necesitando usar también equilibradores de carga de hardware para esos grupos de servidores, pero solo para el tráfico HTTPS de cliente a servidor. El equilibrador de carga de hardware se usa para el tráfico HTTPS de los clientes en los puertos 443 y 80. 
  
A pesar de que seguirá necesitando equilibradores de carga de hardware para esos grupos de servidores, su instalación y administración será fundamentalmente para el tráfico HTTPS, al que están habituados los administradores de equilibradores de carga de hardware.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Equilibrio de carga de DNS y compatibilidad con clientes y servidores más antiguos

El equilibrio de carga de DNS admite la conmutación por error automática solo para servidores que ejecuten Skype empresarial Server o Lync Server 2010, y para clientes de Lync 2013 y Skype empresarial. Las versiones anteriores de clientes y Office Communications Server siguen conectándose a las agrupaciones que ejecutan el equilibrio de carga de DNS, pero si no pueden establecer una conexión con el primer servidor al que el equilibrio de carga DNS hace referencia a él, no pueden conmutar por error a otro servidor del grupo . 
  
Además, si usa la mensajería unificada de Exchange, debe usar un mínimo de Exchange 2010 SP1 para obtener soporte técnico para el equilibrio de carga de DNS de Skype empresarial Server. Si usa alguna versión anterior de Exchange, los usuarios no tendrán capacidades de conmutación por error para estos escenarios de la mensajería unificada de Exchange:
  
- Reproducir el correo de voz de Enterprise en el teléfono
    
- Transferir llamadas de un operador automático de la mensajería unificada de Exchange
    
Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director
<a name="BK_FE_Dir"> </a>

Para implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de servidores de director, es necesario realizar un par de pasos adicionales con los registros de DNS y los FQDN.
  
- Un grupo que usa el equilibrio de carga DNS debe tener dos FQDN: el FQDN de la agrupación normal que usa el equilibrio de carga DNS (como pool01.contoso.com), y se resuelve en la IPs física de los servidores del grupo, y otro FQDN para los servicios web del grupo (como, por ejemplo, web01.contoso.com), que se resuelve en la dirección IP virtual del grupo. 
    
    En el generador de topología, si desea implementar el equilibrio de carga de DNS para un grupo, para crear este FQDN adicional para los servicios web del grupo, debe activar la casilla **invalidar FQDN del grupo de servicios Web internos** y escribir el FQDN, en **especificar las direcciones URL de servicios web para Esta** página de grupo.
    
- Para admitir el FQDN que usa el equilibrio de carga de DNS, necesita aprovisionar el DNS, de modo que resuelva el FQDN del grupo (como, por ejemplo, pool01.contoso.com) en las direcciones IP de todos los servidores del grupo (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Necesita incluir solo las direcciones IP de los servidores implementados actualmente.
    
    > [!CAUTION]
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end. Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end. Si decide invalidar los servicios Web internos con un FQDN definido por el usuario, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Equilibrio de carga de DNS en grupos de servidores perimetrales
<a name="BK_Edge"> </a>

Puede implementar el equilibrio de carga de DNS en grupos de servidores perimetrales. Si lo hace, necesita tener en cuenta varias consideraciones.
  
El uso del equilibrio de carga de DNS en los servidores perimetrales provoca una pérdida en la capacidad de conmutación por error, en los siguientes escenarios:
  
- Federación con organizaciones que ejecutan versiones de Skype empresarial Server publicadas antes de Lync Server 2010.
    
- Intercambio de mensajes instantáneos con usuarios de servicios de mensajería instantánea (mi) públicos AOL y Yahoo!, además de los servidores y proveedores basados en XMPP, como Google Talk, que actualmente son el único socio de XMPP admitido.
    
Estos escenarios funcionarán siempre que se ejecuten correctamente todos los servidores perimetrales del grupo pero, si un servidor perimetral no está disponible, fallarán todas las solicitudes de estos escenarios que se envíen a él, en lugar de redirigirse a otro servidor perimetral.
  
 Si usa la mensajería unificada de Exchange, debe usar un mínimo de 2013 de Exchange para obtener compatibilidad con el equilibrio de carga de DNS de Skype empresarial Server en Edge. Si usa alguna versión anterior de Exchange, los usuarios remotos no tendrán capacidades de conmutación por error para estos escenarios de mensajería unificada de Exchange:
  
- Reproducir el correo de voz de Enterprise en el teléfono
    
- Transferir llamadas de un operador automático de la mensajería unificada de Exchange
    
Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.
  
La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga de DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implementar el equilibrio de carga de DNS en grupos de servidores perimetrales

Para implementar el equilibrio de carga de DNS en la interfaz externa del grupo de servidores perimetrales, necesita las siguientes entradas de DNS:
  
- Para el servicio perimetral de acceso, necesita una entrada por cada servidor del grupo. Cada entrada necesita resolver el FQDN del servicio perimetral de acceso (por ejemplo, sip.contoso.com) en la dirección IP del servicio perimetral de acceso de uno de los servidores perimetrales del grupo.
    
- Para el servicio perimetral de conferencia web, necesita una entrada por cada servidor del grupo. Cada entrada necesita resolver el FQDN del servicio perimetral de conferencia web (por ejemplo, webconf.contoso.com) en la dirección IP del servicio perimetral de conferencia web de uno de los servidores perimetrales del grupo.
    
- Para el servicio perimetral de audio y vídeo, necesita una entrada por cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de audio/vídeo (por ejemplo, av.contoso.com) a la dirección IP del servicio de borde A/V de uno de los servidores perimetrales del grupo.
    
Para implementar el equilibrio de carga de DNS en la interfaz interna del grupo de servidores perimetrales, necesita agregar un registro A de DNS que resuelva el FQDN interno del grupo de servidores perimetrales en la dirección IP de cada servidor del grupo.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Usar el equilibrio de carga de DNS en grupos de servidores de mediación
<a name="BK_Mediation"> </a>

Puede usar el equilibrio de carga de DNS en grupos de servidores de mediación independientes. Todo el tráfico de medios y SIP se equilibra con el equilibrio de carga de DNS.
  
Para implementar el equilibrio de carga de DNS en un grupo de servidores de mediación, necesita aprovisionar el DNS, de modo que resuelva el FQDN del grupo (por ejemplo, mediationpool1.contoso.com) en las direcciones IP de todos los servidores del grupo (por ejemplo, 192.168.1.1, 192.168.1.2, etc.).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloquear tráfico a un servidor con equilibrio de carga de DNS
<a name="BK_Mediation"> </a>

Si utiliza el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente con solo quitar las entradas de direcciones IP del FQDN del grupo de servidores. También es preciso quitar la entrada de DNS para el equipo. 
  
Tenga en cuenta que para el tráfico de servidor a servidor, Skype empresarial Server usa el equilibrio de carga que reconoce la topología. Los servidores leen la topología Publicada en el almacén central de administración para obtener los FQDN de los servidores de la topología y distribuyen automáticamente el tráfico entre los servidores. Para bloquear un servidor para que no reciba tráfico de servidor a servidor, necesita quitar el servidor de la topología. 
  

