---
title: 'Lync Server 2013: Implementar la telefonía IP empresarial'
TOCTitle: Implementar la telefonía IP empresarial
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48276423
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar la telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-03_

Telefonía IP empresarial de Lync Server 2013 forma parte de la infraestructura de Lync Server 2013.

Para implementar Telefonía IP empresarial, debe hacer lo siguiente:

1.  Consultar la sección [Planear la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) de la documentación sobre planeación.

2.  Terminar los planes de características y componentes para implementar con esta carga de trabajo.

3.  Ejecutar la Herramienta de planeación para diseñar una topología que refleje sus decisiones relacionadas con la implementación.

4.  Abrir el diseño de la topología en el Generador de topologías, como se describe en [Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) en la documentación sobre implementación.
    

    > [!NOTE]
    > La instalación del Generador de topologías forma parte del proceso de implementación del grupo de servidores interno. Para más información, vea <A href="lync-server-2013-install-lync-server-administrative-tools.md">Instalar las herramientas administrativas de Lync Server 2013</A> en la documentación sobre implementación.



Además, debe haber implementado Lync Server, Enterprise Edition en sitios centrales y sitios de sucursal que se correspondan con la topología de referencia que eligió para implementar. No puede implementar los componentes de Telefonía IP empresarial hasta que haya definido, publicado e instalado archivos para al menos un grupo de servidores interno, y debe usar el Generador de topologías para definir y publicar un grupo de servidores interno.

Para ver topologías de referencia con ejemplos de dónde se pueden implementar los roles del servidor de Telefonía IP empresarial (y la relación entre ellos y otros roles del servidor de Lync Server 2013), vea [Topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md) en la documentación sobre planeación.

Para ver una topología de referencia que ilustre y explique una implementación de control de admisión de llamadas de prueba con regiones de red, sitios de red y subredes, vea [Ejemplo: Recopilación de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación sobre planeación.

> [!IMPORTANT]  
> Para implementar Telefonía IP empresarial en un sitio central, siga leyendo los temas de esta sección. Para implementar Telefonía IP empresarial en un sitio de sucursal, vaya a <a href="lync-server-2013-deploying-branch-sites.md">Implementación de sitios de sucursales en Lync Server 2013</a> en la documentación sobre implementación.



La documentación de esta sección incluye procedimientos para implementaciones en las que se instala un servidor de mediación en cada servidor front-end o servidor Standard Edition, como se recomienda, y también para implementaciones con un grupo de servidores de mediación independiente.

Si usó el Generador de topologías para definir y publicar una topología que instala un servidor de mediación en cada servidor front-end o servidor Standard Edition, puede ir al contenido siguiente porque el Asistente para la implementación ya instaló automáticamente los archivos del servidor de mediación cuando instaló los archivos para el grupo de servidores front-end o el servidor Standard Edition:

  - [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md)

Si usó el Generador de topologías para definir y publicar un servidor de mediación en un grupo de servidores independiente, puede usar el contenido siguiente:

  - Compruebe que la topología cumpla los requisitos previos de software y entorno, como se describe en [Requisitos previos de la telefonía IP empresarial para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

## En esta sección

  -   
    [Requisitos previos de la telefonía IP empresarial para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  -   
    [Implementar servidores de mediación y definir servidores del mismo nivel en Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  -   
    [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md)

  -   
    [Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  -   
    [Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  -   
    [Exportar e importar la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  -   
    [Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

  -   
    [Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  -   
    [Implementar la mensajería unificada de Exchange local para proporcionar correo de voz de Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  -   
    [Proporcionar correo de voz a usuarios de Lync Server 2013 en la mensajería unificada de Exchange hospedada](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  -   
    [Configuración de la integración local de Lync Server 2013 con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  -   
    [Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Acerca de las regiones de red, sitios y subredes en Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Configurar 9-1-1 mejorado en Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  -   
    [Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

## Vea también

#### Otros recursos

[Implementación de sitios de sucursales en Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Configurar una conferencia de acceso telefónico local en Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Configurar el estacionamiento de llamadas en Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Configuración de anuncios para números sin asignar en Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Implementación de supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)

