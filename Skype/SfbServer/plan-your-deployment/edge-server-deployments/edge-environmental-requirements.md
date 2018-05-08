---
title: Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Resumen: Obtenga información sobre los requisitos del entorno de servidor perimetral en Skype para Business Server 2015.'
ms.openlocfilehash: 1e4eb8f63089ed4074489342727aa9a70f0211da
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server-2015"></a>Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre los requisitos del entorno de servidor perimetral en Skype para Business Server 2015.
  
Una gran cantidad de planeación y preparación debe llevarse a cabo fuera de la Skype para el entorno de servidor perimetral de Business Server 2015 propio. En este artículo, repasaremos qué preparativos tiene que realizar en el entorno de la organización, según la lista que se muestra abajo:
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planificar la topología
<a name="TopoPlan"> </a>

Skype para topologías de servidor perimetral de Business Server 2015 son capaces de usar:
  
- Direcciones IP públicas enrutables.
    
- Direcciones IP privadas no enrutables si se usa la traducción de direcciones de red (NAT) **simétrica**.
    
> [!TIP]
> El servidor perimetral puede configurarse para utilizar una sola dirección IP con puertos distintos para cada servicio, o puede usar distintas direcciones IP para cada servicio, pero usan el mismo puerto predeterminado (que, de forma predeterminada, será TCP 443). Hay más información en la sección de requisitos de las direcciones IP de abajo. 
  
Si elige direcciones IP privadas no enrutables con NAT, recuerde los siguientes puntos:
  
- Tiene que usar direcciones IP privadas enrutables en las **tres** interfaces externas.
    
- Tiene que configurar la NAT **simétrica** para el tráfico entrante y saliente. NAT simétrico es que el único admitido NAT puede usar con Skype para servidor perimetral de Business Server 2015.
    
- Configure la NAT para que no cambie las direcciones de origen entrantes. El / servicio perimetral A/v debe poder recibir la dirección de origen entrante para buscar la ruta de medios óptima.
    
- Los servidores perimetrales necesita poder comunicarse entre sí desde sus pública / direcciones IP perimetrales de A/v. El firewall tiene que permitir este tráfico.
    
- NAT puede **sólo** se utilizan para escalado los servidores perimetrales consolidados si usa equilibrio de carga DNS. Si usa el equilibrio de carga de hardware (HLB), tiene que usar direcciones IP enrutables públicamente **sin** NAT.
    
No tendrá que tienen problemas con su acceso, conferencia Web y / interfaces de servidor perimetral A/v detrás de un enrutador o firewall realiza NAT simétrica para escaladas y únicas consolidan topologías de servidor perimetral (siempre que no se utiliza el equilibrio de carga de hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Resumen de las opciones de topología de servidor perimetral

Tenemos varias opciones de topología disponibles para Skype para implementaciones de servidor perimetral de Business Server 2015:
  
- Servidor perimetral consolidado simple con direcciones IP privadas y NAT
    
- Servidor perimetral consolidado simple con direcciones IP públicas
    
- Servidor perimetral consolidado ampliado con direcciones IP privadas y NAT
    
- Servidor perimetral consolidado ampliado con direcciones IP públicas
    
- Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
    
Para que le sea más fácil elegir una, la siguiente tabla le ofrece un resumen de las opciones de cada topología:
  
|**Topología**|**Alta disponibilidad**|**¿Registros DNS adicionales necesarios para el servidor perimetral externo en el grupo de servidores perimetrales?**|**Conmutación por error perimetral para Skype para las sesiones de Business Server**|**Conmutación por error perimetral para Skype para sesiones de federación Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Servidor perimetral consolidado simple con direcciones IP privadas y NAT  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Servidor perimetral consolidado simple con direcciones IP públicas  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Servidor perimetral consolidado ampliado con direcciones IP privadas y NAT (con equilibrio de carga DNS)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí & sup1;  <br/> |
|Servidor perimetral consolidado ampliado con direcciones IP públicas (con equilibrio de carga DNS)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí & sup1;  <br/> |
|Servidor perimetral consolidado ampliado con equilibradores de carga de hardware  <br/> |Sí  <br/> |No (un registro A DNS por VIP)  <br/> |Sí  <br/> |Sí  <br/> |
   
& sup1; Conmutación por error de usuarios remotos de mensajería unificada de Exchange (UM) con equilibrio de carga DNS requiere Exchange 2013 o más reciente.
  
### <a name="ip-address-requirements"></a>Requisitos de direcciones IP

En un nivel fundamental, tres servicios necesitan direcciones IP; Servicio de acceso perimetral, servicio perimetral de conferencia Web y / servicio perimetral A/v. Tiene la opción de usar tres direcciones IP, una para cada uno de los servicios, o puede usar uno y optar por poner cada servicio en un puerto diferente (puede comprobar la sección [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto). Para un entorno de servidor perimetral consolidado simple, es prácticamente todo.
  
> [!NOTE]
> Como se indica anteriormente, puede optar por tener una dirección IP para los tres servicios y ejecutarlos en diferentes puertos. Para ser claros, no lo recomendamos. Si sus clientes no pueden tener acceso a los puertos alternativos que usa en este escenario, tampoco pueden obtener acceso a la característica completa de su entorno perimetral. 
  
Puede ser un poco más complicado con topologías consolidadas ampliadas, por lo que vamos a ver algunas tablas que organizan los requisitos de direcciones IP, teniendo en cuenta que los aspectos principales a la hora de decantarse por una topología son la alta disponibilidad y el equilibrio de carga. Las necesidades de la alta disponibilidad pueden influir en la opción del equilibrio de carga (hablaremos de ello después de las tablas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de dirección IP para servidor perimetral consolidado ampliado (dirección IP por rol)

|**Número de servidores perimetrales por grupo de servidores**|**Número de direcciones IP requeridas para DNS el equilibrio de carga**|**Número de direcciones IP requeridas para el equilibrio de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 por VIP) + 6  <br/> |
|3  <br/> |9  <br/> |3 (1 por VIP) + 9  <br/> |
|4  <br/> |12  <br/> |3 (1 por VIP) + 12  <br/> |
|5  <br/> |15  <br/> |3 (1 por VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de dirección IP para servidor perimetral consolidado ampliado (dirección IP única para todos los roles)

|**Número de servidores perimetrales por grupo de servidores**|**Número de direcciones IP requeridas para DNS el equilibrio de carga**|**Número de direcciones IP requeridas para el equilibrio de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 por VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 por VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 por VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 por VIP) + 5  <br/> |
   
Veamos algunos asuntos adicionales en los que pensar durante la planeación.
  
- **Alta disponibilidad**: si necesita una alta disponibilidad en su implementación, debe implementar al menos dos servidores perimetrales en un grupo de servidores. Merece la pena indicar que un único grupo de servidores perimetrales admitirá hasta 12 servidores perimetrales (aunque Topology Builder le permitirá agregar hasta 20, que no se ha probado o compatible, por lo que le recomendamos que no lo haga). Si necesita más de 12 servidores perimetrales, debe crear grupos de servidores perimetrales adicionales para ellos.
    
- **Equilibrio de carga de hardware**: se recomienda para la mayoría de los escenarios de equilibrio de carga de DNS. Equilibrio de carga de hardware también es compatible, por supuesto, pero en particular, es necesario para un escenario de único a través de equilibrio de carga de DNS:
    
  - Acceso externo a Exchange 2007 o mensajería unificada de Exchange 2010 (con ningún SP) (UM).
    
- **Equilibrio de carga DNS**: para mensajería unificada, Exchange 2010 SP1 y son más reciente puede ser compatible con el equilibrio de carga DNS. Tenga en cuenta que si necesita ir con DNS equilibrio de carga para una versión anterior de Exchange, va a trabajar, pero todo el tráfico para esto se realizarán en el primer servidor en el grupo de servidores, y si no está disponible, ese tráfico posteriormente se producirá un error.
    
    También se recomienda el equilibrio de carga DNS, si está federar con compañías mediante Lync Server 2010, Lync Server 2013 y Microsoft Office 365.
    
## <a name="dns-planning"></a>Planificación de DNS
<a name="DNSPlan"> </a>

Cuando se trata de Skype para la implementación de servidor perimetral de Business Server 2015, es esencial para preparar correctamente para DNS. Con los registros correctos en su ubicación, la implementación será mucho más sencilla. Afortunadamente ha elegido una topología en la sección anterior, ya que realizaremos una descripción general y después enumeraremos algunas tablas que esquematicen los registros DNS para esos escenarios. También tendremos algunos [avanzada DNS de servidor perimetral de planeación de Skype para Business Server 2015](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) para la lectura más detallada, si lo necesita.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Registros DNS para un solo consolidada escenarios de servidor perimetral

Se trata de los registros DNS que se va a necesitar para un servidor perimetral mediante ambos pública única IP o IP privada con NAT. Dado que estos son datos de ejemplo, le daremos IP de muestra para que pueda resolver sus propias entradas de forma más fácil:
  
- Adaptador de red interna: 172.25.33.10 (no hay ninguna puerta de enlace predeterminada asignada)
    
    > [!NOTE]
    > Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna para todas las redes que contienen servidores que ejecutan Skype para clientes empresariales Server 2015 o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externa:
    
  - IP públicas:
    
  - Servidor perimetral de acceso: 131.107.155.10 (Esto es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, ej: 131.107.155.1)
    
  - Servidor perimetral de conferencia Web: 131.107.155.20 (secundario)
    
  - A / perimetral A/v: 131.107.155.30 (secundario)
    
  Conferencia Web y direcciones IP públicas de servidor perimetral A/v son las direcciones IP adicionales (secundarias) en la sección Opciones avanzada de las propiedades del protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área Local en Windows Server.
    
  - IP privadas:
    
  - Servidor perimetral de acceso: 10.45.16.10 (Esto es el principal, con la puerta de enlace predeterminada establecida en el enrutador, ej: 10.45.16.1)
    
  - Servidor perimetral de conferencia Web: 10.45.16.20 (secundario)
    
  - A / perimetral A/v: 10.45.16.30 (secundario)
    
Conferencia Web y direcciones IP públicas de servidor perimetral A/v son las direcciones IP adicionales (secundarias) en la sección Opciones avanzada de las propiedades del protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área Local en Windows Server.
  
> [!TIP]
>Hay otra configuración posible:
  
- Puede usar una dirección IP en el adaptador de red externa. No se recomienda esto porque, a continuación, va a necesitar diferenciar entre los tres servicios que utilizan diferentes puertos (lo que puede hacer en Skype para Business Server) pero hay algunos servidores de seguridad que se pueden bloquear los puertos alternativos. Vea la sección de [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto.
    
- Puede tener tres adaptadores de red externa en lugar de uno y asignar una de las IP del servicio a cada uno. ¿Por qué? Se separarían los servicios y si algo va mal, facilitaría solucionar los problemas y dejar que otros servicios continuasen trabajando potencialmente mientras resuelve un problema.
    
|**Ubicación**|**Tipo de**|**Puerto**|**Registro FQDN o DNS**|**Dirección IP o el FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |SIP.contoso.com  <br/> |**pública:** 131.107.155.10 <br/> **privada:** 10.45.16.10 <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Uno para cada dominio SIP con Skype que necesitará para los usuarios empresariales.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |Webcon.contoso.com  <br/> |**pública:** 131.107.155.20 <br/> **privada:** 10.45.16.20 <br/> |Una interfaz externa para el servicio perimetral de conferencia Web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |AV.contoso.com  <br/> |**pública:** 131.107.155.30 <br/> **privada:** 10.45.16.30 <br/> |Una interfaz externa para pasar de una / servicio perimetral A/v.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |SIP.contoso.com  <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Este registro SRV es necesario para Skype para clientes empresariales Server 2015, Lync Server 2013 y Lync Server 2010 trabajar externamente. Uno para cada dominio con Skype que necesitará para los usuarios empresariales.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Este registro SRV es necesario para la detección DNS automática de asociados federados denominada Dominios SIP permitidos. Uno para cada dominio con Skype que necesitará para los usuarios empresariales.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |NA  <br/> |sfvedge.contoso.NET  <br/> |172.25.33.10  <br/> |La interfaz interna para el servidor perimetral consolidado.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Registros DNS para DNS escalada y escenarios de servidor perimetral de hardware

Se trata de los registros DNS que se va a necesitar para un servidor perimetral mediante ambos pública única IP o IP privada con NAT. Dado que estos son datos de ejemplo, le daremos IP de muestra para que pueda resolver sus propias entradas de forma más fácil:
  
- Adaptador de red interna:
    
  - Nodo 1: 172.25.33.10 (no hay ninguna puerta de enlace predeterminada asignada)
    
  - Nodo 2: 172.25.33.11 (no hay ninguna puerta de enlace predeterminada asignada)
    
    > [!NOTE]
    > Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna para todas las redes que contienen servidores que ejecutan Skype para clientes empresariales Server 2015 o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externa:
    
  - Nodo 1
    
     - IP públicas:
    
        - Servidor perimetral de acceso: 131.107.155.10 (Esto es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, ej: 131.107.155.1)
    
        - Servidor perimetral de conferencia Web: 131.107.155.20 (secundario)
    
        - A / perimetral A/v: 131.107.155.30 (secundario)
    
          Conferencia Web y direcciones IP públicas de servidor perimetral A/v son las direcciones IP adicionales (secundarias) en la sección Opciones avanzada de las propiedades del protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área Local en Windows Server.
    
    - IP privadas:
    
         - Servidor perimetral de acceso: 10.45.16.10 (Esto es el principal, con la puerta de enlace predeterminada establecida en el enrutador, ej: 10.45.16.1)
    
         - Servidor perimetral de conferencia Web: 10.45.16.20 (secundario)
    
         - A / perimetral A/v: 10.45.16.30 (secundario)
    
      Conferencia Web y direcciones IP públicas de servidor perimetral A/v son las direcciones IP adicionales (secundarias) en la sección Opciones avanzada de las propiedades del protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área Local en Windows Server.
    
  - Nodo 2
    
     - IP públicas:
    
       - Servidor perimetral de acceso: 131.107.155.11 (Esto es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, ej: 131.107.155.1)
    
       - Servidor perimetral de conferencia Web: 131.107.155.21 (secundario)
    
       - A / perimetral A/v: 131.107.155.31 (secundario)
    
      Conferencia Web y direcciones IP públicas de servidor perimetral A/v son las direcciones IP adicionales (secundarias) en la sección Opciones avanzada de las propiedades del protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área Local en Windows Server.
    
  - IP privadas:
    
      - Servidor perimetral de acceso: 10.45.16.11 (Esto es el principal, con la puerta de enlace predeterminada establecida en el enrutador, ej: 10.45.16.1)
    
      - Servidor perimetral de conferencia Web: 10.45.16.21 (secundario)
    
      - A / perimetral A/v: 10.45.16.31 (secundario)
    
      Conferencia Web y direcciones IP públicas de servidor perimetral A/v son las direcciones IP adicionales (secundarias) en la sección Opciones avanzada de las propiedades del protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área Local en Windows Server.
    
Hay otra configuración posible:
  
- Puede usar una dirección IP en el adaptador de red externa. No se recomienda esto porque, a continuación, va a necesitar diferenciar entre los tres servicios que utilizan diferentes puertos (lo que puede hacer en Skype para Business Server) pero hay algunos servidores de seguridad que se pueden bloquear los puertos alternativos. Vea la sección de [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto.
    
- Puede tener tres adaptadores de red externa en lugar de uno y asignar una de las IP del servicio a cada uno. ¿Por qué? Se separarían los servicios y si algo va mal, facilitaría solucionar los problemas y dejar que otros servicios continuasen trabajando potencialmente mientras resuelve un problema.
    
|**Ubicación**|**Tipo de**|**Puerto**|**Registro FQDN o DNS**|**Dirección IP o el FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |SIP.contoso.com  <br/> |**público:** 131.107.155.10 y 131.107.155.11 <br/> **privadas:** 10.45.16.10 y 10.45.16.11 <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Uno para cada dominio SIP con Skype que necesitará para los usuarios empresariales.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |Webcon.contoso.com  <br/> |**público:** 131.107.155.20 y 131.107.155.21 <br/> **privadas:** 10.45.16.20 y 10.45.16.21 <br/> |Una interfaz externa para el servicio perimetral de conferencia Web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |AV.contoso.com  <br/> |**público:** 131.107.155.30 y 131.107.155.31 <br/> **privadas:** 10.45.16.30 y 10.45.16.31 <br/> |Una interfaz externa para pasar de una / servicio perimetral A/v.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |SIP.contoso.com  <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Este registro SRV es necesario para Skype para clientes empresariales Server 2015, Lync Server 2013 y Lync Server 2010 trabajar externamente. Necesitará una para cada dominio con Skype para la empresa.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Este registro SRV es necesario para la detección DNS automática de asociados federados denominada Dominios SIP permitidos. Necesitará una para cada dominio con Skype para la empresa.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |NA  <br/> |sfvedge.contoso.NET  <br/> |172.25.33.10 y 172.25.33.11  <br/> |La interfaz interna para el servidor perimetral consolidado.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para la federación (todos los escenarios)

|**Ubicación**|**Tipo de**|**Puerto**|**FQDN**|**Registro de host FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |La interfaz externa de servidor perimetral de acceso SIP requerida para la detección automática de DNS. Usada por otros posibles asociados de federación. También se conoce como "Permitir dominios SIP". Uno de los siguientes para cada dominio SIP con Skype que necesitará para los usuarios empresariales.  <br/><br/> **Nota:** Necesitará este registro SRV para movilidad y compensación de la notificación de inserción. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Registros DNS para el protocolo extensible de mensajería y presencia

|**Ubicación**|**Tipo de**|**Puerto**|**FQDN**|**Dirección IP o el registro de host FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp server._tcp.contoso.com  <br/> |XMPP.contoso.com  <br/> |La interfaz de proxy XMPP en el servicio de servidor perimetral de acceso o el grupo de servidores perimetrales. Debe repetir este según sea necesario para todos los dominios SIP internos con Skype para los usuarios profesionales habilitado, que se permite en contacto con los contactos XMPP a través de:  <br/> • una directiva global  <br/> • una directiva de sitio donde el usuario del habilitado  <br/> • una directiva de usuario que se aplican a la Skype para la empresa de usuario habilitado  <br/> Una directiva XMPP permitida también se tiene que configurar en la directiva de usuarios federados XMPP.  <br/> |
|DNS externo  <br/> |SRV  <br/> |A  <br/> |XMPP.contoso.com  <br/> |Dirección IP del servicio de servidor perimetral de acceso en el servidor perimetral o grupo de servidores perimetrales que hospeda el servicio Proxy XMPP  <br/> |Esto señala al servicio de servidor perimetral de acceso en el servidor perimetral o grupo de servidores perimetrales que hospeda el servicio Proxy XMPP. Por lo general, el registro SRV que crea apuntará a este registro de host (A o AAAA).  <br/> |
   
## <a name="certificate-planning"></a>Planificar certificado
<a name="CertPlan"> </a>

Skype para Business Server 2015 utiliza certificados para las comunicaciones seguras, cifradas entre los servidores y del servidor al cliente. Como cabría esperar, los certificados tendrán que tener registros DNS para sus servidores para que coincidan con cualquier nombre de sujeto (SN) y nombre alternativo de sujeto (SAN) en los certificados. Esto le llevará trabajo ahora, en la fase de planificación, para garantizar que tiene los FQDN correctos registrados en DNS para las entradas de SN y de SAN para los certificados.
  
Hablaremos de las necesidades de los certificados internos y externos por separado y después veremos una tabla que proporciona los requisitos para ambos.
  
### <a name="external-certificates"></a>Certificados externos

Como mínimo, el certificado asignado a las interfaces de servidor perimetral externas deberá ser proporcionado por una entidad de certificación (CA) pública. No podemos recomendamos una entidad de certificación específico para usted, pero hemos desarrollado una lista de entidades de certificación de [los socios de certificados de comunicaciones unificadas](https://support.microsoft.com/en-us/kb/929395) que puede Eche un vistazo a ver si la entidad de certificación preferido aparece.
  
¿Cuándo tendrá que enviar una solicitud a una entidad de certificación para este certificado público y cómo lo tiene que hacer? Hay un par de formas de llevar esto a cabo:
  
- Puede ir a través de la instalación de Skype para Business Server y, a continuación, en la implementación de servidor perimetral. El Skype para el Asistente para la implementación de Business Server tendrá un paso para generar una solicitud de certificado, a continuación, puede enviar a la entidad de certificación seleccionada.
    
- También puede usar comandos de Windows PowerShell para generar esta solicitud si está más en línea con su estrategia de implementación o necesidades de negocio.
    
- Por último, la entidad de certificación puede tener su propio proceso de envío, que también puede implicar Windows PowerShell u otro método. En ese caso, tendrá que basarse en su documentación, además de en la información proporcionada aquí para su consulta.
    
Una vez que ha llegado el certificado, necesitará a asignar a estos servicios en Skype para Business Server:
  
- Interfaz de servicio de acceso perimetral
    
- Interfaz de servicio de servidor perimetral de conferencia Web
    
- Servicio de autenticación de audio y vídeo (no se debe confundir esto con el servicio perimetral A/v, como los que no utilizar un certificado para cifrar las secuencias de audio y vídeos)
    
> [!IMPORTANT]
> Todos los servidores perimetrales tienen que tener exactamente el mismo certificado con la misma clave privada para el servicio de autenticación relé multimedia. 
  
### <a name="internal-certificates"></a>Certificados internos

Para la interfaz interna del servidor perimetral, puede usar un certificado público de una CA pública, o un certificado emitido por la entidad de certificación interna de la organización. Lo que hay que recordar sobre el certificado interno es que usa una entrada de SN y no entradas de SAN, de modo que no tiene que preocuparse por SAN en el certificado interno en absoluto.
  
### <a name="required-certificates-table"></a>Tabla de certificados necesarios

Aquí tenemos una tabla para ayudarle con las solicitudes. Las entradas de FQDN son solo para dominios de ejemplo. Tendrá que realizar solicitudes en función de sus propios dominios privados y públicos, pero esta es una guía sobre lo que hemos usado:
  
- contoso.com: FQDN público
    
- fabrikam.com: segundo FQDN público (agregado como una demo de lo que tiene que solicitar si tiene varios dominios SIP)
    
- Contoso.net: dominio interno
    
#### <a name="edge-certificate-table"></a>Tabla de certificado perimetral

Independientemente de si está realizando un solo servidor perimetral o un grupo de servidores perimetrales, esto es lo que necesita para el certificado:
  
|**Componente**|**Nombre de sujeto (SN)**|**Nombres de sujeto alternativos (SAN) / orden**|**Notas**|
|:-----|:-----|:-----|:-----|
|Servidor perimetral externo  <br/> |SIP.contoso.com  <br/> |SIP.contoso.com  <br/> Webcon.contoso.com  <br/> SIP.fabrikam.com  <br/> |Este es el certificado que tiene que solicitar a una entidad de certificación pública. Tendrá que estar asignado a las interfaces perimetrales externas para lo siguiente:<br/> • Servidor perimetral de acceso  <br/> • Servidor perimetral de conferencia web  <br/> • Autenticación de audio y vídeo  <br/> <br/>La buena noticia es que SAN se agrega automáticamente a la solicitud de certificado y, por lo tanto, el certificado después de enviar la solicitud, según lo que haya definido para esta implementación en el generador de topología. Solo tiene que agregar las entradas de SAN para cualquier dominio SIP adicional u otras entradas que necesite admitir. ¿Por qué sip.contoso.com aparece duplicado en esta instancia? Esto se produce automáticamente y es necesario para que todo funcione correctamente.  <br/><br/> **Nota:** También se puede utilizar este certificado para la conectividad de mensajería instantánea pública. No tiene que hacer nada diferente con él, pero en versiones anteriores de esta documentación, se ha incluido como una tabla independiente, y ahora no lo es. <br/> |
|Servidor perimetral interno  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Puede obtener este certificado de una entidad de certificación pública o de una entidad de certificación interna. Tendrá que contener el EKU del servidor (uso mejorado de clave) y lo asignará a la interfaz interna del servidor perimetral.  <br/> |
   
Si necesita un certificado para el protocolo extensible de mensajería y presencia (XMPP), tendrá un aspecto idéntico a las entradas del servidor perimetral externo de la tabla anterior, pero tendrá las siguientes dos entradas SAN adicionales:
  
- XMPP.contoso.com
    
- \*. contoso.com
    
Recuerde que actualmente XMPP solo es compatible con Google Talk, si lo desea o necesita usarlo para cualquier otra cosa, necesita confirmar esa característica con el proveedor involucrado.
  
## <a name="port-and-firewall-planning"></a>Planificación de puerto y de firewall
<a name="PortFirewallPlan"> </a>

Introducción a la planeación adecuado para los puertos y los firewalls de Skype para servidor perimetral de Business Server implementaciones pueden ahorrar días o semanas de solución de problemas y sobrecargar. Como resultado, enumeraremos un par de tablas que indicarán nuestro uso de protocolo y qué puertos necesita tener abiertos, entrantes y salientes, tanto para los escenarios de NAT y de IP pública. También le mostraremos tablas separadas para escenarios con equilibrio de carga de hardware (HLB) y alguna ayuda a mayores de esto. Para obtener más leerlo desde allí, también tenemos [diagramas técnicos de Skype para Business Server 2015](../../technical-diagrams.md), así como algunos [escenarios de servidor perimetral de Skype para Business Server 2015](scenarios.md) puede desproteger para sus preocupaciones de implementación concreto.
  
### <a name="general-protocol-usage"></a>Uso general de protocolo

Antes de ver las tablas de resumen para los firewall internos y externos, veamos la siguiente tabla:
  
|**Transporte de audio y vídeo**|**Uso**|
|:-----|:-----|
|UDP  <br/> |El protocolo de capa de transporte preferido para audio y vídeo.  <br/> |
|TCP  <br/> |El protocolo de capa de transporte de reserva para audio y vídeo.  <br/> El protocolo de capa de transporte necesarios para la aplicación de uso compartido a Skype para Business Server 2015, Lync Server 2013 y Lync Server 2010.  <br/> El protocolo de capa de transporte necesarios para la transferencia de archivo a Skype para Business Server 2015, Lync Server 2013 y Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para usuarios que estén usando direcciones IP privadas con NAT, así como las personas que usen direcciones IP públicas. Esto explicará todas las permutaciones en nuestra sección de [escenarios de servidor perimetral de Skype para Business Server 2015](scenarios.md) .
  
|**Función o protocolo**|**TCP o UDP**|**Intervalo de puerto de destino o puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio de servidor perimetral de acceso  <br/> |El servicio Proxy XMPP acepta tráfico desde contactos XMPP en federaciones XMPP definidas.  <br/> |
|Acceso/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Acceso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Cualquiera  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acceso/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Cualquiera  <br/> |Consulta DNS sobre UDP.  <br/> |
|Acceso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Cualquiera  <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Conferencia web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de conferencia Web <br/> **IP públicas:** Dirección IP pública de servidor perimetral servidor perimetral de conferencia Web servicio servicio <br/> |Medios de conferencias Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privadas que usan NAT:** Servidor perimetral A/v servicio del servicio <br/> **IP públicas:** Un servidor perimetral / dirección IP pública del servicio perimetral A/v <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privadas que usan NAT:** Servidor perimetral A/v servicio del servicio <br/> **IP públicas:** Un servidor perimetral / dirección IP pública del servicio perimetral A/v <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privadas que usan NAT:** Un servidor perimetral o servicio perimetral A/v <br/> **IP públicas:** Un servidor perimetral / dirección IP pública del servicio perimetral A/v <br/> |Cualquiera  <br/> |3478 saliente:  <br/> • Skype para Business Server usada para determinar la versión del servidor perimetral se está comunicando con.  <br/> • Utilizado para el tráfico de medios entre los servidores perimetrales.  <br/> • Se necesita para federación con Lync Server 2010.  <br/> • Es necesario si se implementan varios grupos de servidores perimetrales dentro de la organización.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Un servidor perimetral o servicio perimetral A/v <br/> **IP públicas:** Un servidor perimetral / dirección IP pública del servicio perimetral A/v <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Un servidor perimetral o servicio perimetral A/v <br/> **IP públicas:** Un servidor perimetral / dirección IP pública del servicio perimetral A/v <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privadas que usan NAT:** Un servidor perimetral o servicio perimetral A/v <br/> **IP públicas:** Un servidor perimetral / dirección IP pública del servicio perimetral A/v <br/> |Cualquiera  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto interno

|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de los siguientes que ejecutan el servicio de puerta de enlace XMPP:  <br/> • Servidor de Front-End  <br/> • Grupo de Front-End  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecutan en el grupo de servidores Front-End o de servidor Front-End.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Cualquier:  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor de Front-End  <br/> • Grupo de Front-End  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico SIP saliente desde el Director, el grupo de servidores Director, servidor Front-End o Front-End del grupo de servidores a la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interfaz interna del servidor perimetral  <br/> |Cualquier:  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor de Front-End  <br/> • Grupo de Front-End  <br/> |Tráfico SIP entrante al grupo de servidores Director, grupo de servidores de Director, servidor Front-End o Front-End de la interfaz interna del servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Cada servidor Front-End  <br/>  en el grupo de servidores Front-End <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico de conferencia Web su servidor Front-End o en cada servidor Front-End (si tiene un grupo de servidores Front-End) a la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Grupo de Front-End  <br/> • Cualquier aplicación de sucursal con funciones de supervivencia con este servidor perimetral  <br/> • Cualquier uso de este servidor perimetral de un servidor de sucursal con funciones de supervivencia  <br/> |Interfaz interna del servidor perimetral  <br/> |Autenticación de A y los usuarios de V desde el grupo de servidores Front-End o de servidor Front-End, o su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, con el servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta preferida para una transferencia de multimedia entre los usuarios internos y externos y su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de reserva para transferencia de multimedia entre los usuarios internos y externos y su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, si no funciona la comunicación UDP. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Cualquier:  <br/> • Servidor Front-End que contiene el almacén de Administración Central  <br/> Grupo de servidores Front-End • que contiene el almacén de Administración Central  <br/> |Interfaz interna del servidor perimetral  <br/> |Almacén de replicación de los cambios desde el almacén de Administración Central para el servidor perimetral.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado con Skype para los cmdlets del Shell de administración de Business Server y el servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registro.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado con Skype para los cmdlets del Shell de administración de Business Server y el servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registro.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado con Skype para los cmdlets del Shell de administración de Business Server y el servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registro.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Tablas de puerto de servidor perimetral para equilibradores de carga de hardware

Les estamos dando a los equilibradores de carga de hardware (HLB) y a los puertos de servidor perimetral su propia sección, ya que son algo más complicados con el hardware adicional. Vea las tablas siguientes para instrucciones para este escenario concreto:
  
#### <a name="external-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para usuarios que estén usando direcciones IP privadas con NAT, así como las personas que usen direcciones IP públicas. Esto explicará todas las permutaciones en nuestra sección de [escenarios de servidor perimetral de Skype para Business Server 2015](scenarios.md) .
  
|**Función o protocolo**|**TCP o UDP**|**Intervalo de puerto de destino o puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acceso/HTTP  <br/> |TCP  <br/> |80  <br/> |Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral  <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Acceso/DNS  <br/> |TCP  <br/> |53  <br/> |Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral  <br/> |Cualquiera  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acceso/DNS  <br/> |UDP  <br/> |53  <br/> |Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral  <br/> |Cualquiera  <br/> |Consulta DNS sobre UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Un servidor perimetral / dirección IP del servicio perimetral A/v  <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Un servidor perimetral / dirección IP pública del servicio perimetral A/v  <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Un servidor perimetral / dirección IP pública del servicio perimetral A/v  <br/> |Cualquiera  <br/> |3478 saliente:  <br/> • Skype para Business Server usada para determinar la versión del servidor perimetral se está comunicando con.  <br/> • Utilizado para el tráfico de medios entre los servidores perimetrales.  <br/> • Se necesita para federación.  <br/> • Es necesario si se implementan varios grupos de servidores perimetrales dentro de la organización.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Un servidor perimetral / dirección IP pública del servicio perimetral A/v  <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Un servidor perimetral / dirección IP pública del servicio perimetral A/v  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Un servidor perimetral / dirección IP pública del servicio perimetral A/v  <br/> |Cualquiera  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto interno

|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de los siguientes que ejecutan el servicio de puerta de enlace XMPP:  <br/> • Servidor de Front-End  <br/> Grupo de Front-End • dirección VIP que ejecuta el servicio de puerta de enlace XMPP  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecutan en el grupo de servidores Front-End o de servidor Front-End.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Cualquier:  <br/> • Servidor Front-End que contiene el almacén de Administración Central  <br/> Grupo de servidores Front-End • que contiene el almacén de Administración Central  <br/> |Interfaz interna del servidor perimetral  <br/> |Replicación de los cambios realizados desde el almacén de Administración Central en el servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Cada servidor Front-End en el grupo de servidores Front-End  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico de conferencia Web su servidor Front-End o en cada servidor Front-End (si tiene un grupo de servidores Front-End) a la interfaz interna del servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Cada servidor Front-End en el grupo de servidores Front-End  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta preferida para una transferencia de multimedia entre los usuarios internos y externos y su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Cada servidor Front-End en el grupo de servidores  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de reserva para transferencia de multimedia entre los usuarios internos y externos y su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, si no funciona la comunicación UDP. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado con Skype para los cmdlets del Shell de administración de Business Server y el servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registro.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado con Skype para los cmdlets del Shell de administración de Business Server y el servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registro.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado con Skype para los cmdlets del Shell de administración de Business Server y el servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registro.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IP virtuales de la interfaz externa

|**Función o protocolo**|**TCP o UDP**|**Intervalo de puerto de destino o puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio de servidor perimetral de acceso)  <br/> |El servicio Proxy XMPP acepta tráfico desde contactos XMPP en federaciones XMPP definidas.  <br/> |
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio de servidor perimetral de acceso)  <br/> |Cualquiera  <br/> |El servicio Proxy XMPP envía el tráfico desde contactos XMPP en federaciones XMPP definidas.  <br/> |
|Acceso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privadas que usan NAT:** Servicio de servicio servidor perimetral de acceso <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de acceso de servidor perimetral <br/> |Cualquiera  <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Conferencia web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Servicio de servidor perimetral de conferencia Web <br/> **IP públicas:** Dirección IP pública de servicio de servidor perimetral de conferencia Web de servidor perimetral <br/> |Medios de conferencias Web.  <br/> |
|V/A/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Un servidor perimetral o servicio perimetral A/v <br/> **IP públicas:** Un servidor perimetral / dirección IP pública del servicio perimetral A/v <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|V/A/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas que usan NAT:** Un servidor perimetral o servicio perimetral A/v <br/> **IP públicas:** Un servidor perimetral / dirección IP pública del servicio perimetral A/v <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IP virtuales de la interfaz interna

Nuestra guía aquí va a ser algo diferente. En realidad, en una situación HLB, ahora le recomendamos que solo tenga enrutamiento a través de un VIP interno en las siguientes circunstancias:
  
- Si está usando Exchange 2007 o Exchange 2010 Unified Messaging (UM).
    
- Si tiene clientes heredados con el servidor perimetral.
    
En la siguiente tabla ofrece instrucciones para dichos escenarios, pero en caso contrario, debería poder dependen de almacén de Administración Central (CMS) para enrutar el tráfico al servidor perimetral individuales es tener en cuenta (Esto requiere que se mantengan actualizados CMS en servidor perimetral información, por supuesto).
  
|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquier:  <br/> • Director  <br/> • Dirección VIP de grupo de directores  <br/> • Servidor de Front-End  <br/> Grupo de Front-End • dirección VIP  <br/> |Interfaz interna del servidor perimetral  <br/> |El tráfico SIP saliente desde el Director, la dirección VIP, servidor Front-End o VIP de grupo de servidores Front-End del grupo de directores de direcciones a la interfaz interna del servidor perimetral.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interfaz VIP interna del servidor perimetral  <br/> |Cualquier:  <br/> • Director  <br/> • Dirección VIP de grupo de directores  <br/> • Servidor de Front-End  <br/> Grupo de Front-End • dirección VIP  <br/> |El Director, el tráfico SIP entrante dirección VIP de grupo de servidores de Director, servidor Front-End o dirección VIP de grupo de servidores de Front-End de la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Cualquier:  <br/> • Dirección de IP de servidor de Front-End  <br/> • Dirección de IP de grupo de servidores Front-End  <br/> • Cualquier aplicación de sucursal con funciones de supervivencia con este servidor perimetral  <br/> • Cualquier uso de este servidor perimetral de un servidor de sucursal con funciones de supervivencia  <br/> |Interfaz interna del servidor perimetral  <br/> |Autenticación de A y los usuarios de V desde el grupo de servidores Front-End o de servidor Front-End, o su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, con el servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta preferida para una transferencia de medios de A/V entre usuarios internos y externos.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Interfaz VIP interna del servidor perimetral  <br/> |Ruta de acceso de reserva para la transferencia de medios de A/V entre los usuarios internos y externos si la comunicación UDP no funciona. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |