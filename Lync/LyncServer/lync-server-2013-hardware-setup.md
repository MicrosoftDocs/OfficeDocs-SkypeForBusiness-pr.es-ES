---
title: 'Lync Server 2013: Configuración del hardware'
TOCTitle: Configuración del hardware
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48274953
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del hardware en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

La configuración del hardware y otros componentes necesarios para la infraestructura en la que debe implementar la topología requiere que, antes de publicar la topología en Generador de topologías, siga este procedimiento:

  - Instale el hardware para cada componente del diseño de la topología que creó y guardó con Generador de topologías, incluidos todos los equipos necesarios (servidores que ejecuten Lync Server 2013, servidores de base de datos, servidores que ejecuten Internet Information Services (IIS) y servidores proxy inversos, según corresponda), adaptadores de red, equilibradores de carga de hardware y dispositivos de almacenamiento (como servidores de archivos). Confirme que ha seguido las recomendaciones sobre el número y la velocidad de los adaptadores de red. Si usa equilibradores de carga de hardware, asegúrese de que el proveedor le haya proporcionado la información correcta para configurarlos y usarlos con Lync Server 2013. Si usa un servidor de archivos u otro servidor para hospedar el recurso compartido de archivos que requiere Lync Server, compruebe que el servidor esté disponible y preparado para la configuración del recurso compartido de archivos. Para más información sobre cómo definir una topología que especifique los componentes necesarios para la implementación, consulte [Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Para más información sobre los requisitos de servidores, consulte [Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad.

  - Asegúrese de que la infraestructura de red cumple los requisitos. Para más información, consulte [Requisitos de la infraestructura de red](lync-server-2013-network-infrastructure-requirements.md) en la documentación sobre planeación.

  - Configure Servicios de dominio de Active Directory. La configuración de AD DS incluye la preparación de AD DS y la definición de todos los componentes que desea implementar en AD DS. Para más información sobre la preparación de AD DS, consulte [Preparar Servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación.

  - Configure los permisos necesarios para crear el recurso compartido de archivos. Los permisos de uso de recursos compartidos de archivos por parte de Lync Server 2013 los configura automáticamente Generador de topologías cuando se publica la topología. No obstante, la cuenta de usuario empleada para publicar la topología debe tener control total (lectura/escritura/modificación) en el recurso compartido de archivos para que Generador de topologías configure los permisos necesarios. Para asegurarse de que el recurso compartido de archivos se puede administrar correctamente durante el proceso de publicación de Topology Builder, el grupo de usuarios o de dominios al que pertenece el usuario debe convertirse en miembro del grupo local Administradores del equipo en que se ubica el recurso compartido de archivos. En un escenario con varios dominios, el usuario o el grupo del dominio A debería convertirse en miembro del grupo de administradores locales en el equipo en el dominio B donde se ubicará el recurso compartido de archivos.
    
    Para más información sobre la actualización con recursos compartidos de archivos en un Sistema de archivos distribuido (DFS), consulte [Configurar el almacenamiento de archivos para Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    > [!WARNING]  
    > El recurso compartido de archivos de Lync Server 2013 Enterprise Edition no se puede ubicar en el Servidor front-end.
    


  - Instale y configure el equilibrador de carga de hardware para Servicios web. Aunque se haya implementado el equilibrio de carga del Sistema de nombres de dominio (DNS), sigue siendo necesario usar también equilibradores de carga de hardware en estos grupos de servidores, pero únicamente para el tráfico HTTP/HTTPS. El equilibrador de carga de hardware se usa para el tráfico HTTPS procedente de clientes a través de los puertos 443 y 80. Aunque siga siendo necesario usar equilibradores de carga de hardware para estos grupos de servidores, su configuración y administración será sobre todo para el tráfico HTTP/HTTPS, a lo que están acostumbrados los administradores de los equilibradores de carga de hardware.

Cuando haya completado todas las tareas de preparación que se describen en este tema, pero antes de publicar la topología, también es necesario realizar las siguientes tareas:

  - [Instalar los sistemas operativos y el software necesario como requisito previo en los servidores en Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configurar IIS para Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configurar SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurar los registros DNS para un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

