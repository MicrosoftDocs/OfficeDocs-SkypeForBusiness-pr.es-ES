---
title: 'Lync Server 2013: configurar plataformas del sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bd5bff0b215060b1d352d5cc5798b114140c15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509787"
---
# <a name="set-up-system-platforms-in-lync-server-2013"></a>Configurar plataformas del sistema en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Antes de iniciar la implementación del servidor de chat persistente, debe instalar el sistema operativo necesario en hardware que cumpla los requisitos del sistema en los servidores:

Para obtener más información sobre el hardware compatible con servidores que ejecutan Lync Server 2013, servidores de bases de datos y servidores de archivos, consulte [Supported hardware for Lync server 2013](lync-server-2013-supported-hardware.md) en la documentación sobre compatibilidad. Para obtener más información sobre los sistemas operativos y el software de bases de datos compatibles, consulte [Server Software and Infrastructure support en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación sobre compatibilidad. Para obtener más información sobre los requisitos de Windows Update, consulte [soporte y requisitos de servidor adicionales en Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) en la documentación sobre compatibilidad.

El servidor front-end del servidor de chat persistente, **PersistentChatService**, se puede implementar en uno o varios equipos independientes de un grupo de servidores de Lync Server 2013 Enterprise Edition. No se pueden combinar en los servidores front-end de Lync Server Enterprise Edition. El arranque puede implementar el servidor de chat persistente, al igual que ocurre con otras funciones de Lync Server. Los **servicios Web de chat persistente para la carga y descarga de archivos**y los **servicios Web de chat persistente para la administración de salones de chat** son componentes Web implementados en los servidores Front-End de Lync Server 2013.

Un solo servidor front-end de servidor de chat persistente puede admitir usuarios activos de 20.000. Puede tener un grupo de servidores de chat persistente con hasta 4 servidores front-end activos que admitan un total de 80.000 usuarios simultáneos. El servidor back-end de chat persistente, **PersistentChatStore**, almacena las categorías y los salones de chat. Le recomendamos que instale el **PersistentChatStore** en un servidor back-end de SQL Server dedicado en el grupo de servidores Enterprise Edition; aunque admitimos combinar servidor back-end de Lync Server 2013 y **PersistentChatStore** en la misma instancia de SQL Server.

Si su organización requiere compatibilidad con el cumplimiento, puede instalarla mediante el generador de topologías. El servicio de cumplimiento del servidor de chat persistente está instalado en el mismo equipo que el servidor front-end del servidor de chat persistente. Se necesita una base de datos diferente para el cumplimiento. Para obtener más información sobre los requisitos de cumplimiento para el servidor de chat persistente, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación.

Como mínimo, cada topología requiere un servidor que tenga instalado Lync Server 2013 y un servidor con software de base de datos de SQL Server instalado. El generador de topologías admite varios grupos de servidores de chat persistente. Siga las mismas instrucciones de implementación para implementar varios grupos de servidores de chat persistente como lo haría para cualquier grupo de servidores desde la implementación de [Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.

También puede implementar un servidor de chat persistente con Lync Server 2013 Standard Edition. En este caso, el servidor front-end de **PersistentChatService** se combina en el servidor Standard Edition y puede implementar el servidor back-end de **PersistentChatStore** en la instancia local de SQL Server Express.

<div>


> [!IMPORTANT]  
> No se admite el servidor de chat persistente &nbsp; Standard Edition para alta disponibilidad. El rendimiento y la escala se limitarán. Además, solo se admiten las implementaciones de servidor de servidor de chat persistente de &nbsp; Standard Edition nuevas. No se admite una actualización de Lync Server 2010, servidor de chat en grupo a un servidor de chat persistente de Lync Server 2013 &nbsp; &nbsp; Standard Edition.



</div>

<div>

## <a name="see-also"></a>Consulte también


[Compatibilidad de servidor adicional y requisitos en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Hardware compatible con Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Software de servidor y compatibilidad con la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

