---
title: Requisitos dns para Skype Empresarial Server
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
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumen: revise las consideraciones de DNS de este tema antes de implementar Skype Empresarial Server.'
ms.openlocfilehash: ee69019df0c137fa4cd64260bd804769747ff2a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096244"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos dns para Skype Empresarial Server

**Resumen:** Revise las consideraciones de DNS de este tema antes de implementar Skype Empresarial Server.

En este artículo solo se aborda la planeación de DNS para las implementaciones de Skype Empresarial Server en la red local de una organización. For Skype for Business Online refer to "Office 365 URLs and IP address ranges" at [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) .

Un servidor de servicio de nombres de dominio (DNS) asigna nombres de host (como www. <span></span> contoso <span></span> .com, presumiblemente un servidor web) a direcciones IP (como 10.10.10.10). Ayuda a los clientes y servidores interdependientes a comunicarse entre sí en la red. Al configurar una implementación de Skype Empresarial Server 2015, deberá asegurarse de que la asignación de nuevos nombres de servidor (normalmente reflejando el rol que asumirán) coincida con las direcciones IP a las que están asignadas.

Aunque esto puede parecer un poco desalentador al principio, el trabajo pesado para planear esto se puede hacer con la Herramienta de planeación de [Skype Empresarial Server 2015](https://www.microsoft.com/download/details.aspx?id=50357). Una vez que haya pasado por las preguntas del asistente acerca de las características que planea usar, para cada sitio que defina puede ver el informe DNS en el Informe de administración perimetral y usar la información que aparece allí para crear los registros DNS. También puede realizar ajustes en muchos de los nombres y direcciones IP usados, para obtener más información, vea [Review the DNS Report](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo de Excel y el informe DNS será una de las hojas de cálculo del archivo. Aunque esta herramienta incluye características en desuso de [Skype Empresarial Server 2019,](../../../SfBServer2019/deprecated.md)aún se puede usar para crear un plan inicial si no se seleccionan esas características.

Al instalar una nueva implementación como se describe en Crear registros DNS para Skype Empresarial [Server](../../deploy/install/create-dns-records.md) y crear la topología para Skype Empresarial Server, reconocemos que puede elegir usar las capacidades DNS integradas en Windows Server 2016 o un paquete DNS de terceros, por lo que las discusiones de este artículo son generales en lugar de específicas. Estamos detallando lo que se necesita y la forma en que cumple esa necesidad es su decisión de tomar.

Los administradores experimentados de Skype Empresarial, Lync y Office Communications Suite probablemente encontrarán útiles las tablas siguientes. Si la tabla le resulta confusa, las secciones o artículos posteriores mostrarán algo de luz sobre los siguientes conceptos:

## <a name="summary-tables"></a>Tablas de resumen
<a name="BK_Summary"> </a>

En las tablas siguientes se muestran los registros DNS que Skype Empresarial Server usa para proporcionar servicios a los usuarios. Algunos son opcionales, ya que solo son necesarios para admitir determinadas características y se pueden omitir si no se desean. Los registros DNS necesarios para el acceso interno solo están en la primera tabla y una implementación que permita el acceso interno y externo necesitará registros de ambas tablas.

**Asignaciones dns internas**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Obligatorio|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN del grupo de servidores front-end  <br/> *FE-pool. <span></span> contoso <span></span> .com*   |Direcciones IP del servidor de grupo de servidores front-end  <br/>  DNS LB a *192.168.21.122 192.168.21.123 192.168.21.124*   |Equilibrio de carga DNS de grupos de servidores front-end. Asigna el nombre del grupo de servidores front-end a un conjunto de direcciones IP.  <br/> Consulte [Implementación del equilibrio de carga DNS en grupos de servidores front-end y grupos de directores](load-balancing.md#BK_FE_Dir)  |v   |
|A/AAAA   | FQDN de cada servidor front-end o servidor Standard Edition de un grupo de servidores o de un servidor independiente <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> contoso <span></span> .com FE03. <span></span> contoso <span></span> .com*   |IP correspondiente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Asigna el nombre del servidor a su dirección IP.   |v   |
|A/AAAA   |Fqdn de invalidación de servicios web internos del grupo de empresas  <br/> *Web-int. <span></span> contoso <span></span> .com*   |VIP de HLB para servicios web internos del servidor front-end  <br/> *192.168.21.120*   |Necesario para habilitar el tráfico web del cliente al servidor, como descargar la aplicación web de Skype Empresarial. También es necesario para clientes móviles.   |v   |
|A/AAAA   |Fqdn de invalidación de servicios web externos del grupo de servidores empresariales  <br/> *Web-ext. <span></span> contoso <span></span> .com*   |VIP de HLB para servicios web externos del servidor front-end  <br/>*68.123.56.90*   |Necesario para habilitar el tráfico web del cliente al servidor, como descargar la aplicación web de Skype Empresarial. Obligatorio si los clientes móviles resolverán DNS internamente. Puede resolverse en DMZ Reverse Proxy IP o IP de Internet.   ||
|A/AAAA   | FQDN de servidor SQL servidor back-end <br/> *SQL1. <span></span> contoso <span></span> .com*   |dirección IP del servidor  <br/> *192.168.11.90*   |Asigna el nombre del servidor de un servidor back-end SQL que trabaja con el grupo de servidores front-end a su dirección IP   ||
|A/AAAA   |FQDN del servidor SQL servidor back-end  <br/> *SQL2. <span></span> contoso <span></span> .com*   |dirección IP del servidor  <br/> *192.168.11.91*   |Asigna el nombre del servidor de un servidor back-end SQL servidor reflejado que trabaja con el grupo de servidores front-end a su dirección IP   ||
|A/AAAA   |FQDN del grupo de directores  <br/>**Nota:** No es aplicable cuando se usa un servidor director independiente <br/> *DirPool. <span></span> contoso <span></span> .com*   |Direcciones IP del grupo de directores  <br/> DNS LB a *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Equilibrio de carga DNS de los servidores del grupo de directores. Asigna el nombre del grupo de servidores del grupo de directores a una dirección IP, vea [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir) <br/> Un director puede autenticar a un usuario y es opcional.   ||
|A/AAAA   |Director FQDN   |Dirección IP del servidor de cada servidor director   |Asigna el nombre del grupo de servidores del director a una dirección IP, vea [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN del grupo de servidores de mediación   |Direcciones IP de grupo   |El rol servidor de mediación es opcional. Puede localizar los servicios proporcionados por un servidor de mediación en el servidor front-end o grupo de servidores. Consulte [Uso del equilibrio de carga DNS en grupos de servidores de mediación](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del servidor de mediación   |Dirección IP del servidor   |Puede localizar los servicios proporcionados por un servidor de mediación en el servidor front-end o grupo de servidores. Consulte [Uso del equilibrio de carga DNS en grupos de servidores de mediación](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del servidor de chat persistente   |Dirección IP del servidor de chat persistente   |Se requiere un servidor de chat persistente para la característica de chat persistente y, de lo contrario, es opcional.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |HLB Front-End pool VIP or Director IP  <br/>  192.168.21.121  |Servicio de detección automática interno1, necesario para la compatibilidad con movilidad. Si se usa DNS interno para resolver en dispositivos móviles, debe apuntar a la DIRECCIÓN IP externa o a la DIRECCIÓN VIP de DMZ.  <br/> Para los servicios web, se requiere HLB en el grupo de servidores front-end, ya que HTTPS no puede aprovechar DNS. Para el grupo de servidores front-end o el grupo de directores, esto debe resolverse en una VIP de HLB o en una DIRECCIÓN IP normal para un servidor Standard Edition o un servidor de director independiente.   |v   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |FQDN de grupo de HLB FE o FQDN de director  <br/> Web-int. <span></span> contoso <span></span> .com   |Servicio de detección automática interna1 <br/> Puede implementar esto como CNAME en lugar de un registro A si lo desea.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |Direcciones IP del servidor de grupo de servidores front-end (o a una dirección IP de director)  <br/>  DNS LB a *192.168.21.122 192.168.21.123 192.168.21.124*   |Requerido para la configuración automática, vea [Tutorial de los servicios de localización de clientes](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) de Skype Empresarial <br/> Registro o registros que apuntan a los servidores de grupo de servidores front-end o servidores de director de la red interna, o al servicio perimetral de acceso cuando el cliente es externo   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |HLB FE Pool VIP Or Director Pool HLB VIP , or SE/Director Server IP  <br/>  192.168.21.121  |La implementación de este registro es &#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>Puerto 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>Puerto 5061  |FQDN del grupo de servidores front-end  <br/>*FE-Pool. <span></span> contoso <span></span> .com*  |Habilita el inicio de sesión automático de usuario interno 1 en el servidor front-end/grupo de servidores o servidor SE/grupo de servidores que autentica y redirige las solicitudes de cliente para el inicio de sesión.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |FQDN del grupo de servidores front-end  <br/>_FE-Pool. <span></span> contoso <span></span> .com_  |Acceso de usuario interno &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Origen NTP necesario para dispositivos Lync Phone Edition   |Esto es necesario para admitir los teléfonos de escritorio.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | FQDN del servicio perimetral de acceso <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |Crea un registro SRV para cada dominio SIP que tenga clientes IOS o Windows Phone Mobile.   |Para soporte de cliente móvil   |
|A/AAAA   |DIRECCIÓN URL de administrador  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Panel de control de Skype Empresarial Server, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |dirección URL de meet  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Reuniones en línea, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |DIRECCIÓN URL de acceso telefónico  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Conferencias de acceso telefónico local, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN interno de servicios web  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Skype Empresarial Web Service usado por Skype Empresarial Web App   ||
|A/AAAA   |FQDN del grupo de servidores de Office Web Apps Server  <br/> OWA. <span></span> contoso <span></span> .com   | Dirección VIP del grupo de servidores de Office Web Apps Server <br/> 192.168.1.5   |Define el FQDN del grupo de servidores de Office Web Apps Server   ||
|A/AAAA   | FQDN web interno <br/> Web-int. <span></span> contoso <span></span> .com   | Dirección VIP del grupo de servidores front-end <br/> 192.168.21.121   |Define el FQDN web interno usado por Skype Empresarial Web App  <br/> Si usa el equilibrio de carga DNS en este grupo de servidores, el grupo de servidores front-end y la granja de servidores web interna no pueden tener el mismo FQDN.   ||

&#x2776; usado por un cliente para detectar el servidor front-end o el grupo de servidores front-end, y autenticarse y haber iniciado sesión como usuario. Para obtener más información, vea [Tutorial de los servicios de localización de clientes](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)de Skype Empresarial.

&#x2777; Esto solo es necesario para admitir clientes heredados anteriores a Lync 2013 y los teléfonos de escritorio.

&#x2778; En la situación en la que un dispositivo de comunicaciones unificadas está activado, pero un usuario nunca ha iniciado sesión en el dispositivo, el registro A permite al dispositivo detectar el servidor que hospeda el servicio web de actualización de dispositivos y obtener actualizaciones. En otro caso, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.

En el diagrama siguiente se muestra un ejemplo que incluye registros DNS internos y externos y muchos de los registros que se muestran en las tablas circundantes:

**Diagrama de red perimetral con direcciones IPv4 públicas**

![ejemplo de diagrama de red DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Asignaciones dns de red perimetral (interfaces internas y externas)**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Obligatorio|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN del grupo perimetral interno  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |Direcciones IP de grupo perimetral interno  <br/> 172.25.33.10, 172.25.33.11   |Direcciones IP de interfaz interna del grupo perimetral consolidado   |v   |
|A/AAAA   |FQDN del servidor perimetral  <br/>*Cons-1. <span></span> contoso <span></span> .com*  |IP de servidor de cara interna para un servidor en el grupo de servidores perimetrales  <br/> 172.25.33.10   |Cree un registro para cada servidor del grupo con el FQDN del servidor que apunte a su DIRECCIÓN IP del nodo de servidor interno en el grupo de servidores, vea Equilibrio de carga DNS en grupos de servidores [perimetrales.](load-balancing.md#BK_Edge)   |v   |
|A/AAAA   |FQDN del grupo de servidores perimetrales de acceso  <br/>*Access1. <span></span> contoso <span></span> .com*  |Direcciones IP externas del grupo de servidores perimetrales de acceso  <br/> 131.107.16.10, 131.107.16.11   |El servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico SIP (protocolo de inicio de sesión) saliente y entrante.   |v   |
|A/AAAA   |FQDN del grupo de servidores perimetrales de conferencia web  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |Direcciones IP externas del servicio perimetral de conferencia web  <br/> 131.107.16.90, 131.107.16.91   |El servicio perimetral de conferencia web permite a los usuarios externos unirse a reuniones hospedadas en su entorno interno de Skype Empresarial Server.   |v   |
|A/AAAA   |*av.\<sip-domain\>* FQDN del grupo de servidores <br/>*AV1. <span></span> contoso <span></span> .com*  |Direcciones IP externas perimetrales A/V  <br/> 131.107.16.170, 131.107.16.171   |El servicio perimetral A/V pone a disposición de los usuarios externos audio, vídeo, uso compartido de aplicaciones y transferencia de archivos.   |v   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |FQDN del grupo perimetral de acceso externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Localiza el grupo de servidores perimetrales . Consulte [Tutorial de los servicios de localización de clientes de Skype Empresarial](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |FQDN perimetral de acceso externo  <br/>_Access1. <span></span> contoso <span></span> .com_  |Se usa para el acceso de usuarios externos. Consulte [Tutorial de los servicios de localización de clientes de Skype Empresarial](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Se usa para la federación y la conectividad de mensajería instantánea pública   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |El servicio proxy XMPP acepta y envía mensajes de protocolo de presencia y mensajería extensible (XMPP) a y desde socios federados XMPP configurados.   |Y, para implementar federación, de lo contrario opcional  <br/> No disponible en Skype Empresarial Server 2019.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Para admitir el servicio de notificaciones de inserción y el servicio de notificaciones de inserción de Apple, creas un registro SRV para cada dominio SIP. &#x2778;  ||
|A/AAAA   |FQDN de servicios web de grupo de servidores front-end externos  <br/>*Web-ext. <span></span> contoso <span></span> .com*  |Dirección IP pública de proxy inverso, servidores proxy a la VIP de servicios web externos para el grupo de servidores front-end &#x2776; <br/> 131.107.155.1 proxy a 192.168.21.120   |Interfaz externa del grupo de servidores front-end usada por Skype Empresarial Web App   |v   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |Dirección IP pública de proxy inverso, se resuelve en la VIP de servicios web externos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director &#x2777; <br/> 131.107.155.1 proxy a 192.168.21.120   | Registro externo para la detección automática de cliente, también usado por Mobility, Skype Empresarial Web App y la aplicación web del programador, resuelto por el servidor proxy inverso <br/> Para admitir el servicio de notificaciones de inserción y el servicio de notificación de inserción de Apple, se crea un registro SRV para cada dominio SIP que tenga clientes de Microsoft Lync Mobile. 3  |v   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |Dirección IP pública de proxy inverso, se resuelve en la interfaz web externa del grupo de servidores front-end  <br/> 131.107.155.1 proxy a 192.168.21.120   |Proxy para Skype Empresarial Web Service  <br/> Ver [direcciones URL sencillas](dns.md#BK_Simple)  |v   |
|A/AAAA   |acceso telefónico.*\<sipdomain\>* <br/> acceso telefónico. *<span></span> contoso <span></span> .com*  |Dirección IP pública de proxy inverso, servidores proxy a la interfaz web externa para el grupo de servidores front-end  <br/> 131.107.155.1 proxy a 192.168.21.120   |Proxy para Skype Empresarial Web Service  <br/> Ver [direcciones URL sencillas](dns.md#BK_Simple)  |v   |
|A/AAAA   |FQDN del grupo de servidores de Office Web Apps Server  <br/> OWA. <span></span> contoso <span></span> .com   | Dirección IP pública de proxy inverso, servidores proxy a la interfaz web externa para Office Web Apps Server <br/> 131.107.155.1 proxy a 192.168.1.5   | Dirección VIP del grupo de servidores de Office Web Apps Server <br/> 192.168.1.5   |Define el FQDN del grupo de servidores de Office Web Apps Server   |

&#x2776; necesario para implementar la federación, de lo contrario es opcional.

&#x2777; usado por un cliente para detectar el servidor front-end o el grupo de servidores front-end, y autenticarse y haber iniciado sesión como usuario.

&#x2778; Este requisito solo se aplica a los clientes de dispositivos móviles basados en Apple o Microsoft. Los dispositivos Android y Nokia Symbian no usan notificaciones push.

 Para obtener más información sobre los servidores perimetrales y las redes perimetrales, consulte el contenido de planeación [de DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) del servidor perimetral.

> [!IMPORTANT]
> Skype Empresarial Server admite el uso de direccionamiento IPv6. Vea [Plan for IPv6 in Skype for Business](ipv6.md) para obtener más información.

> [!IMPORTANT]
> Para obtener más información sobre los FQDN, vea [Conceptos básicos de DNS](basics.md).

**DNS de cerebro dividido** 
 <a name="BK_split"></a>

DNS de cerebro dividido es una configuración dns donde tiene dos zonas DNS con el mismo espacio de nombres. La primera zona DNS controla las solicitudes internas, mientras que la segunda zona DNS controla las solicitudes externas, como se menciona en estas tablas. Para obtener más información sobre esto, [vea SPLIT-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Consideraciones híbridas
<a name="BK_Hybrid"> </a>

Si tiene previsto que algunos usuarios se alo usen en línea y otros se alo de forma local, consulte el artículo Planeación de conectividad híbrida de Skype Empresarial [Server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Deberá configurar DNS como normal para Skype Empresarial Server 2015 y agregar registros DNS adicionales.

También debe hacer referencia a "Direcciones URL e intervalos de direcciones IP de Office 365" en para confirmar que los usuarios tendrán acceso a los recursos en línea que [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) necesitarán.

## <a name="simple-urls"></a>Direcciones URL simples
<a name="BK_Simple"> </a>

Un localizador uniforme de recursos (URL) es una referencia a un recurso web que especifica su ubicación en una red de equipo y un protocolo usado para recuperarlo.

Skype Empresarial Server admite el uso de tres direcciones URL "sencillas" para acceder a los servicios:

- **Meet** se usa como la dirección URL base para todas las conferencias del sitio. Un ejemplo de una dirección URL sencilla de reunión es https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com. Una dirección URL para una reunión determinada puede ser https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com/_username_/7322994.

    Con la dirección URL sencilla De reunión, los vínculos para unirse a reuniones son fáciles de comprender y fáciles de comunicar.

- **El acceso telefónico local** habilita el acceso a la página web Configuración de conferencia de acceso telefónico local. Esta página muestra números de acceso telefónico local de conferencia con sus idiomas disponibles, información de conferencia asignada (es decir, para reuniones que no es necesario programar) y controles DTMF en la conferencia, y admite la administración del número de identificación personal (PIN) y la información de conferencia asignada. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios. Un ejemplo de la dirección URL sencilla de acceso telefónico es https:// <span></span> dialin. <span></span> contoso <span></span> .com.

- **El** administrador habilita el acceso rápido al Panel de control de Skype Empresarial Server. Desde cualquier equipo dentro de los firewalls de la organización, un administrador puede abrir el Panel de control de Skype Empresarial Server escribiendo la dirección URL sencilla del administrador en un explorador. La dirección URL simple de administración es de uso interno para la organización. Un ejemplo de la dirección URL simple de administrador es https:// <span></span> administrador. <span></span> contoso <span></span> .com.

Las direcciones URL sencillas se analizan con más detalle en [requisitos DNS](simple-urls.md)para direcciones URL sencillas en Skype Empresarial Server .

## <a name="dns-by-server-role"></a>DNS por rol de servidor
<a name="BK_Servers"> </a>

Puede establecer los nombres de estos grupos de servidores como desee, pero hacerlos memorables y reflejar su función en el sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS para servidores o grupos individuales

Estos requisitos de registro genéricos se aplican a cualquier rol de servidor usado por Skype Empresarial. Un grupo de servidores es un conjunto de servidores que ejecutan los mismos servicios que funcionan juntos para controlar las solicitudes de cliente dirigidas a ellos a través de un equilibrador de carga. Vea [Requisitos de equilibrio de carga para Skype Empresarial para obtener](load-balancing.md) más información

**Requisitos de registro DNS para roles de servidor/grupo (supone el equilibrio de carga DNS)**

|Escenario de implementación|Requisito de DNS|
|:-----|:-----|
|Un servidor:  <br/> Chat persistente, director, servidor de mediación, servidor front-end   |Registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|Grupo de servidores:  <br/> Chat persistente, director, servidor perimetral, servidor de mediación, front-end   |Un registro A interno que resuelve el nombre de dominio completo (FQDN) de cada nodo de servidor del grupo en su dirección IP.  <br/>**Ejemplo** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> Varios registros A internos que resuelven el nombre de dominio completo (FQDN) del grupo en las direcciones IP de los nodos de servidor del grupo.  <br/>**Ejemplo** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Temas DNS específicos del servidor perimetral

 Para planear la implementación de servidores perimetrales, revise [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)y Advanced Edge Server DNS planning for Skype for Business Server [2015,](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) que tiene las secciones siguientes.

- [Recuperación ante desastres de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Equilibrio de carga DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuración automática sin DNS de cerebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS de cerebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Tutorial de los servicios de localización de clientes de Skype Empresarial](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)