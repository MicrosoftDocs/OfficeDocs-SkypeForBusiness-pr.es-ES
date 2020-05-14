---
title: Requisitos de entorno del servidor perimetral en Skype empresarial Server
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
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Resumen: Obtenga información sobre los requisitos del entorno para el servidor perimetral en Skype empresarial Server.'
ms.openlocfilehash: 8e2ec6d2afc53648fe50af4cd5ab02ad21d11643
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219930"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisitos de entorno del servidor perimetral en Skype empresarial Server
 
**Resumen:** Obtenga información sobre los requisitos del entorno para el servidor perimetral en Skype empresarial Server.
  
Una gran cantidad de planeación y preparación tiene que realizarse fuera del entorno del servidor perimetral de Skype empresarial Server en sí. En este artículo, revisaremos los preparativos que deben realizarse en el entorno de la organización, según la lista siguiente:
  
- [Planeación de la topología](edge-environmental-requirements.md#TopoPlan)
    
- [Planeación de DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Planeación de certificados](edge-environmental-requirements.md#CertPlan)
    
- [Planeación de puertos y firewalls](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planeación de la topología
<a name="TopoPlan"> </a>

Las topologías de servidor perimetral de Skype empresarial Server pueden usar:
  
- Direcciones IP públicas enrutables.
    
- Direcciones IP privadas no enrutables, si se usa la traducción de direcciones de red (NAT) **simétrica** .
    
> [!TIP]
> El servidor perimetral se puede configurar para usar una dirección IP única con puertos distintos para cada servicio, o puede usar direcciones IP distintas para cada servicio, pero usar el mismo puerto predeterminado (que será TCP 443 de forma predeterminada). Encontrará más información en la sección requisitos de direcciones IP, a continuación. 
  
Si elige direcciones IP privadas no enrutables con NAT, recuerde estos puntos:
  
- Debe usar direcciones IP privadas enrutables en **las tres** interfaces externas.
    
- Debe configurar NAT **simétrica** para el tráfico entrante y saliente. La NAT simétrica es la única NAT admitida que puede usar con el servidor perimetral de Skype empresarial Server.
    
- Configure el NAT para que no cambie las direcciones de origen de entrada. El servicio perimetral a/V necesita poder recibir la dirección de origen entrante para encontrar la ruta de acceso de medios óptima.
    
- Los servidores perimetrales deben poder comunicarse entre sí desde sus direcciones IP perimetrales de A/V públicas. El Firewall debe permitir este tráfico.
    
- NAT **solo** se puede usar para servidores perimetrales consolidados escalados si usa el equilibrio de carga de DNS. Si usa el equilibrio de carga de hardware (HLB), debe usar direcciones IP enrutables públicamente **sin** NAT.
    
No tendrá ningún problema con las interfaces perimetrales de acceso, conferencia web y a/V detrás de un enrutador o firewall que realicen NAT simétricas para topologías de servidor perimetral consolidado simples y escaladas (siempre que no use el equilibrio de carga de hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Resumen de opciones de topología de servidores perimetrales

Disponemos de varias opciones de topología disponibles para las implementaciones del servidor perimetral de Skype empresarial Server:
  
- Servidor perimetral consolidado único con direcciones IP privadas y NAT
    
- Servidor perimetral consolidado único con direcciones IP públicas
    
- Servidor perimetral consolidado ampliado con direcciones IP privadas y NAT
    
- Servidor perimetral consolidado ampliado con direcciones IP públicas
    
- Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
    
Para ayudarle a elegir una, tenemos la siguiente tabla, que proporciona un resumen de las opciones que tiene para cada topología:
  
|**Topología**|**Alta disponibilidad**|**¿Se requieren registros DNS adicionales para el servidor perimetral externo en el grupo de servidores perimetrales?**|**Failover perimetral para sesiones de Skype empresarial Server**|**Failover perimetral para sesiones de Federación de Skype empresarial Server**|
|:-----|:-----|:-----|:-----|:-----|
|Servidor perimetral consolidado único con direcciones IP privadas y NAT  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Servidor perimetral consolidado único con direcciones IP públicas  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Servidor perimetral consolidado ampliado con direcciones IP privadas y NAT (con equilibrio de carga de DNS)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí&Sup1;  <br/> |
|Servidor perimetral consolidado ampliado con direcciones IP públicas (con equilibrio de carga DNS)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí&Sup1;  <br/> |
|Servidor perimetral consolidado ampliado con equilibradores de carga de hardware  <br/> |Sí  <br/> |No (un registro A DNS por VIP)  <br/> |Sí  <br/> |Sí  <br/> |
   
&Sup1; La conmutación por error de usuario de mensajería unificada (UM) de Exchange mediante el equilibrio de carga de DNS requiere Exchange 2013 o posterior.
  
### <a name="ip-address-requirements"></a>Requisitos de dirección IP

En un nivel fundamental, tres servicios necesitan direcciones IP; Servicio perimetral de acceso, servicio perimetral de conferencia web y servicio perimetral A/V. Tiene la opción de usar tres direcciones IP, una para cada uno de los servicios, o puede usar una y optar por poner cada servicio en un puerto diferente (puede consultar la sección de [planeación de puertos y firewall](edge-environmental-requirements.md#PortFirewallPlan) para obtener más información sobre algunos de ellos). Para un entorno de servidor perimetral consolidado único, es muy importante.
  
> [!NOTE]
> Como se indicó anteriormente, puede elegir tener una dirección IP para los tres servicios y ejecutarla en diferentes puertos. Pero, para ser claro, no lo recomendamos. Si los clientes no pueden acceder a los puertos alternativos que va a usar en este escenario, no podrán acceder a toda la funcionalidad del entorno perimetral. 
  
Puede ser algo más complicado con topologías consolidadas escaladas, así que vamos a analizar algunas tablas que diseñan los requisitos de las direcciones IP, teniendo en cuenta que los puntos de decisión principales para la selección de topología son la alta disponibilidad y el equilibrio de carga. Las necesidades de alta disponibilidad pueden influir en su elección de equilibrio de carga (hablaremos de ello más después de las tablas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de dirección IP para servidor perimetral consolidado escalado (dirección IP por rol)

|**Número de servidores perimetrales por grupo**|**Número de direcciones IP necesarias para el equilibrio de carga de DNS**|**Número de direcciones IP necesarias para el equilibrio de carga de hardware**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (1 por VIP) + 6  <br/> |
|3  <br/> |9   <br/> |3 (1 por VIP) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 por VIP) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 por VIP) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de dirección IP para servidor perimetral consolidado de escala (una dirección IP única para todos los roles)

|**Número de servidores perimetrales por grupo**|**Número de direcciones IP necesarias para el equilibrio de carga de DNS**|**Número de direcciones IP necesarias para el equilibrio de carga de hardware**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (1 por VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 por VIP) + 3  <br/> |
|4   <br/> |4   <br/> |1 (1 por VIP) + 4  <br/> |
|5   <br/> |2,5  <br/> |1 (1 por VIP) + 5  <br/> |
   
Veamos algunas cosas adicionales que hay que considerar al planear.
  
- **Alta disponibilidad**: Si necesita alta disponibilidad en su implementación, debe implementar al menos dos servidores perimetrales en un grupo. Merece la pena tener en cuenta que un solo grupo de servidores perimetrales admitirá hasta 12 servidores perimetrales (aunque el generador de topologías le permitirá agregar hasta 20, que no están probados ni son compatibles, por lo que le recomendamos que no lo haga). Si necesita más de 12 servidores perimetrales, debe crear grupos de servidores perimetrales adicionales para ellos.
    
- **Equilibrio de carga de hardware**: se recomienda el equilibrio de carga de DNS en la mayoría de los escenarios. El equilibrio de carga de hardware también es compatible, por supuesto, pero es necesario para un escenario único a través del equilibrio de carga de DNS:
    
  - Acceso externo a Exchange 2007 o Exchange 2010 (sin SP) mensajería unificada (UM).
    
- **Equilibrio de carga de DNS**: para la mensajería unificada, Exchange 2010 SP1 y versiones posteriores pueden ser compatibles con el equilibrio de carga de DNS. Tenga en cuenta que si tiene que ir con el equilibrio de carga de DNS para una versión anterior de Exchange, funcionará, pero todo el tráfico para ello irá al primer servidor del grupo y, si no está disponible, se producirá un error en ese tráfico.
    
    El equilibrio de carga de DNS también se recomienda si está realizando una federación con empresas que usan:
- Skype empresarial Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 u Office 365
- Skype empresarial Server 2019:
    - Lync Server 2013
    - Skype Empresarial Server 2015
    - Microsoft 365 u Office 365
    
## <a name="dns-planning"></a>Planeación de DNS
<a name="DNSPlan"> </a>

En lo que respecta a la implementación de servidores perimetrales de Skype empresarial Server, es fundamental prepararse para DNS correctamente. Con los registros correctos en su ubicación, la implementación será mucho más sencilla. Esperamos que haya elegido una topología en la sección anterior, ya que vamos a hacer una introducción y, a continuación, enumerar un par de tablas que esquematiza los registros DNS para esos escenarios. También tendremos en cuenta la [planificación de DNS del servidor perimetral avanzado para Skype empresarial Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) para una lectura más profunda, si es necesario.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Registros DNS para escenarios de servidor perimetral consolidado único

Estos serán los registros DNS que necesitará para un servidor perimetral único mediante IP públicas o IP privadas con NAT. Como se trata de datos de ejemplo, proporcionaremos direcciones IP de ejemplo para que pueda trabajar con sus propias entradas de forma más sencilla:
  
- Adaptador de red interna: 172.25.33.10 (no hay puertas de enlace predeterminadas asignadas)
    
    > [!NOTE]
    > Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna a cualquier red que contenga servidores que ejecuten clientes de Skype empresarial Server o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externa:
    
  - IP públicas:
    
  - Servidor perimetral de acceso: 131.107.155.10 (es la principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
  - Perimetral de conferencia web: 131.107.155.20 (secundario)
    
  - Servidor perimetral A/V: 131.107.155.30 (secundario)
    
  Las direcciones IP públicas de servidor perimetral de conferencia web y de A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades de protocolo de Internet versión 4 (TCP/IPv4) y Protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
  - IP privadas:
    
  - Servidor perimetral de acceso: 10.45.16.10 (es la principal, con la puerta de enlace predeterminada establecida en el enrutador, por ejemplo: 10.45.16.1)
    
  - Perimetral de conferencia web: 10.45.16.20 (secundario)
    
  - Servidor perimetral A/V: 10.45.16.30 (secundario)
    
Las direcciones IP públicas de servidor perimetral de conferencia web y de A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades de protocolo de Internet versión 4 (TCP/IPv4) y Protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
  
> [!TIP]
>Hay otras configuraciones posibles:
  
- Puede usar una dirección IP en el adaptador de red externa. No se recomienda esto porque necesitará diferenciar entre los servicios que usan diferentes puertos (que puede hacer en Skype empresarial Server), pero hay algunos firewalls que pueden bloquear los puertos alternativos. Consulte la sección [planificación de puertos y firewall](edge-environmental-requirements.md#PortFirewallPlan) para obtener más información al respecto.
    
- Puede tener tres adaptadores de red externos en lugar de uno y asignar una de las IP de servicio a cada uno de ellos. ¿Por qué hacerlo? Separaría los servicios y, si algo va mal, facilitaría la solución de problemas y, posiblemente, permitiría que el resto de los servicios continuara funcionando mientras se resuelve un problema.
    
|**Ubicación**|**Tipo**|**Port**|**FQDN o registro DNS**|**Dirección IP o FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 <br/> **privado:** 10.45.16.10 <br/> |Una interfaz externa para el servicio perimetral de acceso. Necesitará uno para cada dominio SIP con usuarios de Skype empresarial.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 <br/> **privado:** 10.45.16.20 <br/> |Una interfaz externa para el servicio perimetral de conferencia Web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 <br/> **privado:** 10.45.16.30 <br/> |Una interfaz externa para el servicio perimetral A/V.  <br/> |
|DNS externo  <br/> |registro SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para el servicio perimetral de acceso. Este registro SRV es necesario para que los clientes de Skype empresarial Server, Lync Server 2013 y Lync Server 2010 funcionen de forma externa. Necesitará uno para cada dominio con usuarios de Skype empresarial.  <br/> |
|DNS externo  <br/> |registro SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para el servicio perimetral de acceso. Este registro SRV es necesario para la detección automática de DNS de socios federados denominados dominios SIP permitidos. Necesitará uno para cada dominio con usuarios de Skype empresarial.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |N/D  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |La interfaz interna del servidor perimetral consolidado.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Registros DNS para escenarios de servidor perimetral de hardware y DNS escalados

Estos serán los registros DNS que necesitará para un servidor perimetral único mediante IP públicas o IP privadas con NAT. Como se trata de datos de ejemplo, proporcionaremos direcciones IP de ejemplo para que pueda trabajar con sus propias entradas de forma más sencilla:
  
- Adaptador de red interna:
    
  - Nodo 1:172.25.33.10 (no hay ninguna puerta de enlace predeterminada asignada)
    
  - Nodo 2:172.25.33.11 (no hay ninguna puerta de enlace predeterminada asignada)
    
    > [!NOTE]
    > Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna a cualquier red que contenga servidores que ejecuten clientes de Skype empresarial Server o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externa:
    
  - Nodo 1
    
     - IP públicas:
    
        - Servidor perimetral de acceso: 131.107.155.10 (es la principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
        - Perimetral de conferencia web: 131.107.155.20 (secundario)
    
        - Servidor perimetral A/V: 131.107.155.30 (secundario)
    
          Las direcciones IP públicas de servidor perimetral de conferencia web y de A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades de protocolo de Internet versión 4 (TCP/IPv4) y Protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
    - IP privadas:
    
         - Servidor perimetral de acceso: 10.45.16.10 (es la principal, con la puerta de enlace predeterminada establecida en el enrutador, por ejemplo: 10.45.16.1)
    
         - Perimetral de conferencia web: 10.45.16.20 (secundario)
    
         - Servidor perimetral A/V: 10.45.16.30 (secundario)
    
      Las direcciones IP públicas de servidor perimetral de conferencia web y de A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades de protocolo de Internet versión 4 (TCP/IPv4) y Protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
  - Nodo 2
    
    - IP públicas:
    
      - Servidor perimetral de acceso: 131.107.155.11 (es la principal, con la puerta de enlace predeterminada establecida en el enrutador público, por ejemplo: 131.107.155.1)
    
      - Perimetral de conferencia web: 131.107.155.21 (secundario)
    
      - Servidor perimetral A/V: 131.107.155.31 (secundario)
    
      Las direcciones IP públicas de servidor perimetral de conferencia web y de A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades de protocolo de Internet versión 4 (TCP/IPv4) y Protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
  - IP privadas:
    
    - Servidor perimetral de acceso: 10.45.16.11 (es la principal, con la puerta de enlace predeterminada establecida en el enrutador, por ejemplo: 10.45.16.1)
    
    - Perimetral de conferencia web: 10.45.16.21 (secundario)
    
    - Servidor perimetral A/V: 10.45.16.31 (secundario)
    
      Las direcciones IP públicas de servidor perimetral de conferencia web y de A/V son direcciones IP adicionales (secundarias) en la sección avanzadas de las propiedades de protocolo de Internet versión 4 (TCP/IPv4) y Protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área local en Windows Server.
    
Hay otras configuraciones posibles:
  
- Puede usar una dirección IP en el adaptador de red externa. No se recomienda esto porque necesitará diferenciar entre los servicios que usan diferentes puertos (que puede hacer en Skype empresarial Server), pero hay algunos firewalls que pueden bloquear los puertos alternativos. Consulte la sección [planificación de puertos y firewall](edge-environmental-requirements.md#PortFirewallPlan) para obtener más información al respecto.
    
- Puede tener tres adaptadores de red externos en lugar de uno y asignar una de las IP de servicio a cada uno de ellos. ¿Por qué hacerlo? Separaría los servicios y, si algo va mal, facilitaría la solución de problemas y, posiblemente, permitiría que el resto de los servicios continuara funcionando mientras se resuelve un problema.
    
|**Ubicación**|**Tipo**|**Port**|**FQDN o registro DNS**|**Dirección IP o FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 y 131.107.155.11 <br/> **privado:** 10.45.16.10 y 10.45.16.11 <br/> |Una interfaz externa para el servicio perimetral de acceso. Necesitará uno para cada dominio SIP con usuarios de Skype empresarial.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 y 131.107.155.21 <br/> **privado:** 10.45.16.20 y 10.45.16.21 <br/> |Una interfaz externa para el servicio perimetral de conferencia Web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |N/D  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 y 131.107.155.31 <br/> **privado:** 10.45.16.30 y 10.45.16.31 <br/> |Una interfaz externa para el servicio perimetral A/V.  <br/> |
|DNS externo  <br/> |registro SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para el servicio perimetral de acceso. Este registro SRV es necesario para que los clientes de Skype empresarial Server, Lync Server 2013 y Lync Server 2010 funcionen de forma externa. Necesitará uno para cada dominio con Skype empresarial.  <br/> |
|DNS externo  <br/> |registro SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Una interfaz externa para el servicio perimetral de acceso. Este registro SRV es necesario para la detección automática de DNS de socios federados denominados dominios SIP permitidos. Necesitará uno para cada dominio con Skype empresarial.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |N/D  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 y 172.25.33.11  <br/> |La interfaz interna del servidor perimetral consolidado.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para la Federación (todos los escenarios)

|**Ubicación**|**Tipo**|**Port**|**FQDN**|**Registro de host de FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp. contoso. com  <br/> |sip.contoso.com  <br/> |La interfaz perimetral externa de acceso SIP necesaria para la detección automática de DNS. Lo usan otros posibles socios de Federación. También se conoce como "Permitir dominios SIP". Necesitará uno de estos para cada dominio SIP con usuarios de Skype empresarial.  <br/><br/> **Nota:** Necesitará este registro SRV para la movilidad y el centro de enrutamiento de notificaciones de inserción. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Registros DNS para el protocolo extensible de mensajería y presencia

|**Ubicación**|**Tipo**|**Port**|**FQDN**|**Dirección IP o registro de host de FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server. _tcp. contoso. com  <br/> |xmpp.contoso.com  <br/> |La interfaz proxy XMPP en el servicio perimetral de acceso o el grupo de servidores perimetrales. Debe repetir esto según sea necesario para todos los dominios SIP internos con usuarios habilitados para Skype empresarial Server, donde se permite el contacto con contactos XMPP:  <br/> • una directiva global  <br/> • una directiva de sitio en la que el usuario ha habilitado  <br/> • una directiva de usuario aplicada al usuario habilitado de Skype empresarial Server  <br/> También es necesario configurar una directiva XMPP permitida en la Directiva de usuarios federados de XMPP.  <br/> |
|DNS externo  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Dirección IP del servicio perimetral de acceso en el servidor perimetral o en el grupo de servidores perimetrales que hospeda el servicio de proxy XMPP  <br/> |Esto apunta al servicio perimetral de acceso en el servidor perimetral o en el grupo de servidores perimetrales que hospeda el servicio de proxy XMPP. Normalmente, el registro SRV que cree apuntará a este registro host (A o AAAA).  <br/> |
   
> [!NOTE]
> Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019. Consulte [migrar la Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.

## <a name="certificate-planning"></a>Planificación de certificado
<a name="CertPlan"> </a>

Skype empresarial Server usa certificados para comunicaciones seguras y cifradas entre servidores y de servidor a cliente. Como cabría esperar, los certificados deben tener registros DNS para que los servidores se correspondan con el nombre de sujeto (SN) y el nombre alternativo de sujeto (SAN) en los certificados. Esto le llevará trabajo ahora, en la fase de planeación, para asegurarse de que tiene los FQDN correctos registrados en DNS para las entradas SN y SAN para los certificados.
  
Analizaremos las necesidades de certificado externo e interno por separado y, a continuación, veremos una tabla que proporciona los requisitos para ambas.
  
### <a name="external-certificates"></a>Certificados externos

Como mínimo, una entidad de certificación (CA) pública deberá proporcionar el certificado asignado a las interfaces del servidor perimetral externo. No se puede recomendar una CA específica a usted, pero tenemos una lista de entidades de certificación, [asociados de certificado de comunicaciones unificadas](/SkypeForBusiness/certification/services-ssl) , en las que puede ver si la entidad de certificación preferida aparece en la lista.
  
¿Cuándo tendrá que enviar una solicitud a una entidad de certificación para este certificado público y cómo hacerlo? Hay dos formas de hacerlo:
  
- Puede pasar por la instalación de Skype empresarial Server y, a continuación, la implementación del servidor perimetral. El Asistente para la implementación de Skype empresarial Server tendrá un paso para generar una solicitud de certificado, que luego podrá enviar a la entidad de certificación que haya elegido.
    
- También puede usar los comandos de Windows PowerShell para generar esta solicitud, si está más alineada con las necesidades de su negocio o la estrategia de implementación.
    
- Por último, la entidad de certificación puede tener su propio proceso de envío, que también puede implicar a Windows PowerShell u otro método. En ese caso, necesitará confiar en su documentación, además de la información que se proporciona aquí para su referencia.
    
Una vez que haya obtenido el certificado, tendrá que seguir adelante y asignarlo a estos servicios en Skype empresarial Server:
  
- Interfaz del servicio perimetral de acceso
    
- Interfaz del servicio perimetral de conferencia Web
    
- Servicio de autenticación de audio y vídeo (no confunda esto con el servicio perimetral A/V, ya que no usa un certificado para cifrar secuencias de audio y vídeo)
    
> [!IMPORTANT]
> Todos los servidores perimetrales (si pertenecen al mismo grupo de servidores perimetrales) necesitan tener exactamente el mismo certificado con la misma clave privada para el servicio de autenticación de retransmisión de medios. 
  
### <a name="internal-certificates"></a>Certificados internos

Para la interfaz del servidor perimetral interno, puede usar un certificado público de una entidad de certificación pública o un certificado emitido desde la entidad de certificación interna de la organización. Lo que debe recordar sobre el certificado interno es que usa una entrada SN y no hay entradas de SAN, por lo que no tiene que preocuparse por el uso de SAN en el certificado interno.
  
### <a name="required-certificates-table"></a>Tabla de certificados requeridos

Tenemos una tabla para ayudarle con las solicitudes. Las entradas FQDN son solo para dominios de ejemplo. Necesitará realizar solicitudes en función de sus propios dominios públicos y privados, pero esta es una guía de lo que hemos usado:
  
- Contoso <span></span> . com: FQDN público
    
- Fabrikam <span></span> . com: segundo FQDN público (agregado como una demostración de lo que se debe solicitar si tiene varios dominios SIP)
    
- Contoso <span></span> .net: dominio interno
    
#### <a name="edge-certificate-table"></a>Tabla de certificados perimetrales

Independientemente de si está realizando un solo servidor perimetral o un grupo de servidores perimetrales, esto es lo que necesitará para el certificado:
  
|**Componente**|**Nombre del sujeto**|**Nombres alternativos de sujeto (SAN)/Order**|**Notas**|
|:-----|:-----|:-----|:-----|
|Periferia externa  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Este es el certificado que debe solicitar de una entidad de certificación pública. Debe asignarse a las interfaces perimetrales externas para lo siguiente:  <br/> • Servidor perimetral de acceso  <br/> • Servidor perimetral de conferencia Web  <br/> • Autenticación de audio y vídeo  <br/> <br/>La buena noticia es que las redes San se agregan automáticamente a la solicitud del certificado y, por lo tanto, el certificado después de enviar la solicitud, en función de lo que haya definido para esta implementación en el generador de topologías. Solo tendrá que agregar entradas de SAN para los dominios SIP adicionales u otras entradas que necesite admitir. ¿Por qué se replica sip.contoso.com en esta instancia? Esto también ocurre automáticamente y es necesario para que todo funcione correctamente.  <br/><br/> **Nota:** Este certificado también puede usarse para la conectividad de mensajería instantánea pública. No es necesario hacer nada diferente con ella, pero en versiones anteriores de esta documentación se incluyó como una tabla independiente y ahora no lo es. <br/> |
|Perímetro interno  <br/> |sfbedge.contoso.com  <br/> |N/D  <br/> |Puede obtener este certificado de una entidad de certificación pública o interna. Necesitará contener el EKU del servidor (uso mejorado de clave) y lo asignará a la interfaz perimetral interna.  <br/> |
   
Si necesita un certificado para el protocolo extensible de mensajería y presencia (XMPP), tendrá un aspecto idéntico a las entradas de la tabla perimetral externa, pero tendrá las siguientes dos entradas de SAN adicionales:
  
- XMPP. <span></span> Contoso <span></span> . com
    
- \*. contoso <span></span> . com
    
Recuerde que actualmente XMPP solo se admite en Skype empresarial Server para Google Talk, si quiere o necesita usarlo para cualquier otro usuario, debe confirmar dicha funcionalidad con el proveedor de terceros implicado.
  
## <a name="port-and-firewall-planning"></a>Planeación de puertos y firewalls
<a name="PortFirewallPlan"> </a>

Obtener su derecho de planeación para puertos y firewalls para las implementaciones del servidor perimetral de Skype empresarial Server puede ahorrarle días o semanas de solución de problemas y estrés. Como resultado, vamos a enumerar un par de tablas que indicarán nuestro uso del protocolo y los puertos que necesita tener abiertos, entrantes y salientes, tanto para los escenarios de NAT como las IP públicas. También tendremos tablas separadas para los escenarios de equilibrio de carga de hardware (HLB) y otras instrucciones. Para obtener más información al respecto, también tenemos algunos [escenarios de servidores perimetrales en Skype empresarial Server](scenarios.md) que puede consultar para conocer sus preocupaciones específicas sobre la implementación.
  
### <a name="general-protocol-usage"></a>Uso general de protocolos

Antes de ver las tablas de Resumen de los firewalls externos e internos, vamos a considerar la siguiente tabla:
  
|**Transporte de audio y vídeo**|**Usage**|
|:-----|:-----|
|UDP  <br/> |Protocolo de capa de transporte preferido para audio y vídeo.  <br/> |
|TCP  <br/> |El protocolo de la capa de transporte de reserva para audio y vídeo.  <br/> El protocolo de capa de transporte necesario para el uso compartido de aplicaciones en Skype empresarial Server, Lync Server 2013 y Lync Server 2010.  <br/> El protocolo de capa de transporte necesario para la transferencia de archivos a Skype empresarial Server, Lync Server 2013 y Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabla de Resumen de Firewall de puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para los usuarios que usen direcciones IP privadas con NAT, así como personas que usen direcciones IP públicas. Esto abarcará todas las permutaciones en nuestra sección [escenarios de servidores perimetrales en Skype empresarial Server](scenarios.md) .
  
|**Rol o protocolo**|**TCP o UDP**|**Intervalo de puertos o puerto de destino**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> No se admite en Skype empresarial Server 2019 |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso  <br/> |El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas.  <br/> |
|Acceso/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Acceso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Cualquiera  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acceso/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Cualquiera  <br/> |Consulta DNS sobre UDP.  <br/> |
|Acceso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Para la conectividad de mensajería instantánea pública y federada con SIP.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Cualquiera  <br/> |Para la conectividad de mensajería instantánea pública y federada con SIP.  <br/> |
|Conferencia web/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral de conferencia web del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de conferencia web del servidor perimetral <br/> |Medios de conferencia Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privada mediante NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Cualquiera  <br/> |Se usa para retransmitir el tráfico de medios.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privada mediante NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Cualquiera  <br/> |Se usa para retransmitir el tráfico de medios.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privada mediante NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Cualquiera  <br/> |3478 saliente es:  <br/> • Usado por Skype empresarial Server para determinar la versión del servidor perimetral con el que se comunica.  <br/> • Se usa para el tráfico de medios entre los servidores perimetrales.  <br/> • Necesario para la Federación con Lync Server 2010.  <br/> • Es necesario si hay varios grupos de servidores perimetrales implementados en la organización.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |STUN/TURN negociación de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |STUN/TURN negociación de candidatos sobre TCP en el puerto 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privada mediante NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |Cualquiera  <br/> |STUN/TURN negociación de candidatos sobre TCP en el puerto 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabla de Resumen de Firewall de puerto interno

|**Protocolo**|**TCP o UDP**|**Port**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de las siguientes opciones ejecutan el servicio de puerta de enlace XMPP:  <br/> • Servidor front-end  <br/> • Grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o el grupo de servidores front-end.  <br/> **Nota:** Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019. Consulte [migrar la Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Todas  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor front-end  <br/> • Grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico SIP saliente de su director, grupo de directores, servidor front-end o grupo de servidores front-end a la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interfaz interna del servidor perimetral  <br/> |Todas  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor front-end  <br/> • Grupo de servidores front-end  <br/> |Tráfico SIP entrante a su director, grupo de directores, servidor front-end o grupo de servidores front-end desde la interfaz interna del servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Todas  <br/> • Servidor front-end  <br/> • Cada servidor front-end  <br/>  en el grupo de servidores front-end <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico de conferencias web desde el servidor front-end o cada servidor front-end (si tiene un grupo de servidores front-end) a la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Todas  <br/> • Servidor front-end  <br/> • Grupo de servidores front-end  <br/> • Cualquier aplicación de sucursal con funciones de supervivencia que use este servidor perimetral  <br/> • Cualquier servidor de sucursal con funciones de supervivencia que use este servidor perimetral  <br/> |Interfaz interna del servidor perimetral  <br/> |Autenticación de usuarios de A/V desde el servidor front-end o el grupo de servidores front-end, o bien su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, mediante el servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso preferida para la transferencia de medios de A/V entre los usuarios internos y externos y la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso de reserva para la transferencia de medios de A/V entre los usuarios internos y externos y la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia, si la comunicación UDP no funciona. A continuación, se usa TCP para las transferencias de archivos y el uso compartido del escritorio.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Todas  <br/> • Servidor front-end que retiene el almacén de administración central  <br/> • Grupo de servidores front-end que contiene el almacén de administración central  <br/> |Interfaz interna del servidor perimetral  <br/> |Replicación de los cambios desde el almacén de administración central en el servidor perimetral.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Skype empresarial Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe).  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Skype empresarial Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe).  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Skype empresarial Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe).  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Equilibradores de carga de hardware para tablas de puertos perimetrales

Proporcionamos a los equilibradores de carga de hardware (HLB) y a los puertos perimetrales su propia sección, ya que las cosas son un poco más complicadas con el hardware adicional. Consulte las tablas siguientes para obtener información sobre este escenario en particular:
  
#### <a name="external-port-firewall-summary-table"></a>Tabla de Resumen de Firewall de puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para los usuarios que usen direcciones IP privadas con NAT, así como personas que usen direcciones IP públicas. Esto abarcará todas las permutaciones en nuestra sección [escenarios de servidores perimetrales en Skype empresarial Server](scenarios.md) .
  
|**Rol o protocolo**|**TCP o UDP**|**Intervalo de puertos o puerto de destino**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acceso/HTTP  <br/> |TCP  <br/> |80  <br/> |Dirección IP pública del servicio perimetral de acceso del servidor perimetral  <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Acceso/DNS  <br/> |TCP  <br/> |53  <br/> |Dirección IP pública del servicio perimetral de acceso del servidor perimetral  <br/> |Cualquiera  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acceso/DNS  <br/> |UDP  <br/> |53  <br/> |Dirección IP pública del servicio perimetral de acceso del servidor perimetral  <br/> |Cualquiera  <br/> |Consulta DNS sobre UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Dirección IP del servicio perimetral del servidor perimetral A/V  <br/> |Cualquiera  <br/> |Se usa para retransmitir el tráfico de medios.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |Cualquiera  <br/> |Se usa para retransmitir el tráfico de medios.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |Cualquiera  <br/> |3478 saliente es:  <br/> • Usado por Skype empresarial Server para determinar la versión del servidor perimetral con el que se comunica.  <br/> • Se usa para el tráfico de medios entre los servidores perimetrales.  <br/> • Necesario para la Federación.  <br/> • Es necesario si hay varios grupos de servidores perimetrales implementados en la organización.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |STUN/TURN negociación de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |STUN/TURN negociación de candidatos sobre TCP en el puerto 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Dirección IP pública del servicio perimetral A/V del servidor perimetral  <br/> |Cualquiera  <br/> |STUN/TURN negociación de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabla de Resumen de Firewall de puerto interno

|**Protocolo**|**TCP o UDP**|**Port**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de las siguientes opciones ejecutan el servicio de puerta de enlace XMPP:  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end que ejecuta el servicio de puerta de enlace XMPP  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico XMPP saliente desde el servicio de puerta de enlace XMPP que se ejecuta en el servidor front-end o el grupo de servidores front-end.  <br/><br/> **Nota:** Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019. Consulte [migrar la Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información. |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Todas  <br/> • Servidor front-end que retiene el almacén de administración central  <br/> • Grupo de servidores front-end que contiene el almacén de administración central  <br/> |Interfaz interna del servidor perimetral  <br/> |Replicación de los cambios desde el almacén de administración central en el servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Todas  <br/> • Servidor front-end  <br/> • Cada servidor front-end de su grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico de conferencias web desde el servidor front-end o cada servidor front-end (si tiene un grupo de servidores front-end) a la interfaz interna del servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Todas  <br/> • Servidor front-end  <br/> • Cada servidor front-end de su grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso preferida para la transferencia de medios de A/V entre los usuarios internos y externos y la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Todas  <br/> • Servidor front-end  <br/> • Cada servidor front-end de su grupo de servidores  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso de reserva para la transferencia de medios de A/V entre los usuarios internos y externos y la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia, si la comunicación UDP no funciona. A continuación, se usa TCP para las transferencias de archivos y el uso compartido del escritorio.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Skype empresarial Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe).  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Skype empresarial Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe).  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador del servicio de registro centralizado con los cmdlets del shell de administración de Skype empresarial Server y el servicio de registro centralizado, la línea de comandos de ClsController (ClsController. exe) o los comandos y la colección de registros del agente (ClsAgent. exe).  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IP virtuales de la interfaz externa

|**Rol o protocolo**|**TCP o UDP**|**Intervalo de puertos o puerto de destino**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> No es compatible con Skype empresarial Server 2019 |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso)  <br/> |El servicio Proxy XMPP acepta el tráfico de los contactos XMPP en las federaciones XMPP definidas.  <br/> |
|XMPP  <br/>No es compatible con Skype empresarial Server 2019 |TCP  <br/> |5269  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio perimetral de acceso)  <br/> |Cualquiera  <br/> |El servicio Proxy XMPP envía tráfico desde los contactos XMPP en las federaciones XMPP definidas.  <br/> |
|Acceso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Para la conectividad de mensajería instantánea pública y federada con SIP.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privada mediante NAT:** Servicio perimetral de acceso del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de acceso del servidor perimetral <br/> |Cualquiera  <br/> |Para la conectividad de mensajería instantánea pública y federada con SIP.  <br/> |
|Conferencia web/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral de conferencia web del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral de conferencia web del servidor perimetral <br/> |Medios de conferencia Web.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |STUN/TURN negociación de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privada mediante NAT:** Servicio perimetral A/V del servidor perimetral <br/> **IP pública:** Dirección IP pública del servicio perimetral A/V del servidor perimetral <br/> |STUN/TURN negociación de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IP virtuales de la interfaz interna

Nuestra orientación aquí será un poco diferente. En realidad, en una situación HLB, ahora le recomendamos que solo tenga enrutamiento a través de una VIP interna en las siguientes circunstancias:
  
- Si usa la mensajería unificada (UM) de Exchange 2007 o Exchange 2010.
    
- Si tiene clientes heredados que usan el servidor perimetral.
    
En la tabla siguiente se proporcionan instrucciones para estos escenarios, pero, en caso contrario, debe poder depender del almacén de administración central (CMS) para enrutar el tráfico al servidor perimetral individual que tiene constancia (esto requiere que se mantenga la actualización de CMS actualizada en la información del servidor perimetral, por supuesto).
  
|**Protocolo**|**TCP o UDP**|**Port**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Todas  <br/> • Director  <br/> • Dirección VIP del grupo de servidores Director  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico SIP saliente del Director, la dirección VIP del grupo de directores, el servidor front-end o la dirección VIP del grupo de servidores front-end a la interfaz interna del servidor perimetral.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interfaz VIP interna del servidor perimetral  <br/> |Todas  <br/> • Director  <br/> • Dirección VIP del grupo de servidores Director  <br/> • Servidor front-end  <br/> • Dirección VIP del grupo de servidores front-end  <br/> |Tráfico SIP entrante a su director, dirección VIP del grupo de directores, servidor front-end o dirección VIP del grupo de servidores front-end de la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Todas  <br/> • Dirección IP del servidor front-end  <br/> • Dirección IP del grupo de servidores front-end  <br/> • Cualquier aplicación de sucursal con funciones de supervivencia que use este servidor perimetral  <br/> • Cualquier servidor de sucursal con funciones de supervivencia que use este servidor perimetral  <br/> |Interfaz interna del servidor perimetral  <br/> |Autenticación de usuarios de A/V desde el servidor front-end o el grupo de servidores front-end, o bien su aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, mediante el servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de acceso preferida para la transferencia de medios de A/V entre los usuarios internos y externos.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Interfaz VIP interna del servidor perimetral  <br/> |Ruta de acceso de reserva para la transferencia de medios de A/V entre los usuarios internos y externos si la comunicación UDP no funciona. A continuación, se usa TCP para las transferencias de archivos y el uso compartido del escritorio.  <br/> |
