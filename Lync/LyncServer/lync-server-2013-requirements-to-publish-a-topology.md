---
title: 'Lync Server 2013: Requisitos para publicar una topología'
TOCTitle: Requisitos para publicar una topología
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48275883
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos para publicar una topología en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

En este tema se describen los requisitos de infraestructura y software que son específicos a la publicación de una topología, ya sea mediante Generador de topologías o la interfaz de línea de comandos de Shell de administración de Lync Server 2013. Estos requisitos son adicionales a los requisitos generales de permisos, software y sistema operativo aplicables a todas las herramientas administrativas de Lync Server 2013. Asegúrese de cumplir todos los requisitos de tareas administrativas antes de publicar una topología.

  - Debe ejecutar Generador de topologías en un equipo unido al mismo dominio o bosque de la implementación de Lync Server 2013 que está creando de modo que los pasos de preparación de Servicios de dominio de Active Directory ya estén completados, lo que le permite usar las herramientas administrativas de ese equipo para publicar correctamente su topología.

  - Los equipos definidos en la topología deben estar unidos al dominio, excepto los servidores perimetrales y en AD DS. Sin embargo, los equipos no necesitan estar en línea cuando publica la topología.

  - El recurso compartido de archivos para el grupo de servidores debe estar creado y disponible para los usuarios remotos.

  - Para publicar un Grupo de servidores front-end de Enterprise Edition, el servidor back-end basado en SQL Server debe estar unido al dominio en el que está implementando los servidores, en línea, y configurado con las reglas de firewall adecuadas, para hacerlo disponible para los usuarios remotos. Para obtener información sobre la especificación de excepciones de firewall, consulte [Descripción de los requisitos de firewall para SQL Server con Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Para obtener otros detalles sobre la configuración de SQL Server, consulte [Configurar SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    

    > [!NOTE]
    > Servidor Standard Edition tiene una base de datos instalada que aceptará la configuración publicada. Primero debe ejecutar la tarea de configuración de <STRONG>Preparar el primer servidor Standard Edition</STRONG> en la Asistente para la implementación de Lync Server.



## Vea también

#### Tareas

[Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  

#### Conceptos

[Requisitos de software para herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  

#### Otros recursos

[Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

