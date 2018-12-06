---
title: 'Lync Server 2013: Configuración de troncos'
TOCTitle: Configuración de troncos
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48274407
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de troncos en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Como parte de la implementación de Telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes equivalentes para proporcionar conectividad de red telefónica conmutada (RTC) para clientes y dispositivos de Telefonía IP empresarial de su organización:

  - Conexión basada en troncos SIP para un proveedor de servicio s de telefonía

  - Puerta de enlace RTC

  - Central de conmutación (PBX)

Para obtener más información, consulte [Planeación de la conectividad con RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) en la documentación sobre planeamiento.

> [!IMPORTANT]  
> Antes de iniciar la configuración de troncos, verifique que se ha creado la topología y que el servidor de mediación y su par se han configurado y asociado entre sí. Para obtener información detallada, consulte <a href="lync-server-2013-define-a-gateway-in-topology-builder.md">Definir una puerta de enlace en el Generador de topologías en Lync Server 2013</a> en la documentación sobre implementación.




> [!NOTE]
> Como parte de la configuración de troncos, puede habilitar la característica de desvío de medios de Lync Server 2013, que permite que los medios no pasen por el servidor de mediación. Los troncos pueden configurarse con el desvío de medios habilitado o deshabilitado, aunque le recomendamos que lo habilite. Para obtener más información, consulte <A href="lync-server-2013-planning-for-media-bypass.md">Planificar la omisión de medios en Lync Server 2013</A> en la documentación sobre planeación.



## En esta sección

  - [Compatibilidad con varios troncos en Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Enrutamiento entre troncos en Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Visualización de la información de configuración de troncos en Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Creación de un nuevo conjunto de opciones de configuración de troncos en Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Eliminación de un conjunto existente de opciones de configuración de troncos SIP en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Modificación de las opciones de configuración de troncos SIP en Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Prueba de las opciones de configuración de troncos SIP en Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Visualización de información sobre troncos SIP individuales en Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

## Vea también

#### Tareas

[Definir una puerta de enlace en el Generador de topologías en Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  

#### Otros recursos

[Planeación de la conectividad con RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

