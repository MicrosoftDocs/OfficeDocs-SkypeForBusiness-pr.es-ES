---
title: 'Lync Server 2013: Preparación de la infraestructura y los sistemas'
TOCTitle: Preparación de la infraestructura y los sistemas
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48274486
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparación de la infraestructura y los sistemas para Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

La implementación de Lync Server 2013 requiere el uso de la Generador de topologías para definir y publicar el diseño de la topología. Para identificar los componentes necesarios para la topología, puede usar Generador de topologías para crear y guardar el diseño de una topología. Antes de publicar la topología en el Generador de topologías, haga lo siguiente:

  - Adquiera e instale el hardware para cada componente en el diseño de la topología que ha creado y guardado con el Generador de topologías, incluidos todos los equipos necesarios (los servidores que ejecutan Lync Server 2013, los servidores de base de datos, los servidores que ejecutan servicios de Internet Information Server (IIS) y servidores de proxy inverso, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos de almacenamiento (como servidores de archivos). Para más información sobre cómo definir una topología que especifique los componentes necesarios para la implementación, consulte [Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para más información sobre los requisitos de servidores, consulte [Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad.

  - Asegúrese de que la infraestructura de red cumple los requisitos. Para más información, consulte [Requisitos de la infraestructura de red](lync-server-2013-network-infrastructure-requirements.md) en la documentación sobre planeación.

  - Instale Servicios de dominio de Active Directory. Para publicar y habilitar la topología, necesita que los servidores internos sean representados por cuentas de equipo en AD DS. Esto se lleva a cabo uniendo los equipos a AD DS. Para más información sobre cómo preparar AD DS, consulte [Preparar Servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Cree un recurso compartido de archivos. Los servidores Standard Edition pueden hospedar el recurso compartido de archivos del archivo necesario, mientras que en una implementación empresarial el recurso compartido de archivos no puede hospedarse en el servidor front-end. Los permisos y las pertenencias a grupos necesarios para la implementación y configuración de la lista de control de acceso (ACL) en la carpeta y el recurso compartido deben establecerse correctamente para que el Generador de topologías finalice correctamente. Debe asegurarse de que la persona que ejecuta el Generador de topologías tenga los siguientes permisos y pertenencias a grupos:
    
      - Miembro de administradores locales
    
      - Miembro de usuarios de dominio
    
      - Control total sobre el recurso compartido y la carpeta del almacén de archivos

  - Para Enterprise Edition, instale y configure SQL Server. Para que la instalación de SQL Server se realice correctamente, el servidor basado en SQL Server debe estar en línea y la persona que publica la topología debe ser un administrador local en el SQL Server y debe ser miembro del grupo sysadmin de SQL Server en la instancia de SQL Server.

Una vez completadas todas las tareas de preparación descritas en este tema, pero antes de publicar la topología, también es necesario realizar el resto de tareas de preparación, incluida la instalación de los sistemas operativos Windows y otro software necesario como requisito previo, la instalación de IIS y la configuración de DNS. Para más información sobre estas tareas, consulte [Requisitos del sistema para servidores que ejecuten Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configurar IIS para Lync Server 2013](lync-server-2013-configure-iis.md) y [Preparación de la infraestructura y los sistemas para Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Asimismo, es necesario familiarizarse con los clientes y los requisitos de los clientes. Para más información, consulte [Implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

## En esta sección

  - [Configuración del hardware en Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configuración del software para Lync Server 2013](lync-server-2013-software-setup.md)

  - [Preparar Servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configurar SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar los registros DNS para un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

