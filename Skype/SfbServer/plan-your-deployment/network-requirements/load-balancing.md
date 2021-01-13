---
title: Requisitos de equilibrio de carga para Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Resumen: revise las consideraciones de equilibrio de carga antes de implementar Skype Empresarial Server.'
ms.openlocfilehash: 5790ef1ba0d32774ced45be5af257f70fc4cf594
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834380"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Requisitos de equilibrio de carga para Skype Empresarial
 
**Resumen:** Revise las consideraciones de equilibrio de carga antes de implementar Skype Empresarial Server.
  
El equilibrio de carga distribuye el tráfico entre los servidores de un grupo. Si tiene grupos de servidores front-end, grupos de servidores de mediación o grupos de servidores perimetrales, debe implementar el equilibrio de carga para estos grupos.
  
Skype Empresarial Server admite dos tipos de soluciones de equilibrio de carga para el tráfico de cliente a servidor: equilibrio de carga del Sistema de nombres de dominio (DNS) y equilibrio de carga de hardware (a menudo abreviado como HLB). El equilibrio de carga de DNS ofrece varias ventajas, como una administración más sencilla, una solución de problemas más eficaz y la capacidad de aislar gran parte del tráfico de Skype Empresarial Server de cualquier posible problema del equilibrador de carga de hardware.
  
Decida usted mismo qué solución de equilibrio de carga es adecuada para cada grupo de servidores de la implementación, pero tenga en cuenta las siguientes restricciones: 
  
- La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz y el equilibrio de carga de hardware en la otra.
    
- Algunos tipos de tráfico requieren un equilibrador de carga de hardware. Por ejemplo, el tráfico HTTP requiere un equilibrador de carga de hardware en lugar del equilibrio de carga de DNS. El  equilibrio de carga de DNS no trabaja con tráfico web de cliente a servidor.
    
Si decide usar el equilibrio de carga DNS para un grupo pero aún tiene que implementar equilibradores de carga de hardware para tráfico como el tráfico HTTP, la administración de los equilibradores de carga de hardware será mucho más sencilla. Por ejemplo, la configuración del equilibrador de carga de hardware será más sencilla, ya que solo administrará el tráfico HTTP y HTTPS, mientras que el equilibrio de carga de DNS administrará todos los demás protocolos. Para obtener información detallada, consulte [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Para el tráfico de servidor a servidor, Skype Empresarial Server usa el equilibrio de carga para topologías. Los servidores leen la topología publicada en el almacén de administración central para obtener los FQDN de los servidores de la topología y distribuir automáticamente el tráfico entre los servidores. Los administradores no necesitan configurar ni administrar este tipo de equilibrio de carga. 
  
Si usa el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente simplemente quitar las entradas de dirección IP del FQDN del grupo de servidores. También debe quitar la entrada DNS del equipo. 
  
## <a name="hardware-load-balancer-requirements"></a>Requisitos del equilibrador de carga de hardware

La topología perimetral consolidada a escala de Skype Empresarial Server está optimizada para el equilibrio de carga dns para nuevas implementaciones federadas principalmente con otras organizaciones que usan Skype Empresarial Server o Lync Server. En caso de que se necesite una gran disponibilidad en cualquiera de los siguientes escenarios, se deberá usar un equilibrador de carga de hardware en grupos de servidores perimetrales: 
  
- Federación con organizaciones que usan Office Communications Server 2007 R2 u Office Communications Server 2007
    
- Mensajería unificada de Exchange para usuarios remotos que usan mensajería unificada de Exchange antes de Exchange 2010 con SP1
    
- Conectividad con usuarios de mensajería instantánea pública
    
> [!IMPORTANT]
> No se admite el uso del equilibrio de carga de DNS en una interfaz y del equilibrio de carga de hardware en otra. Debe utilizar el equilibrio de carga de hardware o de DNS en ambas interfaces. 
  
> [!NOTE]
> Si usa un equilibrador de carga de hardware, el equilibrador de carga que se haya implementado para las conexiones con la red interna deberá configurarse de modo que solo equilibre la carga del tráfico de los servidores que ejecuten el servicio perimetral de acceso y el servicio perimetral A/V. No puede equilibrar la carga del tráfico al servicio perimetral de conferencia web interno o al servicio proxy XMPP interno. 
  
> [!NOTE]
> La NAT de devolución directa de servidor (DSR) no es compatible con Skype Empresarial Server. 
  
Para determinar si el equilibrador de carga de hardware admite las características necesarias que necesita Skype Empresarial Server, consulte [Infraestructura para Skype Empresarial.](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos de equilibrador de carga de hardware para servidores perimetrales que ejecutan el servicio perimetral A/V

Estos son los requisitos del equilibrador de carga de hardware para los servidores perimetrales que ejecutan el servicio perimetral A/V:
  
- Inhabilitar la aplicación del algoritmo de Nagle TCP para los puertos 443 internos y externos. La aplicación del algoritmo de Nagle es la combinación de varios paquetes pequeños en un único paquete más grande para obtener una transmisión más eficiente.
    
- Desactive el algoritmo de naje TCP para el intervalo de puertos externos de 50.000 a 59.999. 
    
- No usar NAT en el firewall interno o externo. 
    
- La interfaz interna del servidor perimetral y la interfaz externa del servidor perimetral deben estar en redes diferentes, y debe inhabilitarse el enrutamiento entre ellas. 
    
- La interfaz externa del servidor perimetral que ejecuta el servicio perimetral A/V debe usar direcciones IP enrutables públicamente y ninguna NAT o traducción de puertos en ninguna de las direcciones IP externas perimetrales. 
    
- El equilibrador de carga no debe cambiar la dirección de origen del cliente.
    
### <a name="other-hardware-load-balancer-requirements"></a>Otros requisitos del equilibrador de carga de hardware

Los requisitos de afinidad basados en cookies se reducen considerablemente en Skype Empresarial Server para servicios web. Si va a implementar Skype Empresarial Server y no conservará ningún servidor front-end de Lync Server 2010 ni grupos de servidores front-end, no necesita persistencia basada en cookies. Sin embargo, si conservará temporal o permanentemente los servidores front-end de Lync Server 2010 o grupos de servidores front-end, seguirá utilizando la persistencia basada en cookies mientras se implementa y configura para Lync Server 2010. 
  
> [!NOTE]
> **La utilización de la afinidad basada en cookies pese a que su implementación no la necesite** no tiene repercusiones. 
  
Para las implementaciones que **no utilicen** la afinidad basada en cookies:
  
- En la regla de publicación del proxy inverso para el puerto 4443, establezca **Transferir encabezado de host** en True. Esto garantizará que se transfiera la URL original.
    
Para las implementaciones que **utilicen** la afinidad basada en cookies:
  
- En la regla de publicación del proxy inverso para el puerto 4443, establezca **Transferir encabezado de host** en True. Esto garantizará que se transfiera la URL original.
    
- La cookie de equilibrio de carga de hardware NO DEBE estar marcada como httpOnly
    
- La cookie de equilibrio de carga de hardware NO DEBE tener tiempo de expiración
    
- La cookie de equilibrio de carga de hardware DEBE tener el nombre **MS-WSMAN** (este es el esperado por los servicios web y no puede modificarse)
    
- La cookie de equilibrio de carga de hardware DEBE estar establecida en cada respuesta HTTP para la que la solicitud HTTP entrante no tenía una cookie, independientemente de si una respuesta HTTP anterior en la misma conexión TCP ya había obtenido una cookie. Si el equilibrador de carga optimiza la inserción de cookies para que solo ocurra una vez por conexión TCP, la optimización NO debe usarse.
    
> [!NOTE]
> Las configuraciones típicas del equilibrador de carga de hardware usan afinidad de dirección de origen y una duración de sesión TCP de 20 minutos, lo que es adecuado para clientes de Lync Server y Lync 2013 porque el estado de sesión se mantiene a través del uso del cliente y/o de la interacción de la aplicación. 
  
Si se implementan dispositivos móviles, el equilibrador de carga de hardware debe poder equilibrar la carga de una solicitud individual dentro de una sesión TCP (de hecho, debe poder equilibrar la carga de una solicitud individual basada en la dirección IP de destino).
  
> [!CAUTION]
> Si va a implementar dispositivos móviles, el equilibrador de carga de hardware debe ser capaz de equilibrar individualmente la carga de cada solicitud dentro de una conexión TCP. Las últimas aplicaciones móviles que utilizan el sistema Apple iOS requieren el uso seguridad de capa de transporte (TLS), versión 1.2.  
  
> [!CAUTION]
> Para obtener más información sobre equilibradores de carga de hardware de terceros, consulte [Infraestructura para Skype Empresarial.](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)  
  
A continuación se muestran los requisitos del equilibrador de carga de hardware para servicios web de grupo de directores y de servidores front-end:
  
- Para VIPS de servicios web internos, configure la persistencia Source_addr (puerto interno 80, 443) en el equilibrador de carga de hardware. Para Skype Empresarial Server, Source_addr persistencia significa que se envían siempre varias conexiones procedentes de una única dirección IP a un servidor para mantener el estado de sesión.
    
- Use un tiempo de espera de inactividad TCP de 1.800 segundos.
    
- En el firewall entre el proxy inverso y el equilibrador de carga de hardware del grupo de servidores del próximo salto, cree una regla para permitir el tráfico https: en el puerto 4443, desde el proxy inverso al equilibrador de carga de hardware. El equilibrador de carga de hardware debe configurarse de modo que escuche los puertos 80, 443 y 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumen de requisitos de afinidad del equilibrador de carga de hardware

|**Ubicación de cliente/usuario**|**Requisitos de afinidad del FQDN de servicios web externos**|**Requisitos de afinidad del FQDN de servicios web internos**|
|:-----|:-----|:-----|
|Lync Web App (usuarios internos y externos)  <br/> Dispositivo móvil (usuarios internos y externos)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Lync Web App (solo usuarios externos)  <br/> Dispositivo móvil (usuarios internos y externos)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
|Lync Web App (solo usuarios internos)  <br/> Dispositivo móvil (no implementado)  <br/> |Sin afinidad  <br/> |Afinidad de direcciones de origen  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Supervisión de puertos para los equilibradores de carga de hardware

Es necesario definir la supervisión de puertos en los equilibradores de carga de hardware para determinar cuándo determinados servicios dejan de estar disponibles debido a errores de comunicaciones o de hardware. Por ejemplo, si el servicio de servidor front-end (RTCSRV) se detiene porque se produce un error en el servidor front-end o el grupo de servidores front-end, la supervisión de HLB también debe dejar de recibir tráfico en los servicios web. La supervisión de puertos en el equilibrador de carga de hardware debe implementarse para supervisar lo siguiente:
  
**Grupo de usuarios del servidor front-end: interfaz interna de HLB**

|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-end  <br/> 5061  <br/> |Origen  <br/> |HTTPS  <br/> |
|\<pool\>web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-end  <br/> 5061  <br/> |Origen  <br/> |HTTP  <br/> |
   
**Grupo de usuarios del servidor front-end: interfaz externa de HLB**

|**Puerto/IP virtual**|**Puerto de nodo**|**Monitor/máquina de nodo**|**Perfil de persistencia**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Ninguno  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>Equilibrio de carga de DNS
<a name="BKMK_DNSLoadBalancing"> </a>

Skype Empresarial Server habilita el equilibrio de carga de DNS, una solución de software que puede reducir en gran medida la sobrecarga de administración para el equilibrio de carga en la red. El equilibrio de carga de DNS equilibra el tráfico de red que es exclusivo de Skype Empresarial Server, como el tráfico SIP y el tráfico de medios.
  
Si implementa el equilibrio de carga de DNS, se minimizará la sobrecarga de administración de la organización para los equilibradores de carga de hardware. Además, se evitará la solución de problemas complejos asociados a errores de configuración de equilibradores de carga del tráfico SIP. También puede impedir que se establezcan conexiones de servidores para poder desconectar servidores. El equilibrio de carga de DNS también garantiza que los problemas relacionados con los equilibradores de carga de hardware no afecten a elementos de tráfico SIP, como el enrutamiento de llamadas básico.

En el siguiente diagrama se muestra un ejemplo que incluye el equilibrio de carga de DNS interno y externo: 
  
**Diagrama de red perimetral con direcciones IPv4 públicas**

![ejemplo de diagrama de red DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Si se utiliza el equilibrio de carga de DNS también podría adquirir equilibradores de carga de hardware a un precio más económico que si usa equilibradores de carga de hardware para todos los tipos de tráfico. Debe usar equilibradores de carga que han superado las pruebas de calificación de interoperabilidad con Skype Empresarial Server. Para obtener más información acerca de las pruebas de interoperabilidad del equilibrador de carga, consulte [Lync Server 2010 Load Balancer Partners](https://go.microsoft.com/fwlink/p/?linkId=202452). El contenido se aplica a Skype Empresarial Server.
  
El equilibro de carga de DNS es compatible con los grupos front-end, los grupos de servidores perimetrales, los grupos de director y los grupos del servidor de mediación independientes.
  
El equilibrio de carga de DNS suele implementarse en el nivel de la aplicación. La aplicación (por ejemplo, un cliente que ejecuta Skype Empresarial) intenta conectarse a un servidor de un grupo de servidores conectándose a una de las direcciones IP devueltas desde la consulta de registro A y AAAA (si se usa el direccionamiento IPv6) de DNS para el nombre de dominio completo (FQDN) del grupo de servidores. 
  
Por ejemplo, si hay tres servidores front-end en un grupo de servidores denominado pool01.contoso.com, pasará lo siguiente:
  
- Los clientes que ejecutan Skype Empresarial consultan DNS para pool01.contoso.com. La consulta devuelve tres direcciones IP y las almacena en caché de la siguiente manera (no necesariamente en este orden):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- El cliente intenta establecer una conexión del Protocolo de control de transmisión (TCP) a una de las direcciones IP. Si no funciona, lo intentará con la siguiente dirección IP almacenada en caché.
    
- Si la conexión TCP se realiza correctamente, el cliente negocia TLS para conectarse al registrador principal en pool01.contoso.com.
    
- Si el cliente intenta todas las entradas almacenadas en caché sin una conexión correcta, se notifica al usuario que no hay servidores que ejecuten Skype Empresarial Server en este momento.
    
> [!NOTE]
> El equilibrio de carga basado en DNS es distinto al round robin de DNS (DNS RR), que normalmente hace referencia al equilibrio de carga usando el DNS para proporcionar un orden distinto de direcciones IP correspondientes a los servidores de un grupo de servidores. Por lo general, DNS RR solo habilita la distribución de carga, pero no habilita la conmutación por error. Por ejemplo, si se produce un error en la conexión a la única dirección IP devuelta por la consulta A y AAAA (si usa el direccionamiento IPv6) de DNS, se produce un error en la conexión. Por tanto, el round robin de DNS por sí solo es menos fiable que el equilibrio de carga basado en DNS. Puede usar el round robin de DNS junto con el equilibrio de carga de DNS. 
  
El equilibrio de carga de DNS se usa para lo siguiente:
  
- Equilibrio de carga de SIP de servidor a servidor con los servidores perimetrales
    
- Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS, Unified Communications Application Services), como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas.
    
- Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (proceso también conocido como "purga").
    
- Equilibrar la carga de todo el tráfico de servidor a cliente entre clientes y servidores perimetrales
    
El equilibrio de carga de DNS no puede usarse para:
  
- Tráfico web de cliente a servidor a servidores front-end o directores
    
Equilibrio de carga de DNS y tráfico federado:
  
Si una consulta SRV de DNS devuelve varios registros DNS, el servicio perimetral de acceso siempre selecciona el registro SRV de DNS con la prioridad numérica más baja y el peso numérico más alto. El documento "Un RR de DNS para especificar la ubicación de los servicios (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) especifica que si hay varios registros SRV de DNS definidos, primero se usa la prioridad y, a continuación, el peso. Por ejemplo, el registro SRV de DNS A tiene un peso de 20 y una prioridad de 40 y el registro SRV de DNS B tiene un peso de 10 y una prioridad de 50. Se seleccionará el registro SRV de DNS A con prioridad 40. Las siguientes reglas se aplican a la selección de registros SRV de DNS:
  
- La prioridad se considera en primer lugar. Un cliente DEBE intentar ponerse en contacto con el host de destino definido por el registro SRV de DNS con la prioridad numerada más baja que pueda alcanzar. Los destinos con la misma prioridad DEBEN probarse en un orden definido por el campo de peso.
    
- El campo de peso especifica un peso relativo para las entradas con la misma prioridad. Los pesos más grandes DEBEN tener una probabilidad proporcionalmente mayor de ser seleccionados. Los administradores de DNS DEBEN usar el peso 0 cuando no hay ninguna selección de servidor que hacer. En presencia de registros que contienen pesos mayores que 0, los registros con peso 0 deben tener una probabilidad muy pequeña de ser seleccionados.
    
Si se devuelven varios registros DNS SRV con la misma prioridad y peso, el servicio perimetral de acceso seleccionará el registro SRV que se recibió primero desde el servidor DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director

Puede usar el equilibrio de carga DNS para el tráfico SIP de los grupos de servidores front-end y grupos de servidores de director. Con el equilibrio de carga DNS implementado, seguirá necesitando usar también equilibradores de carga de hardware para esos grupos de servidores, pero solo para el tráfico HTTPS de cliente a servidor. El equilibrador de carga de hardware se usa para el tráfico HTTPS de los clientes en los puertos 443 y 80. 
  
A pesar de que seguirá necesitando equilibradores de carga de hardware para esos grupos de servidores, su instalación y administración será fundamentalmente para el tráfico HTTPS, al que están habituados los administradores de equilibradores de carga de hardware.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Equilibrio de carga DNS y compatibilidad con clientes y servidores más antiguos

El equilibrio de carga de DNS solo admite la conmutación por error automática para los servidores que ejecutan Skype Empresarial Server o Lync Server 2010, y para clientes de Lync 2013 y Skype Empresarial. Las versiones anteriores de los clientes y Office Communications Server aún pueden conectarse a grupos que ejecutan equilibrio de carga dns, pero si no pueden establecer una conexión con el primer servidor al que hace referencia el equilibrio de carga de DNS, no podrán conmutar por error a otro servidor del grupo. 
  
Además, si usa la mensajería unificada de Exchange, debe usar un mínimo de Exchange 2010 SP1 para obtener compatibilidad con el equilibrio de carga de DNS de Skype Empresarial Server. Si usa una versión anterior de Exchange, los usuarios no tendrán capacidades de conmutación por error para estos escenarios de mensajería unificada de Exchange:
  
- Reproducir el correo de voz enterprise en su teléfono
    
- Transferir llamadas de un operador automático de la mensajería unificada de Exchange
    
Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Implementación del equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director
<a name="BK_FE_Dir"> </a>

Para implementar el equilibrio de carga DNS en grupos de servidores front-end y grupos de servidores de director, es necesario realizar un par de pasos adicionales con los registros DNS y los FQDN.
  
- Un grupo de servidores que usa el equilibrio de carga de DNS debe tener dos FQDN: el FQDN del grupo normal que usa el equilibrio de carga de DNS (como pool01.contoso.com) y se resuelve en las DIRECCIONES IP físicas de los servidores del grupo de servidores y otro FQDN para los servicios web del grupo (como web01.contoso.com), que se resuelve en la dirección IP virtual del grupo. 
    
    En el Generador de topologías, si desea implementar el equilibrio de carga dns para un grupo de servidores, para crear este FQDN adicional para  los servicios web del grupo, debe activar la casilla invalidar el **FQDN** del grupo de servidores de servicios web internos y escribir el FQDN, en la página Especificar las direcciones URL de servicios web para este grupo de servidores.
    
- Para admitir el FQDN que usa el equilibrio de carga DNS, debe aprovisionar el DNS de modo que resuelva el FQDN del grupo de servidores (como, por ejemplo, pool01.contoso.com) como las direcciones IP de todos los servidores del grupo de servidores (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Solo deberá incluir las direcciones IP de los servidores implementados actualmente.
    
    > [!CAUTION]
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end. Si también implementa directores, el FQDN de servicios web externos definido para cualquier director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como de cualquier grupo de servidores front-end o servidor front-end. Si decide invalidar los servicios web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Equilibrio de carga DNS en grupos de servidores perimetrales
<a name="BK_Edge"> </a>

Puede implementar el equilibrio de carga DNS en grupos de servidores perimetrales. Si lo hace, debe tener en cuenta varias consideraciones.
  
El uso del equilibrio de carga DNS en los servidores perimetrales provoca una pérdida en la capacidad de conmutación por error, en los siguientes escenarios:
  
- Federación con organizaciones que ejecutan versiones de Skype Empresarial Server publicadas antes de Lync Server 2010.
    
- Intercambio de mensajes instantáneos con usuarios de servicios públicos de mensajería instantánea (MI) AOL y Yahoo!, además de proveedores y servidores basados en XMPP, como Google Talk, actualmente el único socio XMPP compatible.
    
Estos escenarios funcionarán siempre que se ejecuten correctamente todos los servidores perimetrales del grupo de servidores pero, si un servidor perimetral no está disponible, fallarán todas las solicitudes de estos escenarios que se envíen a él, en lugar de enrutarse a otro servidor perimetral.
  
 Si usa la mensajería unificada de Exchange, debe usar un mínimo de Exchange 2013 para obtener compatibilidad con el equilibrio de carga dns de Skype Empresarial Server en el servidor perimetral. Si usa una versión anterior de Exchange, los usuarios remotos no tendrán capacidades de conmutación por error para estos escenarios de mensajería unificada de Exchange:
  
- Reproducir el correo de voz enterprise en su teléfono
    
- Transferir llamadas de un operador automático de la mensajería unificada de Exchange
    
Todos los demás escenarios de la mensajería unificada de Exchange funcionarán correctamente.
  
La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implementación del equilibrio de carga DNS en grupos de servidores perimetrales

Para implementar el equilibrio de carga DNS en la interfaz externa de su grupo de servidores perimetrales, necesita las siguientes entradas DNS:
  
- Para el servicio perimetral de acceso, necesita una entrada para cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de acceso (por ejemplo, sip.contoso.com) en la dirección IP del servicio perimetral de acceso en uno de los servidores perimetrales del grupo de servidores.
    
- Para el servicio perimetral de conferencia web, necesita una entrada para cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de conferencia web (por ejemplo, webconf.contoso.com) en la dirección IP del servicio perimetral de conferencia web en uno de los servidores perimetrales del grupo.
    
- Para el servicio perimetral de audio y vídeo, necesita una entrada para cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de audio y vídeo (por ejemplo, av.contoso.com) en la dirección IP del servicio perimetral A/V en uno de los servidores perimetrales del grupo.
    
Para implementar el equilibrio de carga DNS en la interfaz interna del grupo de servidores perimetrales, debe agregar un registro DNS A que resuelva el FQDN interno del grupo de servidores perimetrales en la dirección IP de cada servidor del grupo de servidores.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Uso del equilibrio de carga DNS en grupos de servidores de mediación
<a name="BK_Mediation"> </a>

Puede usar el equilibrio de carga DNS en grupos de servidores de mediación independientes. Todo el tráfico de medios y SIP se equilibra con el equilibrio de carga DNS.
  
Para implementar el equilibrio de carga DNS en un grupo de servidores de mediación, debe aprovisionar el DNS de modo que resuelva el FQDN del grupo de servidores (por ejemplo, mediationpool1.contoso.com) como las direcciones IP de todos los servidores del grupo de servidores (por ejemplo, 192.168.1.1, 192.168.1.2, etc.).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloquear el tráfico a un servidor con equilibrio de carga dns
<a name="BK_Mediation"> </a>

Si usa el equilibrio de carga de DNS y necesita bloquear el tráfico a un equipo específico, no es suficiente simplemente quitar las entradas de dirección IP del FQDN del grupo de servidores. También debe quitar la entrada DNS del equipo. 
  
Tenga en cuenta que para el tráfico de servidor a servidor, Skype Empresarial Server usa equilibrio de carga para topologías. Los servidores leen la topología publicada en el almacén de administración central para obtener los FQDN de los servidores de la topología y distribuir automáticamente el tráfico entre los servidores. Para impedir que un servidor reciba tráfico de servidor a servidor, debe quitar el servidor de la topología. 
  

