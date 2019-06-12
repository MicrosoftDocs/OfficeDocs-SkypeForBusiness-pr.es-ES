---
title: Requisitos de DNS para Skype empresarial Server
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
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumen: Revise las consideraciones de DNS en este tema antes de implementar Skype empresarial Server.'
ms.openlocfilehash: 13dd8b65c52329ff2db0ac3d7d57eeba990e29f6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297067"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos de DNS para Skype empresarial Server

**Resumen:** Revise las consideraciones de DNS en este tema antes de implementar Skype empresarial Server.

Este artículo solo se redirige al planeamiento de DNS para las implementaciones de Skype empresarial Server en una red local de la organización. Para Skype empresarial online, consulte "Office 365 URL e intervalos de direcciones IP" en [https://aka.ms/o365ips](https://aka.ms/o365ips).

Un servidor de servicio de nombres de dominio (DNS) asigna nombres de host<span> </span> (como www. Contoso<span></span>. com, supuestamente un servidor Web) en direcciones IP (como 10.10.10.10). Ayuda a los clientes y a los servidores interdependientes a comunicarse entre sí en la red. Al configurar una implementación de Skype empresarial Server 2015, tendrá que asegurarse de que la asignación de los nombres de los nuevos servidores (generalmente el rol que adoptarán) coincide con las direcciones IP a las que están asignados.

A pesar de que esto puede parecer complicado, el trabajo pesado para planear esto puede hacerse con la [herramienta de planificación de Skype empresarial Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Una vez que haya finalizado las preguntas del asistente sobre las características que planea usar, para cada sitio que defina, puede ver el informe DNS dentro del informe de administración perimetral y usar la información que se muestra allí para crear los registros DNS. También puede realizar ajustes en muchos de los nombres y direcciones IP usados, para obtener información detallada, consulte [revisar el informe DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo de Excel y el informe DNS será una de las hojas de cálculo del archivo. Aunque esta herramienta incluye características [desusadas de Skype empresarial Server 2019](../../../SfBServer2019/deprecated.md), aún puede usarse para crear un plan inicial si estas características no están seleccionadas

Al instalar una nueva implementación como se describe en [crear registros DNS para Skype empresarial Server](../../deploy/install/create-dns-records.md) y crear su topología para Skype empresarial Server, reconocemos que puede elegir usar las capacidades de DNS integradas en Windows Server 2016 o un paquete DNS de terceros, por lo que guardaremos las discusiones de este artículo en general en lugar de específicas. Le detallamos lo que necesita y cómo usted se reúne con su decisión de tomar.

Es probable que los administradores experimentados de Skype empresarial, Lync y Office Communications Suite encuentren las siguientes tablas útiles. Si la tabla le resulta confusa, los artículos o secciones posteriores arrojarán luz sobre los siguientes conceptos:

## <a name="summary-tables"></a>Tablas de Resumen
<a name="BK_Summary"> </a>

En las tablas siguientes se muestran los registros DNS que usa Skype empresarial Server para proporcionar servicios a los usuarios. Algunas son opcionales en el caso de que solo sean necesarias para admitir determinadas características, y se pueden omitir si no se desean dichas características. Los registros DNS necesarios para el acceso interno solo están en la primera tabla, y una implementación que permita acceso interno y externo necesitará registros de las dos tablas.

**Asignaciones de DNS internas**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Obligatorio|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN del grupo de servidores front-end  <br/> *Grupo FE. <span> </span>contoso<span></span>. com*   |Direcciones IP del servidor del grupo de servidores front-end  <br/>  DNS LB a *192.168.21.122 192.168.21.123 192.168.21.124*   |Equilibrio de carga DNS de grupos front-end. Asigna el nombre del grupo de servidores front-end a un conjunto de direcciones IP.  <br/> Vea [implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de directores](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | FQDN de cada servidor front-end o servidor Standard Edition en un grupo de servidores o un servidor independiente <br/>  *FE01. <span> </span>contoso. <span> </span>com FE02. <span> </span>contoso<span></span>. com FE03. <span> </span>contoso<span></span>. com*   |Dirección IP correspondiente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Asigna el nombre del servidor a su dirección IP.   |Y   |
|A/AAAA   |Los servicios Web internos del grupo de servidores reemplazan el FQDN  <br/> *Web-int.<span></span>contoso<span></span>. com*   |HLB VIP para servicios Web internos del servidor front-end  <br/> *192.168.21.120*   |Necesario para habilitar el tráfico web del cliente al servidor, como descargar la aplicación Web de Skype empresarial. También se requiere para los clientes móviles.   |Y   |
|A/AAAA   |Servicio Web externo de grupo de servidores Enterprise invalidar FQDN  <br/> *Web-ext.<span></span>contoso<span></span>. com*   |HLB VIP para servicios web externos de servidor front-end  <br/>*68.123.56.90*   |Necesario para habilitar el tráfico web del cliente al servidor, como descargar la aplicación Web de Skype empresarial. Necesario si los clientes móviles van a resolver DNS internamente. Puede resolver la IP de proxy invertida de la DMZ o IP de Internet.   ||
|A/AAAA   | Servidor de servicios de fondo FQDN de SQL Server <br/> *SQL1. <span> </span>contoso<span></span>. com*   |Dirección IP del servidor  <br/> *192.168.11.90*   |Asigna el nombre del servidor de un servidor SQL Server de servicios de fondo que trabaja con el grupo de servidores front-end a su dirección IP.   ||
|A/AAAA   |Servidor back-end reflejado FQDN de SQL Server  <br/> *SQL2. <span> </span>contoso<span></span>. com*   |Dirección IP del servidor  <br/> *192.168.11.91*   |Asigna el nombre del servidor de un servidor SQL Mirror back-end que funciona con el grupo de servidores front-end a su dirección IP.   ||
|A/AAAA   |FQDN del grupo de directores  <br/>**Nota:** No se aplica al usar un servidor de director independiente <br/> *DirPool. <span> </span>contoso<span></span>. com*   |Direcciones IP del grupo de directores  <br/> DNS LB a *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Equilibrio de carga DNS de los servidores de grupo de directores. Asigna el nombre de la sección para el grupo de directores a una dirección IP, consulte [implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de directores](load-balancing.md#BK_FE_Dir) <br/> Un director puede autenticar a un usuario y es opcional.   ||
|A/AAAA   |FQDN de Director   |Dirección IP del servidor de cada servidor de directores   |Asigna el nombre de la sección para el director a una dirección IP, consulte [implementar el equilibrio de carga de DNS en grupos de servidores front-end y grupos de directores](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN del grupo de servidores de mediación   |Direcciones IP del grupo   |El rol de servidor de mediación es opcional. Puede coubicar los servicios proporcionados por un servidor de mediación al servidor o grupo de servidores front-end. Vea [usar el equilibrio de carga de DNS en grupos de servidores de mediación](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del servidor de mediación   |Dirección IP del servidor   |Puede coubicar los servicios proporcionados por un servidor de mediación al servidor o grupo de servidores front-end. Vea [usar el equilibrio de carga de DNS en grupos de servidores de mediación](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del servidor de chat persistente   |Dirección IP del servidor de chat persistente   |Se necesita un servidor de chat persistente para la característica de chat persistente y, en caso contrario, es opcional.   ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>contoso<span></span>. com*   |IP de director o VIP de agrupación front end de HLB  <br/>  192.168.21.121  |Service1 interno de detección automática, necesario para la compatibilidad con movilidad. Si se usa DNS interno para resolver los dispositivos móviles, debe apuntar a la IP externa o a la dirección VIP de la DMZ.  <br/> Para los servicios Web, requerimos HLB en el grupo de servidores front-end porque HTTPS no puede sacar provecho de DNS. En el caso de un grupo de servidores front-end o un grupo de directores, debe resolverse en una dirección VIP de HLB o una IP normal para un servidor Standard Edition o un servidor director independiente.   |Y   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>. com*   |FQDN del grupo HLB FE o FQDN del Director  <br/> Web-int.<span></span>contoso<span></span>. com   |Service1 interno de detección automática <br/> Puede implementar esto como un CNAME en lugar de un registro A si lo desea.   ||
|A/AAAA   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>. com*  |Direcciones IP del servidor del grupo de servidores front-end (o a una dirección IP de cada director)  <br/>  DNS LB a *192.168.21.122 192.168.21.123 192.168.21.124*   |Necesario para la configuración automática, consulte [tutorial de clientes de Skype empresarial localizar servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Un registro o registros que apuntan a los servidores de grupo de servidores front-end o a los servidores de directores de la red interna o al servicio perimetral de acceso cuando el cliente es externo   |&#x2777;  |
|A/AAAA   |ucupdates-R2. * \<sipdomain\>* <br/> ucupdates-R2. * <span> </span>contoso<span></span>. com*  |La dirección IP del grupo de HLB o director de HLB VIP o SE/Director  <br/>  192.168.21.121  |La implementación de este registro es opcional &#x2778;  ||
|SRV   |\_sipinternaltls. \_TCP. * \<sipdomain\> * <br/>Puerto 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>contoso<span></span>. com* <br/>Puerto 5061  |FQDN del grupo de servidores front-end  <br/>*Grupo FE. <span> </span>contoso<span></span>. com*  |Habilita el inicio de sesión automático 1 de usuario interno en el servidor/grupo de servidores front-end o el servidor/grupo de servidores que autentica y redirige las solicitudes de inicio de sesión de los clientes.  |&#x2777; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *contoso<span></span>. com*  |FQDN del grupo de servidores front-end  <br/>_Grupo FE. <span> </span>contoso<span></span>. com_  |&#x2776; de acceso de usuarios internos  |&#x2777;  |
|SRV   | \_utilizados. \_UDP. * \<sipdomain\> * <br/> \_utilizados. \_UDP. <span> </span> *contoso<span></span>. com*  |FQDN de TimeServer  <br/> north-america.pool.ntp.org   |Se necesita un origen NTP para los dispositivos de Lync Phone Edition   |Esto es necesario para admitir teléfonos de escritorio.   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *contoso<span></span>. com*  | FQDN del servicio perimetral de acceso <br/> EdgePool-int.<span></span>*contoso<span></span>. com*  |Cree un registro SRV para cada dominio SIP con IOS o clientes móviles de Windows Phone.   |Para compatibilidad con clientes móviles   |
|A/AAAA   |Dirección URL de administración  <br/>*Web-int.<span></span>contoso<span></span>. com*  |VIP de grupo HLB FE  <br/> 192.168.21.121   |Panel de control de Skype empresarial Server, consulte [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |reunirse URL  <br/>*Web-int.<span></span>contoso<span></span>. com*  |VIP de grupo HLB FE  <br/> 192.168.21.121   |Reuniones en línea, consulte [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |Dirección URL de marcado  <br/>*Web-int.<span></span>contoso<span></span>. com*  |VIP de grupo HLB FE  <br/> 192.168.21.121   |Conferencias de acceso telefónico local, consulte [URL simples](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN de los servicios Web internos  <br/>*Web-int.<span></span>contoso<span></span>. com*  |VIP de grupo HLB FE  <br/> 192.168.21.121   |Servicio Web de Skype empresarial usado por la aplicación Web de Skype empresarial   ||
|A/AAAA   |FQDN del grupo de servidores de Office Web Apps  <br/> Access. <span> </span>contoso<span></span>. com   | Dirección VIP del grupo de servidores de Office Web Apps <br/> 192.168.1.5   |Define el FQDN del grupo de servidores de Office Web Apps.   ||
|A/AAAA   | FQDN de la web interna <br/> Web-int.<span></span>contoso<span></span>. com   | Dirección VIP del grupo de servidores front-end <br/> 192.168.21.121   |Define el FQDN de Web interno usado por la aplicación Web de Skype empresarial  <br/> Si está usando el equilibrio de carga de DNS en este grupo, el grupo de servidores front-end y el conjunto de servidores Web internos no pueden tener el mismo FQDN.   ||

&#x2776; usa un cliente para descubrir el servidor front-end o el grupo de servidores front-end, y se autentican e inician sesión como usuario. Más información sobre este tema es una [visita guiada de los clientes de Skype empresarial que localizan los servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; esto solo es necesario para admitir clientes heredados anteriores a la 2013 de Lync y teléfonos de escritorio.

&#x2778; en la situación en la que un dispositivo de comunicaciones unificado está activado, pero un usuario nunca ha iniciado sesión en el dispositivo, el registro A permite que el dispositivo Descubra el servidor que hospeda el servicio Web de actualización de dispositivos y obtenga actualizaciones. De lo contrario, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.

En el siguiente diagrama se muestra un ejemplo que incluye registros DNS internos y externos, así como muchos de los registros que se muestran en las tablas circundantes:

**Diagrama de red perimetral con direcciones IPv4 públicas**

![ejemplo de diagrama de red DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Asignaciones DNS de la red perimetral (interfaces internas y externas)**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Obligatorio|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN del grupo de contorno interno  <br/>*EdgePool-int.<span></span>contoso<span></span>. com*  |Direcciones IP del grupo de servidores perimetrales orientadas internamente  <br/> 172.25.33.10, 172.25.33.11   |Dirección IP de la agrupación perimetral consolidada dirección IP   |Y   |
|A/AAAA   |FQDN del servidor perimetral  <br/>*Cons-1. <span> </span>contoso<span></span>. com*  |IP de servidor con conexión interna para un servidor en el grupo Edge  <br/> 172.25.33.10   |Crear un registro para cada servidor del grupo con el FQDN de servidor que apunta a su IP de nodo de servidor interno en el grupo, consulte [equilibrio de carga DNS en grupos de servidores perimetrales](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |FQDN del grupo de servicio perimetral de acceso  <br/>*Access1. <span> </span>contoso<span></span>. com*  |Direcciones IP externas del grupo de servicio perimetral de Access  <br/> 131.107.16.10, 131.107.16.11   |El servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico de protocolo de inicio de sesión entrante y saliente (SIP).   |Y   |
|A/AAAA   |FQDN del grupo de servicio perimetral de conferencia Web  <br/>*Webcon1. <span> </span>contoso<span></span>. com*  |Direcciones IP externas del servicio perimetral de conferencia Web  <br/> 131.107.16.90, 131.107.16.91   |El servicio perimetral de conferencias web permite a los usuarios externos unirse a reuniones hospedadas en su entorno interno de Skype empresarial Server.   |Y   |
|A/AAAA   |*SIP-AV-domain\> \<* FQDN del grupo <br/>*AV1. <span> </span>contoso<span></span>. com*  |Direcciones IP externas de borde A/V  <br/> 131.107.16.170, 131.107.16.171   |El servicio Edge de A/V hace que el audio, el vídeo, el uso compartido de aplicaciones y la transferencia de archivos estén disponibles para los usuarios externos.   |Y   |
|CNAME   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>. com*  |FQDN del grupo perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>. com*  |Ubica el grupo de servidores perimetrales. Consulte [tutorial de clientes de Skype empresarial localizar servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_TLS. * \<sipdomain\> * <br/>\_SIP. \_TLS. <span> </span> *contoso<span></span>. com*  |FQDN perimetral de acceso externo  <br/>_Access1. <span> </span>contoso<span></span>. com_  |Se usa para el acceso de usuarios externos. Consulte [tutorial de clientes de Skype empresarial localizar servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *contoso<span></span>. com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>. com*  |Se usa para la Federación y la conectividad de mensajería instantánea pública   |&#x2776;  |
|SRV   |\_XMPP-servidor. \_TCP. *<sipdomain\> * <br/>\_XMPP-servidor. \_TCP. * <span> </span>contoso<span></span>. com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>. com*  |El servicio de proxy XMPP acepta y envía mensajes de protocolo de presencia y mensajería extensible (XMPP) a los socios de XMPP federados configurados.   |Y, para implementar la Federación; en caso contrario, opcional  <br/> No disponible en Skype empresarial Server 2019.|
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>contoso<span></span>. com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>. com*  |Para admitir el servicio de notificaciones de inserción y el servicio de notificaciones push de Apple, puede crear un registro SRV para cada dominio SIP. &#x2778;  ||
|A/AAAA   |FQDN de servicios web del grupo de servidores front-end externo  <br/>*Web-ext.<span></span>contoso<span></span>. com*  |Dirección IP pública de proxy invertida, servidores proxy a la VIP de servicios web externos para el grupo de servidores front-end &#x2776; <br/> 131.107.155.1 proxy a 192.168.21.120   |Interfaz externa de grupo de servidores front-end usada por la aplicación Web de Skype empresarial   |Y   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>contoso<span></span>. com*  |Dirección IP pública de proxy invertida, se resuelve en la VIP de servicios web externos para el grupo de directores, si tiene una, o para el grupo de servidores front-end si no tiene un director &#x2777; <br/> 131.107.155.1 proxy a 192.168.21.120   | Registro externo para detección automática de clientes, también lo usa la movilidad, la aplicación Web de Skype empresarial y la aplicación web del programador, que resuelve el servidor proxy inverso <br/> Para admitir el servicio de notificaciones de inserción y el servicio de notificaciones push de Apple, puede crear un registro SRV para cada dominio SIP que tenga clientes móviles de Microsoft Lync. 3  |Y   |
|A/AAAA   |satisfa. * \<sipdomain\>* <br/> satisfa. * <span> </span>contoso<span></span>. com*  |Dirección IP pública de proxy invertida, se resuelve en la interfaz web externa del grupo de servidores front-end  <br/> 131.107.155.1 proxy a 192.168.21.120   |Proxy para el servicio Web de Skype empresarial  <br/> Ver [direcciones URL simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |acceso telefónico.*\<sipdomain\>* <br/> acceso telefónico.*<span></span><span></span>contoso. com*  |Dirección IP pública de proxy invertida, servidores proxy a la interfaz web externa para el grupo de servidores front-end  <br/> 131.107.155.1 proxy a 192.168.21.120   |Proxy para el servicio Web de Skype empresarial  <br/> Ver [direcciones URL simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |FQDN del grupo de servidores de Office Web Apps  <br/> Access. <span> </span>contoso<span></span>. com   | Dirección IP pública de proxy invertida, servidores proxy a la interfaz web externa para Office Web Apps Server <br/> 131.107.155.1 proxy a 192.168.1.5   | Dirección VIP del grupo de servidores de Office Web Apps <br/> 192.168.1.5   |Define el FQDN del grupo de servidores de Office Web Apps.   |

&#x2776; necesario para implementar la Federación; en caso contrario, opcional.

&#x2777; usa un cliente para descubrir el servidor front-end o el grupo de servidores front-end, y se autentican e inician sesión como usuario.

&#x2778; este requisito solo se aplica a los clientes de Apple o de dispositivos móviles basados en Microsoft. Los dispositivos Android y Nokia Symbian no usan notificaciones de inserción.

 Para obtener más información sobre los servidores perimetrales y las redes perimetrales, consulte el contenido de [planeación DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) de servidor perimetral.

> [!IMPORTANT]
> Skype empresarial Server admite el uso de direcciones IPv6. Para obtener más información, consulte [planificación de IPv6 en Skype empresarial](ipv6.md) .

> [!IMPORTANT]
> Para obtener más información sobre los FQDN, consulte [conceptos básicos de DNS](basics.md).

**Redividir DNS** 
 <a name="BK_split"> </a> de Brain

Redividir DNS DNS es una configuración DNS en la que tiene dos zonas DNS con el mismo espacio de nombres. La primera zona DNS controla las solicitudes internas, mientras que la segunda zona DNS controla las solicitudes externas, tal y como se menciona en estas tablas. Para obtener más información [, consulta DNS de horizonte dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Consideraciones Híbridas
<a name="BK_Hybrid"> </a>

Si tiene previsto tener algunos usuarios alojados en línea y algunos domésticos, consulte el artículo sobre planeamiento de conectividad híbrida [de Skype empresarial server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Tendrá que configurar DNS como normal para Skype empresarial Server 2015 y también agregar registros DNS adicionales.

También debe consultar "Office 365 URLs e intervalos de direcciones IP" en [https://aka.ms/o365ips](https://aka.ms/o365ips) para confirmar que los usuarios tendrán acceso a los recursos en línea que necesitarán.

## <a name="simple-urls"></a>Direcciones URL simples
<a name="BK_Simple"> </a>

Un localizador uniforme de recursos (URL) es una referencia a un recurso Web que especifica su ubicación en una red de PC y un protocolo usado para recuperarlo.

Skype empresarial Server admite el uso de tres direcciones URL "simples" para acceder a los servicios:

- **Reunirse** se usa como la dirección URL base para todas las conferencias del sitio. Un ejemplo de una dirección URL simple de reunirse es<span></span>//<span></span>https: Meet. <span> </span>contoso<span></span>. com. Una dirección URL de una reunión determinada podría ser HTTPS<span></span>//<span></span>: reunirse. <span> </span>contoso<span></span>. com/_nombreDeUsuario_/7322994.

    Con la dirección URL sencilla, los vínculos para unirse a las reuniones son fáciles de comprender y son fáciles de comunicar.

- El acceso **telefónico** permite el acceso a la Página Web de configuración de conferencias de acceso telefónico local. Esta página muestra los números de acceso telefónico de la Conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, para las reuniones que no es necesario programar) y los controles de DTMF de la Conferencia, y admite la administración del número de identificación personal ( PIN) y la información de conferencia asignada. La dirección URL de acceso telefónico simple está incluida en todas las invitaciones a reuniones para que los usuarios que deseen llamar a la reunión puedan tener acceso a la información del número de teléfono y del PIN necesarios. Un ejemplo de la dirección URL de acceso telefónico simple es<span></span>https://Dialin. <span> </span>contoso<span></span>. com.

- El **Administrador** permite acceder rápidamente al panel de control de Skype empresarial Server. Desde cualquier equipo de los servidores de seguridad de su organización, un administrador puede abrir el panel de control de Skype empresarial Server escribiendo la dirección URL simple de administrador en un explorador. La dirección URL simple de administración es interna de su organización. Un ejemplo de la dirección URL simple de administración<span></span>es https://admin. <span> </span>contoso<span></span>. com.

Las direcciones URL simples se describen con más detalle en [los requisitos de DNS para las direcciones URL simples en Skype empresarial Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS por rol de servidor
<a name="BK_Servers"> </a>

Puede configurar los nombres de estos grupos y servidores como desee, pero hacerlos memorables y reflejar su función en el sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS para servidores o grupos individuales

Estos requisitos genéricos de registro se aplican a cualquier función de servidor que use Skype empresarial. Un grupo es un conjunto de servidores que ejecutan los mismos servicios que funcionan de forma conjunta para atender las solicitudes de los clientes a través de un equilibrador de carga. Consulta [los requisitos de equilibrio de carga de Skype empresarial](load-balancing.md) para obtener más información

**Requisitos de registro DNS para los roles de servidor o de grupo (supone el equilibrio de carga de DNS)**

|Escenario de implementación|Requisito de DNS|
|:-----|:-----|
|Un servidor:  <br/> Chat persistente, Director, servidor de mediación, servidor front-end   |Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.  <br/> Es. <span> </span>contoso<span></span>. com 10.10.10.0   |
|Agrupa  <br/> Chat persistente, Director, servidor perimetral, servidor de mediación, front-end   |Un registro A interno que resuelve el nombre de dominio completo (FQDN) de cada nodo de servidor del grupo a su dirección IP.  <br/>**Ejemplo** <br/> ServerRole01. <span> </span>contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>contoso<span></span>. com 10.10.10.2  <br/> Varios registros A internos que resuelven el nombre de dominio completo (FQDN) del grupo a las direcciones IP de los nodos del servidor en el grupo.  <br/>**Ejemplo** <br/> ServerPool. <span> </span>contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>contoso<span></span>. com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Temas DNS específicos del servidor perimetral

 Para planificar la implementación del servidor perimetral, revise planificación [de implementaciones de servidores perimetrales en Skype empresarial server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)y el plan [DNS de servidor perimetral avanzado para Skype empresarial Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , que tiene las siguientes secciones

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


