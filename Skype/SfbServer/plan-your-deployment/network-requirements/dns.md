---
title: Requisitos de DNS para Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumen: Revisar las consideraciones de DNS en este tema antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: 2f19e6dbd040a7f553331b6bcb0d7074a30fd0ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="dns-requirements-for-skype-for-business-server-2015"></a>Requisitos de DNS para Skype para Business Server 2015
 
**Resumen:** Revisar las consideraciones de DNS en este tema antes de implementar Skype para Business Server 2015.
  
Este artículo sólo trata DNS planificación para Skype para Business Server 2015 implementaciones de red local de una organización. Para Skype para los negocios en línea consulte "IP y direcciones URL de Office 365 intervalos de direcciones" en [http://aka.ms/o365ips](http://aka.ms/o365ips). 
  
Un servidor de servicio (de dominio DNS) de nombres de dominio asigna nombres de host (por ejemplo, www.contoso.com, presumiblemente en un servidor web) a direcciones IP (como 10.10.10.10). Ayuda a los clientes y servidores interdependientes se comunican entre sí en la red. Al configurar una implementación de Skype para Business Server 2015 debe asegurarse de que la asignación de nuevos nombres de servidor (que normalmente refleja la función tendremos en) coincide con las direcciones IP que están asignados.
  
Aunque pueda parecer complicado bit en primer lugar, el trabajo pesado para planear esto puede hacerse usando el [Skype para la herramienta de planeación de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Una vez que se ha desplazado a través de las preguntas del asistente acerca de qué características piensa utilizar, para cada sitio que define puede ver el informe de DNS en el informe de administración de borde y utilizar la información de la lista para crear los registros DNS. También puede realizar ajustes a muchos de los nombres y las direcciones IP utilizadas para obtener información detallada Consulte [Revisar el informe de DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Tenga en cuenta que puede exportar el informe de administración de borde a una hoja de cálculo de Excel y el informe de DNS será una de las hojas de cálculo en el archivo. 
  
Cuando va a instalar una nueva implementación tal como se describe en [los registros de DNS crea de Skype para Business Server 2015](../../deploy/install/create-dns-records.md) y crear la topología de Skype para Business Server 2015, reconocemos puede elegir utilizar las funciones DNS integradas en Windows 2016 de servidor o un paquete DNS de terceros, así que te mantendremos las discusiones en este artículo general en lugar de específicos. Que estamos detallando en lo que se necesita, y cómo satisfacer esa necesidad es su decisión de realizar.
  
Skype con experiencia para los administradores de negocios, Lync y Office Communications Suite probablemente útil en las siguientes tablas. Si la tabla es confusa para usted, las secciones posteriores o artículos se arrojan luz sobre los siguientes conceptos: 
  
- [Tablas de resumen](dns.md#BK_Summary)
    
- [Conceptos básicos DNS](basics.md)
    
- [Consideraciones de híbrido](dns.md#BK_Hybrid)
    
- [Cerebro dividido DNS](dns.md#BK_split)
    
- [Direcciones URL simples](dns.md#BK_Simple)
    
- [DNS por el rol de servidor](dns.md#BK_Servers)
    
## <a name="summary-tables"></a>Tablas de resumen
<a name="BK_Summary"> </a>

Las tablas siguientes se muestran los registros DNS que utiliza Skype para Business Server 2015 para proporcionar servicios a los usuarios. Algunos son opcional y sólo son necesarios para admitir determinadas funciones y puede omitirse si no se desean tener esas características. Los registros DNS necesarios para el acceso interno sólo están en la primera tabla, y una implementación que permite el acceso interno y externo necesita registros de ambas tablas.
  
**Asignaciones internas de DNS**

|**Tipo de registro**|**Valor**|**Se resuelve en**|**Propósito**|**Requerida.**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |Grupo de servidores frontal FQDN  <br/>  *FE-pool.contoso.com*  <br/> |Front End grupo direcciones IP  <br/>  Libras de DNS a *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |DNS equilibrio de carga de los Pools de Front-End. Asigna el nombre de grupo de servidores Front-End a un conjunto de direcciones IP.  <br/> Vea [implementar DNS equilibrio de carga en agrupaciones de Front-End y agrupaciones de Director](load-balancing.md#BK_FE_Dir) <br/> |Y  <br/> |
|A/AAAA  <br/> | FQDN de cada servidor de servidor Front-End o Standard Edition en un grupo o un servidor independiente <br/>  * FE01.contoso.com, FE02.contoso.com, FE03.contoso.com*  <br/> |IP correspondiente de cada servidor  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Asigna el nombre del servidor en su dirección IP.  <br/> |Y  <br/> |
|A/AAAA  <br/> |Servicios Web interno del conjunto de empresas reemplazar FQDN  <br/>  *Web int.contoso.com*  <br/> |HLB VIP para los servicios de Web interno de servidor Front-End  <br/>  * 192.168.21.120 *  <br/> |Requerido para permitir al tráfico de web server, como descargar el Skype para el negocio de la aplicación Web cliente. También se requiere para los clientes móviles.  <br/> |Y  <br/> |
|A/AAAA  <br/> |Servicios Web externos de grupo de empresa reemplazar FQDN  <br/>  *Web ext.contoso.com*  <br/> |VIP de HLB para servicios Web externos de servidor de Front-End  <br/>  *68.123.56.90*  <br/> |Requerido para permitir al tráfico de web server, como descargar el Skype para el negocio de la aplicación Web cliente. Necesaria si los clientes móviles resolverá DNS internamente. Puede resolver para IP de Proxy inverso de DMZ o Internet.  <br/> ||
|A/AAAA  <br/> | FQDN del servidor SQL Server de extremo posterior <br/>  *SQL1.contoso.com*  <br/> |dirección IP del servidor  <br/>  *192.168.11.90*  <br/> |Asigna el nombre del servidor para un servidor SQL back-end, trabajar con el grupo de servidores frontales a su dirección IP  <br/> ||
|A/AAAA  <br/> |FQDN del servidor SQL de extremo servidor espejo posterior  <br/>  *SQL2.contoso.com*  <br/> |dirección IP del servidor  <br/>  *192.168.11.91*  <br/> |Asigna el nombre del servidor para un servidor de back-end SQL espejo trabaja con el grupo de servidores frontales a su dirección IP  <br/> ||
|A/AAAA  <br/> |FQDN del grupo de director  <br/> **Nota:** No es aplicable cuando se utiliza un servidor de independiente Director <br/>  *DirPool.contoso.com*  <br/> |Direcciones IP de grupo de director  <br/> LB de DNS para *192.168.21.132, 192.168.21.133, 192.168.21.134*  <br/> |DNS equilibrio de carga de los servidores del grupo de directores. Asigna el nombre del grupo para el grupo de Director a una dirección IP, consulte [Implementación de equilibrio de carga en el DNS en agrupaciones de extremo frontal y agrupaciones de Director](load-balancing.md#BK_FE_Dir) <br/> Un Director es opcional y puede autenticar a un usuario.  <br/> ||
|A/AAAA  <br/> |FQDN del director  <br/> |Dirección IP de cada servidor Director  <br/> |Asigna el nombre del grupo para el Director a una dirección IP, consulte [Implementación de equilibrio de carga en el DNS en agrupaciones de extremo frontal y agrupaciones de Director](load-balancing.md#BK_FE_Dir) <br/> ||
|A/AAAA  <br/> |FQDN del grupo de servidor de mediación  <br/> |Direcciones IP de grupo  <br/> |El rol de servidor de mediación es opcional. Puede ubicar los servicios proporcionados por un servidor de mediación para el servidor Front-End o un grupo de servidores. Vea [utilizar DNS equilibrio de carga en los grupos de servidores de mediación](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |FQDN del servidor de mediación  <br/> |Dirección IP del servidor  <br/> |Puede ubicar los servicios proporcionados por un servidor de mediación para el servidor Front-End o un grupo de servidores. Vea [utilizar DNS equilibrio de carga en los grupos de servidores de mediación](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |FQDN del servidor de Chat persistentes  <br/> |Dirección IP del servidor de charla persistente  <br/> |Un servidor de charla persistente es necesario para la característica Charla persistente y lo contrario es opcional.  <br/> ||
|A/AAAA  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *contoso.com*  <br/> |Grupo de servidores Front-End de HLB VIP o Director IP  <br/>  192.168.21.121 <br/> |AutoDiscover Service1 interno, necesario para la movilidad. Si se utiliza DNS interno para resolver para dispositivos móviles, debe señalar a la dirección IP externa o DMZ VIP.  <br/> Para servicios Web necesitamos HLB en el grupo de servidores Front-End como HTTPS no puede aprovechar el DNS. Para el grupo de servidores Front-End o grupo de directores debe se resuelve en una VIP de HLB o una dirección IP normal para un servidor Standard edition o un servidor de independiente Director.  <br/> |Y  <br/> |
|CNAME  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *contoso.com*  <br/> |FQDN del grupo HLB FE o FQDN del Director  <br/> Web int.contoso.com  <br/> |Interno de detección automática de Service1 <br/> Puede implementar como un CNAME en lugar de un registro si lo desea.  <br/> ||
|A/AAAA  <br/> |sip. _\<sipdomain\>_ <br/> sip. _contoso.com_ <br/> |Frente a grupo de servidores IP del servidor (o a una IP de cada Director de direcciones)  <br/>  Libras de DNS a *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Necesario para la configuración automática, vea [Tutorial de Skype para clientes empresariales buscar servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Un registro o registros que señala a los servidores de grupo de servidores Front-End o Director de servidores en la red interna o el servicio de servidor perimetral de acceso cuando el cliente es externo  <br/> |2 <br/> |
|A/AAAA  <br/> |UCUpdates-r2. _\<sipdomain\>_ <br/> UCUpdates-r2. _contoso.com_ <br/> |IP HLB FE grupo VIP VIP o Director de grupo de HLB o servidor SE/Director  <br/>  192.168.21.121 <br/> |La implementación de este registro es opcional 3 <br/> ||
|SRV  <br/> |_sipinternaltls._tcp. _ \<sipdomain\> _ Puerto 5061 <br/> _sipinternaltls._tcp. _contoso.com_ puerto 5061 <br/> |Grupo de servidores frontal FQDN  <br/>  _FE-Pool.contoso.com_ <br/> |Permite interno automático de sesión del usuario 1 en el servidor Front-End o el grupo o SE servidor o el grupo que se autentica y redirige las solicitudes de cliente de inicio de sesión. <br/> |2 <br/> |
|SRV  <br/> |_sipinternal. _\<sipdomain\>_ <br/> _sipinternal. _contoso.com_ <br/> |Grupo de servidores frontal FQDN  <br/>  _FE-Pool.contoso.com_ <br/> |Acceso de usuario interno 1 <br/> |2 <br/> |
|SRV  <br/> |_ntp._udp. _\<sipdomain\>_ <br/> _ntp._udp. _contoso.com_ <br/> |FQDN de servidores horarios  <br/> North-america.pool.ntp.org  <br/> |Origen NTP requerido para los dispositivos Phone Edition de Lync  <br/> |Esto es necesario para admitir los auriculares de sobremesa.  <br/> |
|SRV  <br/> |_sipfederationtls._tcp.  _\<sipdomain\>_ <br/> _sipfederationtls._tcp.  _contoso.com_ <br/> | Servicio de acceso perimetral FQDN <br/> EdgePool-int. _contoso.com_ <br/> |Crear un registro SRV para cada dominio SIP con IOS o Windows phone clientes móviles.  <br/> |Para la compatibilidad con clientes móviles  <br/> |
|A/AAAA  <br/> |dirección URL de Admin  <br/>  _Web int.contoso.com_ <br/> |Grupo HLB FE VIP  <br/> 192.168.21.121  <br/> |Skype para el Panel de Control de servidor de empresa, vea [Direcciones URL Simple](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |conocer la dirección URL  <br/>  _Web int.contoso.com_ <br/> |Grupo HLB FE VIP  <br/> 192.168.21.121  <br/> |Reuniones en línea, vea [Direcciones URL Simple](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |dirección URL de acceso telefónico  <br/>  _Web int.contoso.com_ <br/> |Grupo HLB FE VIP  <br/> 192.168.21.121  <br/> |Conferencias de acceso telefónico, vea [Direcciones URL Simple](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |FQDN interno de servicios Web  <br/>  _Web int.contoso.com_ <br/> |Grupo HLB FE VIP  <br/> 192.168.21.121  <br/> |Skype para servicio Web de Business utiliza Skype para Business Web App  <br/> ||
|A/AAAA  <br/> |FQDN del grupo de servidor de aplicaciones Web de Office  <br/> OWA.contoso.com  <br/> | Grupo de Office Web Apps Server dirección VIP <br/> 192.168.1.5  <br/> |Define el FQDN del grupo de servidor de Office Web Apps  <br/> ||
|A/AAAA  <br/> | Web interno FQDN <br/> Web int.contoso.com  <br/> | Frente a grupo final dirección VIP <br/> 192.168.21.121  <br/> |Define el nombre completo de la Web interno utilizado por Skype para Business Web App  <br/> Si utiliza DNS equilibrio de carga en este grupo, el grupo de servidores Front-End y granja de servidores web internos no pueden tener el mismo FQDN.  <br/> ||
   
 **1** utiliza un cliente para descubrir el grupo de servidor Front-End o Front-End y ser autenticado e inició sesión como un usuario. Es más detalle en este [Tutorial de Skype para clientes de empresa](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)localizar servicios.
  
 **2** esto sólo es necesario para compatibilidad con clientes antiguos antes de 2013 de Lync y auriculares de sobremesa.
  
 **3** en la situación donde un dispositivo de comunicaciones unificadas está activado, pero un usuario nunca inició sesión en el dispositivo, el registro permite que el dispositivo detectar el servidor que aloja el servicio Web de actualización de dispositivo y obtener actualizaciones. De lo contrario, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.
  
El siguiente diagrama muestra un ejemplo que incluye los registros DNS internos y externos y muchos de los registros mostrados en las tablas que lo rodea: 
  
**Diagrama de red de borde mediante direcciones IPv4 públicas**

![ejemplo de diagrama de red DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
**Asignaciones DNS de red perimetral (interfaces internas y externas)**

|**Tipo de registro**|**Valor**|**Se resuelve en**|**Propósito**|**Requerida.**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |FQDN del grupo de borde interno  <br/>  _EdgePool-int.contoso.com_ <br/> |Direcciones IP de grupo interno orientadas borde  <br/> 172.25.33.10, 172.25.33.11  <br/> |Consolidan las direcciones IP de interfaz interna de la piscina de borde  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN del servidor de borde  <br/>  _Contras 1.contoso.com_ <br/> |IP del servidor interno hacia un servidor en la piscina de borde  <br/> 172.25.33.10  <br/> |Crear un registro para cada servidor en el grupo con el FQDN del servidor que señala a su IP de nodo servidor interno en el fondo, vea [DNS equilibrio de carga en los grupos de servidores de borde](load-balancing.md#BK_Edge).  <br/> |Y  <br/> |
|A/AAAA  <br/> |Servicio de acceso perimetral Pool FQDN  <br/>  _Access1.contoso.com_ <br/> |Acceso perimetral servicio grupo las direcciones IP externas  <br/> 131.107.16.10, 131.107.16.11  <br/> |El servicio de servidor perimetral de acceso proporciona un punto de conexión único de confianza para el tráfico entrante y saliente de protocolo de inicio de sesión (SIP).  <br/> |Y  <br/> |
|A/AAAA  <br/> |Servicio de perimetral de conferencia Web Pool FQDN  <br/>  _Webcon1.contoso.com_ <br/> |Las direcciones IP externas de servicio perimetral de conferencia Web  <br/> 131.107.16.90, 131.107.16.91  <br/> |El servicio perimetral de conferencia Web permite a los usuarios externos puedan unirse a reuniones que se hospedan en su Skype para entorno Business Server interno.  <br/> |Y  <br/> |
|A/AAAA  <br/> | _av.\<dominio sip\> _ FQDN del grupo <br/>  _AV1.contoso.com_ <br/> |A / V borde externo direcciones de IP  <br/> 131.107.16.170, 131.107.16.171  <br/> |A / servicio de borde V hace audio, vídeo, uso compartido de aplicaciones y transferencia de archivos usuarios disponibles externos.  <br/> |Y  <br/> |
|CNAME  <br/> |sip. _\<sipdomain\>_ <br/> sip. _contoso.com_ <br/> |FQDN del grupo de borde de acceso externo  <br/>  _Access1.contoso.com_ <br/> |Localiza el grupo de servidor perimetral. Vea el [Tutorial de Skype para clientes de empresa localizar servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sip._tls. _\<sipdomain\>_ <br/> _sip._tls. _contoso.com_ <br/> |Servidor perimetral de acceso externo FQDN  <br/>  _Access1.contoso.com_ <br/> |Se utiliza para el acceso de usuarios externos. Vea el [Tutorial de Skype para clientes de empresa localizar servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sipfederationtls._tcp. _\<sipdomain\>_ <br/> _sipfederationtls._tcp. _contoso.com_ <br/> |Servidor perimetral de acceso externo FQDN  <br/>  _Access1.contoso.com_ <br/> |Utilizado para la federación y la conectividad con IM pública  <br/> |1 <br/> |
|SRV  <br/> |_xmpp-server._tcp. _\<sipdomain\>_ <br/> _xmpp-server._tcp. _contoso.com_ <br/> |Servidor perimetral de acceso externo FQDN  <br/>  _Access1.contoso.com_ <br/> |El servicio de servidor Proxy XMPP acepta y envía mensajes de protocolo (XMPP) de presencia y mensajería extensible y de socios federados XMPP configurados.  <br/> |Y, para implementar la federación, de lo contrario opcional  <br/> |
|SRV  <br/> |_sipfederationtls._tcp.  _\<sipdomain\>_ <br/> _sipfederationtls._tcp.  _contoso.com_ <br/> |Servidor perimetral de acceso externo FQDN  <br/>  _Access1.contoso.com_ <br/> |Para admitir el servicio de notificación de inserción y el servicio de notificación de inserción de Apple, crear un registro SRV para cada dominio SIP. 3 <br/> ||
|A/AAAA  <br/> |FQDN de servicios web externos de grupo de servidores Front-End  <br/>  _Web ext.contoso.com_ <br/> |Dirección IP pública del proxy, servidores proxy inversos para la VIP de servicios Web externos para el grupo de servidores Front-End 1 <br/> 131.107.155.1 proxy de a 192.168.21.120  <br/> |Frontal final grupo interfaz externa utilizada Skype para Business Web App  <br/> |Y  <br/> |
|A/AAAA/CNAME  <br/> |lyncdiscover. _\<sipdomain\>_ <br/> lyncdiscover. _contoso.com_ <br/> |Invertir dirección IP pública de proxy, se resuelve al VIP de servicios Web externos para su grupo de directores, si tiene uno, o para el grupo de servidores Front-End si no tiene un Director de 2 <br/> 131.107.155.1 proxy de a 192.168.21.120  <br/> | Registro externo para cliente detección automática, también utilizado por movilidad, Skype para Business Web App y programador Web app, resuelto por el servidor proxy inverso <br/> Para admitir el servicio de notificación de inserción y el servicio de notificación de inserción de Apple, crear un registro SRV para cada dominio SIP que tenga clientes de Microsoft Lync Mobile. 3 <br/> |Y  <br/> |
|A/AAAA  <br/> |cumplir. _\<sipdomain\>_ <br/> cumplir. _contoso.com_ <br/> |Invertir dirección IP pública de proxy, se resuelve a la interfaz Web externa para el grupo de servidores Front-End  <br/> 131.107.155.1 proxy de a 192.168.21.120  <br/> |Proxy de Skype para el servicio Web de Business  <br/> Vea [direcciones URL Simple](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |marcado de _ \<sipdomain\>_ <br/> acceso telefónico _contoso.com_ <br/> |Dirección IP pública del proxy, servidores proxy inversos para la interfaz externa del Web para el grupo de servidores Front-End  <br/> 131.107.155.1 proxy de a 192.168.21.120  <br/> |Proxy de Skype para el servicio Web de Business  <br/> Vea [direcciones URL Simple](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN del grupo de servidor de aplicaciones Web de Office  <br/> OWA.contoso.com  <br/> | Dirección IP pública del proxy, servidores proxy inversos para la interfaz de Web externa para el servidor de Office Web Apps <br/> 131.107.155.1 proxy de a 192.168.1.5  <br/> | Grupo de Office Web Apps Server dirección VIP <br/> 192.168.1.5  <br/> |Define el FQDN del grupo de servidor de Office Web Apps  <br/> |
   
 **1** necesarios para implementar la federación, de lo contrario opcional.
  
 **2** se utiliza un cliente para descubrir el servidor front-end o grupo de servidores Front End y ser autenticado y conectado como un usuario.
  
 **3** este requisito sólo se aplica a los clientes de Apple o Microsoft en dispositivos móviles. Los dispositivos Android y Nokia Symbian no usan notificaciones de inserción.
  
 Para obtener más información sobre los servidores perimetrales y redes perimetrales, vea el contenido de [Diseño de DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) del servidor perimetral.
  
> [!IMPORTANT]
> Skype para Business Server admite el uso del direccionamiento IPv6. Para obtener más detalles, consulte [Plan para IPv6 en Skype para el negocio](ipv6.md) .
  
> [!IMPORTANT]
> Para obtener más información acerca de los FQDN, consulte [conceptos básicos DNS](basics.md). 
  
 **Dividir el cerebro DNS** 
 <a name="BK_split"> </a>
 
Dividir el cerebro DNS es una configuración de DNS en el que tiene dos zonas DNS con el mismo espacio de nombres. La primera zona DNS controla solicitudes internas, mientras que la segunda zona DNS controla las solicitudes externas, como se menciona en estas tablas. Para obtener más información, ver [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS). 
  
## <a name="hybrid-considerations"></a>Consideraciones de híbrido
<a name="BK_Hybrid"> </a>

Si piensa tener algunos usuarios alojados en línea y algunos alojados en locales, consulte la [configuración DNS](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS)del híbrido. Debe configurar DNS como normal para Skype para Business Server 2015 y también agregar registros DNS adicionales. 
  
Además, debe consultar a "IP y direcciones URL de Office 365 intervalos de direcciones" en [http://aka.ms/o365ips](http://aka.ms/o365ips) para confirmar que los usuarios tendrán acceso a los recursos en línea que se necesitan.
  
## <a name="simple-urls"></a>Direcciones URL simples
<a name="BK_Simple"> </a>

Un localizador de recursos uniforme (URL) es una referencia a un recurso web que especifica su ubicación en una red de equipo y un protocolo utilizado para recuperarlo. 
  
Skype para Business Server admite el uso de tres direcciones URL "simples" para tener acceso a servicios:
  
- **Cumplir** se utiliza como la dirección URL base para todas las conferencias en el sitio. Un ejemplo de un sencillo satisfacer URL es https://meet.contoso.com. Puede ser una dirección URL para una reunión concreta https://meet.contoso.com/ _nombre de usuario_/7322994. 
    
    Con la dirección URL simple satisfacer, vínculos a unirse a reuniones son fácil de comprender y comunicar.
    
- **Acceso telefónico** permite el acceso a la página web de configuración conferencias de acceso telefónico. Esta página muestra los números de acceso telefónico de conferencia con sus idiomas disponibles, asignadas la información de la conferencia (es decir, para las reuniones que no es necesario programar), controles DTMF en la conferencia y soporta la administración de (número de identificación personal PIN) y asigna la información de la conferencia. La dirección URL simple acceso telefónico se incluye en todas las invitaciones a reuniones para que los usuarios que deseen conectarse a la reunión pueden tener acceso a la información de PIN y número de teléfono es necesario. Un ejemplo de la dirección URL simple acceso telefónico es https://dialin.contoso.com.
    
- **Admin** permite un acceso rápido a la Skype para Panel de Control de servidor empresarial. Desde cualquier equipo dentro de los servidores de seguridad de la organización, un administrador puede abrir el Skype para Panel de Control de servidor de negocio escribiendo la dirección URL de administración simple en un explorador. La dirección URL de administración simple es interna de su organización. Un ejemplo de la dirección URL de administración simple es https://admin.contoso.com.
    
Direcciones URL simples se tratan con más detalle en los [requisitos de DNS para direcciones URL simples en Skype para Business Server 2015](simple-urls.md).
  
## <a name="dns-by-server-role"></a>DNS por el rol de servidor
<a name="BK_Servers"> </a>

Puede establecer los nombres de estos grupos y servidores como desee, pero hacerlas fáciles de recordar y reflejar su función en el sistema.
  
### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS para los servidores individuales o grupos de servidores

Estos requisitos de registro genérico se aplican a cualquier rol de servidor utilizado por Skype para el negocio. Un grupo es un conjunto de servidores que ejecutan los mismos servicios que trabajan conjuntamente para controlar las solicitudes de cliente dirigidas a ellos a través de un equilibrador de carga. Para obtener detalles, consulte [requisitos de Skype para el negocio de equilibrio de carga](load-balancing.md)
  
**Requisitos de registro de DNS para los roles de servidor o el grupo (se da por supuesto DNS equilibrio de carga)**

|**Escenario de implementación**|**Requisitos de DNS**|
|:-----|:-----|
|Un servidor:  <br/> Servidor de mediación de charla, Director, persistente, servidor frontal  <br/> |Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.  <br/> ServerRole.contoso.com 10.10.10.0  <br/> |
|Grupo:  <br/> Charla persistente, Director, servidor perimetral, servidor de mediación, Front end  <br/> |Interno un registro que resuelve el nombre de dominio completo (FQDN) de cada nodo de servidor en el grupo a su dirección IP.  <br/> **Ejemplo** <br/> ServerRole01.contoso.com 10.10.10.1  <br/> ServerRole02.contoso.com 10.10.10.2  <br/> A interno varios registros que resuelven el nombre de dominio completo (FQDN) de la agrupación que las direcciones IP de los nodos de servidor en el grupo.  <br/> **Ejemplo** <br/> ServerPool.contoso.com 10.10.10.1  <br/> ServerPool.contoso.com 10.10.10.2  <br/> |
   
### <a name="edge-server-specific-dns-topics"></a>Temas específicos de DNS del servidor de borde

 Para planear la implementación de servidores de borde, revisar el [Plan para implementaciones de servidor perimetral de Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)y [Planear Skype para Business Server 2015 avanzada borde servidor DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) que tiene la siguientes secciones
  
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    

