---
title: 'Lync Server 2013: Implementar el servidor de chat persistente'
TOCTitle: Implementar el servidor de chat persistente
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48276981
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar el servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2014-03-31_

Lync Server 2013 de Servidor de chat persistente forma parte de la infraestructura de Lync Server 2013.

La implementación de Servidor de chat persistente requiere:

  - Usar Generador de topologías para definir o importar y posteriormente publicar su topología y los componentes que desea implementar

  - Preparar el entorno para implementar componentes de Servidor de chat persistente

  - Instalar y configurar componentes de Servidor de chat persistente para la implementación.

Servidor de chat persistente está disponible con Lync Server 2013Enterprise Edition como grupo de servidores diferente (sin combinar con los Enterprise EditionServidores front-end). Servidor de chat persistente necesita un SQL ServerServidor back-end en el grupo de servidores de Enterprise Edition para almacenar el contenido del salón de chat y otros metadatos pertinentes. Recomendamos instalar **PersistentChatStore** en un SQL ServerServidor back-end dedicado, aunque se admite combinar Lync Server 2013Servidor back-end y **PersistentChatStore** en la misma instancia de SQL Server.

Servidor de chat persistente también se puede implementar con Lync Server 2013Standard Edition. En este caso, **PersistentChatService**Servidor front-end se combina con el PC de Standard Edition y **PersistentChatStore**Servidor back-end se puede implementar en la instancia de SQL Server Express local.

Para obtener información detallada sobre configuraciones de combinación admitida, consulte [Instalación de servidores compatibles en Lync Server 2013](lync-server-2013-supported-server-collocation.md).

> [!IMPORTANT]  
> No admitimos la alta disponibilidad para Servidor de chat persistenteStandard Edition. El rendimiento y la escala se limitarán. Además, solo admitimos nuevos Servidor de chat persistenteServidor Standard Edition. No admitimos la actualización de Lync Server 2010, Servidor de chat en grupo a un Lync Server 2013Servidor de chat persistenteStandard Edition.



Si su organización necesita compatibilidad de cumplimiento, instale el servicio de cumplimiento de Servidor de chat persistente en el Servidor de chat persistenteServidor front-end. Se necesita una base de datos diferente para el cumplimiento.

Como mínimo, cada tipología requiere un servidor con Lync Server 2013 instalado y un servidor con software de base de datos de Microsoft SQL Server instalado.

Use Generador de topologías para agregar el Servidor de chat persistente a las implementaciones de Lync Server 2013. Elija entre agregar uno o varios Grupos de servidores de chat persistente con la Generador de topologías. Siga las mismas instrucciones de implementación que para implementar varios Grupos de servidores de chat persistente como lo haría con cualquier grupo de servidores. Para más información, vea [Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.

Para más información sobre las topologías disponibles y los requisitos técnicos y de software necesarios para instalar Servidor de chat persistente, vea [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planificación, [Funcionamiento del servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones y [Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación de compatibilidad.

Para más información sobre la adquisición de certificados, la creación de bases de datos de SQL Server y la creación de almacenes de archivos, vea [Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)en la documentación de implementación.

Un único Servidor de chat persistenteServidor front-end admite 20000 usuarios activos. Puede tener un Grupo de servidores de chat persistente con un máximo de 4 Servidores front-end activos que den soporte a un total de 80 000 usuarios simultáneos.

Servidor de chat persistente también se admite en un servidor virtual. El servidor virtual puede admitir hasta 20 000 usuarios a la vez si coincide con las especificaciones del servidor físico.

> [!IMPORTANT]  
> Servidor de chat persistente debe instalarse en un sistema de archivos NTFS para ayudar a aplicar la seguridad del sistema de archivos. FAT32 no es un sistema de archivos admitido para Servidor de chat persistente.



## En esta sección

  - [Funcionamiento del servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lista de comprobación para la implementación de servidores de chat persistente en Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Requisitos técnicos para el servidor de chat persistente en Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configurar los sistemas y la infraestructura para servidores de chat persistente en Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Agregar un servidor de chat persistente a la implementación en Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Instalación del servidor de chat persistente en Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Agregar un administrador de chat persistente en Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configurar servidor de chat persistente en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configuración del servidor de chat persistente con cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Solucionar problemas de configuración de servidores de chat persistentes mediante los cmdlets de Windows PowerShell en Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Conmutación por recuperación y por error de servidores de chat persistente en Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

