---
title: Requisitos de DNS de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumen: Revise las consideraciones de DNS en este tema antes de implementar Skype para Business Server.'
ms.openlocfilehash: 649528c21254625b1aac8d2933c59988138b38b1
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069583"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos de DNS de Skype para Business Server

**Resumen:** Revise las consideraciones de DNS en este tema antes de implementar Skype para Business Server.

En este artículo sólo direcciones DNS planeación de Skype para las implementaciones de Business Server en la red de la organización local. Para Skype para profesionales Online consulte "IP y URL de Office 365 intervalos de direcciones" en [https://aka.ms/o365ips](https://aka.ms/o365ips).

Un servidor de servicio (de dominio DNS) del nombre de dominio asigna nombres de host (como www.<span> </span> Contoso<span></span>.com, supuestamente en un servidor web) a direcciones IP (por ejemplo, 10.10.10.10). Ayuda a los clientes y servidores interdependientes comunican entre sí en la red. Al configurar una implementación de Skype para Business Server 2015 necesita para asegurarse de que la asignación de nuevos nombres de servidor (que normalmente refleja la función tendremos en) coincide con las direcciones IP que están asignados.

Aunque esto puede parecer complicado bit en primer lugar, el trabajo para planear esto puede realizarse mediante el [Skype para la herramienta de planeación de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Una vez que se ha desplazado a través de las preguntas del asistente acerca de qué características que se va a utilizar, para cada sitio que defina se puede ver el informe de DNS en el informe de administración perimetral y usar la información que aparece no existe para crear sus registros DNS. También puede realizar ajustes en muchos de los nombres y las direcciones IP utilizadas para obtener más información vea [revisión del informe de DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo de Excel y el informe de DNS será una de las hojas de cálculo en el archivo. Mientras esta herramienta incluye características [en desuso de Skype para Business Server 2019](../../../SfBServer2019/deprecated.md), aún se puede usar para crear un plan inicial si esas características no se han seleccionado

Cuando va a instalar una nueva implementación tal como se describe en [crear registros DNS para Skype para Business Server](../../deploy/install/create-dns-records.md) y la creación de la topología de Skype para Business Server, sabemos se puede optar por usar las capacidades de DNS integradas en Windows Server 2016 o un paquete DNS de terceros, por lo que se mantendrá las discusiones en este artículo general en lugar de específicos. Estamos que detallan lo que necesita, y cómo satisfacer dicha necesidad es su decisión para realizar.

Skype con experiencia para los administradores de negocios, Lync y el conjunto de aplicaciones de Office Communications probablemente útil en las tablas siguientes. Si la tabla es confusa para usted, las secciones posterior o artículos tiene como finalidad explicar en los siguientes conceptos:

## <a name="summary-tables"></a>Tablas de resumen
<a name="BK_Summary"> </a>

Las siguientes tablas muestran los registros DNS que Skype para Business Server usa para proporcionar servicios a los usuarios. Algunas son opcionales en que sólo son necesarios para admitir determinadas características, y puede omitirse si no se desean esas características. Los registros DNS necesarios para el acceso interno sólo se encuentran en la primera tabla y una implementación que permite el acceso interno y externo necesitará registros de ambas tablas.

**Asignaciones DNS interno**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Requerido|
|:-----|:-----|:-----|:-----|:-----|
|A O AAAA   |Servidor front-end FQDN  <br/> *FE-pool. <span> </span>contoso<span></span>.com*   |Direcciones IP de servidor de grupo de servidores de Front-End  <br/>  Libras de DNS para *192.168.21.122 192.168.21.123 192.168.21.124*   |Equilibrio de carga de DNS de grupos de servidores Front-End. Asigna el nombre de grupo de servidores Front-End a un conjunto de direcciones IP.  <br/> Vea [implementar DNS equilibrio de carga en los grupos de servidores Front-End y grupos de directores](load-balancing.md#BK_FE_Dir)  |Y   |
|A O AAAA   | FQDN de cada servidor Front-End o servidor Standard Edition en un grupo de servidores o un servidor independiente <br/>  *FE01. <span> </span>contoso. <span> </span>FE02 com. <span> </span>contoso<span></span>.com FE03. <span> </span>contoso<span></span>.com*   |IP correspondiente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Asigna el nombre del servidor en su dirección IP.   |Y   |
|A O AAAA   |Servicios de Web internos de grupo de servidores Enterprise invalidar FQDN  <br/> *Web-int.<span></span>contoso<span></span>.com*   |HLB VIP para servicios Web internos de servidor de Front-End  <br/> *192.168.21.120*   |Necesario para habilitar el cliente para el tráfico web del servidor, como una descarga el Skype para la aplicación empresarial de Web. También se necesita para los clientes móviles.   |Y   |
|A O AAAA   |Servicios Web externos de grupo de servidores de Enterprise invalidar FQDN  <br/> *Web-ext<span></span>contoso<span></span>.com*   |HLB VIP para servicios Web externos de servidor de Front-End  <br/>*68.123.56.90*   |Necesario para habilitar el cliente para el tráfico web del servidor, como una descarga el Skype para la aplicación empresarial de Web. Requerido si los clientes móviles se puede resolver con DNS internamente. Puede resolver en IP de Proxy inverso DMZ o Internet.   ||
|A O AAAA   | Realizar una copia de FQDN del servidor de SQL Server de final <br/> *SQL1. <span> </span>contoso<span></span>.com*   |dirección IP del servidor  <br/> *192.168.11.90*   |Asigna el nombre del servidor para un servidor SQL back-end, trabajar con el grupo de servidores Front-End en su dirección IP   ||
|A O AAAA   |Realizar una copia de FQDN del servidor SQL de End servidor reflejado  <br/> *SQL2. <span> </span>contoso<span></span>.com*   |dirección IP del servidor  <br/> *192.168.11.91*   |Asigna el nombre del servidor para un servidor de reflejo SQL back-end trabajar con el grupo de servidores Front-End en su dirección IP   ||
|A O AAAA   |FQDN del grupo de servidores de director  <br/>**Nota:** No se aplica cuando se usa un servidor de Director independiente <br/> *DirPool. <span> </span>contoso<span></span>.com*   |Direcciones IP de grupo de servidores de director  <br/> Libras de DNS para *192.168.21.132, 192.168.21.133, 192.168.21.134*   |DNS equilibrio de carga de los servidores del grupo de directores. Se asigna el grupo de servidores de nombre para el grupo de directores como una dirección IP, vea [Implementación de equilibrio de carga DNS en grupos de servidores Front-End y grupos de directores](load-balancing.md#BK_FE_Dir) <br/> Un Director es opcional y puede autenticar un usuario.   ||
|A O AAAA   |FQDN del director   |Dirección IP del servidor de cada servidor de Director   |Se asigna el grupo de servidores de nombre para el Director como una dirección IP, vea [Implementación de equilibrio de carga DNS en grupos de servidores Front-End y grupos de directores](load-balancing.md#BK_FE_Dir)  ||
|A O AAAA   |FQDN del grupo de servidores de mediación   |Direcciones IP de grupo de servidores   |El rol de servidor de mediación es opcional. Puede ubicar los servicios proporcionados por un servidor de mediación para el servidor Front-End o un grupo de servidores. Vea [Using en grupos de servidores de mediación de equilibrio de carga DNS](load-balancing.md#BK_Mediation)  ||
|A O AAAA   |FQDN del servidor de mediación   |Dirección IP del servidor   |Puede ubicar los servicios proporcionados por un servidor de mediación para el servidor Front-End o un grupo de servidores. Vea [Using en grupos de servidores de mediación de equilibrio de carga DNS](load-balancing.md#BK_Mediation)  ||
|A O AAAA   |FQDN del servidor de Chat en grupo   |Dirección IP del servidor de Chat persistente   |Un servidor de Chat persistente es necesario para la característica de Chat persistente y en caso contrario, es opcional.   ||
|A O AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>contoso<span></span>.com*   |Grupo de servidores Front-End de HLB VIP o IP de Director  <br/>  192.168.21.121  |AutoDiscover Service1 interno, necesario para la movilidad. Si se utiliza DNS interno para resolver para dispositivos móviles, deben apuntar a la dirección IP externa o DMZ VIP.  <br/> Para los servicios Web necesitamos HLB en el grupo de servidores Front-End como HTTPS no puede sacar provecho de DNS. Para el grupo de servidores Front-End o grupo de servidores de Director que esto debe se resuelve en un HLB VIP o una IP regular para un servidor Standard edition o un servidor Director independiente.   |Y   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>.com*   |FQDN del grupo HLB FE o el FQDN del Director  <br/> Web-int.<span></span>contoso<span></span>.com   |Service1 de detección automática interna <br/> Puede implementar como un CNAME en lugar de un registro si así lo desea.   ||
|A O AAAA   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>.com*  |Servidor front-end de dirección IP del servidor (dirección o a un cada IP de Director direcciones)  <br/>  Libras de DNS para *192.168.21.122 192.168.21.123 192.168.21.124*   |Es necesario para la configuración automática, vea el [Tutorial de Skype para los clientes empresariales de ubicación de servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Un registro o registros que señala a los servidores del grupo de servidores Front-End o servidores de Director en la red interna o el servicio de servidor perimetral de acceso cuando el cliente es externo   |& #x 2777;  |
|A O AAAA   |UCUpdates-r2. * \<sipdomain\>* <br/> UCUpdates-r2. * <span> </span>contoso<span></span>.com*  |IP de servidor SE/Director o grupo de servidores de FE de HLB VIP o Director del grupo HLB VIP  <br/>  192.168.21.121  |La implementación de este registro es opcional & #x 2778;  ||
|SRV   |\_sipinternaltls. \_tcp. * \<sipdomain\> * <br/>Puerto 5061 <br/>\_sipinternaltls. \_tcp. * <span> </span>contoso<span></span>.com* <br/>Puerto 5061  |Servidor front-end FQDN  <br/>*FE-Pool. <span> </span>contoso<span></span>.com*  |Permite el usuario interno de sesión automático 1 para el servidor o grupo de servidores Front-End o ingeniero o grupo de servidores que se autentica y redirige las solicitudes de inicio de sesión de clientes.  |& #x 2777; |
|A O AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *contoso<span></span>.com*  |Servidor front-end FQDN  <br/>_FE-Pool. <span> </span>contoso<span></span>.com_  |_AMP_ de acceso de usuario interno #x 2776;  |& #x 2777;  |
|SRV   | \_NTP. \_udp. * \<sipdomain\> * <br/> \_NTP. \_udp. <span> </span> *contoso<span></span>.com*  |Servidores horarios FQDN  <br/> america.pool.ntp.org del Norte   |Origen NTP requerido para dispositivos de Lync Phone Edition   |Este proceso es necesario para admitir los auriculares de escritorio.   |
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. <span> </span> *contoso<span></span>.com*  | Servicio perimetral de acceso FQDN <br/> EdgePool-int.<span></span>*contoso<span></span>.com*  |Crear un registro SRV para cada dominio SIP que tiene IOS o Windows phone clientes móviles.   |Para compatibilidad con clientes móviles   |
|A O AAAA   |dirección URL de administración  <br/>*Web-int.<span></span>contoso<span></span>.com*  |Grupo de servidores de FE de HLB VIP  <br/> 192.168.21.121   |Skype para el Panel de Control de servidor empresarial, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A O AAAA   |cumple con la dirección URL  <br/>*Web-int.<span></span>contoso<span></span>.com*  |Grupo de servidores de FE de HLB VIP  <br/> 192.168.21.121   |Reuniones en línea, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A O AAAA   |dirección URL de acceso telefónico  <br/>*Web-int.<span></span>contoso<span></span>.com*  |Grupo de servidores de FE de HLB VIP  <br/> 192.168.21.121   |Conferencia de acceso telefónico, vea [Direcciones URL sencillas](dns.md#BK_Simple)  ||
|A O AAAA   |FQDN de servicios Web interno  <br/>*Web-int.<span></span>contoso<span></span>.com*  |Grupo de servidores de FE de HLB VIP  <br/> 192.168.21.121   |Skype para servicio Web de negocio utilizados por Skype para la aplicación empresarial de Web   ||
|A O AAAA   |FQDN del grupo de Office Web Apps Server  <br/> OWA. <span> </span>contoso<span></span>.com   | Grupo de servidores de Office Web Apps Server dirección VIP <br/> 192.168.1.5   |Define el FQDN del grupo de Office Web Apps Server   ||
|A O AAAA   | El FQDN Web interno <br/> Web-int.<span></span>contoso<span></span>.com   | Servidor front-end dirección VIP <br/> 192.168.21.121   |Define el FQDN Web interno utilizado por Skype para la aplicación empresarial de Web  <br/> Si se usa en este grupo de servidores de equilibrio de carga DNS, su grupo de servidores Front-End y de la granja de servidores web interno no pueden tener el mismo FQDN.   ||

& #x 2776; Utilizado por un cliente para detectar el grupo de servidores Front-End o de servidor Front-End y ser autenticados y ha iniciado sesión en como un usuario. Es más detalle en este [Tutorial de Skype para clientes empresariales](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)localizar servicios.

& #x 2777; Este proceso sólo es necesario para admitir a los clientes heredados antes de Lync 2013 y auriculares de sobremesa.

& #x 2778; En la situación donde está activado un dispositivo de comunicaciones unificadas, pero un usuario nunca ha iniciado sesión en el dispositivo, el registro permite que el dispositivo detectar el servidor que hospeda el servicio Web de actualización de dispositivos y obtener actualizaciones. De lo contrario, los dispositivos obtienen la información del servidor a través del aprovisionamiento en banda la primera vez que un usuario inicia sesión.

En el siguiente diagrama muestra un ejemplo que incluye los registros DNS internos y externos y muchos de los registros que se muestran en las tablas que lo rodea:

**Diagrama de red perimetral con las direcciones IPv4 públicas**

![ejemplo de diagrama de red DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Asignaciones DNS de red perimetral (las interfaces interna y externas)**

|Tipo de registro|Valor|Se resuelve en|Finalidad|Requerido|
|:--- |:--- |:--- |:--- |:--- |
|A O AAAA   |FQDN del grupo perimetral interna  <br/>*EdgePool-int.<span></span>contoso<span></span>.com*  |Direcciones IP de grupo de servidores de internal orientado perimetral  <br/> 172.25.33.10, 172.25.33.11   |Consolidar las direcciones IP de interfaz interna de grupo de servidores perimetrales   |Y   |
|A O AAAA   |FQDN del servidor perimetral  <br/>*Inconvenientes-1. <span> </span>contoso<span></span>.com*  |Dirección IP del servidor interno orientado para un servidor en el grupo de servidores perimetrales  <br/> 172.25.33.10   |Crear un registro para cada servidor del grupo de servidores con el FQDN del servidor que señala a su IP de nodo de servidor interno en el grupo de servidores, vea [El equilibrio de carga DNS en grupos de servidores perimetrales](load-balancing.md#BK_Edge).   |Y   |
|A O AAAA   |Servicio perimetral FQDN del grupo de servidores de acceso  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Obtener acceso a direcciones IP externas de grupo de servidores de servicio de servidor perimetral  <br/> 131.107.16.10, 131.107.16.11   |El servicio de servidor perimetral de acceso proporciona un punto de conexión de confianza, solo para el tráfico de protocolo de inicio de sesión (SIP) entrante y saliente.   |Y   |
|A O AAAA   |Servicio de servidor perimetral de conferencia Web FQDN del grupo de servidores  <br/>*Webcon1. <span> </span>contoso<span></span>.com*  |Las direcciones IP externas de servicio de servidor perimetral de conferencia Web  <br/> 131.107.16.90, 131.107.16.91   |El servicio de servidor perimetral de conferencia Web permite a los usuarios externos unirse a reuniones que se hospedan en su Skype interna para el entorno de servidor empresarial.   |Y   |
|A O AAAA   |*av.\<dominio sip\> * FQDN del grupo <br/>*AV1. <span> </span>contoso<span></span>.com*  |A / direcciones de IP externa perimetral de A/v  <br/> 131.107.16.170, 131.107.16.171   |El / servicio perimetral A/v realiza audio, vídeo, uso compartido de aplicaciones y transferencia de archivos disponibles para externo a los usuarios.   |Y   |
|CNAME   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>.com*  |Grupo de servidores perimetrales de acceso externo FQDN  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Busca el grupo de servidores perimetrales. Vea el [Tutorial de Skype para los clientes empresariales de ubicación de servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_tls. * \<sipdomain\> * <br/>\_SIP. \_tls. <span> </span> *contoso<span></span>.com*  |FQDN de servidor perimetral de acceso externo  <br/>_Access1. <span> </span>contoso<span></span>.com_  |Se usa para el acceso de usuarios externos. Vea el [Tutorial de Skype para los clientes empresariales de ubicación de servicios](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. <span> </span> *contoso<span></span>.com*  |FQDN de servidor perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Utilizado para la federación y la conectividad de mensajería instantánea pública   |& #x 2776;  |
|SRV   |\_servidor de XMPP. \_tcp. *<sipdomain\> * <br/>\_servidor de XMPP. \_tcp. * <span> </span>contoso<span></span>.com*  |FQDN de servidor perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>.com*  |El servicio Proxy XMPP acepta y envía los mensajes de protocolo (XMPP) de presencia y mensajería extensible a y configurado corresponde a socios federados XMPP.   |Y, para implementar la federación, en caso contrario, opcional  <br/> No está disponible en Skype para Business Server 2019.|
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. * <span> </span>contoso<span></span>.com*  |FQDN de servidor perimetral de acceso externo  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Para admitir el servicio de notificación de inserción y el servicio de notificación de inserción de Apple, cree un registro SRV para cada dominio SIP. & #x 2778;  ||
|A O AAAA   |FQDN de los servicios web externos de grupo de servidores Front-End  <br/>*Web-ext<span></span>contoso<span></span>.com*  |Dirección IP pública del proxy, servidores proxy inversos para la VIP de servicios Web externo para su & de grupo de servidores Front-End #x 2776; <br/> 131.107.155.1 proxy de a 192.168.21.120   |Front-End del grupo externo interfaz utilizada por Skype para la aplicación empresarial de Web   |Y   |
|AAAA/A O CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>contoso<span></span>.com*  |Invertir la dirección IP pública del proxy, resuelve a la VIP de servicios Web externos para el grupo de servidores Director, si dispone de uno, o para el grupo de servidores Front-End si no tiene un Director & #x 2777; <br/> 131.107.155.1 proxy de a 192.168.21.120   | Registro externo para el cliente de detección automática, también la utilizan movilidad, Skype para la aplicación empresarial de Web y el programador Web app, resuelto por el servidor proxy inverso <br/> Para admitir el servicio de notificación de inserción y el servicio de notificación de inserción de Apple, cree un registro SRV para cada dominio SIP que tenga clientes de Microsoft Lync Mobile. 3  |Y   |
|A O AAAA   |cumplir. * \<sipdomain\>* <br/> cumplir. * <span> </span>contoso<span></span>.com*  |Invertir la dirección IP pública del proxy, resuelve a la interfaz de Web externa para el grupo de servidores Front-End  <br/> 131.107.155.1 proxy de a 192.168.21.120   |Proxy de Skype para el servicio Web de negocio  <br/> Vea [las direcciones URL sencillas](dns.md#BK_Simple)  |Y   |
|A O AAAA   |marcado-pda.*\<sipdomain\>* <br/> marcado-pda.*<span></span>contoso<span></span>.com*  |Dirección IP pública del proxy, servidores proxy inversos para la interfaz externa de Web para el grupo de servidores Front-End  <br/> 131.107.155.1 proxy de a 192.168.21.120   |Proxy de Skype para el servicio Web de negocio  <br/> Vea [las direcciones URL sencillas](dns.md#BK_Simple)  |Y   |
|A O AAAA   |FQDN del grupo de Office Web Apps Server  <br/> OWA. <span> </span>contoso<span></span>.com   | Dirección IP pública de proxy inverso, los servidores proxy para la interfaz externa de Web para Office Web Apps Server <br/> 131.107.155.1 proxy de a 192.168.1.5   | Grupo de servidores de Office Web Apps Server dirección VIP <br/> 192.168.1.5   |Define el FQDN del grupo de Office Web Apps Server   |

& #x 2776; Necesarios para implementar la federación, en caso contrario, opcional.

& #x 2777; Utilizado por un cliente para detectar el servidor front-end o el grupo de servidores Front-End y ser autenticados y ha iniciado sesión en como un usuario.

& #x 2778; Este requisito se aplica sólo a los clientes de Apple o dispositivos móviles basadas en Microsoft. Los dispositivos Android y Nokia Symbian no usan notificaciones de inserción.

 Para obtener más información acerca de los servidores perimetrales y redes perimetrales, vea el contenido de [planeación de DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) del servidor perimetral.

> [!IMPORTANT]
> Skype para Business Server admite el uso de direcciones IPv6. Para obtener más información, consulte [Plan para IPv6 en Skype para la empresa](ipv6.md) .

> [!IMPORTANT]
> Para obtener más detalles acerca de los FQDN, consulte [conceptos básicos DNS](basics.md).

**Dividir brain DNS** 
 <a name="BK_split"> </a>

Dividir brain DNS es una configuración de DNS en el que tiene dos zonas DNS con el mismo espacio de nombres. La primera zona DNS administra las solicitudes internas, mientras que la segunda zona DNS administra las solicitudes externas, como se ha mencionado en estas tablas. Para obtener más información acerca de este [DNS de horizonte dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS), consulte.

## <a name="hybrid-considerations"></a>Consideraciones sobre la híbrida
<a name="BK_Hybrid"> </a>

Si planea tener unos usuarios hospedados en línea y algunos entornos hospedados en, consulte la conectividad híbrida planning artículo [Skype para Business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Debe configurar DNS como normal de Skype para Business Server 2015 y también agregar registros DNS adicionales.

También debe consultar a "IP y URL de Office 365 intervalos de direcciones" en [https://aka.ms/o365ips](https://aka.ms/o365ips) para confirmar que los usuarios tendrán acceso a los recursos en línea que se necesitan.

## <a name="simple-urls"></a>Direcciones URL simples
<a name="BK_Simple"> </a>

Un localizador uniforme de recursos (URL) es una referencia a un recurso web que especifica su ubicación en una red de equipo y un protocolo que se usa para recuperarlo.

Skype para Business Server admite el uso de tres direcciones URL "simples" para servicios de access:

- **Cumplir** se usa como la dirección URL base para todas las conferencias en el sitio. Un ejemplo de un URL simples de reunión es https:<span></span>//<span></span>reunirse. <span> </span>contoso<span></span>. com. Es posible que una dirección URL para una reunión concreta https:<span></span>//<span></span>reunirse. <span> </span>contoso<span></span>.com /_nombre de usuario_/7322994.

    Con la URL simples de reunión, vínculos a unirse a reuniones son fáciles de comprender y fácil de comunicarse.

- **Dial-in** habilita el acceso a la página web de configuración de conferencia de acceso telefónico. Esta página muestra los números de acceso telefónico de conferencia con sus idiomas disponibles, asignadas información de conferencia (es decir, para las reuniones que no es necesario ser programadas) y los controles DTMF en conferencia y soporta la administración de (número de identificación personal PIN) y asigna la información de la conferencia. La dirección URL sencilla de marcado se incluye en todas las invitaciones a reuniones para que los usuarios que deseen conectarse a la reunión pueden tener acceso a la información de PIN y número de teléfono es necesario. Un ejemplo de la dirección URL simple Dial-in es https://<span></span>dialin. <span> </span>contoso<span></span>. com.

- **Admin** permite el acceso rápido a la Skype para el Panel de Control de servidor empresarial. Desde cualquier equipo dentro de los servidores de seguridad de la organización, un administrador puede abrir el Skype para el Panel de Control de Business Server escribiendo la dirección URL de administración sencilla en un explorador. La dirección URL de administración simple es interna a la organización. Un ejemplo de la dirección URL de administración simple es https://<span></span>Admin. <span> </span>contoso<span></span>. com.

Las direcciones URL sencillas se tratan con más detalle en [los requisitos de DNS para direcciones URL simples en Skype para Business Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS por función de servidor
<a name="BK_Servers"> </a>

Puede establecer los nombres de estos servidores y grupos de servidores como desee, pero que sean fáciles de recordar y que refleje su función en el sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS para servidores individuales o grupos de servidores

Estos requisitos de registro genérico se aplican a cualquier rol de servidor utilizado por Skype para la empresa. Un grupo de servidores es un conjunto de servidores que ejecutan los mismos servicios que funcionan conjuntamente para controlar las solicitudes de cliente dirigidas a ellos a través de un equilibrador de carga. Para obtener detalles, consulte [Equilibrio de carga de los requisitos de Skype para la empresa](load-balancing.md)

**Requisitos de registro de DNS para los roles de servidor o el grupo (se da por supuesto equilibrio de carga de DNS)**

|Escenario de implementación|Requisito de DNS|
|:-----|:-----|
|Un servidor:  <br/> Persistent Chat, Director, servidor de mediación, servidor front-end   |Un registro A interno que resuelve el nombre de dominio completo (FQDN) del servidor en su dirección IP.  <br/> ServerRole. <span> </span>contoso<span></span>.com 10.10.10.0   |
|Grupo de servidores:  <br/> Chat persistente, Director, servidor perimetral, el servidor de mediación, front-end   |Un registro a interno que resuelve el nombre de dominio completo (FQDN) de cada nodo del servidor en el grupo de servidores en su dirección IP.  <br/>**Ejemplo** <br/> ServerRole01. <span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerRole02. <span> </span>contoso<span></span>.com 10.10.10.2  <br/> Varios A interno de registros que resuelven el nombre de dominio completo (FQDN) del grupo de servidores para las direcciones IP de los nodos de servidor en el grupo de servidores.  <br/>**Ejemplo** <br/> ServerPool. <span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerPool. <span> </span>contoso<span></span>.com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Temas DNS específicos de Edge Server

 Para planear la implementación del servidor perimetral, revise [Plan para las implementaciones de servidor perimetral de Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)y [planeación de DNS de servidor perimetral avanzada de Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) que tiene las siguientes secciones

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


