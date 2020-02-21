---
title: 'Lync Server 2013: implementación del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4eb457dbaee5e91b7b4f408018242384cd8992c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Implementación del servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-31_

Lync Server 2013, el servidor de chat persistente forma parte de la infraestructura de Lync Server 2013.

La implementación del servidor de chat persistente requiere que:

  - Use el generador de topologías para definir o importar y, posteriormente, publicar la topología y los componentes que desea implementar.

  - Preparar el entorno para la implementación de componentes del servidor de chat persistente.

  - Instale y configure los componentes del servidor de chat persistente para su implementación.

El servidor de chat persistente está disponible con Lync Server 2013 Enterprise Edition como un grupo independiente (no combinado con los servidores front-end de Enterprise Edition). El servidor de chat persistente requiere un servidor back-end de SQL Server en el grupo de servidores Enterprise Edition para almacenar el contenido del salón de chat y otros metadatos relevantes. Le recomendamos que instale el **PersistentChatStore** en un servidor back-end de SQL Server dedicado, aunque combinar el servidor back-end de Lync Server 2013 y **PersistentChatStore** en la misma instancia de SQL Server es compatible.

El servidor de chat persistente también se puede implementar con Lync Server 2013 Standard Edition. En este caso, el servidor front-end de **PersistentChatService** se combina en el equipo Standard Edition y el servidor back-end **PersistentChatStore** se puede implementar en la instancia local de SQL Server Express.

Para obtener más información sobre las configuraciones de colocaciones admitidas, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> No se admite la alta disponibilidad para el servidor&nbsp;de chat persistente Standard Edition. El rendimiento y la escala se limitarán. Además, solo admitimos un nuevo servidor de&nbsp;servidor de chat persistente Server Standard Edition. No se admite la actualización de Lync Server 2010, el servidor de chat en grupo a un&nbsp;servidor&nbsp;de chat persistente de Lync Server 2013 Standard Edition.



</div>

Si su organización requiere compatibilidad con el cumplimiento, puede instalar el servicio de cumplimiento del servidor de chat persistente en el servidor front-end del servidor de chat persistente. Se necesita una base de datos diferente para el cumplimiento.

Como mínimo, cada topología requiere un servidor que tenga instalado Lync Server 2013 y un servidor con software de base de datos de SQL Server instalado.

Use el generador de topologías para agregar un servidor de chat persistente a las implementaciones de Lync Server 2013. Puede elegir agregar uno o varios grupos de servidores de chat persistente con el generador de topologías. Siga las mismas instrucciones de implementación para implementar varios grupos de servidores de chat persistente de la misma manera que lo haría para cualquier grupo de servidores. Para más información, vea [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.

Para obtener más información sobre las topologías disponibles y los requisitos técnicos y de software para instalar el servidor de chat persistente, consulte [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación, [Cómo funciona el servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) en la documentación de planeación, la documentación de implementación o las operaciones y el [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md)

Para obtener información detallada acerca de la adquisición de certificados, la creación de la base de datos de SQL Server y la creación de almacenes de archivos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.

Un solo servidor front-end de servidor de chat persistente puede admitir usuarios activos de 20.000. Puede tener un grupo de servidores de chat persistente con un máximo de 4 servidores front-end activos que admitan un total de 80.000 usuarios simultáneos.

El servidor de chat persistente también se admite en un servidor virtual. El servidor virtual puede admitir hasta 20 000 usuarios si coincide con las especificaciones del servidor físico.

<div>


> [!IMPORTANT]  
> El servidor de chat persistente debe estar instalado en un sistema de archivos NTFS para ayudar a forzar la seguridad del sistema de archivos. FAT32 no es un sistema de archivos compatible con el servidor de chat persistente.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Cómo funciona el servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lista de comprobación para la implementación del servidor de chat persistente en Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Requisitos técnicos para el servidor de chat persistente en Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configurar los sistemas y la infraestructura para el servidor de chat persistente en Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Adición de un servidor de chat persistente a la implementación en Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Instalar el servidor de chat persistente en Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Adición de un administrador de chat persistente en Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configurar el servidor de chat persistente en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configuración del servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Solución de problemas de configuración de servidores de chat persistentes mediante los cmdlets de Windows PowerShell en Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configurar el servidor de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Conmutación por recuperación y conmutación por recuperación del servidor de chat persistente en Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

