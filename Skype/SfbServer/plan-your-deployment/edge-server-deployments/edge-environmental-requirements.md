---
title: Requisitos ambientales para servidores perimetrales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Resumen: Obtenga información sobre los requisitos ambientales para el servidor perimetral en Skype empresarial Server.'
ms.openlocfilehash: a154882e6fe78faee3b020830de4049827babf89
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277177"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisitos ambientales para servidores perimetrales en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre los requisitos ambientales para el servidor perimetral en Skype empresarial Server.
  
Es necesario tener una gran cantidad de planeación y preparación fuera del entorno de servidor perimetral de Skype empresarial Server. En este artículo, repasaremos qué preparativos tiene que realizar en el entorno de la organización, según la lista que se muestra abajo:
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planificar la topología
<a name="TopoPlan"> </a>

Las topologías de servidor perimetral de Skype empresarial Server pueden usar:
  
- Direcciones IP públicas enrutables.
    
- Direcciones IP privadas no enrutables si se usa la traducción de direcciones de red (NAT) **simétrica**.
    
> [!TIP]
> El servidor perimetral puede configurarse para usar una única dirección IP con puertos distintos para cada servicio, o bien puede usar distintas direcciones IP para cada servicio, pero usar el mismo puerto predeterminado (que de forma predeterminada es TCP 443). Hay más información en la sección de requisitos de las direcciones IP de abajo. 
  
Si elige direcciones IP privadas no enrutables con NAT, recuerde los siguientes puntos:
  
- Tiene que usar direcciones IP privadas enrutables en las **tres** interfaces externas.
    
- Tiene que configurar la NAT **simétrica** para el tráfico entrante y saliente. El NAT simétrico es el único NAT compatible que puede usar con el servidor perimetral de Skype empresarial Server.
    
- Configure la NAT para que no cambie las direcciones de origen entrantes. El servicio perimetral A/V debe poder recibir la dirección de origen entrante para encontrar la ruta de acceso de medios óptima.
    
- Los servidores perimetrales deben poder comunicarse entre sí desde su dirección IP de borde A/V pública. El firewall tiene que permitir este tráfico.
    
- NAT **solo** se puede usar para servidores de vanguardia consolidados en escala si usas el equilibrio de carga de DNS. Si usa el equilibrio de carga de hardware (HLB), tiene que usar direcciones IP enrutables públicamente **sin** NAT.
    
No tendrá ningún problema con las interfaces de acceso, conferencia web y borde de a/V detrás de un router o firewall que realicen NAT simétricos para topologías de servidores perimetrales simples y escalables (siempre que no use el equilibrio de carga de hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Resumen de las opciones de topología de servidores perimetrales

Tenemos varias opciones de topología disponibles para las implementaciones del servidor perimetral de Skype empresarial Server:
  
- Servidor perimetral consolidado simple con direcciones IP privadas y NAT
    
- Servidor perimetral consolidado simple con direcciones IP públicas
    
- Servidor perimetral consolidado ampliado con direcciones IP privadas y NAT
    
- Servidor perimetral consolidado ampliado con direcciones IP públicas
    
- Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
    
Para que le sea más fácil elegir una, la siguiente tabla le ofrece un resumen de las opciones de cada topología:
  
|**Topología**|**Alta disponibilidad**|**¿Necesita registros DNS adicionales para el servidor perimetral externo en el grupo Edge?**|**Conmutación por error de perímetro en sesiones de Skype empresarial Server**|**Failover perimetral para sesiones de Federación de Skype empresarial Server**|
|:-----|:-----|:-----|:-----|:-----|
|Servidor perimetral consolidado simple con direcciones IP privadas y NAT  <br/> |No  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |
|Servidor perimetral consolidado simple con direcciones IP públicas  <br/> |No  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |No  <br/> |
|Servidor perimetral consolidado ampliado con direcciones IP privadas y NAT (con equilibrio de carga DNS)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Yes&sup1;  <br/> |
|Servidor perimetral consolidado ampliado con direcciones IP públicas (con equilibrio de carga DNS)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Yes&sup1;  <br/> |
|Servidor perimetral consolidado ampliado con equilibradores de carga de hardware  <br/> |Sí  <br/> |No (un registro A DNS por VIP)  <br/> |Sí  <br/> |Sí  <br/> |
   
&sup1; La conmutación por error de usuario de mensajería unificada de Exchange (UM) con el equilibrio de carga de DNS requiere Exchange 2013 o posterior.
  
### <a name="ip-address-requirements"></a>Requisitos de direcciones IP

En un nivel fundamental, hay tres servicios que necesitan direcciones IP. Servicio perimetral de acceso, servicio perimetral de conferencias web y servicio perimetral A/V. Tiene la opción de usar tres direcciones IP, una para cada uno de los servicios, o puede usar uno y optar por poner cada servicio en un puerto diferente (puede comprobar la sección [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto). Para un entorno de servidor perimetral consolidado simple, es prácticamente todo.
  
> [!NOTE]
> Como se indica anteriormente, puede optar por tener una dirección IP para los tres servicios y ejecutarlos en diferentes puertos. Para ser claros, no lo recomendamos. Si sus clientes no pueden tener acceso a los puertos alternativos que usa en este escenario, tampoco pueden obtener acceso a la característica completa de su entorno perimetral. 
  
Puede ser un poco más complicado con topologías consolidadas ampliadas, por lo que vamos a ver algunas tablas que organizan los requisitos de direcciones IP, teniendo en cuenta que los aspectos principales a la hora de decantarse por una topología son la alta disponibilidad y el equilibrio de carga. Las necesidades de la alta disponibilidad pueden influir en la opción del equilibrio de carga (hablaremos de ello después de las tablas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de dirección IP para servidor perimetral consolidado ampliado (dirección IP por rol)

|**Número de servidores perimetrales por grupo**|**Número de direcciones IP necesarias para el equilibrio de carga de DNS**|**Número de direcciones IP necesarias para el equilibrio de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 por VIP) + 6  <br/> |
|3  <br/> |99,999  <br/> |3 (1 por VIP) + 9  <br/> |
|4  <br/> |2007  <br/> |3 (1 por VIP) + 12  <br/> |
|5  <br/> |4,5  <br/> |3 (1 por VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de dirección IP para servidor perimetral consolidado ampliado (dirección IP única para todos los roles)

|**Número de servidores perimetrales por grupo**|**Número de direcciones IP necesarias para el equilibrio de carga de DNS**|**Número de direcciones IP necesarias para el equilibrio de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 por VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 por VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 por VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 por VIP) + 5  <br/> |
   
Veamos algunos asuntos adicionales en los que pensar durante la planeación.
  
- **Alta disponibilidad**: Si necesita una mayor disponibilidad en su implementación, debe implementar al menos dos servidores perimetrales en un grupo. Merece la pena tener en cuenta que un solo grupo puede admitir hasta 12 servidores perimetrales (aunque el generador de topología le permitirá sumar hasta 20, eso no está probado ni admitido, por lo que le recomendamos que no lo hace). Si necesita más de 12 servidores perimetrales, debe crear agrupaciones perimetrales adicionales para ellos.
    
- **Equilibrio de carga de hardware**: se recomienda el equilibrio de carga de DNS en la mayoría de los escenarios. El equilibrio de carga de hardware también es compatible, por supuesto, pero es necesario para un escenario único sobre el equilibrio de carga de DNS:
    
  - Acceso externo a Exchange 2007 o Exchange 2010 (sin SP) mensajería unificada (UM).
    
- **Equilibrio de carga de DNS**: para um, Exchange 2010 SP1 y versiones posteriores pueden ser compatibles con el equilibrio de carga de DNS. Tenga en cuenta que si necesita ir con el equilibrio de carga de DNS para una versión anterior de Exchange, funcionará, pero todo el tráfico para ello irá al primer servidor del grupo y, si no está disponible, ese tráfico fallará posteriormente.
    
    También se recomienda el equilibrio de carga de DNS si se va a federar con empresas mediante:
- Skype empresarial Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - O365 de Microsoft Office
- Skype empresarial Server 2019:
    - Lync Server 2013
    - Skype Empresarial Server 2015
    - Microsoft Office 365.
    
## <a name="dns-planning"></a>Planificación de DNS
<a name="DNSPlan"> </a>

Cuando se trata de la implementación del servidor perimetral de Skype empresarial Server, es vital prepararse para DNS correctamente. Con los registros correctos en su ubicación, la implementación será mucho más sencilla. Afortunadamente ha elegido una topología en la sección anterior, ya que realizaremos una descripción general y después enumeraremos algunas tablas que esquematicen los registros DNS para esos escenarios. También tenemos un [plan DNS avanzado de servidor perimetral para Skype empresarial Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) para una lectura más profunda, si así lo necesita.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Registros DNS para escenarios de servidor perimetral único consolidado

Estos serán los registros DNS que necesitará para un servidor perimetral único que use IPS público o IP privado con NAT. Dado que estos son datos de ejemplo, le daremos IP de muestra para que pueda resolver sus propias entradas de forma más fácil:
  
- Adaptador de red interna: 172.25.33.10 (no hay ninguna puerta de enlace predeterminada asignada)
    
    > [!NOTE]
    > Asegúrese de que haya una ruta desde la red que contenga la interfaz interna perimetral a cualquier red que contenga servidores que ejecuten Skype empresarial Server o clientes de Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externa:
    
  - IP públicas:
    
  - Perimetral de acceso: 131.107.155.10 (es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
  - Borde de conferencias web: 131.107.155.20 (secundaria)
    
  - Borde A/V: 131.107.155.30 (secundaria)
    
  Las direcciones IP públicas de las conferencias web y A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y el protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Servidor de Windows.
    
  - IP privadas:
    
  - Perimetral de acceso: 10.45.16.10 (es el principal, con la puerta de enlace predeterminada establecida para el enrutador; por ejemplo: 10.45.16.1)
    
  - Borde de conferencias web: 10.45.16.20 (secundaria)
    
  - Borde A/V: 10.45.16.30 (secundaria)
    
Las direcciones IP públicas de las conferencias web y A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y el protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Servidor de Windows.
  
> [!TIP]
>Hay otra configuración posible:
  
- Puede usar una dirección IP en el adaptador de red externa. No recomendamos esto porque entonces tendrá que diferenciar entre los servicios que usan puertos diferentes (que puede hacer en Skype empresarial Server) pero hay algunos firewalls que pueden bloquear los puertos alternativos. Vea la sección de [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto.
    
- Puede tener tres adaptadores de red externa en lugar de uno y asignar una de las IP del servicio a cada uno. ¿Por qué? Se separarían los servicios y si algo va mal, facilitaría solucionar los problemas y dejar que otros servicios continuasen trabajando potencialmente mientras resuelve un problema.
    
|**Ubicación**|**Tipo**|**Puerto**|**Registro FQDN o DNS**|**Dirección IP o FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 <br/> **privado:** 10.45.16.10 <br/> |Una interfaz externa para tu servicio perimetral de acceso. Necesitará uno para cada dominio SIP con usuarios de Skype empresarial.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 <br/> **privado:** 10.45.16.20 <br/> |Una interfaz externa para el servicio perimetral de conferencias web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 <br/> **privado:** 10.45.16.30 <br/> |Una interfaz externa para tu servicio perimetral A/V.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para tu servicio perimetral de acceso. Este registro SRV es necesario para que los clientes de Skype empresarial Server, Lync Server 2013 y Lync Server 2010 funcionen de forma externa. Necesitará uno para cada dominio con usuarios de Skype empresarial.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para tu servicio perimetral de acceso. Este registro SRV es necesario para la detección DNS automática de asociados federados denominada Dominios SIP permitidos. Necesitará uno para cada dominio con usuarios de Skype empresarial.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |La interfaz interna para el servidor perimetral consolidado.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Registros DNS para escenarios de servidor perimetral de hardware y DNS a escala

Estos serán los registros DNS que necesitará para un servidor perimetral único que use IPS público o IP privado con NAT. Dado que estos son datos de ejemplo, le daremos IP de muestra para que pueda resolver sus propias entradas de forma más fácil:
  
- Adaptador de red interna:
    
  - Nodo 1: 172.25.33.10 (no hay ninguna puerta de enlace predeterminada asignada)
    
  - Nodo 2: 172.25.33.11 (no hay ninguna puerta de enlace predeterminada asignada)
    
    > [!NOTE]
    > Asegúrese de que haya una ruta desde la red que contenga la interfaz interna perimetral a cualquier red que contenga servidores que ejecuten Skype empresarial Server o clientes de Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externa:
    
  - Nodo 1
    
     - IP públicas:
    
        - Perimetral de acceso: 131.107.155.10 (es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
        - Borde de conferencias web: 131.107.155.20 (secundaria)
    
        - Borde A/V: 131.107.155.30 (secundaria)
    
          Las direcciones IP públicas de las conferencias web y A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y el protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Servidor de Windows.
    
    - IP privadas:
    
         - Perimetral de acceso: 10.45.16.10 (es el principal, con la puerta de enlace predeterminada establecida para el enrutador; por ejemplo: 10.45.16.1)
    
         - Borde de conferencias web: 10.45.16.20 (secundaria)
    
         - Borde A/V: 10.45.16.30 (secundaria)
    
      Las direcciones IP públicas de las conferencias web y A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y el protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Servidor de Windows.
    
  - Nodo 2
    
    - IP públicas:
    
      - Perimetral de acceso: 131.107.155.11 (es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
      - Borde de conferencias web: 131.107.155.21 (secundaria)
    
      - Borde A/V: 131.107.155.31 (secundaria)
    
      Las direcciones IP públicas de las conferencias web y A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y el protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Servidor de Windows.
    
  - IP privadas:
    
    - Perimetral de acceso: 10.45.16.11 (es el principal, con la puerta de enlace predeterminada establecida para el enrutador; por ejemplo: 10.45.16.1)
    
    - Borde de conferencias web: 10.45.16.21 (secundaria)
    
    - Borde A/V: 10.45.16.31 (secundaria)
    
      Las direcciones IP públicas de las conferencias web y A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y el protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Servidor de Windows.
    
Hay otra configuración posible:
  
- Puede usar una dirección IP en el adaptador de red externa. No recomendamos esto porque entonces tendrá que diferenciar entre los servicios que usan puertos diferentes (que puede hacer en Skype empresarial Server) pero hay algunos firewalls que pueden bloquear los puertos alternativos. Vea la sección de [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto.
    
- Puede tener tres adaptadores de red externa en lugar de uno y asignar una de las IP del servicio a cada uno. ¿Por qué? Se separarían los servicios y si algo va mal, facilitaría solucionar los problemas y dejar que otros servicios continuasen trabajando potencialmente mientras resuelve un problema.
    
|**Ubicación**|**Tipo**|**Puerto**|**Registro FQDN o DNS**|**Dirección IP o FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 y 131.107.155.11 <br/> **privado:** 10.45.16.10 y 10.45.16.11 <br/> |Una interfaz externa para tu servicio perimetral de acceso. Necesitará uno para cada dominio SIP con usuarios de Skype empresarial.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 y 131.107.155.21 <br/> **privado:** 10.45.16.20 y 10.45.16.21 <br/> |Una interfaz externa para el servicio perimetral de conferencias web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 y 131.107.155.31 <br/> **privado:** 10.45.16.30 y 10.45.16.31 <br/> |Una interfaz externa para tu servicio perimetral A/V.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para tu servicio perimetral de acceso. Este registro SRV es necesario para que los clientes de Skype empresarial Server, Lync Server 2013 y Lync Server 2010 funcionen de forma externa. Necesitará uno para cada dominio con Skype empresarial.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para tu servicio perimetral de acceso. Este registro SRV es necesario para la detección DNS automática de asociados federados denominada Dominios SIP permitidos. Necesitará uno para cada dominio con Skype empresarial.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 y 172.25.33.11  <br/> |La interfaz interna para el servidor perimetral consolidado.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para la federación (todos los escenarios)

|**Ubicación**|**Tipo**|**Puerto**|**NOMBRES**|**Registro de host de FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |La interfaz externa perimetral de acceso SIP necesaria para la detección automática de DNS. Usada por otros posibles asociados de federación. También se conoce como "Permitir dominios SIP". Necesitará uno de estos para cada dominio SIP con usuarios de Skype empresarial.  <br/><br/> **Nota:** Necesitará este registro SRV para la movilidad y el centro de enrutamiento de notificaciones de inserción. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Registros DNS para el protocolo extensible de mensajería y presencia

|**Ubicación**|**Tipo**|**Puerto**|**NOMBRES**|**Dirección IP o registro de host FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |La interfaz de proxy XMPP en el servicio perimetral de acceso o en el grupo perimetral. Debe repetir esta opción según sea necesario para todos los dominios SIP internos que tengan usuarios habilitados para Skype empresarial Server, en los que se permite el acceso a través de contactos XMPP:  <br/> • una política global  <br/> • una directiva de sitio en la que el usuario ha habilitado  <br/> • se aplica una directiva de usuario al usuario habilitado para Skype empresarial Server.  <br/> Una directiva XMPP permitida también se tiene que configurar en la directiva de usuarios federados XMPP.  <br/> |
|DNS externo  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Dirección IP del servicio perimetral de acceso en el servidor perimetral o grupo perimetral que aloja el servicio de proxy XMPP  <br/> |Esto señala el servicio perimetral de acceso en el servidor perimetral o el grupo perimetral que hospeda el servicio de proxy XMPP. Por lo general, el registro SRV que crea apuntará a este registro de host (A o AAAA).  <br/> |
   
> [!NOTE]
> Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Para obtener más información, consulte migrar la [Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

## <a name="certificate-planning"></a>Planificar certificado
<a name="CertPlan"> </a>

Skype empresarial Server usa certificados para comunicaciones cifradas y seguras entre servidores y desde el servidor al cliente. Como cabría esperar, los certificados tendrán que tener registros DNS para sus servidores para que coincidan con cualquier nombre de sujeto (SN) y nombre alternativo de sujeto (SAN) en los certificados. Esto le llevará trabajo ahora, en la fase de planificación, para garantizar que tiene los FQDN correctos registrados en DNS para las entradas de SN y de SAN para los certificados.
  
Hablaremos de las necesidades de los certificados internos y externos por separado y después veremos una tabla que proporciona los requisitos para ambos.
  
### <a name="external-certificates"></a>Certificados externos

Como mínimo, el certificado asignado a las interfaces del servidor perimetral externo debe proporcionarlo una entidad emisora de certificados (CA) pública. No se puede recomendar una entidad emisora de certificados específica, pero tenemos una lista de los [socios de certificados de comunicaciones unificadas](https://support.microsoft.com/en-us/kb/929395) que puede consultar para ver si su CA preferida aparece en la lista.
  
¿Cuándo tendrá que enviar una solicitud a una entidad de certificación para este certificado público y cómo lo tiene que hacer? Hay un par de formas de llevar esto a cabo:
  
- Puede pasar por la instalación de Skype empresarial Server y, a continuación, la implementación del servidor perimetral. El Asistente para la implementación de Skype empresarial Server tendrá un paso para generar una solicitud de certificado, que podrá enviar a la entidad emisora elegida.
    
- También puede usar los comandos de Windows PowerShell para generar esta solicitud, si está más alineada con las necesidades de su empresa o su estrategia de implementación.
    
- Por último, la entidad emisora de certificados puede tener su propio proceso de envío, que también puede incluir Windows PowerShell u otro método. En ese caso, tendrá que basarse en su documentación, además de en la información proporcionada aquí para su consulta.
    
Una vez que haya obtenido el certificado, tendrá que seguir adelante y asignarlo a estos servicios en Skype empresarial Server:
  
- Interfaz de servicio perimetral de acceso
    
- Interfaz de servicio perimetral de conferencia Web
    
- Servicio de autenticación de audio y vídeo (no confunda esta acción con el servicio de borde a/V, ya que no usa un certificado para cifrar secuencias de audio y vídeo)
    
> [!IMPORTANT]
> Todos los servidores perimetrales (si pertenecen al mismo grupo de servidores perimetrales) necesitan tener exactamente el mismo certificado con la misma clave privada para el servicio de autenticación de retransmisión multimedia. 
  
### <a name="internal-certificates"></a>Certificados internos

Para la interfaz de servidor perimetral interno, puede usar un certificado público de una entidad de certificación pública o un certificado emitido por la entidad de certificación interna de su organización. Lo que hay que recordar sobre el certificado interno es que usa una entrada de SN y no entradas de SAN, de modo que no tiene que preocuparse por SAN en el certificado interno en absoluto.
  
### <a name="required-certificates-table"></a>Tabla de certificados necesarios

Aquí tenemos una tabla para ayudarle con las solicitudes. Las entradas de FQDN son solo para dominios de ejemplo. Tendrá que realizar solicitudes en función de sus propios dominios privados y públicos, pero esta es una guía sobre lo que hemos usado:
  
- Contoso<span></span>. com: FQDN público
    
- Fabrikam<span></span>. com: segundo FQDN público (agregado como una demostración de lo que debe solicitar si tiene varios dominios SIP)
    
- Contoso<span></span>.net: dominio interno
    
#### <a name="edge-certificate-table"></a>Tabla de certificado perimetral

Independientemente de si está haciendo un solo servidor perimetral o un grupo Edge, esto es lo que necesita para su certificado:
  
|**Componente**|**Nombre de sujeto**|**Nombres alternativos del sujeto (SAN)/orden**|**Notas**|
|:-----|:-----|:-----|:-----|
|Servidor perimetral externo  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Este es el certificado que tiene que solicitar a una entidad de certificación pública. Tendrá que estar asignado a las interfaces perimetrales externas para lo siguiente:<br/> • Edge de acceso  <br/> • Borde de conferencias web  <br/> • Autenticación de audio y vídeo  <br/> <br/>La buena noticia es que las redes San se agregan automáticamente a su solicitud de certificado y, por lo tanto, su certificado después de enviar la solicitud, en función de lo que haya definido para esta implementación en el generador de topología. Solo tiene que agregar las entradas de SAN para cualquier dominio SIP adicional u otras entradas que necesite admitir. ¿Por qué sip.contoso.com aparece duplicado en esta instancia? Esto se produce automáticamente y es necesario para que todo funcione correctamente.  <br/><br/> **Nota:** Este certificado también puede usarse para la conectividad de mensajería instantánea pública. No tiene que hacer nada diferente con él, pero en versiones anteriores de esta documentación, se ha incluido como una tabla independiente, y ahora no lo es. <br/> |
|Servidor perimetral interno  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Puede obtener este certificado de una entidad de certificación pública o de una entidad de certificación interna. Tendrá que contener el EKU del servidor (uso mejorado de clave) y lo asignará a la interfaz interna del servidor perimetral.  <br/> |
   
Si necesita un certificado para el protocolo extensible de mensajería y presencia (XMPP), tendrá un aspecto idéntico a las entradas del servidor perimetral externo de la tabla anterior, pero tendrá las siguientes dos entradas SAN adicionales:
  
- XMPP. <span> </span>contoso<span></span>. com
    
- \*. contoso<span></span>. com
    
Recuerde que actualmente XMPP sólo es compatible con Skype empresarial Server para Google Talk, si lo desea o necesita usarlo para cualquier otra cosa, necesita confirmar la funcionalidad con el proveedor de terceros implicado.
  
## <a name="port-and-firewall-planning"></a>Planificación de puerto y de firewall
<a name="PortFirewallPlan"> </a>

Obtener su plan adecuado para los puertos y los firewalls para las implementaciones del servidor perimetral de Skype empresarial Server puede ahorrarle días o semanas de solución de problemas y estrés. Como resultado, enumeraremos un par de tablas que indicarán nuestro uso de protocolo y qué puertos necesita tener abiertos, entrantes y salientes, tanto para los escenarios de NAT y de IP pública. También le mostraremos tablas separadas para escenarios con equilibrio de carga de hardware (HLB) y alguna ayuda a mayores de esto. Para obtener más información, también tenemos [escenarios de servidor EDGE en Skype empresarial Server](scenarios.md) que puede consultar para conocer las preocupaciones específicas de su implementación.
  
### <a name="general-protocol-usage"></a>Uso general de protocolo

Antes de ver las tablas de resumen para los firewall internos y externos, veamos la siguiente tabla:
  
|**Transporte de audio y vídeo**|**Uso**|
|:-----|:-----|
|UDP  <br/> |El protocolo de capa de transporte preferido para audio y vídeo.  <br/> |
|TCP  <br/> |El protocolo de capa de transporte de reserva para audio y vídeo.  <br/> El protocolo de capa de transporte requerido para compartir aplicaciones con Skype empresarial Server, Lync Server 2013 y Lync Server 2010.  <br/> El protocolo de nivel de transporte requerido para la transferencia de archivos a Skype empresarial Server, Lync Server 2013 y Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para usuarios que estén usando direcciones IP privadas con NAT, así como las personas que usen direcciones IP públicas. Esto cubrirá todas las permutaciones en los [escenarios de los servidores perimetrales de la sección de Skype empresarial Server](scenarios.md) .
  
|**Rol o protocolo**|**TCP o UDP**|**Intervalo de puertos o puerto de destino**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> No es compatible con Skype empresarial Server 2019 |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio de proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso  <br/> |El servicio de proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas.  <br/> |
|Acceso/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Acceso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Cualquiera  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acceso/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Cualquiera  <br/> |Consulta DNS sobre UDP.  <br/> |
|Acceso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Cualquiera  <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Conferencia web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |**IP privada usando NAT:** Servicio perimetral de conferencias web del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de conferencias web del servidor perimetral <br/> |Medios de conferencias web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privada usando NAT:** Servidor perimetral A/V servicio perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privada usando NAT:** Servidor perimetral A/V servicio perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privada usando NAT:** Servidor perimetral A/V servicio perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Cualquiera  <br/> |3478 saliente:  <br/> • Usado por Skype empresarial Server para determinar la versión del servidor perimetral con el que se comunica.  <br/> • Se usa para tráfico de medios entre servidores perimetrales.  <br/> • Necesario para la Federación con Lync Server 2010.  <br/> • Necesario si se implementan varios grupos perimetrales dentro de su organización.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privada usando NAT:** Servidor perimetral A/V servicio perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |**IP privada usando NAT:** Servidor perimetral A/V servicio perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privada usando NAT:** Servidor perimetral A/V servicio perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Cualquiera  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto interno

|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de los siguientes que ejecutan el servicio de puerta de enlace XMPP:  <br/> • Servidor front-end  <br/> • Pool front-end  <br/> |Interfaz interna de Edge Server  <br/> |Tráfico de salida XMPP desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o en el grupo front-end.  <br/> **Nota:** Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Para obtener más información, consulte migrar la [Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Cualquier:  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor front-end  <br/> • Pool front-end  <br/> |Interfaz interna de Edge Server  <br/> |Tráfico SIP saliente de su director, grupo de directores, servidor front-end o grupo front-end a la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interfaz interna de Edge Server  <br/> |Cualquier:  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor front-end  <br/> • Pool front-end  <br/> |Tráfico SIP entrante a su director, grupo de directores, servidor front-end o grupo front-end de la interfaz interna de su servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Cualquier:  <br/> • Servidor front-end  <br/> • Cada servidor front-end  <br/>  en el grupo de servidores front-end <br/> |Interfaz interna de Edge Server  <br/> |Tráfico de conferencias web de su servidor front-end o de cada servidor front-end (si tiene un grupo de servidores front-end) a la interfaz interna de su servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Cualquier:  <br/> • Servidor front-end  <br/> • Pool front-end  <br/> • Cualquier otro dispositivo de sucursal que use este servidor perimetral  <br/> • Cualquier servidor de sucursal con la que se use este servidor perimetral  <br/> |Interfaz interna de Edge Server  <br/> |Autenticación de usuarios de A/V de su servidor front-end o grupo de servidores front-end, o de su equipo de sucursal que sea reviviente o servidor de sucursal con la supervivencia, usando su servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna de Edge Server  <br/> |Ruta de acceso preferida para la transferencia de medios A/V entre los usuarios internos y externos y el equipo de sucursal que tiene la supervivencia o el servidor de sucursal con la supervivencia.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |Interfaz interna de Edge Server  <br/> |Ruta de reserva para la transferencia de medios A/V entre los usuarios internos y externos y su equipo de sucursal con la supervivencia o servidor de sucursal superviviente, si la comunicación UDP no funciona. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Cualquier:  <br/> • Servidor front-end que contiene el almacén de administración central  <br/> • Grupo front-end que contiene el almacén de administración central  <br/> |Interfaz interna de Edge Server  <br/> |La replicación de los cambios desde la tienda de administración central en el servidor perimetral.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna de Edge Server  <br/> |Controlador de servicio de registro centralizado con el shell de administración de Skype empresarial Server y cmdlets de servicio de registro centralizados, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna de Edge Server  <br/> |Controlador de servicio de registro centralizado con el shell de administración de Skype empresarial Server y cmdlets de servicio de registro centralizados, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna de Edge Server  <br/> |Controlador de servicio de registro centralizado con el shell de administración de Skype empresarial Server y cmdlets de servicio de registro centralizados, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Tablas de puerto de servidor perimetral para equilibradores de carga de hardware

Les estamos dando a los equilibradores de carga de hardware (HLB) y a los puertos de servidor perimetral su propia sección, ya que son algo más complicados con el hardware adicional. Vea las tablas siguientes para instrucciones para este escenario concreto:
  
#### <a name="external-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para usuarios que estén usando direcciones IP privadas con NAT, así como las personas que usen direcciones IP públicas. Esto cubrirá todas las permutaciones en los [escenarios de los servidores perimetrales de la sección de Skype empresarial Server](scenarios.md) .
  
|**Rol o protocolo**|**TCP o UDP**|**Intervalo de puertos o puerto de destino**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acceso/HTTP  <br/> |TCP  <br/> |80  <br/> |Dirección IP pública del servicio perimetral de acceso al servidor perimetral  <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Acceso/DNS  <br/> |TCP  <br/> |53  <br/> |Dirección IP pública del servicio perimetral de acceso al servidor perimetral  <br/> |Cualquiera  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acceso/DNS  <br/> |UDP  <br/> |53  <br/> |Dirección IP pública del servicio perimetral de acceso al servidor perimetral  <br/> |Cualquiera  <br/> |Consulta DNS sobre UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Dirección IP del servicio Edge del servidor perimetral A/V  <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |Cualquiera  <br/> |3478 saliente:  <br/> • Usado por Skype empresarial Server para determinar la versión del servidor perimetral con el que se comunica.  <br/> • Se usa para tráfico de medios entre servidores perimetrales.  <br/> • Necesario para la Federación.  <br/> • Necesario si se implementan varios grupos perimetrales dentro de su organización.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |Cualquiera  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto interno

|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de los siguientes que ejecutan el servicio de puerta de enlace XMPP:  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP  <br/> |Interfaz interna de Edge Server  <br/> |Tráfico de salida XMPP desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o en el grupo front-end.  <br/><br/> **Nota:** Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Para obtener más información, consulte migrar la [Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Cualquier:  <br/> • Servidor front-end que contiene el almacén de administración central  <br/> • Grupo front-end que contiene el almacén de administración central  <br/> |Interfaz interna de Edge Server  <br/> |La replicación de los cambios desde la tienda de administración central en el servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Cualquier:  <br/> • Servidor front-end  <br/> • Cada servidor front-end en el grupo de servidores front-end  <br/> |Interfaz interna de Edge Server  <br/> |Tráfico de conferencias web de su servidor front-end o de cada servidor front-end (si tiene un grupo de servidores front-end) a la interfaz interna de su servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquier:  <br/> • Servidor front-end  <br/> • Cada servidor front-end en el grupo de servidores front-end  <br/> |Interfaz interna de Edge Server  <br/> |Ruta de acceso preferida para la transferencia de medios A/V entre los usuarios internos y externos y el equipo de sucursal que tiene la supervivencia o el servidor de sucursal con la supervivencia.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquier:  <br/> • Servidor front-end  <br/> • Cada servidor front-end de su grupo  <br/> |Interfaz interna de Edge Server  <br/> |Ruta de reserva para la transferencia de medios A/V entre los usuarios internos y externos y su equipo de sucursal con la supervivencia o servidor de sucursal superviviente, si la comunicación UDP no funciona. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna de Edge Server  <br/> |Controlador de servicio de registro centralizado con el shell de administración de Skype empresarial Server y cmdlets de servicio de registro centralizados, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna de Edge Server  <br/> |Controlador de servicio de registro centralizado con el shell de administración de Skype empresarial Server y cmdlets de servicio de registro centralizados, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna de Edge Server  <br/> |Controlador de servicio de registro centralizado con el shell de administración de Skype empresarial Server y cmdlets de servicio de registro centralizados, la línea de comandos de ClsController (ClsController. exe) o los comandos del agente (ClsAgent. exe) y la colección de registros.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IP virtuales de la interfaz externa

|**Rol o protocolo**|**TCP o UDP**|**Intervalo de puertos o puerto de destino**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> No es compatible con el servidor de Skype empresarial 2019 |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio de proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso)  <br/> |El servicio de proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas.  <br/> |
|XMPP  <br/>No es compatible con el servidor de Skype empresarial 2019 |TCP  <br/> |5269  <br/> |Servicio de proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso)  <br/> |Cualquiera  <br/> |El servicio Proxy XMPP envía tráfico de contactos XMPP en federaciones de XMPP definidas.  <br/> |
|Acceso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privada usando NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral <br/> |Cualquiera  <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Conferencia web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |**IP privada usando NAT:** Servicio perimetral de conferencias web del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de conferencias web del servidor perimetral <br/> |Medios de conferencias web.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privada usando NAT:** Servidor perimetral A/V servicio perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |**IP privada usando NAT:** Servidor perimetral A/V servicio perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IP virtuales de la interfaz interna

Nuestra guía aquí va a ser algo diferente. En realidad, en una situación HLB, ahora le recomendamos que solo tenga enrutamiento a través de un VIP interno en las siguientes circunstancias:
  
- Si está usando Exchange 2007 o la mensajería unificada de Exchange 2010 (UM).
    
- Si tiene clientes heredados con el servidor perimetral.
    
En la tabla siguiente se proporcionan instrucciones para estas situaciones, pero, de lo contrario, debería poder depender del almacén de administración central (CMS) para enrutar el tráfico al servidor perimetral individual que tiene constancia (esto requiere que CMS esté actualizado en el servidor perimetral). información, por supuesto).
  
|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquier:  <br/> • Director  <br/> • Dirección VIP del grupo de directores  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end  <br/> |Interfaz interna de Edge Server  <br/> |Tráfico SIP saliente de su director, la dirección VIP del grupo de directores, el servidor front-end o la dirección VIP del grupo de servidores front-end a la interfaz interna del servidor perimetral.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interfaz VIP interna de Edge Server  <br/> |Cualquier:  <br/> • Director  <br/> • Dirección VIP del grupo de directores  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end  <br/> |Tráfico SIP entrante al Director, la dirección VIP del grupo de directores, el servidor front-end o la dirección VIP del grupo de servidores front-end de la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Cualquier:  <br/> • Dirección IP del servidor front-end  <br/> • Dirección IP del grupo de servidores front-end  <br/> • Cualquier otro dispositivo de sucursal que use este servidor perimetral  <br/> • Cualquier servidor de sucursal con la que se use este servidor perimetral  <br/> |Interfaz interna de Edge Server  <br/> |Autenticación de usuarios de A/V de su servidor front-end o grupo de servidores front-end, o de su equipo de sucursal que sea reviviente o servidor de sucursal con la supervivencia, usando su servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna de Edge Server  <br/> |Ruta preferida para una transferencia de medios de A/V entre usuarios internos y externos.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera   <br/> |Interfaz VIP interna de Edge Server  <br/> |Ruta de acceso de reserva para la transferencia de medios de A/V entre los usuarios internos y externos si la comunicación UDP no funciona. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |
