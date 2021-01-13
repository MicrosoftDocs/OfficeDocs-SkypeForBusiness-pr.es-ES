---
title: Requisitos de DNS para Skype Empresarial Server
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
ms.openlocfilehash: 3db3641e5b884ef5bca43222fcf001bd4c5a538a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825280"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos de DNS para Skype Empresarial Server

**Resumen:** Revise las consideraciones de DNS de este tema antes de implementar Skype Empresarial Server.

En este artículo solo se aborda la planeación de DNS para las implementaciones de Skype Empresarial Server en la red local de una organización. For Skype for Business Online refer to "Office 365 URLs and IP address ranges" at [https://aka.ms/o365ips](https://aka.ms/o365ips) .

Un servidor de servicio de nombres de dominio (DNS) asigna nombres de host (como www. <span></span> contoso <span></span> .com, presumiblemente un servidor web) a direcciones IP (como 10.10.10.10). Ayuda a los clientes y servidores interdependientes a comunicarse entre sí en la red. When you set up an implementation of Skype for Business Server 2015 you'll need to make sure the mapping of new server names (usually reflect the role they'll be taking on) matches the IP addresses they are assigned to.

Aunque esto puede parecer un poco desalentador al principio, el trabajo pesado para planear esto puede hacerse con la Herramienta de planeación de [Skype Empresarial Server 2015.](https://www.microsoft.com/download/details.aspx?id=50357) Una vez que haya pasado por las preguntas del asistente sobre las características que planea usar, para cada sitio que defina puede ver el informe DNS en el informe de administración perimetral y usar la información que aparece allí para crear los registros DNS. También puede realizar ajustes en muchos de los nombres y direcciones IP usados, para obtener más información, consulte [Review the DNS Report](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo de Excel y el informe DNS será una de las hojas de cálculo del archivo. Aunque esta herramienta incluye características en desuso de [Skype Empresarial Server 2019,](../../../SfBServer2019/deprecated.md)aún se puede usar para crear un plan inicial si estas características no están seleccionadas

Al instalar una nueva implementación como se describe en Crear registros DNS para Skype Empresarial [Server](../../deploy/install/create-dns-records.md) y crear la topología para Skype Empresarial Server, reconocemos que puede elegir usar las capacidades DNS integradas en Windows Server 2016 o un paquete DNS de terceros, por lo que conservaremos las discusiones de este artículo en general en lugar de específicas. Estamos detallando lo que se necesita y la forma en que cumple esa necesidad es su decisión.

Los administradores experimentados de Skype Empresarial, Lync y Conjunto de comunicaciones de Office probablemente encontrarán útiles las tablas siguientes. Si la tabla le resulta confusa, las secciones o artículos posteriores mostrarán algo de luz sobre los siguientes conceptos:

## <a name="summary-tables"></a>Tablas de resumen
<a name="BK_Summary"> </a>

En las tablas siguientes se muestran los registros DNS que Skype Empresarial Server usa para proporcionar servicios a los usuarios. Algunas son opcionales, ya que solo son necesarias para admitir determinadas características y se pueden omitir si no se desean. Los registros DNS necesarios para el acceso interno solo se encuentran en la primera tabla, y una implementación que permita el acceso interno y externo necesitará registros de ambas tablas.

**Asignaciones dns internas**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Obligatorio|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN del grupo de servidores front-end  <br/> *FE-pool. <span></span> contoso <span></span> .com*   |Direcciones IP del servidor del grupo de servidores front-end  <br/>  DNS LB a *192.168.21.122 192.168.21.123 192.168.21.124*   |Equilibrio de carga de DNS de grupos de servidores front-end. Asigna el nombre del grupo de servidores front-end a un conjunto de direcciones IP.  <br/> Consulte [Implementación del equilibrio de carga de DNS en grupos de servidores front-end y grupos de directores](load-balancing.md#BK_FE_Dir)  |v   |
|A/AAAA   | FQDN de cada servidor front-end o servidor Standard Edition de un grupo de servidores, o un servidor independiente <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> contoso <span></span> .com FE03. <span></span> contoso <span></span> .com*   |IP correspondiente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Asigna el nombre del servidor a su dirección IP.   |v   |
|A/AAAA   |FQDN de invalidación de servicios web internos del grupo de servidores de empresa  <br/> *Web-int. <span></span> contoso <span></span> .com*   |VIP de HLB para servicios web internos del servidor front-end  <br/> *192.168.21.120*   |Necesario para habilitar el tráfico web de cliente a servidor, como descargar la aplicación web de Skype Empresarial. También es necesario para los clientes móviles.   |v   |
|A/AAAA   |FQDN de invalidación de servicios web externos del grupo de servidores de empresa  <br/> *Web-ext. <span></span> contoso <span></span> .com*   |VIP de HLB para servicios web externos del servidor front-end  <br/>*68.123.56.90*   |Necesario para habilitar el tráfico web de cliente a servidor, como descargar la aplicación web de Skype Empresarial. Necesario si los clientes móviles resolverán DNS internamente. Puede resolverse en IP de proxy inverso de DMZ o IP de Internet.   ||
|A/AAAA   | FQDN del servidor SQL servidor back-end <br/> *SQL1. <span></span> contoso <span></span> .com*   |dirección IP del servidor  <br/> *192.168.11.90*   |Asigna el nombre del servidor de un servidor back-end SQL que trabaja con el grupo de servidores front-end a su dirección IP   ||
|A/AAAA   |FQDN del servidor reflejado SQL servidor back-end  <br/> *SQL2. <span></span> contoso <span></span> .com*   |dirección IP del servidor  <br/> *192.168.11.91*   |Asigna el nombre del servidor de un servidor back-end SQL reflejado que trabaja con el grupo de servidores front-end a su dirección IP   ||
|A/AAAA   |FQDN del grupo de directores  <br/>**Nota:** No aplicable al usar un servidor director independiente <br/> *DirPool. <span></span> contoso <span></span> .com*   |Direcciones IP del grupo de directores  <br/> DNS LB a *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Equilibrio de carga de DNS de servidores de grupo de directores. Asigna el nombre del grupo de servidores para el grupo de directores a una dirección IP, consulte Implementación del equilibrio de carga dns en grupos [de servidores front-end y grupos de directores](load-balancing.md#BK_FE_Dir) <br/> Un director puede autenticar a un usuario y es opcional.   ||
|A/AAAA   |Director FQDN   |Dirección IP del servidor de cada servidor director   |Asigna el nombre del grupo de servidores del director a una dirección IP, vea Implementar el equilibrio de carga dns en grupos [de servidores front-end y grupos de directores](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN del grupo de servidores de mediación   |Direcciones IP del grupo de servidores   |El rol de servidor de mediación es opcional. Puede localizar en co-ubicación los servicios proporcionados por un servidor de mediación al servidor o grupo de servidores front-end. Consulte [Uso del equilibrio de carga de DNS en grupos de servidores de mediación](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del servidor de mediación   |Dirección IP del servidor   |Puede localizar en co-ubicación los servicios proporcionados por un servidor de mediación al servidor o grupo de servidores front-end. Consulte [Uso del equilibrio de carga de DNS en grupos de servidores de mediación](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del servidor de chat persistente   |Dirección IP del servidor de chat persistente   |Se requiere un servidor de chat persistente para la característica de chat persistente y, de lo contrario, es opcional.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |IP de director o VIP del grupo de servidores front-end HLB  <br/>  192.168.21.121  |Servicio de detección automática interna1, necesario para la compatibilidad con la movilidad. Si el DNS interno se usa para resolverse en dispositivos móviles, debe apuntar a la DIRECCIÓN IP externa o a la DIRECCIÓN VIP de DMZ.  <br/> Para los servicios web, se requiere HLB en el grupo de servidores front-end, ya que HTTPS no puede aprovechar DNS. Para un grupo de servidores front-end o un grupo de directores, esto debe resolverse en una DIRECCIÓN VIP de HLB o una DIRECCIÓN IP normal para un servidor Standard Edition o un servidor director independiente.   |v   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |FQDN de grupo de SERVIDORES FE de HLB o FQDN de director  <br/> Web-int. <span></span> contoso <span></span> .com   |Servicio de detección automática interna1 <br/> Puede implementar esto como un CNAME en lugar de un registro A si lo desea.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |Direcciones IP del servidor de grupo de servidores front-end (o a una dirección IP de director)  <br/>  DNS LB a *192.168.21.122 192.168.21.123 192.168.21.124*   |Obligatorio para la configuración automática, consulte Tutorial de los servicios de localización [de clientes de Skype Empresarial](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Un registro o registros que apuntan a los servidores de grupo de servidores front-end o servidores director de la red interna, o al servicio perimetral de acceso cuando el cliente es externo   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |VIP del grupo de servidores FE de HLB o VIP de HLB del grupo de directores o IP del servidor SE/Director  <br/>  192.168.21.121  |La implementación de este registro es opcional &#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>Puerto 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>Puerto 5061  |FQDN del grupo de servidores front-end  <br/>*FE-Pool. <span></span> contoso <span></span> .com*  |Habilita el inicio de sesión automático de usuario interno 1 en el servidor o grupo de servidores front-end o servidor SE/grupo de servidores que autentica y redirige las solicitudes de inicio de sesión del cliente.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |FQDN del grupo de servidores front-end  <br/>_FE-Pool. <span></span> contoso <span></span> .com_  |Acceso de usuarios internos &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Origen NTP necesario para dispositivos Lync Phone Edition   |Esto es necesario para admitir los teléfonos de escritorio.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | FQDN del servicio perimetral de acceso <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |Cree un registro SRV para cada dominio SIP que tenga clientes IOS o Windows Phone Mobile.   |Para la compatibilidad con clientes móviles   |
|A/AAAA   |DIRECCIÓN URL de administrador  <br/>*Web-int. <span></span> contoso <span></span> .com*  |VIP del grupo HLB FE  <br/> 192.168.21.121   |Panel de control de Skype Empresarial Server, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |dirección URL de reunión  <br/>*Web-int. <span></span> contoso <span></span> .com*  |VIP del grupo HLB FE  <br/> 192.168.21.121   |Reuniones en línea, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |dirección URL de acceso telefónico  <br/>*Web-int. <span></span> contoso <span></span> .com*  |VIP del grupo HLB FE  <br/> 192.168.21.121   |Conferencia de acceso telefónico local, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN de servicios web internos  <br/>*Web-int. <span></span> contoso <span></span> .com*  |VIP del grupo HLB FE  <br/> 192.168.21.121   |Servicio web de Skype Empresarial usado por la aplicación web de Skype Empresarial   ||
|A/AAAA   |FQDN del grupo de servidores de Office Web Apps Server  <br/> OWA. <span></span> contoso <span></span> .com   | Dirección VIP del grupo de servidores de Office Web Apps Server <br/> 192.168.1.5   |Define el FQDN del grupo de servidores de Office Web Apps Server   ||
|A/AAAA   | FQDN web interno <br/> Web-int. <span></span> contoso <span></span> .com   | Dirección VIP del grupo de servidores front-end <br/> 192.168.21.121   |Define el FQDN web interno usado por Skype Empresarial Web App  <br/> Si usa el equilibrio de carga de DNS en este grupo de servidores, el grupo de servidores front-end y la granja de servidores web interna no pueden tener el mismo FQDN.   ||

&#x2776; lo usa un cliente para detectar el servidor front-end o el grupo de servidores front-end, y autenticarse e haber iniciado sesión como usuario. Encontrará más información sobre esto en [tutorial de clientes de Skype Empresarial que localizan servicios.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)

&#x2777; Esto solo es necesario para admitir clientes heredados anteriores a Lync 2013 y teléfonos de escritorio.

&#x2778; En la situación en la que un dispositivo de comunicaciones unificadas está activado, pero un usuario nunca ha iniciado sesión en el dispositivo, el registro A permite que el dispositivo detecte el servidor que hospeda el servicio web de actualización de dispositivos y obtenga actualizaciones. En otro caso, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.

En el siguiente diagrama se muestra un ejemplo que incluye registros DNS internos y externos, así como muchos de los registros que se muestran en las tablas que lo rodean:

**Diagrama de red perimetral con direcciones IPv4 públicas**

![ejemplo de diagrama de red DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Asignaciones DNS de red perimetral (interfaces internas y externas)**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Obligatorio|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN del grupo de servidores perimetrales internos  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |Direcciones IP del grupo de servidores perimetrales orientados internamente  <br/> 172.25.33.10, 172.25.33.11   |Direcciones IP de la interfaz interna del grupo de servidores perimetrales consolidado   |v   |
|A/AAAA   |FQDN del servidor perimetral  <br/>*Cons-1. <span></span> contoso <span></span> .com*  |IP de servidor orientado internamente para un servidor del grupo de servidores perimetrales  <br/> 172.25.33.10   |Cree un registro para cada servidor del grupo de servidores con el FQDN del servidor que señale a su DIRECCIÓN IP del nodo de servidor interno en el grupo de servidores, consulte Equilibrio de carga de DNS en grupos de servidores [perimetrales.](load-balancing.md#BK_Edge)   |v   |
|A/AAAA   |FQDN del grupo de servidores de servicio perimetral de acceso  <br/>*Access1. <span></span> contoso <span></span> .com*  |Direcciones IP externas del grupo de servidores perimetrales de acceso  <br/> 131.107.16.10, 131.107.16.11   |El servicio perimetral de acceso proporciona un único punto de conexión de confianza para el tráfico SIP (protocolo de inicio de sesión) saliente y entrante.   |v   |
|A/AAAA   |FQDN del grupo de servidores perimetrales de conferencia web  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |Direcciones IP externas del servicio perimetral de conferencia web  <br/> 131.107.16.90, 131.107.16.91   |El servicio perimetral de conferencia web permite a los usuarios externos unirse a reuniones hospedadas en su entorno interno de Skype Empresarial Server.   |v   |
|A/AAAA   |*av.\<sip-domain\>* FQDN del grupo de servidores <br/>*AV1. <span></span> contoso <span></span> .com*  |Direcciones IP externas del servidor perimetral A/V  <br/> 131.107.16.170, 131.107.16.171   |El servicio perimetral A/V pone a disposición de los usuarios externos audio, vídeo, uso compartido de aplicaciones y transferencia de archivos.   |v   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |FQDN del grupo de servidores perimetrales de acceso externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Busca el grupo de servidores perimetrales. See [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |FQDN perimetral de acceso externo  <br/>_Access1. <span></span> contoso <span></span> .com_  |Se usa para el acceso de usuarios externos. See [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |v   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Se usa para federación y conectividad de mensajería instantánea pública   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |El servicio de proxy XMPP acepta y envía mensajes de protocolo extensible de mensajería y presencia (XMPP) a socios federados XMPP configurados y desde estos.   |Y, para implementar la federación; de lo contrario, opcional  <br/> No disponible en Skype Empresarial Server 2019.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN perimetral de acceso externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Para admitir el servicio de notificación de inserción y el servicio de notificación de inserción de Apple, cree un registro SRV para cada dominio SIP. &#x2778;  ||
|A/AAAA   |FQDN de servicios web de grupo de servidores front-end externos  <br/>*Web-ext. <span></span> contoso <span></span> .com*  |Dirección IP pública de proxy inverso, servidores proxy a la DIRECCIÓN VIP de servicios web externos para el grupo de servidores front-end &#x2776; <br/> Proxy 131.107.155.1 a 192.168.21.120   |Interfaz externa del grupo de servidores front-end usada por Skype Empresarial Web App   |v   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |La dirección IP pública de proxy inverso se resuelve en la dirección VIP de servicios web externos para el grupo de servidores director, si tiene uno, o para el grupo de servidores front-end si no tiene una dirección &#x2777; <br/> Proxy 131.107.155.1 a 192.168.21.120   | Registro externo para la Detección automática de cliente, también usado por Mobility, Skype Empresarial Web App y aplicación web del programador, resuelto por el servidor proxy inverso <br/> Para admitir el servicio de notificación de inserción y el servicio de notificación de inserción de Apple, cree un registro SRV para cada dominio SIP que tenga clientes de Microsoft Lync Mobile. 3   |v   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |Dirección IP pública de proxy inverso, se resuelve en la interfaz web externa para el grupo de servidores front-end  <br/> Proxy 131.107.155.1 a 192.168.21.120   |Proxy al servicio web de Skype Empresarial  <br/> Ver [direcciones URL sencillas](dns.md#BK_Simple)  |v   |
|A/AAAA   |acceso telefónico.*\<sipdomain\>* <br/> acceso telefónico. *<span></span> contoso <span></span> .com*  |Dirección IP pública de proxy inverso, servidores proxy a la interfaz web externa para el grupo de servidores front-end  <br/> Proxy 131.107.155.1 a 192.168.21.120   |Proxy al servicio web de Skype Empresarial  <br/> Ver [direcciones URL sencillas](dns.md#BK_Simple)  |v   |
|A/AAAA   |FQDN del grupo de servidores de Office Web Apps Server  <br/> OWA. <span></span> contoso <span></span> .com   | Dirección IP pública de proxy inverso, servidores proxy a la interfaz web externa para Office Web Apps Server <br/> 131.107.155.1 proxy a 192.168.1.5   | Dirección VIP del grupo de servidores de Office Web Apps Server <br/> 192.168.1.5   |Define el FQDN del grupo de servidores de Office Web Apps Server   |

&#x2776; necesario para implementar la federación; de lo contrario, es opcional.

&#x2777; lo usa un cliente para detectar el servidor front-end o el grupo de servidores front-end, y autenticarse e haber iniciado sesión como usuario.

&#x2778; este requisito se aplica solo a los clientes de dispositivos móviles basados en Apple o Microsoft. Los dispositivos Android y Nokia Symbian no usan notificaciones de inserción.

 Para obtener más información sobre los servidores perimetrales y las redes perimetrales, consulte el contenido de planeación [de DNS del servidor](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) perimetral.

> [!IMPORTANT]
> Skype Empresarial Server admite el uso de direccionamiento IPv6. Vea [plan para IPv6 en Skype Empresarial](ipv6.md) para obtener más información.

> [!IMPORTANT]
> Para obtener más información sobre los FQDN, consulte [conceptos básicos de DNS.](basics.md)

**DNS de cerebro dividido** 
 <a name="BK_split"></a>

DNS de cerebro dividido es una configuración DNS en la que tiene dos zonas DNS con el mismo espacio de nombres. La primera zona DNS controla las solicitudes internas, mientras que la segunda zona DNS controla las solicitudes externas, como se menciona en estas tablas. Para obtener más información, consulte [DNS de cerebro dividido.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

## <a name="hybrid-considerations"></a>Consideraciones híbridas
<a name="BK_Hybrid"> </a>

Si piensa que algunos usuarios están en línea y otros en local, consulte el artículo de planeación de conectividad híbrida de Skype Empresarial [Server 2019.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) Tendrá que configurar DNS como normal para Skype Empresarial Server 2015 y también agregar registros DNS adicionales.

También debe consultar "Direcciones URL e intervalos de direcciones IP de Office 365" para confirmar que los usuarios tendrán acceso a los recursos en línea que [https://aka.ms/o365ips](https://aka.ms/o365ips) necesitarán.

## <a name="simple-urls"></a>Direcciones URL simples
<a name="BK_Simple"> </a>

Un localizador uniforme de recursos (URL) es una referencia a un recurso web que especifica su ubicación en una red de equipo y un protocolo usado para recuperarlo.

Skype Empresarial Server admite el uso de tres direcciones URL "sencillas" para acceder a los servicios:

- **Meet** se usa como la dirección URL base para todas las conferencias del sitio. Un ejemplo de una dirección URL sencilla de reunión es https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com. Una dirección URL para una reunión determinada puede ser https: <span></span> // <span></span> meet. <span></span> contoso <span></span> _.com/username_/7322994.

    Con la dirección URL sencilla de reunión, los vínculos para unirse a reuniones son fáciles de comprender y fáciles de comunicar.

- **El acceso telefónico local** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. Esta página muestra los números de acceso telefónico de conferencia con sus idiomas disponibles, la información de conferencia asignada (es decir, para reuniones que no es necesario programar) y controles DTMF en la conferencia, y admite la administración del número de identificación personal (PIN) y la información de conferencia asignada. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios. Un ejemplo de la dirección URL sencilla de acceso telefónico es https:// <span></span> marcado. <span></span> contoso <span></span> .com.

- **La** administración permite el acceso rápido al Panel de control de Skype Empresarial Server. Desde cualquier equipo dentro de los firewalls de su organización, un administrador puede abrir el Panel de control de Skype Empresarial Server escribiendo la dirección URL sencilla de administración en un explorador. La dirección URL simple de administración es de uso interno para la organización. Un ejemplo de la dirección URL sencilla de administración es https:// <span></span> administrador. <span></span> contoso <span></span> .com.

Las direcciones URL sencillas se de abordan con más detalle en los requisitos dns para direcciones URL sencillas [en Skype Empresarial Server.](simple-urls.md)

## <a name="dns-by-server-role"></a>DNS por rol de servidor
<a name="BK_Servers"> </a>

Puede establecer los nombres de estos grupos de servidores y servidores como desee, pero hacerlos memorables y reflejar su función en el sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS para servidores o grupos individuales

Estos requisitos de registro genéricos se aplican a cualquier rol de servidor usado por Skype Empresarial. Un grupo de servidores es un conjunto de servidores que ejecutan los mismos servicios que funcionan conjuntamente para administrar las solicitudes de cliente dirigidas a ellos a través de un equilibrador de carga. Consulte [los requisitos de equilibrio de carga para Skype Empresarial para](load-balancing.md) obtener más información

**Requisitos de registros DNS para roles de servidor/grupo de servidores (se supone que el equilibrio de carga de DNS)**

|Escenario de implementación|Requisito de DNS|
|:-----|:-----|
|Un servidor:  <br/> Chat persistente, director, servidor de mediación, servidor front-end   |Registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|Grupo de servidores:  <br/> Chat persistente, director, servidor perimetral, servidor de mediación, front-end   |Un registro A interno que resuelve el nombre de dominio completo (FQDN) de cada nodo de servidor del grupo en su dirección IP.  <br/>**Ejemplo** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> Varios registros A internos que resuelven el nombre de dominio completo (FQDN) del grupo en las direcciones IP de los nodos de servidor del grupo.  <br/>**Ejemplo** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Temas DNS específicos del servidor perimetral

 Para planear la implementación de servidores perimetrales, revise [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)y Advanced Edge Server DNS planning for Skype for Business Server [2015,](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) que tiene las siguientes secciones:

- [Recuperación ante desastres de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Equilibrio de carga de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuración automática sin DNS de cerebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS de cerebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Tutorial de los servicios de búsqueda de clientes de Skype Empresarial](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


