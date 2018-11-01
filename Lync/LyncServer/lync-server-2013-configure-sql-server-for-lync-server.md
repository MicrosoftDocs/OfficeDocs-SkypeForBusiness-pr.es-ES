---
title: 'Lync Server 2013: Configurar SQL Server para Lync Server'
TOCTitle: Configurar SQL Server para Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48274942
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar SQL Server para Lync Server 2013

 

_**Última modificación del tema:** 2013-08-12_

En los temas de esta sección se explica cómo implementar y configurar SQL Server para usarlo en una implementación Enterprise de Lync Server. Los Servidores Standard Edition usan una versión instalada de SQL Server Express de SQL Server adecuada para las cargas de trabajo de un Servidor Standard Edition.

El Lync Server 2013  Almacén de administración central contiene datos de usuario de todos los servidores Enterprise Edition de un grupo y está diseñado para ser ubicado en un servidor back-end basado en SQL Server. Al ser un repositorio centralizado, Almacén de administración central no se puede instalar en el mismo equipo que cualquier otro rol de Lync Server 2013. Almacén de administración central no puede residir en un servidor Enterprise Edition del grupo. Almacén de administración central se crea automáticamente al publicar la topología y seleccionar la creación de las bases de datos. El equipo que se designe como servidor back-end debe tener ya en funcionamiento el software de bases de datos de SQL Server para que la instalación se pueda llevar a cabo correctamente.

## En esta sección

  - [Ubicación de datos y de archivos de registro de SQL Server para Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configurar SQL Server en Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Instalación de la base de datos con el Shell de administración de Lync Server en Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Descripción de los requisitos de firewall para SQL Server con Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurar la agrupación en clústeres de SQL Server en Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

