---
title: Lync Server 2013 topologías de cambios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a993057d3aae52b1c080d05fe9bba4eaff1ebeab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Cambios en la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Los requisitos y consideraciones de la topología para Lync Server 2013 son diferentes de los de versiones anteriores, como se describe en esta sección.

<div>

## <a name="new-front-end-pools-architecture"></a>Nueva arquitectura para grupos de servidores front-end

En Lync Server 2013, la arquitectura de los grupos de servidores front-end Enterprise Edition ha cambiado a una arquitectura de sistemas distribuidos.

Con esta nueva arquitectura, base de datos back-end ya no es el almacén de datos en tiempo real de un grupo de servidores. La información sobre un usuario en particular se guarda en tres servidores front-end del grupo. Para cada usuario habrá un servidor front-end que actuará como servidor de información principal y otros dos servidores front-end que actuarán como réplicas. Si uno de los servidores front-end deja de funcionar, se ascenderá automáticamente al rol de principal a otro de los dos servidores que sirven de réplica.

Esto ocurre en segundo plano y los administradores no necesitan saber qué servidores front-end son los principales para qué usuarios. Esta distribución del almacenamiento de datos mejora el rendimiento y la escalabilidad en el grupo, y elimina el único punto de error de un único servidor back-end.

El servidor back-end se utiliza como almacén de copias de seguridad para datos de usuarios y conferencias y es también el almacén principal para otras bases de datos como la de grupo de respuesta.

Estas mejoras significan, además, que cambia la forma de planear y mantener los grupos de servidores. Se recomienda que todos los grupos de servidores front-end Enterprise Edition incluyan al menos tres servidores front-end para proporcionar el número completo de réplicas para las que está diseñada la arquitectura de grupo de servidores front-end. Además, debe seguir determinados procedimientos al agregar servidores a un grupo de servidores front-end, quitar servidores de él o actualizar servidores. Para obtener más información, vea [topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Cambios en la topología de roles de servidor

Algunos roles de servidor que anteriormente se ejecutaban en servidores aparte se han consolidado en el rol de servidor front-end y esto permite ahorrar en costes de hardware.

  - En Lync Server 2013, el servidor de conferencia A/V siempre se combina con el servidor front-end.

  - Ahora, los front-end de Supervisión y Archivado se instalan siempre con el servidor front-end. Supervisión y Archivado siguen necesitando cada uno una base de datos back-end independiente, que puede instalarse en el mismo servidor que la base de datos back-end del grupo de servidores front-end o bien puede hospedarse en servidores back-end aparte.

  - El servidor de chat persistente ahora es un rol de servidor. En Microsoft Lync Server 2010, el servidor de chat en grupo era una aplicación de confianza de terceros para Microsoft Lync Server 2010. En Lync Server 2013, la funcionalidad del servidor de chat persistente se implementa con tres nuevos roles de servidor:
    
      - **PersistentChatService:** Servicios principales del servidor de chat persistente implementados como rol front-end
    
      - **PersistentChatStore:** Rol de servidor back-end
    
      - **PersistentChatComplianceStore:** Rol de servidor back-end para el cumplimiento de chat persistente

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

