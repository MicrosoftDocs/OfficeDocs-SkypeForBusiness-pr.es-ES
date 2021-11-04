---
title: Requisitos del entorno del servidor perimetral en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Summary: Learn about the environmental requirements for Edge Server in Skype Empresarial Server.'
ms.openlocfilehash: 7dbd2b3c40b60f69813edbfee29a29fb003fb703
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749969"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisitos del entorno del servidor perimetral en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre los requisitos del entorno para el servidor perimetral en Skype Empresarial Server.
  
Debe tener lugar una gran cantidad de planeación y preparación fuera del entorno Skype Empresarial Server servidor perimetral en sí. En este artículo, revisaremos los preparativos que deben realizarse en el entorno organizativo, según nuestra lista siguiente:
  
- [Planeación de topologías](edge-environmental-requirements.md#TopoPlan)
    
- [Planeación de DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Planeación de certificados](edge-environmental-requirements.md#CertPlan)
    
- [Planeación de puertos y firewall](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planeación de topologías
<a name="TopoPlan"> </a>

Skype Empresarial Server Las topologías de servidor perimetral pueden usar:
  
- Direcciones IP públicas enrutables.
    
- Direcciones IP privadas no enrutables, si **se** usa la traducción de direcciones de red simétrica (NAT).
    
> [!TIP]
> El servidor perimetral puede configurarse para usar una sola dirección IP con puertos distintos para cada servicio, o bien puede usar direcciones IP distintas para cada servicio, pero usar el mismo puerto predeterminado (que de forma predeterminada será TCP 443). A continuación, encontrará más información en la sección Requisitos de direcciones IP. 
  
Si elige direcciones IP privadas no enrutables con NAT, recuerde estos puntos:
  
- Debe usar direcciones IP privadas enrutables en **las tres** interfaces externas.
    
- Debe configurar NAT **simétrica** para el tráfico entrante y saliente. NAT simétrica es la única NAT compatible que puede usar con Skype Empresarial Server servidor perimetral.
    
- Configure la NAT para que no cambie las direcciones de origen entrantes. El servicio perimetral A/V debe poder recibir la dirección de origen entrante para encontrar la ruta de acceso multimedia óptima.
    
- Los servidores perimetrales deben poder comunicarse entre sí desde sus direcciones IP perimetrales A/V públicas. El firewall debe permitir este tráfico.
    
- NAT solo **se puede** usar para servidores perimetrales consolidados escalados si usa el equilibrio de carga dns. Si usa el equilibrio de carga de hardware (HLB), debe usar direcciones IP enrutables públicamente **sin** NAT.
    
No tendrá problemas al tener las interfaces perimetrales de Access, Web conferencing e A/V detrás de un enrutador o firewall que realicen NAT simétricas para topologías de servidor perimetral consolidadas y únicas (siempre que no use el equilibrio de carga de hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Resumen de las opciones de topología del servidor perimetral

Tenemos varias opciones de topología disponibles para Skype Empresarial Server de servidor perimetral:
  
- Perímetro consolidado único con direcciones IP privadas y NAT
    
- Perímetro consolidado único con direcciones IP públicas
    
- Perimetral consolidado escalado con direcciones IP privadas y NAT
    
- Perímetro consolidado escalado con direcciones IP públicas
    
- Perimetral consolidado escalado con equilibradores de carga de hardware
    
Para ayudarle a elegir uno, tenemos la siguiente tabla que proporciona un resumen de las opciones que tiene para cada topología:
  
|**Topología**|**Alta disponibilidad**|**¿Registros DNS adicionales necesarios para el servidor perimetral externo en el grupo de servidores perimetrales?**|**Conmutación por error perimetral para Skype Empresarial Server sesiones**|**Conmutación por error perimetral para Skype Empresarial Server de federación**|
|:-----|:-----|:-----|:-----|:-----|
|Perímetro consolidado único con direcciones IP privadas y NAT  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Perímetro consolidado único con direcciones IP públicas  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Perímetro consolidado escalado con direcciones IP privadas y NAT (carga DNS equilibrada)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí&sup1;  <br/> |
|Perímetro consolidado escalado con direcciones IP públicas (carga dns equilibrada)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí&sup1;  <br/> |
|Perimetral consolidado escalado con equilibradores de carga de hardware  <br/> |Sí  <br/> |No (un registro A DNS por VIP)  <br/> |Sí  <br/> |Sí  <br/> |
   
&sup1; Exchange La conmutación por error de usuarios remotos de mensajería unificada (MU) mediante equilibrio de carga DNS Exchange 2013 o posterior.
  
### <a name="ip-address-requirements"></a>Requisitos de dirección IP

En un nivel fundamental, tres servicios necesitan direcciones IP; Servicio perimetral de acceso, servicio perimetral de conferencia web y servicio perimetral A/V. Tiene la opción de usar tres direcciones IP, una para cada uno de los servicios, o puede usar uno y optar por colocar cada servicio en un puerto diferente (puede consultar la sección Planeación de puertos y [firewall](edge-environmental-requirements.md#PortFirewallPlan) para obtener más información sobre algunos de ellos). Para un único entorno perimetral consolidado, eso es prácticamente todo.
  
> [!NOTE]
> Como se mencionó anteriormente, puede elegir tener una dirección IP para los tres servicios y ejecutarlos en puertos diferentes. Pero para ser claros, no se recomienda esto. Si los clientes no pueden tener acceso a los puertos alternativos que estaría usando en este escenario, tampoco podrán acceder a la funcionalidad completa del entorno perimetral. 
  
Puede ser un poco más complicado con topologías consolidadas a escala, por lo que vamos a ver algunas tablas que fijan los requisitos de direcciones IP, teniendo en cuenta que los puntos de decisión principales para la selección de topología son la alta disponibilidad y el equilibrio de carga. Las necesidades de alta disponibilidad pueden influir en la elección de equilibrio de carga (hablaremos de ello más después de las tablas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de dirección IP para el perímetro consolidado escalado (dirección IP por rol)

|**Número de servidores perimetrales por grupo**|**Número de direcciones IP necesarias para el equilibrio de carga DNS**|**Número de direcciones IP necesarias para el equilibrio de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |6   <br/> |3 (1 por VIP) + 6  <br/> |
|3  <br/> |9   <br/> |3 (1 por VIP) + 9  <br/> |
|4  <br/> |12   <br/> |3 (1 por VIP) + 12  <br/> |
|5  <br/> |15   <br/> |3 (1 por VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de dirección IP para el perímetro consolidado de escala (dirección IP única para todos los roles)

|**Número de servidores perimetrales por grupo**|**Número de direcciones IP necesarias para el equilibrio de carga DNS**|**Número de direcciones IP necesarias para el equilibrio de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 por VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 por VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 por VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 por VIP) + 5  <br/> |
   
Echemos un vistazo a algunas cosas adicionales en las que pensar durante la planeación.
  
- **Alta disponibilidad:** si necesita alta disponibilidad en la implementación, debe implementar al menos dos servidores perimetrales en un grupo de servidores. Vale la pena tener en cuenta que un solo grupo de servidores perimetrales admitirá hasta 12 servidores perimetrales (aunque el Generador de topologías te permitirá agregar hasta 20, que no se prueban ni admiten, por lo que te recomendamos que no lo hagas). Si necesita más de 12 servidores perimetrales, debe crear grupos de servidores perimetrales adicionales para ellos.
    
- **Equilibrio de carga de hardware:** se recomienda el equilibrio de carga dns para la mayoría de los escenarios. El equilibrio de carga de hardware también es compatible, por supuesto, pero, sobre todo, es necesario para un único escenario sobre el equilibrio de carga dns:
    
  - Acceso externo a Exchange 2007 o Exchange 2010 (sin SP) Mensajería unificada (MU).
    
- **Equilibrio de carga DNS:** para la mensajería unificada, Exchange 2010 SP1 y versiones posteriores pueden ser compatibles con el equilibrio de carga dns. Tenga en cuenta que si necesita ir con el equilibrio de carga DNS para una versión anterior de Exchange, funcionará, pero todo el tráfico para esto irá al primer servidor del grupo y, si no está disponible, ese tráfico producirá un error posterior.
    
    También se recomienda el equilibrio de carga dns si está federando con empresas que usan:
- Skype Empresarial Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 u Office 365
- Skype Empresarial Server 2019:
    - Lync Server 2013
    - Skype Empresarial Server 2015
    - Microsoft 365 u Office 365
    
## <a name="dns-planning"></a>Planeación de DNS
<a name="DNSPlan"> </a>

Cuando se trata de Skype Empresarial Server de servidor perimetral, es fundamental prepararse correctamente para DNS. Con los registros correctos en su lugar, la implementación será mucho más sencilla. Esperemos que haya elegido una topología en la sección anterior, ya que vamos a hacer una introducción y, a continuación, enumerar un par de tablas que delineen los registros DNS para esos escenarios. También tendremos planeación avanzada de DNS de servidor perimetral [para Skype Empresarial Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) para una lectura más detallada, si lo necesita.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Registros DNS para escenarios de servidor perimetral consolidado único

Estos serán los registros DNS que necesitará para un servidor perimetral singe que use direcciones IP públicas o direcciones IP privadas con NAT. Dado que se trata de datos de ejemplo, le proporcionaremos direcciones IP de ejemplo para que pueda trabajar sus propias entradas con más facilidad:
  
- Adaptador de red interno: 172.25.33.10 (sin puertas de enlace predeterminadas asignadas)
    
    > [!NOTE]
    > Asegúrese de que hay una ruta desde la red que contiene la interfaz interna perimetral a cualquier red que contenga servidores que ejecuten clientes de Skype Empresarial Server o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externo:
    
  - Ip públicas:
    
  - Perímetro de acceso: 131.107.155.10 (este es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
  - Servidor perimetral de conferencia web: 131.107.155.20 (secundario)
    
  - Perímetro A/V: 131.107.155.30 (secundario)
    
  Las conferencias web y las direcciones IP públicas perimetrales A/V son direcciones IP adicionales (secundarias) en la sección Avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
  - Ip privadas:
    
  - Perímetro de acceso: 10.45.16.10 (este es el principal, con la puerta de enlace predeterminada establecida en el enrutador, por ejemplo: 10.45.16.1)
    
  - Servidor perimetral de conferencia web: 10.45.16.20 (secundario)
    
  - Perímetro A/V: 10.45.16.30 (secundario)
    
Las conferencias web y las direcciones IP públicas perimetrales A/V son direcciones IP adicionales (secundarias) en la sección Avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
  
> [!TIP]
>Aquí hay otras configuraciones posibles:
  
- Puede usar una dirección IP en el adaptador de red externo. No se recomienda esto porque, a continuación, tendrá que diferenciar entre los servicios de ti usando diferentes puertos (que puede hacer en Skype Empresarial Server), pero hay algunos firewalls que pueden bloquear los puertos alternativos. Consulta la [sección Planeación de puertos](edge-environmental-requirements.md#PortFirewallPlan) y firewalls para obtener más información sobre esto.
    
- Puede tener tres adaptadores de red externos en lugar de uno y asignar una de las direcciones IP de servicio a cada uno. ¿Por qué hacerlo? Separaría los servicios y, si algo sale mal, esto facilitaría la solución de problemas y podría permitir que los demás servicios sigan funcionando mientras resuelve un problema.
    
|**Location**|**Tipo**|**Port**|**Registro DNS o FQDN**|**Dirección IP o FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 <br/> **private:** 10.45.16.10 <br/> |Una interfaz externa para el servicio perimetral de acceso. Necesitará uno para cada dominio SIP con Skype Empresarial usuarios.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 <br/> **private:** 10.45.16.20 <br/> |Una interfaz externa para el servicio perimetral de conferencia web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 <br/> **private:** 10.45.16.30 <br/> |Una interfaz externa para el servicio perimetral A/V.  <br/> |
|DNS externo  <br/> |registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para el servicio perimetral de acceso. Este registro SRV es necesario para que los Skype Empresarial Server, Lync Server 2013 y Lync Server 2010 funcionen externamente. Necesitará uno para cada dominio con Skype Empresarial usuarios.  <br/> |
|DNS externo  <br/> |registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para el servicio perimetral de acceso. Este registro SRV es necesario para la detección automática de DNS de socios federados denominados dominios SIP permitidos. Necesitará uno para cada dominio con Skype Empresarial usuarios.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |N/D  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |La interfaz interna del servidor perimetral consolidado.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Registros DNS para escenarios de servidor perimetral de hardware y DNS escalado

Estos serán los registros DNS que necesitará para un servidor perimetral singe que use direcciones IP públicas o direcciones IP privadas con NAT. Dado que se trata de datos de ejemplo, le proporcionaremos direcciones IP de ejemplo para que pueda trabajar sus propias entradas con más facilidad:
  
- Adaptador de red interno:
    
  - Nodo 1: 172.25.33.10 (sin puerta de enlace predeterminada asignada)
    
  - Nodo 2: 172.25.33.11 (sin puerta de enlace predeterminada asignada)
    
    > [!NOTE]
    > Asegúrese de que hay una ruta desde la red que contiene la interfaz interna perimetral a cualquier red que contenga servidores que ejecuten clientes de Skype Empresarial Server o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externo:
    
  - Nodo 1
    
     - Ip públicas:
    
        - Perímetro de acceso: 131.107.155.10 (este es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
        - Servidor perimetral de conferencia web: 131.107.155.20 (secundario)
    
        - Perímetro A/V: 131.107.155.30 (secundario)
    
          Las conferencias web y las direcciones IP públicas perimetrales A/V son direcciones IP adicionales (secundarias) en la sección Avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
    - Ip privadas:
    
         - Perímetro de acceso: 10.45.16.10 (este es el principal, con la puerta de enlace predeterminada establecida en el enrutador, por ejemplo: 10.45.16.1)
    
         - Servidor perimetral de conferencia web: 10.45.16.20 (secundario)
    
         - Perímetro A/V: 10.45.16.30 (secundario)
    
      Las conferencias web y las direcciones IP públicas perimetrales A/V son direcciones IP adicionales (secundarias) en la sección Avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
  - Nodo 2
    
    - Ip públicas:
    
      - Perímetro de acceso: 131.107.155.11 (este es el principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
      - Servidor perimetral de conferencia web: 131.107.155.21 (secundario)
    
      - Perímetro A/V: 131.107.155.31 (secundario)
    
      Las conferencias web y las direcciones IP públicas perimetrales A/V son direcciones IP adicionales (secundarias) en la sección Avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
  - Ip privadas:
    
    - Perímetro de acceso: 10.45.16.11 (este es el principal, con la puerta de enlace predeterminada establecida en el enrutador, por ejemplo: 10.45.16.1)
    
    - Servidor perimetral de conferencia web: 10.45.16.21 (secundario)
    
    - Perímetro A/V: 10.45.16.31 (secundario)
    
      Las conferencias web y las direcciones IP públicas perimetrales A/V son direcciones IP adicionales (secundarias) en la sección Avanzadas de las propiedades del Protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
Aquí hay otras configuraciones posibles:
  
- Puede usar una dirección IP en el adaptador de red externo. No se recomienda esto porque, a continuación, tendrá que diferenciar entre los servicios de ti usando diferentes puertos (que puede hacer en Skype Empresarial Server), pero hay algunos firewalls que pueden bloquear los puertos alternativos. Consulta la [sección Planeación de puertos](edge-environmental-requirements.md#PortFirewallPlan) y firewalls para obtener más información sobre esto.
    
- Puede tener tres adaptadores de red externos en lugar de uno y asignar una de las direcciones IP de servicio a cada uno. ¿Por qué hacerlo? Separaría los servicios y, si algo sale mal, esto facilitaría la solución de problemas y podría permitir que los demás servicios sigan funcionando mientras resuelve un problema.
    
|**Location**|**Tipo**|**Port**|**Registro DNS o FQDN**|**Dirección IP o FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 y 131.107.155.11 <br/> **private:** 10.45.16.10 y 10.45.16.11 <br/> |Una interfaz externa para el servicio perimetral de acceso. Necesitará uno para cada dominio SIP con Skype Empresarial usuarios.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 y 131.107.155.21 <br/> **private:** 10.45.16.20 y 10.45.16.21 <br/> |Una interfaz externa para el servicio perimetral de conferencia web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 y 131.107.155.31 <br/> **private:** 10.45.16.30 y 10.45.16.31 <br/> |Una interfaz externa para el servicio perimetral A/V.  <br/> |
|DNS externo  <br/> |registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para el servicio perimetral de acceso. Este registro SRV es necesario para que los Skype Empresarial Server, Lync Server 2013 y Lync Server 2010 funcionen externamente. Necesitará uno para cada dominio con Skype Empresarial.  <br/> |
|DNS externo  <br/> |registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para el servicio perimetral de acceso. Este registro SRV es necesario para la detección automática de DNS de socios federados denominados dominios SIP permitidos. Necesitará uno para cada dominio con Skype Empresarial.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |N/D  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 y 172.25.33.11  <br/> |La interfaz interna del servidor perimetral consolidado.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para federación (todos los escenarios)

|**Location**|**Tipo**|**Port**|**FQDN**|**Registro de host FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |La interfaz externa perimetral de acceso SIP necesaria para la detección automática de DNS. Usado por los demás socios de federación potenciales. También se conoce como "Permitir dominios SIP". Necesitará uno de estos para cada dominio SIP con Skype Empresarial usuarios.  <br/><br/> **Nota:** Necesitará este registro SRV para movilidad y la cámara de compensación de notificaciones de inserción. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Registros DNS para mensajería extensible y protocolo de presencia

|**Location**|**Tipo**|**Port**|**FQDN**|**Dirección IP o registro de host FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |La interfaz de proxy XMPP en el servicio perimetral de acceso o el grupo de servidores perimetrales. Debe repetir esto según sea necesario para todos los dominios SIP internos con Skype Empresarial Server usuarios habilitados, donde se permite el contacto con contactos XMPP a través de:  <br/> • una directiva global  <br/> • una directiva de sitio donde el usuario está habilitado  <br/> • una directiva de usuario aplicada al usuario Skype Empresarial Server habilitado  <br/> Una directiva XMPP permitida también debe configurarse en la directiva de usuarios federados XMPP.  <br/> |
|DNS externo  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Dirección IP del servicio perimetral de acceso en el servidor perimetral o grupo de servidores perimetrales que hospeda el servicio de proxy XMPP  <br/> |Esto apunta al servicio perimetral de acceso en el servidor perimetral o grupo de servidores perimetrales que hospeda el servicio proxy XMPP. Normalmente, el registro SRV que cree apuntará a este registro host (A o AAAA).  <br/> |
   
> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.

## <a name="certificate-planning"></a>Planificación de certificado
<a name="CertPlan"> </a>

Skype Empresarial Server certificados para comunicaciones cifradas y seguras entre servidores y de servidor a cliente. Como es de esperar, los certificados tendrán que hacer que los registros DNS de los servidores coincidan con cualquier nombre de sujeto (SN) y nombre alternativo de sujeto (SAN) en los certificados. Esto tomará trabajo ahora, en la fase de planeación, para asegurarse de que tiene los FQDN correctos registrados en DNS para las entradas de SN y SAN para sus certificados.
  
Analizaremos las necesidades de certificados externos e internos por separado y, a continuación, veremos una tabla que proporcione los requisitos para ambos.
  
### <a name="external-certificates"></a>Certificados externos

Como mínimo, una entidad de certificación (CA) pública deberá proporcionar el certificado asignado a las interfaces del servidor perimetral externo. No podemos recomendarle una CA específica, pero sí una lista de [CA,](../../../SfbPartnerCertification/certification/services-ssl.md) asociados de certificados de comunicaciones unificadas que puede echar un vistazo para ver si aparece la CA preferida.
  
¿Cuándo tendrá que enviar una solicitud a una CA para este certificado público y cómo hacerlo? Hay un par de maneras de lograr esto:
  
- Puede ir a través de la instalación de Skype Empresarial Server y, a continuación, la implementación del servidor perimetral. El Skype Empresarial Server de implementación tendrá un paso para generar una solicitud de certificado, que luego puede enviar a la ca elegida.
    
- También puede usar Windows PowerShell comandos para generar esta solicitud, si esto está más en línea con las necesidades empresariales o la estrategia de implementación.
    
- Por último, la CA puede tener su propio proceso de envío, lo que también puede implicar Windows PowerShell otro método. En ese caso, tendrá que basarse en su documentación, además de la información que se proporciona aquí para su referencia.
    
Después de obtener el certificado, deberá seguir adelante y asignarlo a estos servicios en Skype Empresarial Server:
  
- Interfaz de servicio perimetral de acceso
    
- Interfaz de servicio perimetral de conferencia web
    
- Servicio de autenticación de audio y vídeo (no confunda esto con el servicio perimetral A/V, ya que no usa un certificado para cifrar secuencias de audio y vídeo)
    
> [!IMPORTANT]
> Todos los servidores perimetrales (si pertenecen al mismo grupo de servidores perimetrales) deben tener exactamente el mismo certificado con la misma clave privada para el servicio de autenticación de retransmisión multimedia. 
  
### <a name="internal-certificates"></a>Certificados internos

Para la interfaz interna del servidor perimetral, puede usar un certificado público de una CA pública o un certificado emitido desde la CA interna de la organización. Lo que hay que recordar acerca del certificado interno es que usa una entrada SN y no hay entradas de SAN, por lo que no tiene que preocuparse por SAN en el certificado interno en absoluto.
  
### <a name="required-certificates-table"></a>Tabla Certificados requeridos

Tenemos una tabla aquí para ayudarle con sus solicitudes. Las entradas FQDN aquí son solo para dominios de ejemplo. Tendrá que realizar solicitudes en función de sus propios dominios públicos y privados, pero esta es una guía de lo que hemos usado:
  
- contoso <span></span> .com: FQDN público
    
- fabrikam .com: Segundo FQDN público (agregado como una demostración de lo que se va <span></span> a solicitar si tiene varios dominios SIP)
    
- Contoso <span></span> .net: dominio interno
    
#### <a name="edge-certificate-table"></a>Tabla certificado perimetral

Independientemente de si está haciendo un solo servidor perimetral o un grupo de servidores perimetrales, esto es lo que necesitará para el certificado:
  
|**Componente**|**Nombre del sujeto**|**Nombres alternativos de sujeto (SAN)/order**|**Notas**|
|:-----|:-----|:-----|:-----|
|Borde externo  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Este es el certificado que necesita solicitar a una entidad de certificación pública. Tendrá que asignarse a las interfaces perimetrales externas para lo siguiente:  <br/> • Perímetro de acceso  <br/> • Servidor perimetral de conferencia web  <br/> • Autenticación de audio y vídeo  <br/> <br/>La buena noticia es que los SAN se agregan automáticamente a la solicitud de certificado y, por lo tanto, el certificado después de enviar la solicitud, en función de lo que definió para esta implementación en el Generador de topologías. Solo necesitará agregar entradas SAN para cualquier dominio SIP adicional u otras entradas que necesite admitir. ¿Por qué sip.contoso.com replica en esta instancia? Esto también sucede automáticamente y es necesario para que las cosas funcionen correctamente.  <br/><br/> **Nota:** Este certificado también se puede usar para la conectividad de mensajería instantánea pública. No es necesario hacer nada diferente con él, pero en versiones anteriores de esta documentación, se enumeraba como una tabla independiente y ahora no lo es. <br/> |
|Perímetro interno  <br/> |sfbedge.contoso.com  <br/> |N/D  <br/> |Puede obtener este certificado de una CA pública o una CA interna. Tendrá que contener el servidor EKU (uso mejorado de clave) y lo asignará a la interfaz perimetral interna.  <br/> |
   
Si necesita un certificado para el Protocolo extensible de mensajería y presencia (XMPP), tendrá un aspecto idéntico a las entradas de tabla perimetral externa anteriores, pero tendrá las dos entradas san adicionales siguientes:
  
- xmpp. <span></span> contoso <span></span> .com
    
- \*.contoso <span></span> .com
    
Recuerde que actualmente XMPP solo es compatible con Skype Empresarial Server para Google Talk, si desea o necesita usarlo para cualquier otra cosa, debe confirmar esa funcionalidad con el proveedor de terceros implicado.
  
## <a name="port-and-firewall-planning"></a>Planeación de puertos y firewall
<a name="PortFirewallPlan"> </a>

Obtener la planeación adecuada para puertos y firewalls para Skype Empresarial Server implementaciones de servidor perimetral puede ahorrarle días o semanas de solución de problemas y estrés. Como resultado, vamos a enumerar un par de tablas que indicarán el uso de nuestro protocolo y qué puertos necesita tener abiertos, entrantes y salientes, tanto para escenarios NAT como ip pública. También tendremos tablas independientes para escenarios de carga equilibrada de hardware (HLB) y algunas instrucciones adicionales al respecto. Para obtener más información desde allí, también tenemos algunos [escenarios](scenarios.md) de servidor perimetral en Skype Empresarial Server puede consultar sus problemas de implementación concretos.
  
### <a name="general-protocol-usage"></a>Uso de protocolo general

Antes de examinar las tablas de resumen de firewalls externos e internos, vamos a considerar también la siguiente tabla:
  
|**Transporte de audio y vídeo**|**Uso**|
|:-----|:-----|
|UDP  <br/> |Protocolo de capa de transporte preferido para audio y vídeo.  <br/> |
|TCP  <br/> |Protocolo de capa de transporte de reserva para audio y vídeo.  <br/> El protocolo de capa de transporte necesario para el uso compartido de aplicaciones Skype Empresarial Server, Lync Server 2013 y Lync Server 2010.  <br/> El protocolo de capa de transporte necesario para la transferencia de archivos a Skype Empresarial Server, Lync Server 2013 y Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabla de resumen de firewall de puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para los usuarios que usan direcciones IP privadas con NAT, así como las personas que usan direcciones IP públicas. Esto cubrirá todas las permutaciones en nuestros [escenarios](scenarios.md) de servidor perimetral en Skype Empresarial Server sección.
  
|**Rol o protocolo**|**TCP o UDP**|**Puerto de destino o intervalo de puertos**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> No se admite en Skype Empresarial Server 2019 |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso  <br/> |El servicio proxy XMPP acepta tráfico de contactos XMPP en federaciones XMPP definidas.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Cualquiera  <br/> |Consulta DNS a través de TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Cualquiera  <br/> |Consulta DNS a través de UDP.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Para la conectividad de mensajería instantánea pública y federada mediante SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Cualquiera  <br/> |Para la conectividad de mensajería instantánea pública y federada mediante SIP.  <br/> |
|Conferencia web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral de conferencia web de servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de conferencia web del servidor perimetral <br/> |Medios de conferencia web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privada con NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral <br/> |Cualquiera  <br/> |Esto se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privada con NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral <br/> |Cualquiera  <br/> |Esto se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privada con NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral <br/> |Cualquiera  <br/> |3478 saliente es:  <br/> • Se usa Skype Empresarial Server para determinar la versión del servidor perimetral con el que se está comunicando.  <br/> • Se usa para el tráfico multimedia entre servidores perimetrales.  <br/> • Necesario para la federación con Lync Server 2010.  <br/> • Necesario si se implementan varios grupos de servidores perimetrales dentro de la organización.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privada con NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral <br/> |Cualquiera  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabla de resumen del firewall de puerto interno

|**Protocolo**|**TCP o UDP**|**Port**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de los siguientes procedimientos para ejecutar el servicio de puerta de enlace XMPP:  <br/> • Servidor front-end  <br/> • Grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end.  <br/> **Nota:** Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Cualquiera:  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor front-end  <br/> • Grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico SIP saliente desde el director, el grupo de directores, el servidor front-end o el grupo de servidores front-end a la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interfaz interna del servidor perimetral  <br/> |Cualquiera:  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor front-end  <br/> • Grupo de servidores front-end  <br/> |Tráfico SIP entrante a su director, grupo de directores, servidor front-end o grupo de servidores front-end desde la interfaz interna del servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Cualquiera:  <br/> • Servidor front-end  <br/> • Cada servidor front-end  <br/>  en el grupo de servidores front-end <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico de conferencia web desde el servidor front-end o cada servidor front-end (si tiene un grupo de servidores front-end) a la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Cualquiera:  <br/> • Servidor front-end  <br/> • Grupo de servidores front-end  <br/> • Cualquier aplicación de sucursal con funciones de supervivencia que use este servidor perimetral  <br/> • Cualquier servidor de sucursal con funciones de supervivencia que use este servidor perimetral  <br/> |Interfaz interna del servidor perimetral  <br/> |Autenticación de usuarios A/V desde el servidor front-end o el grupo de servidores front-end, o la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia, mediante el servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso preferida para la transferencia de medios A/V entre los usuarios internos y externos y la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso de reserva para la transferencia de medios A/V entre los usuarios internos y externos y la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia, si la comunicación UDP no funciona. A continuación, se usa TCP para transferencias de archivos y uso compartido de escritorio.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Cualquiera:  <br/> • Servidor front-end que contiene el almacén de administración central  <br/> • Grupo de servidores front-end que contiene el almacén de administración central  <br/> |Interfaz interna del servidor perimetral  <br/> |Replicación de cambios desde el almacén de administración central al servidor perimetral.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante los cmdlets del Shell de administración Skype Empresarial Server y el servicio de registro centralizado, la línea de comandos ClsController (ClsController.exe) o los comandos de agente (ClsAgent.exe) y la colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante los cmdlets del Shell de administración Skype Empresarial Server y el servicio de registro centralizado, la línea de comandos ClsController (ClsController.exe) o los comandos de agente (ClsAgent.exe) y la colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante los cmdlets del Shell de administración Skype Empresarial Server y el servicio de registro centralizado, la línea de comandos ClsController (ClsController.exe) o los comandos de agente (ClsAgent.exe) y la colección de registros.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Equilibradores de carga de hardware para tablas de puerto perimetral

Estamos dando a los equilibradores de carga de hardware (HLB) y los puertos perimetrales su propia sección, ya que las cosas son un poco más complicadas con el hardware adicional. Consulte las tablas siguientes para obtener instrucciones sobre este escenario concreto:
  
#### <a name="external-port-firewall-summary-table"></a>Tabla de resumen de firewall de puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para los usuarios que usan direcciones IP privadas con NAT, así como las personas que usan direcciones IP públicas. Esto cubrirá todas las permutaciones en nuestros [escenarios](scenarios.md) de servidor perimetral en Skype Empresarial Server sección.
  
|**Rol o protocolo**|**TCP o UDP**|**Puerto de destino o intervalo de puertos**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral  <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral  <br/> |Cualquiera  <br/> |Consulta DNS a través de TCP.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral  <br/> |Cualquiera  <br/> |Consulta DNS a través de UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Dirección IP del servicio perimetral A/V del servidor perimetral perimetral  <br/> |Cualquiera  <br/> |Esto se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral  <br/> |Cualquiera  <br/> |Esto se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral  <br/> |Cualquiera  <br/> |3478 saliente es:  <br/> • Se usa Skype Empresarial Server para determinar la versión del servidor perimetral con el que se está comunicando.  <br/> • Se usa para el tráfico multimedia entre servidores perimetrales.  <br/> • Necesario para la federación.  <br/> • Necesario si se implementan varios grupos de servidores perimetrales dentro de la organización.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral  <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral  <br/> |Cualquiera  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabla de resumen del firewall de puerto interno

|**Protocolo**|**TCP o UDP**|**Port**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de los siguientes procedimientos para ejecutar el servicio de puerta de enlace XMPP:  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o grupo de servidores front-end.  <br/><br/> **Nota:** Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información. |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Cualquiera:  <br/> • Servidor front-end que contiene el almacén de administración central  <br/> • Grupo de servidores front-end que contiene el almacén de administración central  <br/> |Interfaz interna del servidor perimetral  <br/> |Replicación de cambios desde el almacén de administración central al servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Cualquiera:  <br/> • Servidor front-end  <br/> • Cada servidor front-end del grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico de conferencia web desde el servidor front-end o cada servidor front-end (si tiene un grupo de servidores front-end) a la interfaz interna del servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera:  <br/> • Servidor front-end  <br/> • Cada servidor front-end del grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso preferida para la transferencia de medios A/V entre los usuarios internos y externos y la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera:  <br/> • Servidor front-end  <br/> • Cada servidor front-end del grupo  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso de reserva para la transferencia de medios A/V entre los usuarios internos y externos y la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia, si la comunicación UDP no funciona. A continuación, se usa TCP para transferencias de archivos y uso compartido de escritorio.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante los cmdlets del Shell de administración Skype Empresarial Server y el servicio de registro centralizado, la línea de comandos ClsController (ClsController.exe) o los comandos de agente (ClsAgent.exe) y la colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante los cmdlets del Shell de administración Skype Empresarial Server y el servicio de registro centralizado, la línea de comandos ClsController (ClsController.exe) o los comandos de agente (ClsAgent.exe) y la colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante los cmdlets del Shell de administración Skype Empresarial Server y el servicio de registro centralizado, la línea de comandos ClsController (ClsController.exe) o los comandos de agente (ClsAgent.exe) y la colección de registros.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IPs virtuales de interfaz externa

|**Rol o protocolo**|**TCP o UDP**|**Puerto de destino o intervalo de puertos**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> No se admite en Skype para Businesss Server 2019 |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso)  <br/> |El servicio proxy XMPP acepta tráfico de contactos XMPP en federaciones XMPP definidas.  <br/> |
|XMPP  <br/>No se admite en Skype para Businesss Server 2019 |TCP  <br/> |5269  <br/> |Servicio proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso)  <br/> |Cualquiera  <br/> |El servicio proxy XMPP envía tráfico de contactos XMPP en federaciones XMPP definidas.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Para la conectividad de mensajería instantánea pública y federada mediante SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privada con NAT:** Servicio perimetral de acceso al servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso al servidor perimetral perimetral <br/> |Cualquiera  <br/> |Para la conectividad de mensajería instantánea pública y federada mediante SIP.  <br/> |
|Conferencia web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral de conferencia web de servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de conferencia web del servidor perimetral <br/> |Medios de conferencia web.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada con NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral perimetral <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IPs virtuales de interfaz interna

Nuestra guía aquí va a ser un poco diferente. En realidad, en una situación de HLB, ahora recomendamos que solo tenga el enrutamiento a través de una VIP interna en las siguientes circunstancias:
  
- Si está usando Exchange 2007 o Exchange mensajería unificada (UM) de 2010.
    
- Si tiene clientes heredados con edge.
    
En la tabla siguiente se proporcionan instrucciones para esos escenarios, pero de lo contrario, debería poder depender del almacén de administración central (CMS) para enrutar el tráfico al servidor perimetral individual que conoce (esto requiere que CMS esté actualizado en la información del servidor perimetral, por supuesto).
  
|**Protocolo**|**TCP o UDP**|**Port**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera:  <br/> • Director  <br/> • Dirección VIP del grupo de directores  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico SIP saliente desde el director, la dirección VIP del grupo de directores, el servidor front-end o la dirección VIP del grupo de servidores front-end a la interfaz interna del servidor perimetral.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interfaz VIP interna del servidor perimetral  <br/> |Cualquiera:  <br/> • Director  <br/> • Dirección VIP del grupo de directores  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end  <br/> |Tráfico SIP entrante a su director, dirección VIP del grupo de directores, servidor front-end o dirección VIP del grupo de servidores front-end desde la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Cualquiera:  <br/> • Dirección IP del servidor front-end  <br/> • Dirección IP del grupo de servidores front-end  <br/> • Cualquier aplicación de sucursal con funciones de supervivencia que use este servidor perimetral  <br/> • Cualquier servidor de sucursal con funciones de supervivencia que use este servidor perimetral  <br/> |Interfaz interna del servidor perimetral  <br/> |Autenticación de usuarios A/V desde el servidor front-end o el grupo de servidores front-end, o la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia, mediante el servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso preferida para la transferencia de medios A/V entre los usuarios internos y externos.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Interfaz VIP interna del servidor perimetral  <br/> |Ruta de acceso de reserva para la transferencia de medios A/V entre los usuarios internos y externos si la comunicación UDP no funciona. A continuación, se usa TCP para transferencias de archivos y uso compartido de escritorio.  <br/> |