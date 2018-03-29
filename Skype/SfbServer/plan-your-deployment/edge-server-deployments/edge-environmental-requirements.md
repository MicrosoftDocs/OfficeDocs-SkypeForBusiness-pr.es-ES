---
title: Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Summary: Learn about the environmental requirements for Edge Server in Skype for Business Server 2015.'
ms.openlocfilehash: fd3c7d6c5fe138878b0122ea5c1885ad6ef84171
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server-2015"></a>Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015
 
**Summary:** Learn about the environmental requirements for Edge Server in Skype for Business Server 2015.
  
A lot of planning and preparation needs to take place outside of the Skype for Business Server 2015 Edge Server environment itself. En este artículo, repasaremos qué preparativos tiene que realizar en el entorno de la organización, según la lista que se muestra abajo:
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planificar la topología
<a name="TopoPlan"> </a>

Skype for Business Server 2015 Edge Server topologies are able to use:
  
- Direcciones IP públicas enrutables.
    
- Direcciones IP privadas no enrutables si se usa la traducción de direcciones de red (NAT) **simétrica**.
    
> [!TIP]
> Your Edge Server can be configured to use a single IP address with distinct ports for each service, or it can use distinct IP addresses for each service, but use the same default port (which by default will be TCP 443). Hay más información en la sección de requisitos de las direcciones IP de abajo. 
  
Si elige direcciones IP privadas no enrutables con NAT, recuerde los siguientes puntos:
  
- Tiene que usar direcciones IP privadas enrutables en las **tres** interfaces externas.
    
- Tiene que configurar la NAT **simétrica** para el tráfico entrante y saliente. Symmetric NAT is the only supported NAT you can use with Skype for Business Server 2015 Edge Server.
    
- Configure la NAT para que no cambie las direcciones de origen entrantes. The A/V Edge service needs to be able to receive the incoming source address to find the optimal media path.
    
- Your Edge Servers need to be able to communicate with one another from their public A/V Edge IP addresses. El firewall tiene que permitir este tráfico.
    
- NAT can **only** be used for scaled consolidated Edge Servers if you use DNS load balancing. Si usa el equilibrio de carga de hardware (HLB), tiene que usar direcciones IP enrutables públicamente **sin** NAT.
    
You'll have no problems having your Access, Web conferencing and A/V Edge interfaces behind a router or firewall performing symmetric NAT for both single and scaled consolidated Edge Server topologies (as long as you're not using hardware load balancing).
  
### <a name="summary-of-edge-server-topology-options"></a>Summary of Edge Server topology options

We have several topology options available for Skype for Business Server 2015 Edge Server deployments:
  
- Servidor perimetral consolidado simple con direcciones IP privadas y NAT
    
- Servidor perimetral consolidado simple con direcciones IP públicas
    
- Servidor perimetral consolidado ampliado con direcciones IP privadas y NAT
    
- Servidor perimetral consolidado ampliado con direcciones IP públicas
    
- Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
    
Para que le sea más fácil elegir una, la siguiente tabla le ofrece un resumen de las opciones de cada topología:
  
|**Topología**|**High availability**|**Additional DNS records required for external Edge Server in the Edge pool?**|**Edge failover for Skype for Business Server sessions**|**Edge failover for Skype for Business Server federation sessions**|
|:-----|:-----|:-----|:-----|:-----|
|Servidor perimetral consolidado simple con direcciones IP privadas y NAT  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Servidor perimetral consolidado simple con direcciones IP públicas  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Servidor perimetral consolidado ampliado con direcciones IP privadas y NAT (con equilibrio de carga DNS)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Yes&sup1;  <br/> |
|Servidor perimetral consolidado ampliado con direcciones IP públicas (con equilibrio de carga DNS)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Yes&sup1;  <br/> |
|Servidor perimetral consolidado ampliado con equilibradores de carga de hardware  <br/> |Sí  <br/> |No (un registro A DNS por VIP)  <br/> |Sí  <br/> |Sí  <br/> |
   
&sup1; Exchange Unified Messaging (UM) remote user failover using DNS load balancing requires Exchange 2013 or newer.
  
### <a name="ip-address-requirements"></a>Requisitos de direcciones IP

On a fundamental level, three services need IP addresses; Access Edge service, Web Conferencing Edge service, and A/V Edge service. Tiene la opción de usar tres direcciones IP, una para cada uno de los servicios, o puede usar uno y optar por poner cada servicio en un puerto diferente (puede comprobar la sección [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto). Para un entorno de servidor perimetral consolidado simple, es prácticamente todo.
  
> [!NOTE]
> Como se indica anteriormente, puede optar por tener una dirección IP para los tres servicios y ejecutarlos en diferentes puertos. Para ser claros, no lo recomendamos. Si sus clientes no pueden tener acceso a los puertos alternativos que usa en este escenario, tampoco pueden obtener acceso a la característica completa de su entorno perimetral. 
  
Puede ser un poco más complicado con topologías consolidadas ampliadas, por lo que vamos a ver algunas tablas que organizan los requisitos de direcciones IP, teniendo en cuenta que los aspectos principales a la hora de decantarse por una topología son la alta disponibilidad y el equilibrio de carga. Las necesidades de la alta disponibilidad pueden influir en la opción del equilibrio de carga (hablaremos de ello después de las tablas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de dirección IP para servidor perimetral consolidado ampliado (dirección IP por rol)

|**Number of Edge Servers per pool**|**Number of required IP addresses for DNS load balancing**|**Number of required IP addresses for hardware load balancing**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 por VIP) + 6  <br/> |
|3  <br/> |9  <br/> |3 (1 por VIP) + 9  <br/> |
|4  <br/> |12  <br/> |3 (1 por VIP) + 12  <br/> |
|5  <br/> |15  <br/> |3 (1 por VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de dirección IP para servidor perimetral consolidado ampliado (dirección IP única para todos los roles)

|**Number of Edge Servers per pool**|**Number of required IP addresses for DNS load balancing**|**Number of required IP addresses for hardware load balancing**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 por VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 por VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 por VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 por VIP) + 5  <br/> |
   
Veamos algunos asuntos adicionales en los que pensar durante la planeación.
  
- **High availability**: If you need high availability in your deployment, you should deploy at least two Edge Servers in a pool. It's worth noting that a single Edge pool will support up to 12 Edge Servers (though Topology Builder will allow you to add up to 20, that's not tested or supported, so we advise you don't do that). If you need more than 12 Edge Servers, you should create additional Edge pools for them.
    
- **Hardware load balancing**: We recommend DNS load balancing for most scenarios. Hardware load balancing is also supported, of course, but notably it's required for a single scenario over DNS load balancing:
    
  - External access to Exchange 2007 or Exchange 2010 (with no SP) Unified Messaging (UM).
    
- **DNS load balancing**: For UM, Exchange 2010 SP1 and newer are able to be supported by DNS load balancing. Note that if you need to go with DNS load balancing for an earlier version of Exchange, it'll work, but all the traffic for this will go to the first server in the pool, and if it's not available, that traffic will subsequently fail.
    
    DNS load balancing is also recommended if you're federating with companies using Lync Server 2010, Lync Server 2013, and Microsoft Office 365.
    
## <a name="dns-planning"></a>Planificación de DNS
<a name="DNSPlan"> </a>

When it comes to Skype for Business Server 2015 Edge Server deployment, it's vital to prepare for DNS properly. Con los registros correctos en su ubicación, la implementación será mucho más sencilla. Afortunadamente ha elegido una topología en la sección anterior, ya que realizaremos una descripción general y después enumeraremos algunas tablas que esquematicen los registros DNS para esos escenarios. We'll also have some [Advanced Edge Server DNS planning for Skype for Business Server 2015](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) for more in-depth reading, if you need it.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS records for Single consolidated Edge Server scenarios

These will be the DNS records you're going to need for a singe Edge Server using either public IPs or private IPs with NAT. Dado que estos son datos de ejemplo, le daremos IP de muestra para que pueda resolver sus propias entradas de forma más fácil:
  
- Adaptador de red interna: 172.25.33.10 (no hay ninguna puerta de enlace predeterminada asignada)
    
    > [!NOTE]
    > Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Skype for Business Server 2015 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0). 
  
- Adaptador de red externa:
    
  - IP públicas:
    
  - Access Edge: 131.107.155.10 (this is the primary, with default gateway set to your public router, ex: 131.107.155.1)
    
  - Web Conferencing Edge: 131.107.155.20 (secondary)
    
  - A/V Edge: 131.107.155.30 (secondary)
    
  Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
    
  - IP privadas:
    
  - Access Edge: 10.45.16.10 (this is the primary, with default gateway set to your router, ex: 10.45.16.1)
    
  - Web Conferencing Edge: 10.45.16.20 (secondary)
    
  - A/V Edge: 10.45.16.30 (secondary)
    
Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
  
> [!TIP]
>Hay otra configuración posible:
  
- Puede usar una dirección IP en el adaptador de red externa. We don't recommend this because then you're going to need to differentiate between the thee services using different ports (which you can do in Skype for Business Server) but there are some firewalls that may block the alternate ports. Vea la sección de [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto.
    
- Puede tener tres adaptadores de red externa en lugar de uno y asignar una de las IP del servicio a cada uno. ¿Por qué? Se separarían los servicios y si algo va mal, facilitaría solucionar los problemas y dejar que otros servicios continuasen trabajando potencialmente mientras resuelve un problema.
    
|**Ubicación**|**Type**|**Puerto**|**Registro DNS o el nombre de dominio completo**|**Dirección IP o FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 <br/> **private:** 10.45.16.10 <br/> |An external interface for your Access Edge service. You'll need one for every SIP domain with Skype for Business users.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |Webcon.contoso.com  <br/> |**pública:** 131.107.155.20 <br/> **privado:** 10.45.16.20 <br/> |Una interfaz externa para el servicio perimetral de conferencia Web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |AV.contoso.com  <br/> |**pública:** 131.107.155.30 <br/> **private:** 10.45.16.30 <br/> |An external interface for your A/V Edge service.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |An external interface for your Access Edge service. This SRV record is required for Skype for Business Server 2015, Lync Server 2013, and Lync Server 2010 clients to work externally. You'll need one for every domain with Skype for Business users.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |An external interface for your Access Edge service. Este registro SRV es necesario para la detección DNS automática de asociados federados denominada Dominios SIP permitidos. You'll need one for every domain with Skype for Business users.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |La interfaz interna para el servidor perimetral consolidado.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>DNS records for Scaled DNS and hardware Edge Server scenarios

These will be the DNS records you're going to need for a singe Edge Server using either public IPs or private IPs with NAT. Dado que estos son datos de ejemplo, le daremos IP de muestra para que pueda resolver sus propias entradas de forma más fácil:
  
- Adaptador de red interna:
    
  - Nodo 1: 172.25.33.10 (no hay ninguna puerta de enlace predeterminada asignada)
    
  - Nodo 2: 172.25.33.11 (no hay ninguna puerta de enlace predeterminada asignada)
    
    > [!NOTE]
    > Asegúrese de que hay una ruta de la red que contiene la interfaz interna del borde a todas las redes que contienen servidores que ejecutan Skype para clientes Business Server 2015 o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de red externa:
    
  - Nodo 1
    
     - IP públicas:
    
        - Servidor perimetral de acceso: 131.107.155.10 (éste es el principal, con puerta de enlace predeterminada establecida al router pública, ex: 131.107.155.1)
    
        - Web Conferencing Edge: 131.107.155.20 (secondary)
    
        - A/V Edge: 131.107.155.30 (secondary)
    
          Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
    
    - IP privadas:
    
         - Access Edge: 10.45.16.10 (this is the primary, with default gateway set to your router, ex: 10.45.16.1)
    
         - Web Conferencing Edge: 10.45.16.20 (secondary)
    
         - A/V Edge: 10.45.16.30 (secondary)
    
      Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
    
  - Nodo 2
    
     - IP públicas:
    
       - Access Edge: 131.107.155.11 (this is the primary, with default gateway set to your public router, ex: 131.107.155.1)
    
       - Web Conferencing Edge: 131.107.155.21 (secondary)
    
       - A / V borde: 131.107.155.31 (secundario)
    
      Web conferencias y A las direcciones IP públicas borde V son las direcciones IP adicionales (secundarias) en la sección avanzada de las propiedades del protocolo de Internet versión 4 (TCP/IPv4) y protocolo de Internet versión 6 (TCP/IPv6) de las propiedades de conexión de área Local en Windows Server.
    
  - IP privadas:
    
      - Servidor perimetral de acceso: 10.45.16.11 (éste es el principal, con puerta de enlace predeterminada establecida en el enrutador, ex: 10.45.16.1)
    
      - Borde de conferencias Web: 10.45.16.21 (secundario)
    
      - A / V borde: 10.45.16.31 (secundario)
    
      Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
    
Hay otra configuración posible:
  
- Puede usar una dirección IP en el adaptador de red externa. We don't recommend this because then you're going to need to differentiate between the thee services using different ports (which you can do in Skype for Business Server) but there are some firewalls that may block the alternate ports. Vea la sección de [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para más información sobre esto.
    
- Puede tener tres adaptadores de red externa en lugar de uno y asignar una de las IP del servicio a cada uno. ¿Por qué? Se separarían los servicios y si algo va mal, facilitaría solucionar los problemas y dejar que otros servicios continuasen trabajando potencialmente mientras resuelve un problema.
    
|**Ubicación**|**Tipo**|**Puerto**|**Registro DNS o el nombre de dominio completo**|**Dirección IP o FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |SIP.contoso.com  <br/> |**público:** 131.107.155.10 y 131.107.155.11 <br/> **privado:** 10.45.16.10 y 10.45.16.11 <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Necesitará una para cada dominio SIP con Skype para usuarios de negocios.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |Webcon.contoso.com  <br/> |**público:** 131.107.155.20 y 131.107.155.21 <br/> **privado:** 10.45.16.20 y 10.45.16.21 <br/> |Una interfaz externa para el servicio perimetral de conferencia Web.  <br/> |
|DNS externo  <br/> |Un registro  <br/> |NA  <br/> |AV.contoso.com  <br/> |**público:** 131.107.155.30 y 131.107.155.31 <br/> **privado:** 10.45.16.30 y 10.45.16.31 <br/> |Una interfaz externa para su / servicio V perimetral.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |SIP.contoso.com  <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Este registro SRV es necesaria para Skype para clientes de Lync Server 2010, Lync Server 2013 y Business Server 2015 para que trabaje externamente. Necesitará una para cada dominio con Skype para negocios.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |Una interfaz externa para el servicio de servidor perimetral de acceso. Este registro SRV es necesario para la detección DNS automática de asociados federados denominada Dominios SIP permitidos. Necesitará una para cada dominio con Skype para negocios.  <br/> |
|DNS interno  <br/> |Un registro  <br/> |NA  <br/> |sfvedge.contoso.NET  <br/> |172.25.33.10 y 172.25.33.11  <br/> |La interfaz interna para el servidor perimetral consolidado.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para la federación (todos los escenarios)

|**Ubicación**|**Tipo**|**Puerto**|**FQDN**|**Registro de host FQDN**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |SIP.contoso.com  <br/> |La interfaz externa de SIP servidor perimetral de acceso necesaria para la detección automática de DNS. Usada por otros posibles asociados de federación. También se conoce como "Permitir dominios SIP". Necesitará uno de éstos para cada dominio SIP con Skype para usuarios de negocios.  <br/><br/> **Nota:** Necesitará este registro SRV para la movilidad y la notificación de inserción centro de enrutamiento. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Registros DNS para el protocolo extensible de mensajería y presencia

|**Ubicación**|**Tipo**|**Puerto**|**FQDN**|**Dirección IP o FQDN registro de host**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |XMPP.contoso.com  <br/> |La interfaz de proxy XMPP en el servicio de servidor perimetral de acceso o la piscina de borde. Debe repetir este proceso según sea necesario para todos los dominios SIP internos con Skype habilitado para usuarios de empresas, donde se permite el contacto con contactos XMPP a través de:  <br/> • una directiva global  <br/> • una directiva de sitio donde el usuario del habilitado  <br/> usuario habilitado para • usuario aplicada una directiva a la Skype para empresas  <br/> Una directiva XMPP permitida también se tiene que configurar en la directiva de usuarios federados XMPP.  <br/> |
|DNS externo  <br/> |SRV  <br/> |A  <br/> |XMPP.contoso.com  <br/> |Dirección IP del servicio de servidor perimetral de acceso en el servidor perimetral o la piscina de borde que aloja el servicio de servidor Proxy XMPP  <br/> |Esto señala el servicio de servidor perimetral de acceso en el servidor perimetral o un grupo de servidores de borde que aloja el servicio Proxy XMPP. Por lo general, el registro SRV que crea apuntará a este registro de host (A o AAAA).  <br/> |
   
## <a name="certificate-planning"></a>Planificar certificado
<a name="CertPlan"> </a>

Skype para Business Server 2015 utiliza certificados para la comunicación cifrada segura entre los servidores y del servidor al cliente. Como cabría esperar, los certificados tendrán que tener registros DNS para sus servidores para que coincidan con cualquier nombre de sujeto (SN) y nombre alternativo de sujeto (SAN) en los certificados. Esto le llevará trabajo ahora, en la fase de planificación, para garantizar que tiene los FQDN correctos registrados en DNS para las entradas de SN y de SAN para los certificados.
  
Hablaremos de las necesidades de los certificados internos y externos por separado y después veremos una tabla que proporciona los requisitos para ambos.
  
### <a name="external-certificates"></a>Certificados externos

Como mínimo, el certificado asignado a las interfaces del servidor perimetral externas deberá ser proporcionada por una autoridad de certificación (CA) pública. No podemos recomendar una CA específica para usted, pero tenemos una lista de entidades emisoras de certificados de [socios de certificados de comunicaciones unificadas](https://support.microsoft.com/en-us/kb/929395) que puede echar un vistazo a para ver si aparece su CA preferido.
  
¿Cuándo tendrá que enviar una solicitud a una entidad de certificación para este certificado público y cómo lo tiene que hacer? Hay un par de formas de llevar esto a cabo:
  
- Puede ir a través de la instalación de Skype para Business Server y, a continuación, la implementación de servidor perimetral. El Skype para el Asistente para implementación de Business Server tendrá un paso para generar una solicitud de certificado, que puede enviar a la entidad emisora de certificados seleccionada.
    
- También puede utilizar los comandos de Windows PowerShell para generar esta solicitud, si es más en línea con sus necesidades de negocio o estrategia de implementación.
    
- Por último, la entidad emisora de certificados puede tener su propio proceso de envío, que también puede implicar Windows PowerShell o cualquier otro método. En ese caso, tendrá que basarse en su documentación, además de en la información proporcionada aquí para su consulta.
    
Una vez que ha llegado el certificado, deberá continuar y asignar a estos servicios en Skype para Business Server:
  
- Acceso a la interfaz de servicio de bordes
    
- Interfaz del servicio perimetral de conferencia Web
    
- Servicio de autenticación de audio/vídeo (no confunda con el A / servicio de borde V, que no utiliza un certificado para cifrar las transmisiones de audio o vídeo)
    
> [!IMPORTANT]
> Todos los servidores perimetrales tienen que tener exactamente el mismo certificado con la misma clave privada para el servicio de autenticación relé multimedia. 
  
### <a name="internal-certificates"></a>Certificados internos

Para la interfaz interna del servidor perimetral, puede utilizar un certificado de una CA pública pública o un certificado emitido por la entidad emisora de certificados interna de su organización. Lo que hay que recordar sobre el certificado interno es que usa una entrada de SN y no entradas de SAN, de modo que no tiene que preocuparse por SAN en el certificado interno en absoluto.
  
### <a name="required-certificates-table"></a>Tabla de certificados necesarios

Aquí tenemos una tabla para ayudarle con las solicitudes. Las entradas de FQDN son solo para dominios de ejemplo. Tendrá que realizar solicitudes en función de sus propios dominios privados y públicos, pero esta es una guía sobre lo que hemos usado:
  
- contoso.com: FQDN público
    
- fabrikam.com: segundo FQDN público (agregado como una demo de lo que tiene que solicitar si tiene varios dominios SIP)
    
- Contoso.net: dominio interno
    
#### <a name="edge-certificate-table"></a>Tabla de certificado perimetral

Independientemente de si está haciendo un solo servidor perimetral o un grupo de servidores de borde, esto es lo que necesita para el certificado:
  
|**Componente**|**Nombre del sujeto (SN)**|**Nombres alternativos (SAN) de asunto / orden**|**Notas**|
|:-----|:-----|:-----|:-----|
|Servidor perimetral externo  <br/> |SIP.contoso.com  <br/> |SIP.contoso.com  <br/> Webcon.contoso.com  <br/> SIP.fabrikam.com  <br/> |Este es el certificado que tiene que solicitar a una entidad de certificación pública. Tendrá que estar asignado a las interfaces perimetrales externas para lo siguiente:<br/> • Servidor perimetral de acceso  <br/> Borde de conferencias web •  <br/> • Autenticación de audio y vídeo  <br/> <br/>La buena noticia es que SANs se agregan automáticamente a la solicitud de certificado y, por tanto, el certificado después de enviar la solicitud, basándose en lo que se ha definido para esta implementación de generador de topología. Solo tiene que agregar las entradas de SAN para cualquier dominio SIP adicional u otras entradas que necesite admitir. ¿Por qué sip.contoso.com aparece duplicado en esta instancia? Esto se produce automáticamente y es necesario para que todo funcione correctamente.  <br/><br/> **Nota:** Este certificado puede utilizarse también para la conectividad de mensajería instantánea pública. No tiene que hacer nada diferente con él, pero en versiones anteriores de esta documentación, se ha incluido como una tabla independiente, y ahora no lo es. <br/> |
|Servidor perimetral interno  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Puede obtener este certificado de una entidad de certificación pública o de una entidad de certificación interna. Tendrá que contener el EKU del servidor (uso mejorado de clave) y lo asignará a la interfaz interna del servidor perimetral.  <br/> |
   
Si necesita un certificado para el protocolo extensible de mensajería y presencia (XMPP), tendrá un aspecto idéntico a las entradas del servidor perimetral externo de la tabla anterior, pero tendrá las siguientes dos entradas SAN adicionales:
  
- XMPP.contoso.com
    
- \*. contoso.com
    
Recuerde que actualmente XMPP solo es compatible con Google Talk, si lo desea o necesita usarlo para cualquier otra cosa, necesita confirmar esa característica con el proveedor involucrado.
  
## <a name="port-and-firewall-planning"></a>Planificación de puerto y de firewall
<a name="PortFirewallPlan"> </a>

Obteniendo su planificación adecuada para puertos y servidores de seguridad para Skype para Business Server Edge Server implementaciones pueden ahorrar días o semanas de solución de problemas y estrés. Como resultado, enumeraremos un par de tablas que indicarán nuestro uso de protocolo y qué puertos necesita tener abiertos, entrantes y salientes, tanto para los escenarios de NAT y de IP pública. También le mostraremos tablas separadas para escenarios con equilibrio de carga de hardware (HLB) y alguna ayuda a mayores de esto. Para leer más desde allí, también tenemos [diagramas técnicos de Skype para Business Server 2015](../../technical-diagrams.md), así como algunos [escenarios de servidor perimetral de Skype para Business Server 2015](scenarios.md) puede desproteger para sus preocupaciones de implementación particular.
  
### <a name="general-protocol-usage"></a>Uso general de protocolo

Antes de ver las tablas de resumen para los firewall internos y externos, veamos la siguiente tabla:
  
|**Transporte de audio y vídeo**|**Uso**|
|:-----|:-----|
|UDP  <br/> |El protocolo de capa de transporte preferido para audio y vídeo.  <br/> |
|TCP  <br/> |El protocolo de capa de transporte de reserva para audio y vídeo.  <br/> El protocolo de capa de transporte requeridos para aplicación compartida a Skype para Business Server 2015, Lync Server 2013 y Lync Server 2010.  <br/> El protocolo de capa de transporte requeridos para la transferencia de archivos a Skype para Business Server 2015, Lync Server 2013 y Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para usuarios que estén usando direcciones IP privadas con NAT, así como las personas que usen direcciones IP públicas. Esto cubrirá todas las permutaciones en nuestra sección de [escenarios de servidor perimetral de Skype para Business Server 2015](scenarios.md) .
  
|**Función o protocolo**|**TCP o UDP**|**Intervalo de puerto de destino o puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio de servidor perimetral de acceso  <br/> |El servicio Proxy XMPP acepta tráfico de contactos XMPP en federaciones de XMPP definidas.  <br/> |
|Acceso/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso perimetral <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Acceso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso perimetral <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Cualquiera  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acceso/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso perimetral <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Cualquiera  <br/> |Consulta DNS sobre UDP.  <br/> |
|Acceso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso perimetral <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso perimetral <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso perimetral <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Cualquiera  <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Conferencia web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servicio perimetral de conferencia Web Server perimetral <br/> **IP pública:** Dirección IP pública de borde perimetral de conferencia Web Server servicio servicio <br/> |Medios de conferencias Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privadas mediante NAT:** Servidor de borde / Edge V servicio <br/> **IP pública:** Servidor de borde / Edge V servicio dirección IP pública <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privadas mediante NAT:** Servidor de borde / Edge V servicio <br/> **IP pública:** Servidor de borde / Edge V servicio dirección IP pública <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privadas mediante NAT:** Servidor de borde / servicio perimetral V <br/> **IP pública:** Servidor de borde / Edge V servicio dirección IP pública <br/> |Cualquiera  <br/> |3478 saliente:  <br/> • Utilizada Skype para Business Server para determinar la versión de servidor perimetral se está comunicando.  <br/> • Utilizado para el tráfico de medios entre servidores perimetrales.  <br/> • Se requiere para la federación con Lync Server 2010.  <br/> • Es necesario si se implementan varios grupos de borde dentro de su organización.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servidor de borde / servicio perimetral V <br/> **IP pública:** Servidor de borde / Edge V servicio dirección IP pública <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servidor de borde / servicio perimetral V <br/> **IP pública:** Servidor de borde / Edge V servicio dirección IP pública <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privadas mediante NAT:** Servidor de borde / servicio perimetral V <br/> **IP pública:** Servidor de borde / Edge V servicio dirección IP pública <br/> |Cualquiera  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto interno

|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de los siguientes que ejecutan el servicio de puerta de enlace XMPP:  <br/> • Servidor de Front-End  <br/> • Grupo de Front-End  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico saliente de XMPP desde el servicio de puerta de enlace de XMPP ejecutando en su servidor Front-End o Front-End de grupo de servidores.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Cualquier:  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor de Front-End  <br/> • Grupo de Front-End  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico SIP saliente desde el Director, el grupo de directores, grupo de servidor Front-End o Front-End para la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interfaz interna del servidor perimetral  <br/> |Cualquier:  <br/> • Director  <br/> • Grupo de directores  <br/> • Servidor de Front-End  <br/> • Grupo de Front-End  <br/> |El tráfico SIP a su grupo grupo Director, Director, servidor Front-End o Front-End de la interfaz interna del servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Cada servidor Front-End  <br/>  en el grupo de servidores Front-End <br/> |Interfaz interna del servidor perimetral  <br/> |Conferencia el tráfico Web desde su servidor Front-End o en cada servidor Front-End (si tiene un grupo de servidores Front-End) para la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Grupo de Front-End  <br/> • Cualquier dispositivo de sucursal que sobreviven utilizando este servidor perimetral  <br/> • Cualquier servidor de sucursal que sobreviven mediante este servidor perimetral  <br/> |Interfaz interna del servidor perimetral  <br/> |Autenticación de A / usuarios V de su grupo de servidor Front-End o Front-End, o el dispositivo de sucursal que sobreviven o servidor de sucursal que sobreviven, usando el servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Recomendado: ruta de acceso A medios de V transferencia entre los usuarios internos y externos y su dispositivo de sucursal que sobreviven o servidor de la sucursal que sobreviven.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de reserva para una transferencia de medios V entre los usuarios internos y externos y su dispositivo de sucursal que sobreviven o servidor de sucursal que sobreviven, si no funciona la comunicación UDP. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Cualquier:  <br/> • Servidor Front-End que contiene el almacén de Administración Central  <br/> • Grupo de Front-End que contiene el almacén de Administración Central  <br/> |Interfaz interna del servidor perimetral  <br/> |Replicación de los cambios desde el almacén de Administración Central se almacenan para el servidor perimetral.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante Skype para cmdlets del Shell de administración de servidor de negocios y servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos de agente (ClsAgent.exe) y colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante Skype para cmdlets del Shell de administración de servidor de negocios y servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos de agente (ClsAgent.exe) y colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante Skype para cmdlets del Shell de administración de servidor de negocios y servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos de agente (ClsAgent.exe) y colección de registros.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Tablas de puerto de servidor perimetral para equilibradores de carga de hardware

Les estamos dando a los equilibradores de carga de hardware (HLB) y a los puertos de servidor perimetral su propia sección, ya que son algo más complicados con el hardware adicional. Vea las tablas siguientes para instrucciones para este escenario concreto:
  
#### <a name="external-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto externo

La dirección IP de origen y la dirección IP de destino contendrán información para usuarios que estén usando direcciones IP privadas con NAT, así como las personas que usen direcciones IP públicas. Esto cubrirá todas las permutaciones en nuestra sección de [escenarios de servidor perimetral de Skype para Business Server 2015](scenarios.md) .
  
|**Función o protocolo**|**TCP o UDP**|**Intervalo de puerto de destino o puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acceso/HTTP  <br/> |TCP  <br/> |80  <br/> |Dirección IP pública de servicio de servidor perimetral de acceso de borde  <br/> |Cualquiera  <br/> |Revocación de certificados y comprobación y recuperación de CRL.  <br/> |
|Acceso/DNS  <br/> |TCP  <br/> |53  <br/> |Dirección IP pública de servicio de servidor perimetral de acceso de borde  <br/> |Cualquiera  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acceso/DNS  <br/> |UDP  <br/> |53  <br/> |Dirección IP pública de servicio de servidor perimetral de acceso de borde  <br/> |Cualquiera  <br/> |Consulta DNS sobre UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Servidor de borde / Edge V servicio dirección IP  <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Servidor de borde / Edge V servicio dirección IP pública  <br/> |Cualquiera  <br/> |Se usa para retransmitir tráfico multimedia.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Servidor de borde / Edge V servicio dirección IP pública  <br/> |Cualquiera  <br/> |3478 saliente:  <br/> • Utilizada Skype para Business Server para determinar la versión de servidor perimetral se está comunicando.  <br/> • Utilizado para el tráfico de medios entre servidores perimetrales.  <br/> • Se requiere para la federación.  <br/> • Es necesario si se implementan varios grupos de borde dentro de su organización.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Servidor de borde / Edge V servicio dirección IP pública  <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Servidor de borde / Edge V servicio dirección IP pública  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Servidor de borde / Edge V servicio dirección IP pública  <br/> |Cualquiera  <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabla de resumen de firewall del puerto interno

|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Cualquiera de los siguientes que ejecutan el servicio de puerta de enlace XMPP:  <br/> • Servidor de Front-End  <br/> Grupo de Front-End • dirección VIP que ejecuta el servicio de puerta de enlace de XMPP  <br/> |Interfaz interna del servidor perimetral  <br/> |Tráfico saliente de XMPP desde el servicio de puerta de enlace de XMPP ejecutando en su servidor Front-End o Front-End de grupo de servidores.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Cualquier:  <br/> • Servidor Front-End que contiene el almacén de Administración Central  <br/> • Grupo de Front-End que contiene el almacén de Administración Central  <br/> |Interfaz interna del servidor perimetral  <br/> |Replicación de los cambios desde el almacén de Administración Central en el servidor perimetral.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Cada servidor Front-End en el grupo de servidores Front-End  <br/> |Interfaz interna del servidor perimetral  <br/> |Conferencia el tráfico Web desde su servidor Front-End o en cada servidor Front-End (si tiene un grupo de servidores Front-End) para la interfaz interna del servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Cada servidor Front-End en el grupo de servidores Front-End  <br/> |Interfaz interna del servidor perimetral  <br/> |Recomendado: ruta de acceso A medios de V transferencia entre los usuarios internos y externos y su dispositivo de sucursal que sobreviven o servidor de la sucursal que sobreviven.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquier:  <br/> • Servidor de Front-End  <br/> • Cada servidor Front-End en la agrupación  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta de reserva para una transferencia de medios V entre los usuarios internos y externos y su dispositivo de sucursal que sobreviven o servidor de sucursal que sobreviven, si no funciona la comunicación UDP. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante Skype para cmdlets del Shell de administración de servidor de negocios y servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos de agente (ClsAgent.exe) y colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante Skype para cmdlets del Shell de administración de servidor de negocios y servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos de agente (ClsAgent.exe) y colección de registros.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Controlador de servicio de registro centralizado mediante Skype para cmdlets del Shell de administración de servidor de negocios y servicio de registro centralizado, línea de comandos de ClsController (ClsController.exe) o comandos de agente (ClsAgent.exe) y colección de registros.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IP virtuales de la interfaz externa

|**Función o protocolo**|**TCP o UDP**|**Intervalo de puerto de destino o puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Cualquiera  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio de servidor perimetral de acceso)  <br/> |El servicio Proxy XMPP acepta tráfico de contactos XMPP en federaciones de XMPP definidas.  <br/> |
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Servicio Proxy XMPP (comparte una dirección IP con el servicio de servidor perimetral de acceso)  <br/> |Cualquiera  <br/> |El servicio Proxy XMPP envía tráfico de contactos XMPP en federaciones de XMPP definidas.  <br/> |
|Acceso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso perimetral <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso perimetral <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privadas mediante NAT:** Servicio de servidor perimetral de acceso de borde <br/> **IP pública:** Dirección IP pública de servicio de servidor perimetral de acceso de borde <br/> |Cualquiera  <br/> |Para la conectividad de MI pública y federada con SIP.  <br/> |
|Conferencia web/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servicio perimetral de conferencia Web Server perimetral <br/> **IP pública:** Dirección IP pública de borde perimetral de conferencia Web Server service <br/> |Medios de conferencias Web.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servidor de borde / servicio perimetral V <br/> **IP pública:** Servidor de borde / Edge V servicio dirección IP pública <br/> |Negociación STUN/TURN de candidatos sobre UDP en el puerto 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |**IP privadas mediante NAT:** Servidor de borde / servicio perimetral V <br/> **IP pública:** Servidor de borde / Edge V servicio dirección IP pública <br/> |Negociación STUN/TURN de candidatos sobre TCP en el puerto 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IP virtuales de la interfaz interna

Nuestra guía aquí va a ser algo diferente. En realidad, en una situación HLB, ahora le recomendamos que solo tenga enrutamiento a través de un VIP interno en las siguientes circunstancias:
  
- Si está utilizando Exchange 2007 o Exchange 2010 Unified Messaging (UM).
    
- Si tiene clientes heredados con el servidor perimetral.
    
En la tabla siguiente proporcionan orientación para esos escenarios, pero en caso contrario, debe ser capaz de dependen de almacén de Administración Central (CMS) para enrutar el tráfico al servidor de borde individual es consciente de (Esto requiere que se mantiene actualizado CMS en servidor perimetral información, por supuesto).
  
|**Protocolo**|**TCP o UDP**|**Puerto**|**Dirección IP de origen**|**Dirección IP de destino**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Cualquier:  <br/> • Director  <br/> • Grupo de directores dirección VIP  <br/> • Servidor de Front-End  <br/> Grupo de Front-End • dirección VIP  <br/> |Interfaz interna del servidor perimetral  <br/> |El tráfico SIP saliente de su Director, Director de grupo dirección VIP, servidor Front-End o Front-End VIP de grupo dirección a la interfaz interna del servidor perimetral.  <br/> |
|Acceso/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interfaz de servidor interno VIP de bordes  <br/> |Cualquier:  <br/> • Director  <br/> • Grupo de directores dirección VIP  <br/> • Servidor de Front-End  <br/> Grupo de Front-End • dirección VIP  <br/> |Tráfico SIP a su Director, dirección de grupo VIP del Director, servidor Front-End o dirección de grupo VIP de Front-End de la interfaz interna del servidor perimetral.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Cualquier:  <br/> • Dirección de IP del servidor final frontal  <br/> • Dirección IP de grupo de servidores Front-End  <br/> • Cualquier dispositivo de sucursal que sobreviven utilizando este servidor perimetral  <br/> • Cualquier servidor de sucursal que sobreviven mediante este servidor perimetral  <br/> |Interfaz interna del servidor perimetral  <br/> |Autenticación de A / usuarios V de su grupo de servidor Front-End o Front-End, o el dispositivo de sucursal que sobreviven o servidor de sucursal que sobreviven, usando el servidor perimetral.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Cualquiera  <br/> |Interfaz interna del servidor perimetral  <br/> |Ruta preferida para una transferencia de medios de A/V entre usuarios internos y externos.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Cualquiera  <br/> |Interfaz de servidor interno VIP de bordes  <br/> |Ruta de acceso de reserva para la transferencia de medios de A/V entre los usuarios internos y externos si la comunicación UDP no funciona. Entonces se usa TCP para las transferencias de archivos y el uso compartido de escritorio.  <br/> |