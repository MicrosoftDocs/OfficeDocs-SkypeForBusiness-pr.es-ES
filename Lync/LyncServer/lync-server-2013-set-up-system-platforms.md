---
title: 'Lync Server 2013: Configurar plataformas del sistema'
TOCTitle: Configurar plataformas del sistema
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48274804
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar plataformas del sistema en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Antes de iniciar la implementación de Servidor de chat persistente, debe instalar el sistema operativo requerido en hardware que cumpla los requisitos del sistema en servidores:

Para obtener más información sobre el hardware compatible con servidores que ejecutan Lync Server 2013, servidores de base de datos y servidores de archivos, consulte [Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad. Para obtener más información sobre sistemas operativos y software de bases de datos admitidos, consulte [Software de servidor y compatibilidad con la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación sobre compatibilidad. Para obtener más información sobre los requisitos de las actualizaciones de Windows, consulte [Compatibilidad y requisitos para un servidor adicional en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) en la documentación sobre compatibilidad.

Los Servidor de chat persistenteServidor front-end, **PersistentChatService**, pueden implementarse en uno o más equipos independientes en un grupo de servidores de Lync Server 2013Enterprise Edition. No pueden instalarse en los Lync ServerEnterprise EditionServidores front-end. Servidor de chat persistente pueden ser implementados por Bootstrapper, al igual que otros roles de Lync Server. Los servicios web de **Chat persistente para la carga y descarga de archivos** y los servicios web de **Chat persistente para la administración de salas de chat** son componentes web implementados en los Lync Server 2013Servidores front-end.

Un único Servidor de chat persistenteServidor front-end puede admitir 20.000 usuarios activos. Puede tener un Grupo de servidores de chat persistente con hasta 4 servidores front-end activos que admitan un total de 80.000 usuarios concurrentes. El Chat persistenteServidor back-end, **PersistentChatStore**, almacena las salas de chat y categorías. Se recomienda instalar el **PersistentChatStore** en un SQL ServerServidor back-end dedicado en su grupo de servidores Enterprise Edition; aunque admitimos la instalación de Lync Server 2013Servidor back-end y **PersistentChatStore** en la misma instancia SQL Server.

Si su organización requiere compatibilidad con el cumplimiento, puede instalarlo utilizando Generador de topologías. El servicio de Cumplimiento Servidor de chat persistente se instala en el mismo equipo que el Servidor de chat persistenteServidor front-end. Se necesita una base de datos independiente para el cumplimiento. Para obtener información detallada sobre los requisitos de cumplimiento para Servidor de chat persistente, consulte [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación sobre planeación.

Como mínimo, cada topología requiere un servidor que tenga Lync Server 2013 instalado y un servidor que tenga el software de la base de datos de SQL Server instalado. Generador de topologías admite varios Grupos de servidores de chat persistente. Siga las mismas instrucciones de implementación para implementar varios Grupos de servidores de chat persistente como lo haría para cualquier grupo de servidores de [Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.

También puede implementar Servidor de chat persistente con Lync Server 2013Standard Edition. En este caso, el **PersistentChatService**Servidor front-end se instala en el Servidor Standard Edition, y puede implementar el **PersistentChatStore**Servidor back-end en la instancia SQL Server Express local.

> [!IMPORTANT]  
> No admitimos alta disponibilidad para Servidor de chat persistenteStandard Edition, y estarán limitados el rendimiento y la escala. Además, solamente admitimos nuevas implementaciones de Servidor de chat persistente  Servidor Standard Edition. No admitimos la actualización de Lync Server 2010Servidor de chat en grupo a un Lync Server 2013Servidor de chat persistenteStandard Edition.



## Vea también

#### Conceptos

[Compatibilidad y requisitos para un servidor adicional en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  

#### Otros recursos

[Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Software de servidor y compatibilidad con la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)

