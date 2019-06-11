---
title: 'Lync Server 2013: Cambios en la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0ea02d1643a686e16d3d1984e756a48311b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Cambios en la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Los requisitos de topología y las consideraciones para Lync Server 2013 son diferentes de los de las versiones anteriores, tal y como se describe en esta sección.

<div>

## <a name="new-front-end-pools-architecture"></a>Nueva arquitectura de pools front end

En Lync Server 2013, la arquitectura de los grupos de aplicaciones para el usuario de Enterprise Edition ha cambiado a una arquitectura de sistemas distribuidos.

Con esta nueva arquitectura, la base de datos back-end ya no es el almacén de datos en tiempo real en un grupo. La información sobre un usuario en particular se mantiene en tres servidores front-end en el grupo. Para cada usuario, un servidor front-end actúa como el maestro para la información del usuario y otros dos servidores front-end actúan como réplicas. Si un servidor front-end deja de funcionar, otro servidor front-end que sirve como réplica se promueve automáticamente a Master.

Esto sucede en segundo plano y los administradores no necesitan saber qué servidores front-end son los patrones para los usuarios. Esta distribución de almacenamiento de datos mejora el rendimiento y la escalabilidad dentro del grupo y elimina el punto único de falla de un único servidor de servicios de fondo.

El servidor back-end sirve como almacenamiento de copia de seguridad de datos de usuarios y de conferencia, y también el almacenamiento principal de otras bases de datos, como la base de datos de grupos de respuesta.

Estas mejoras también significan que hay cambios en la forma en que se planean y mantienen los grupos. Le recomendamos que todos los grupos de aplicaciones para el usuario de Enterprise Edition incluyan al menos tres servidores front-end, para proporcionar el número completo de réplicas para las que está diseñada la arquitectura del grupo de servidores front-end. Además, debe seguir ciertos procedimientos al agregar servidores a un grupo de servidores front-end, quitar servidores de él o actualizar servidores. Para obtener más información, vea [topologías y componentes para servidores front-end, mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Cambios en la topología de roles del servidor

Algunos roles de servidor que se ejecutaban previamente en servidores independientes se consolidan ahora en el rol de servidor front-end, lo que le permite ahorrar en costos de hardware

  - En Lync Server 2013, el servidor de conferencia A/V siempre se encuentra en el servidor front-end.

  - Los front-ends para la supervisión y el archivado ahora se colocan siempre con el servidor front-end. La supervisión y el archivado de cada uno aún requieren una base de datos back-end separada, que se puede colocar en el mismo servidor que la base de datos back-end del grupo de aplicaciones para el usuario o puede alojarse en servidores back-end independientes.

  - El servidor de chat persistente es ahora un rol de servidor. En Microsoft Lync Server 2010, el servidor de chats grupales era una aplicación de confianza de terceros para Microsoft Lync Server 2010. En Lync Server 2013, la funcionalidad del servidor de chat persistente se implementa con tres nuevos roles de servidor:
    
      - **PersistentChatService:** Servicios principales del servidor de chat persistente implementados como un rol front-end
    
      - **PersistentChatStore:** Función back-end del servidor
    
      - **PersistentChatComplianceStore:** Rol de servidor back end para cumplimiento de las conversaciones persistentes

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

