---
title: 'Lync Server 2013: Configurar plataformas del sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 317bfe0efed0417d49cc59dc8f6e7ad3bcca7d7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Configurar plataformas del sistema en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Antes de iniciar la implementación de un servidor de chat persistente, debe instalar el sistema operativo necesario en el hardware que cumpla con los requisitos del sistema en los servidores:

Para obtener detalles sobre el hardware compatible con servidores que ejecutan Lync Server 2013, servidores de bases de datos y servidores de archivos, consulte [hardware compatible para Lync server 2013](lync-server-2013-supported-hardware.md) en la documentación de soporte técnico. Para obtener más información sobre los sistemas operativos y el software de base de datos compatibles, vea [compatibilidad de software y infraestructura de servidor en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación de soporte técnico. Para obtener más información sobre los requisitos de Windows Update, consulte [compatibilidad y requisitos de servidor adicionales en Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) en la documentación de soporte técnico.

El servidor de solicitudes de cliente de chat persistente, **PersistentChatService**, se puede implementar en uno o varios equipos independientes de un grupo de servidores de Lync Server 2013 Enterprise Edition. No se pueden colocar en los servidores front-end de Lync Server Enterprise Edition. El programa previo puede implementar el servidor de chat persistente, del mismo modo que otros roles de Lync Server. Los **servicios Web de chat persistentes para la carga y descarga de archivos**y los **servicios Web de chat persistentes para la administración de salones de chat** son componentes Web implementados en los servidores Front-End de Lync Server 2013.

Un solo servidor de cliente de servidor de chat persistente puede admitir usuarios activos de 20.000. Puede tener un grupo de servidores de chat persistente con hasta 4 extremos frontales activos que admitan un total de 80.000 usuarios simultáneos. El servidor de back-end de chat persistente, **PersistentChatStore**, almacena las categorías y los salones de chat. Le recomendamos que instale el **PersistentChatStore** en un servidor de back-end de SQL Server dedicado en el grupo de servidores Enterprise Edition. aunque admitimos collocating servidor back-end y **PersistentChatStore** de Lync Server 2013 en la misma instancia de SQL Server.

Si su organización requiere soporte de cumplimiento, puede instalarlo con el generador de topologías. El servicio de cumplimiento del servidor de chat persistente está instalado en el mismo equipo que el servidor de solicitudes de cliente de chat persistente. Se necesita una base de datos independiente para el cumplimiento. Para obtener más información sobre los requisitos de cumplimiento para el servidor de chat persistente, consulte [planificación de servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planificación.

Como mínimo, cada topología requiere un servidor con Lync Server 2013 instalado y un servidor con el software de base de datos de SQL Server instalado. El generador de topología admite varios grupos de servidores de chat persistentes. Siga las mismas instrucciones de implementación para implementar varios grupos de servidores de chat persistentes como lo haría para cualquier grupo de servidores desde la [implementación de Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.

También puede implementar un servidor de chat persistente con Lync Server 2013 Standard Edition. En este caso, el servidor front-end **PersistentChatService** se colocará en el servidor Standard Edition y puede implementar el servidor back-end **PersistentChatStore** en la instancia local de SQL Server Express.

<div>


> [!IMPORTANT]  
> No se admite el servidor&nbsp;de chat persistente, Standard Edition, para una alta disponibilidad. El rendimiento y la escala serán limitados. Además, solo admitimos implementaciones de servidor&nbsp;de servidor de chat, Standard Edition. No se admite una actualización de Lync Server 2010, servidor de chats grupales a un servidor&nbsp;de lync Server&nbsp;2013, una versión estándar de servidor de chat.



</div>

<div>

## <a name="see-also"></a>Vea también


[Compatibilidad y requisitos para un servidor adicional en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Software de servidor y compatibilidad con la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

