---
title: 'Lync Server 2013: Implementar el servidor de chat persistente'
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
ms.openlocfilehash: 7fe18bf750eabdb1f53c97a349b553da4f13dec8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Implementar el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-31_

Lync Server 2013, el servidor de chat persistente es parte de la infraestructura de Lync Server 2013.

La implementación del servidor de chat persistente requiere que:

  - Use el generador de topología para definir o importar y posteriormente publicar su topología y los componentes que desea implementar.

  - Preparar el entorno para implementar componentes de servidor de chat persistentes.

  - Instale y configure los componentes del servidor de chat persistentes para su implementación.

El servidor de chat persistente está disponible con Lync Server 2013 Enterprise Edition como un grupo independiente (que no se encuentra en los servidores front-end de Enterprise Edition). El servidor de chat persistente requiere un servidor SQL Server back end en el grupo de servidores Enterprise Edition para almacenar el contenido del salón de chat y otros metadatos relevantes. Le recomendamos que instale el **PersistentChatStore** en un servidor de back-end de SQL Server dedicado, aunque se admite Collocating servidor back-end de Lync Server 2013 y **PersistentChatStore** en la misma instancia de SQL Server.

El servidor de chat persistente también se puede implementar con Lync Server 2013 Standard Edition. En este caso, el servidor front-end de **PersistentChatService** se colocará en el equipo Standard Edition y el servidor back end de **PersistentChatStore** se puede implementar en la instancia local de SQL Server Express.

Para obtener más información sobre las configuraciones de colocaciones compatibles, consulte [compatibilidad de servidores de collocation en Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> No se admite la alta disponibilidad de la versión del&nbsp;servidor de chat persistente. El rendimiento y la escala serán limitados. Además, solo admitimos un servidor de servidor&nbsp;Standard Edition nuevo. No se admite la actualización de Lync Server 2010, servidor de chats grupales a un&nbsp;servidor de lync&nbsp;Server 2013, una versión estándar de servidor de chat.



</div>

Si su organización requiere soporte de cumplimiento, puede instalar el servicio de cumplimiento del servidor de chat persistente en el servidor front-end del servidor de chat persistente. Se necesita una base de datos independiente para el cumplimiento.

Como mínimo, cada topología requiere un servidor con Lync Server 2013 instalado y un servidor con el software de base de datos de SQL Server instalado.

Use el generador de topología para agregar un servidor de chat persistente a las implementaciones de Lync Server 2013. Puede elegir agregar uno o varios grupos de servidores de chat persistentes con el generador de topologías. Siga las mismas instrucciones de implementación para implementar varios grupos de servidores de chat persistentes como lo haría para cualquier grupo. Para obtener más información, vea [implementación de Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.

Para obtener información detallada sobre las topologías disponibles y los requisitos técnicos y de software para instalar el servidor de chat persistente, consulte [planear el servidor de chat persistente en Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planeación, [Cómo funciona el servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) , en la documentación de planeación, la documentación de implementación o la documentación de operaciones, y el [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md)

Para obtener detalles sobre la adquisición de certificados, la creación de la base de datos de SQL Server y la creación de almacenes de archivos, vea [implementar Lync server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.

Un solo servidor de cliente de servidor de chat persistente puede admitir usuarios activos de 20.000. Puede tener un grupo de servidores de chat persistente con hasta 4 servidores activos para el usuario que admitan un total de 80.000 usuarios simultáneos.

El servidor de chat persistente también se admite en un servidor virtual. El servidor virtual puede admitir hasta 20.000 usuarios simultáneos si coincide con las especificaciones del servidor físico.

<div>


> [!IMPORTANT]  
> El servidor de chat persistente debe instalarse en un sistema de archivos NTFS para ayudar a exigir la seguridad del sistema de archivos. FAT32 no es un sistema de archivos compatible para el servidor de chat persistente.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Cómo funciona el servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

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

</div>

</div>

<span> </span>

</div>

</div>

</div>

