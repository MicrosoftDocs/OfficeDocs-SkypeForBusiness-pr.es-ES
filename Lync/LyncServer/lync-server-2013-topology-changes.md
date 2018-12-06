---
title: 'Lync Server 2013: Cambios en la topología'
TOCTitle: Cambios en la topología
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49889502
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambios en la topología en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-02_

Los requisitos de topología y las consideraciones para Lync Server 2013 son diferentes respecto a versiones anteriores, según se explica en esta sección.

## Nueva arquitectura para grupos de servidores front-end

En Lync Server 2013, los Grupos de servidores front-endEnterprise Edition han cambiado a una arquitectura de sistemas distribuidos.

Con esta nueva arquitectura, base de datos back-end ya no es el almacén de datos en tiempo real de un grupo de servidores. La información sobre un usuario en particular se guarda en tres servidores front-end del grupo. Para cada usuario habrá un servidor front-end que actuará como servidor de información principal y otros dos servidores front-end que actuarán como réplicas. Si uno de los servidores front-end deja de funcionar, se ascenderá automáticamente al rol de principal a otro de los dos servidores que sirven de réplica.

Esto ocurre en segundo plano y los administradores no necesitan saber qué servidores front-end son los principales para qué usuarios. Esta distribución del almacenamiento de datos ayuda a mejorar el rendimiento y la escalabilidad dentro del grupo de servidores y acaba con el problema de un solo punto de posibles errores que presenta la configuración de un solo Servidor back-end.

El servidor back-end se utiliza como almacén de copias de seguridad para datos de usuarios y conferencias y es también el almacén principal para otras bases de datos como la de grupo de respuesta.

Estas mejoras significan, además, que cambia la forma de planear y mantener los grupos de servidores. Se recomienda que todos sus Grupos de servidores front-end de Enterprise Edition incluyan al menos tres servidores front-end con el fin de ofrecer el máximo de réplicas para el cual está diseñada la arquitectura de Grupo de servidores front-end. Además, deberá seguir ciertos procedimientos al agregar servidores a un Grupo de servidores front-end, quitar servidores de él o actualizar servidores. Para obtener más información, consulte [Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

## Cambios en la topología de roles de servidor

Algunos roles de servidor que anteriormente se ejecutaban en servidores aparte se han consolidado en el rol de servidor front-end y esto permite ahorrar en costes de hardware.

  - En Lync Server 2013, el servidor de conferencia A/V siempre se instala con el servidor front-end.

  - Ahora, los front-end de Supervisión y Archivado se instalan siempre con el servidor front-end. Supervisión y Archivado siguen necesitando cada uno una base de datos back-end independiente, que puede instalarse en el mismo servidor que la base de datos back-end del grupo de servidores front-end o bien puede hospedarse en servidores back-end aparte.

  - Servidor de chat persistente es ahora un rol de servidor . En Microsoft Lync Server 2010, Servidor de chat en grupo era una aplicación de confianza de terceros para Microsoft Lync Server 2010. En Lync Server 2013, la funcionalidad Servidor de chat persistente se implementa utilizando tres nuevos roles de servidor:
    
      - **PersistentChatService :** servicios principales de Servidor de chat persistente implementados como rol de front-end
    
      - **PersistentChatStore :** rol de servidor back-end
    
      - **PersistentChatComplianceStore :** rol de servidor back-end para Cumplimiento de Chat persistente

