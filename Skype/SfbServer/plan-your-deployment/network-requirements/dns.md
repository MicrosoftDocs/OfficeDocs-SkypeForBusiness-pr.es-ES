---
title: Requisitos de DNS para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumen: Revise las consideraciones de DNS en este tema antes de implementar Skype empresarial Server.'
ms.openlocfilehash: 33c5e18c6bc8d5a29b0e4a6fa447fbde02028556
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982815"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos de DNS para Skype empresarial Server

**Resumen:** Revise las consideraciones de DNS en este tema antes de implementar Skype empresarial Server.

En este artículo solo se trata la planeación de DNS para las implementaciones de Skype empresarial Server en la red local de una organización. Para Skype empresarial online consulte "direcciones URL e intervalos de direcciones IP de Office 365" [https://aka.ms/o365ips](https://aka.ms/o365ips)en.

Un servidor de servicio de nombres de dominio (DNS) asigna nombres de host<span> </span> (por ejemplo, www. Contoso<span></span>. com, supuestamente un servidor Web) a direcciones IP (por ejemplo, 10.10.10.10). Ayuda a los clientes y a los servidores interdependientes a comunicarse entre sí en la red. Cuando configure una implementación de Skype empresarial Server 2015, deberá asegurarse de que la asignación de los nombres de servidor nuevos (que normalmente reflejan el rol que tomarán) coincide con las direcciones IP a las que están asignados.

Aunque esto puede parecer un poco desalentadora al principio, el trabajo pesado para planear esto puede hacerse con la herramienta de [planeación de Skype empresarial Server 2015](https://www.microsoft.com/download/details.aspx?id=50357). Una vez que haya consultado las preguntas del asistente sobre qué características planea usar, para cada sitio que defina puede ver el informe de DNS en el informe de administración perimetral y usar la información que se muestra allí para crear los registros DNS. También puede realizar ajustes a muchos de los nombres y direcciones IP usados, para obtener información detallada, consulte [Review The DNS Report](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo de Excel y el informe de DNS será una de las hojas de cálculo del archivo. Aunque esta herramienta incluye características [desusadas de Skype empresarial Server 2019](../../../SfBServer2019/deprecated.md), aún se puede usar para crear un plan inicial si no se seleccionan las características.

Al instalar una nueva implementación, tal como se describe en [Create DNS Records for Skype for Business Server](../../deploy/install/create-dns-records.md) y Building Your Topology for Skype for Business Server, reconocemos que puede elegir usar las capacidades de DNS integradas en Windows Server 2016 o un paquete DNS de terceros, por lo que mantendremos las discusiones de este artículo generales en lugar de específicas. Estamos detallando lo que se necesita y cómo se reúne la decisión que debe tomarse.

Los administradores experimentados de Skype empresarial, Lync y Office Communications Suite probablemente verán útiles las siguientes tablas. Si la tabla es confusa para usted, las secciones o artículos posteriores arrojarán luz sobre los siguientes conceptos:

## <a name="summary-tables"></a>Tablas de Resumen
<a name="BK_Summary"> </a>

En las siguientes tablas se muestran los registros DNS que Skype empresarial Server usa para proporcionar servicios a los usuarios. Algunas son opcionales en cuanto a que solo son necesarias para admitir determinadas características, y se pueden omitir si no se desea ninguna característica. Los registros DNS necesarios solo para el acceso interno están en la primera tabla y una implementación que permita el acceso interno y externo necesitará registros de ambas tablas.

**Asignaciones internas de DNS**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Obligatorio|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN del grupo de servidores front-end  <br/> *Grupo de servidores FE. <span> </span>contoso<span></span>. com*   |Direcciones IP del servidor del grupo de servidores front-end  <br/>  De *192.168.21.122 192.168.21.123 192.168.21.124*   |Equilibrio de carga de DNS de grupos de servidores front-end. Asigna el nombre del grupo de servidores front-end a un conjunto de direcciones IP.  <br/> Consulte [implementación del equilibrio de carga de DNS en grupos de servidores front-end y grupos de directores](load-balancing.md#BK_FE_Dir)  |v   |
|A/AAAA   | FQDN de cada servidor front-end o servidor Standard Edition de un grupo de servidores o un servidor independiente <br/>  *FE01. <span> </span>contoso. <span> </span>com FE02. <span> </span>contoso<span></span>. com FE03. <span> </span>contoso<span></span>. com*   |IP correspondiente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Asigna el nombre del servidor a su dirección IP.   |v   |
|A/AAAA   |FQDN del dominio de servicios Web internos del grupo de servidores Enterprise  <br/> *Web-int.<span></span>contoso<span></span>. com*   |HLB VIP para los servicios Web internos del servidor front-end  <br/> *192.168.21.120*   |Necesario para habilitar el tráfico web de cliente a servidor, como la descarga de la aplicación Web de Skype empresarial. También es necesario para los clientes móviles.   |v   |
|A/AAAA   |FQDN de reemplazo de servicios web externos del grupo de servidores Enterprise  <br/> *Web-ext.<span></span>contoso<span></span>. com*   |HLB VIP para servicios web externos de servidor front-end  <br/>*68.123.56.90*   |Necesario para habilitar el tráfico web de cliente a servidor, como la descarga de la aplicación Web de Skype empresarial. Obligatorio si los clientes móviles van a resolver DNS internamente. Puede resolver la IP de proxy inverso de la DMZ o IP de Internet.   ||
|A/AAAA   | FQDN del servidor back-end de SQL Server <br/> *SQL1. <span> </span>contoso<span></span>. com*   |Dirección IP del servidor  <br/> *192.168.11.90*   |Asigna el nombre del servidor de un servidor SQL Server de servicios de fondo que trabaja con el grupo de servidores front-end en su dirección IP.   ||
|A/AAAA   |FQDN de SQL Server de reflejo del servidor back-end  <br/> *SQL2. <span> </span>contoso<span></span>. com*   |Dirección IP del servidor  <br/> *192.168.11.91*   |Asigna el nombre del servidor de un servidor de reflejo SQL back-end que trabaja con el grupo de servidores front-end en su dirección IP.   ||
|A/AAAA   |FQDN del grupo de directores  <br/>**Nota:** No se aplica cuando se usa un servidor de director independiente <br/> *DirPool. <span> </span>contoso<span></span>. com*   |Direcciones IP del grupo de directores  <br/> De la LB a *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Equilibrio de carga DNS de servidores de grupo de directores. Asigna el nombre del grupo de servidores Director a una dirección IP, vea [DEPLOYING DNS Load Balancing on pools front-end y grupos de directores](load-balancing.md#BK_FE_Dir) <br/> Un director puede autenticar a un usuario y es opcional.   ||
|A/AAAA   |FQDN de Director   |Dirección IP del servidor de cada servidor de Director   |Asigna el nombre del grupo para que el director sea una dirección IP, vea [DEPLOYING DNS Load Balancing on pools front-end y los grupos de directores](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN del grupo de servidores de mediación   |Direcciones IP del grupo de servidores   |El rol de servidor de mediación es opcional. Puede ubicar los servicios proporcionados por un servidor de mediación en el servidor front-end o en el grupo de servidores. Vea [usar el equilibrio de carga de DNS en grupos de servidores de mediación](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del servidor de mediación   |Dirección IP del servidor   |Puede ubicar los servicios proporcionados por un servidor de mediación en el servidor front-end o en el grupo de servidores. Vea [usar el equilibrio de carga de DNS en grupos de servidores de mediación](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del servidor de chat persistente   |Dirección IP del servidor de chat persistente   |Se requiere un servidor de chat persistente para la característica chat persistente y, de lo contrario, es opcional.   ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>contoso<span></span>. com*   |IP de director o VIP del grupo de servidores front-end HLB  <br/>  192.168.21.121  |Service1 interno de detección automática, necesario para la compatibilidad con la movilidad. Si se usa DNS interno para resolver los dispositivos móviles, debe apuntar a la dirección IP externa o a la VIP de DMZ.  <br/> Para los servicios Web, necesitamos HLB en el grupo de servidores front-end, ya que HTTPS no puede aprovechar el DNS. Para el grupo de servidores front-end o el grupo de directores, debe resolverse en una dirección VIP de HLB o una IP normal para un servidor Standard Edition o un servidor director independiente.   |v   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>. com*   |FQDN del grupo de HLB FE o FQDN del Director  <br/> Web-int.<span></span>contoso<span></span>. com   |Service1 interno de detección automática <br/> Puede implementar esto como un CNAME en lugar de un registro A si lo desea.   ||
|A/AAAA   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>. com*  |Direcciones IP del servidor del grupo de servidores front-end (o una dirección IP de cada director)  <br/>  De *192.168.21.122 192.168.21.123 192.168.21.124*   |Necesario para la configuración automática, vea [tutorial de clientes de Skype empresarial para buscar servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Un registro o registros que señalan a los servidores del grupo de servidores front-end o los servidores de Director de la red interna, o al servicio perimetral de acceso cuando el cliente es externo   |&#x2777;  |
|A/AAAA   |ucupdates-R2. * \<sipdomain\>* <br/> ucupdates-R2. * <span> </span>contoso<span></span>. com*  |IP del grupo de HLB o VIP del grupo de servidores de HLB VIP o del servidor de Director  <br/>  192.168.21.121  |La implementación de este registro es opcional &#x2778;  ||
|SRV   |\_sipinternaltls. \_TCP. * \<sipdomain\> * <br/>Puerto 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>contoso<span></span>. com* <br/>Puerto 5061  |FQDN del grupo de servidores front-end  <br/>*Grupo de servidores FE. <span> </span>contoso<span></span>. com*  |Habilita el inicio de sesión automático de usuario interno 1 en el servidor o grupo de servidores front-end, o el servidor o grupo de servidores que autentica y redirige las solicitudes de inicio de sesión de los clientes.  |&#x2777; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *contoso<span></span>. com*  |FQDN del grupo de servidores front-end  <br/>_Grupo de servidores FE. <span> </span>contoso<span></span>. com_  |&#x2776; de acceso de usuario interno  |&#x2777;  |
|SRV   | \_utilizados. \_UDP. * \<sipdomain\> * <br/> \_utilizados. \_UDP. <span> </span> *contoso<span></span>. com*  |FQDN TimeServer  <br/> north-america.pool.ntp.org   |Origen NTP necesario para dispositivos de Lync Phone Edition   |Esto es necesario para admitir los teléfonos de escritorio.   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *contoso<span></span>. com*  | FQDN del servicio perimetral de acceso <br/> EdgePool-int.<span></span>*contoso<span></span>. com*  |Cree un registro SRV para cada dominio SIP que tenga clientes móviles de IOS o Windows Phone.   |Para la compatibilidad con clientes móviles   |
|A/AAAA   |Dirección URL de administración  <br/>*Web-int.<span></span>contoso<span></span>. com*  |VIP del grupo de HLB FE  <br/> 192.168.21.121   |Panel de control de Skype empresarial Server, vea [direcciones URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |Dirección URL de la reunión  <br/>*Web-int.<span></span>contoso<span></span>. com*  |VIP del grupo de HLB FE  <br/> 192.168.21.121   |Reuniones en línea, consulte [URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |Dirección URL de acceso telefónico local  <br/>*Web-int.<span></span>contoso<span></span>. com*  |VIP del grupo de HLB FE  <br/> 192.168.21.121   |Conferencias de acceso telefónico local, consulte [direcciones URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN de servicios Web internos  <br/>*Web-int.<span></span>contoso<span></span>. com*  |VIP del grupo de HLB FE  <br/> 192.168.21.121   |Servicio Web de Skype empresarial usado por la aplicación Web de Skype empresarial   ||
|A/AAAA   |FQDN del grupo de servidores de Office Web Apps  <br/> Outlook. <span> </span>contoso<span></span>. com   | Dirección VIP del grupo de servidores de Office Web Apps <br/> 192.168.1.5   |Define el FQDN del grupo de servidores de Office Web Apps Server   ||
|A/AAAA   | FQDN Web interno <br/> Web-int.<span></span>contoso<span></span>. com   | Dirección VIP del grupo de servidores front-end <br/> 192.168.21.121   |Define el FQDN de Web interno usado por la aplicación Web de Skype empresarial  <br/> Si usa el equilibrio de carga de DNS en este grupo, el grupo de servidores front-end y la granja de servidores web interna no pueden tener el mismo FQDN.   ||

&#x2776; que usa un cliente para detectar el servidor front-end o el grupo de servidores front-end, y se debe autenticar y iniciar sesión como usuario. Más información sobre este tema está en [tutorial de los clientes de Skype empresarial que buscan servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; esto solo es necesario para admitir clientes heredados anteriores a Lync 2013 y teléfonos de escritorio.

&#x2778; en la situación en la que un dispositivo de comunicaciones unificado está activado, pero un usuario nunca ha iniciado sesión en el dispositivo, el registro A permite que el dispositivo detecte el servidor que hospeda el servidor que hospeda el servicio Web de actualización de dispositivos y obtenga actualizaciones. En otro caso, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.

En el siguiente diagrama se muestra un ejemplo que incluye registros DNS internos y externos, así como muchos de los registros que se muestran en las tablas circundantes:

**Diagrama de red perimetral con direcciones IPv4 públicas**

![ejemplo de diagrama de red DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Asignaciones DNS de la red perimetral (tanto interfaces internas como externas)**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Obligatorio|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN del grupo de servidores perimetrales interno  <br/>*EdgePool-int.<span></span>contoso<span></span>. com*  |Direcciones IP del grupo de servidores perimetrales orientado internamente  <br/> 172.25.33.10, 172.25.33.11   |Direcciones IP de la interfaz interna del grupo de servidores perimetrales consolidado   |v   |
|A/AAAA   |FQDN del servidor perimetral  <br/>*Cons-1. <span> </span>contoso<span></span>. com*  |IP de servidor orientado internamente para un servidor en el grupo de servidores perimetrales  <br/> 172.25.33.10   |Cree un registro para cada servidor del grupo con el FQDN de servidor que apunta a su IP de nodo de servidor interno en el grupo de servidores, vea [equilibrio de carga de DNS en grupos de servidores perimetrales](load-balancing.md#BK_Edge).   |v   |
|A/AAAA   |FQDN del grupo de servicio perimetral de acceso  <br/>*Access1. <span> </span>contoso<span></span>. com*  |Direcciones IP externas del grupo de servicio perimetral de acceso  <br/> 131.107.16.10, 131.107.16.11   |El servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico SIP (protocolo de inicio de sesión) saliente y entrante.   |v   |
|A/AAAA   |FQDN del grupo de servicio perimetral de conferencia Web  <br/>*Webcon1. <span> </span>contoso<span></span>. com*  |Direcciones IP externas del servicio perimetral de conferencia Web  <br/> 131.107.16.90, 131.107.16.91   |El servicio perimetral de conferencia web permite a los usuarios externos unirse a reuniones hospedadas en su entorno interno de Skype empresarial Server.   |v   |
|A/AAAA   |*v.\<SIP-domain\> * FQDN del grupo de servidores <br/>*AV1. <span> </span>contoso<span></span>. com*  |Direcciones IP externas del servidor perimetral A/V  <br/> 131.107.16.170, 131.107.16.171   |El servicio perimetral A/V hace que el audio, vídeo, uso compartido de aplicaciones y transferencia de archivos estén disponibles para los usuarios externos.   |v   |
|CNAME   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>. com*  |FQDN del grupo de servidores perimetrales de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>. com*  |Busca el grupo de servidores perimetrales. Consulte el [tutorial de servicios de búsqueda de clientes de Skype empresarial](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_SIP. \_TLS. * \<sipdomain\> * <br/>\_SIP. \_TLS. <span> </span> *contoso<span></span>. com*  |FQDN de servidor perimetral de acceso externo  <br/>_Access1. <span> </span>contoso<span></span>. com_  |Se usa para el acceso de usuarios externos. Consulte el [tutorial de servicios de búsqueda de clientes de Skype empresarial](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *contoso<span></span>. com*  |FQDN de servidor perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>. com*  |Se usa para la Federación y la conectividad de mensajería instantánea pública   |&#x2776;  |
|SRV   |\_XMPP-servidor. \_TCP. *<sipdomain\> * <br/>\_XMPP-servidor. \_TCP. * <span> </span>contoso<span></span>. com*  |FQDN de servidor perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>. com*  |El servicio Proxy XMPP acepta y envía mensajes del protocolo extensible de mensajería y presencia (XMPP) a los socios federados de XMPP configurados.   |Y, para implementar la Federación; en caso contrario, opcional  <br/> No disponible en Skype empresarial Server 2019.|
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>contoso<span></span>. com*  |FQDN de servidor perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>. com*  |Para admitir el servicio de notificaciones de inserción y el servicio de notificaciones de inserción de Apple, cree un registro SRV para cada dominio SIP. &#x2778;  ||
|A/AAAA   |FQDN de servicios web del grupo de servidores front-end externo  <br/>*Web-ext.<span></span>contoso<span></span>. com*  |Dirección IP pública del proxy inverso, servidores proxy a la VIP de servicios web externos para el grupo de servidores front-end &#x2776; <br/> proxy de 131.107.155.1 a 192.168.21.120   |Interfaz externa de grupo de servidores front-end usada por la aplicación Web de Skype empresarial   |v   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>contoso<span></span>. com*  |Dirección IP pública del proxy inverso, se resuelve en la VIP de servicios web externos para el grupo de directores, si dispone de uno, o para el grupo de servidores front-end si no tiene un director &#x2777; <br/> proxy de 131.107.155.1 a 192.168.21.120   | Registro externo para detección automática de clientes, también lo usa la movilidad, la aplicación Web de Skype empresarial y la aplicación web del programador, que resuelve el servidor de proxy inverso <br/> Para admitir el servicio de notificaciones de inserción y el servicio de notificaciones de inserción de Apple, cree un registro SRV para cada dominio SIP que tenga clientes móviles de Microsoft Lync. 3   |v   |
|A/AAAA   |cumplir. * \<sipdomain\>* <br/> cumplir. * <span> </span>contoso<span></span>. com*  |Dirección IP pública del proxy inverso, se resuelve en la interfaz web externa del grupo de servidores front-end  <br/> proxy de 131.107.155.1 a 192.168.21.120   |Proxy para el servicio Web de Skype empresarial  <br/> Ver [direcciones URL sencillas](dns.md#BK_Simple)  |v   |
|A/AAAA   |acceso telefónico.*\<sipdomain\>* <br/> acceso telefónico local.*<span></span>contoso<span></span>. com*  |Dirección IP pública del proxy inverso, servidores proxy a la interfaz web externa del grupo de servidores front-end  <br/> proxy de 131.107.155.1 a 192.168.21.120   |Proxy para el servicio Web de Skype empresarial  <br/> Ver [direcciones URL sencillas](dns.md#BK_Simple)  |v   |
|A/AAAA   |FQDN del grupo de servidores de Office Web Apps  <br/> Outlook. <span> </span>contoso<span></span>. com   | Dirección IP pública del proxy inverso, servidores proxy de la interfaz web externa para Office Web Apps Server <br/> proxy de 131.107.155.1 a 192.168.1.5   | Dirección VIP del grupo de servidores de Office Web Apps <br/> 192.168.1.5   |Define el FQDN del grupo de servidores de Office Web Apps Server   |

&#x2776; necesario para implementar la Federación; de lo contrario, es opcional.

&#x2777; que usa un cliente para detectar el servidor front-end o el grupo de servidores front-end, y se debe autenticar y iniciar sesión como usuario.

&#x2778; este requisito solo se aplica a los clientes de dispositivos móviles basados en Apple o Microsoft. Los dispositivos Android y Nokia Symbian no usan la notificación de inserción.

 Para obtener más información sobre los servidores perimetrales y las redes perimetrales, consulte el contenido de [planeación DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) del servidor perimetral.

> [!IMPORTANT]
> Skype empresarial Server admite el uso del direccionamiento IPv6. Consulte [Plan for IPv6 in Skype for Business](ipv6.md) para obtener más información.

> [!IMPORTANT]
> Para obtener más información acerca de los FQDN, consulte [conceptos básicos de DNS](basics.md).

**DNS de cerebro dividido** 
 <a name="BK_split"> </a>

El DNS del cerebro dividido es una configuración DNS en la que tiene dos zonas DNS con el mismo espacio de nombres. La primera zona DNS administra las solicitudes internas, mientras que la segunda zona DNS administra las solicitudes externas, como se menciona en estas tablas. Para obtener más información sobre esto [, consulte DNS de cerebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Consideraciones sobre el entorno híbrido
<a name="BK_Hybrid"> </a>

Si planea tener algunos usuarios alojados en línea y hospedados en local, consulte el artículo de planeación de conectividad híbrida [de Skype empresarial server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Tendrá que configurar DNS como normal para Skype empresarial Server 2015 y también agregar registros DNS adicionales.

También debe consultar "direcciones URL e intervalos de direcciones IP de Office 365" [https://aka.ms/o365ips](https://aka.ms/o365ips) en para confirmar que los usuarios tendrán acceso a los recursos en línea que van a necesitar.

## <a name="simple-urls"></a>Direcciones URL simples
<a name="BK_Simple"> </a>

Un localizador uniforme de recursos (URL) es una referencia a un recurso Web que especifica su ubicación en una red de equipos y un protocolo usado para recuperarlo.

Skype empresarial Server admite el uso de tres direcciones URL "sencillas" para acceder a los servicios:

- La **reunión** se usa como dirección URL base para todas las conferencias del sitio. Un ejemplo de una dirección URL sencilla de reunión es<span></span>//<span></span>https: Meet. <span> </span>contoso<span></span>. com. Una dirección URL de una reunión determinada podría ser HTTPS<span></span>//<span></span>: Meet. <span> </span>contoso<span></span>. com/_username_/7322994.

    Con la dirección URL sencilla de reunirse, los vínculos para unirse a las reuniones son fáciles de comprender y se pueden comunicar fácilmente.

- El acceso **telefónico** permite el acceso a la Página Web de configuración de conferencia de acceso telefónico local. Esta página muestra los números de acceso telefónico de conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, para las reuniones que no necesitan programarse) y los controles de DTMF en conferencia, y admite la administración del número de identificación personal ( PIN) y la información de conferencia asignada. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios. Un ejemplo de la dirección URL sencilla de acceso telefónico es<span></span>https://dialen. <span> </span>contoso<span></span>. com.

- El **Administrador** habilita el acceso rápido al panel de control de Skype empresarial Server. Desde cualquier equipo de los firewalls de su organización, un administrador puede abrir el panel de control de Skype empresarial Server escribiendo la dirección URL sencilla de administración en un explorador. La dirección URL simple de administración es de uso interno para la organización. Un ejemplo de la dirección URL sencilla de administración<span></span>es https://admin. <span> </span>contoso<span></span>. com.

Las direcciones URL sencillas se describen con más detalle en [requisitos de DNS para direcciones URL sencillas en Skype empresarial Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS por rol del servidor
<a name="BK_Servers"> </a>

Puede establecer los nombres de estos grupos de servidores y servidores como desee, pero hacerlos memorables y reflejar su función en el sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS para servidores o grupos de servidores individuales

Estos requisitos de registro genérico se aplican a cualquier función del servidor que usa Skype empresarial. Un grupo de servidores es un conjunto de servidores que ejecutan los mismos servicios que funcionan conjuntamente para administrar las solicitudes de cliente dirigidas a ellos a través de un equilibrador de carga. Consulte [requisitos de equilibrio de carga para Skype empresarial](load-balancing.md) para obtener más información

**Requisitos de registro DNS para roles de servidor o grupo de servidores (se supone que el equilibrio de carga de DNS)**

|Escenario de implementación|Requisito de DNS|
|:-----|:-----|
|Un servidor:  <br/> Chat persistente, Director, servidor de mediación, servidor front-end   |Registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.  <br/> ServerRole. <span> </span>10.10.10.0<span></span>de contoso. com   |
|Repositorio  <br/> Chat persistente, Director, servidor perimetral, servidor de mediación, front-end   |Un registro A interno que resuelve el nombre de dominio completo (FQDN) de cada nodo de servidor del grupo de servidores en su dirección IP.  <br/>**Ejemplo** <br/> ServerRole01. <span> </span>contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>10.10.10.2<span></span>de contoso. com  <br/> Varios registros A internos que resuelven el nombre de dominio completo (FQDN) del grupo de servidores a las direcciones IP de los nodos del servidor del grupo.  <br/>**Ejemplo** <br/> ServerPool. <span> </span>contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>10.10.10.2<span></span>de contoso. com   |

### <a name="edge-server-specific-dns-topics"></a>Temas DNS específicos del servidor perimetral

 Para planear la implementación del servidor perimetral, revise [Plan for Edge Server Deployments in Skype for Business server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)y [Advanced Edge Server Planning for Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , que tiene las siguientes secciones

- [Recuperación ante desastres de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Equilibrio de carga de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuración automática sin DNS de horizonte dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS de horizonte dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Tutorial de los clientes de Skype empresarial que buscan servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


