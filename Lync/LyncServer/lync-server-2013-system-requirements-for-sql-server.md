---
title: 'Lync Server 2013: Requisitos del sistema para SQL Server'
TOCTitle: Requisitos del sistema para SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48276136
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos del sistema para SQL Server en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-25_

Antes de implementar un servidor de Enterprise Edition, instale Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 en un equipo dedicado a ese fin y que cumpla con los requisitos de hardware. Para obtener más información sobre los requisitos de hardware, consulte [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad. Para obtener más información sobre los requisitos de software, consulte [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md) en la documentación sobre compatibilidad. Para obtener más información sobre los permisos necesarios para la implementación, consulte [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

Antes de crear el grupo de servidores front-end, también debe configurar Firewall de Windows para permitir el acceso de Lync Server 2013 a SQL Server a través de puertos mediante la definición de puertos para el servidor con el Administrador de configuración de SQL Server y abrir puertos en Firewall de Windows con seguridad avanzada.

