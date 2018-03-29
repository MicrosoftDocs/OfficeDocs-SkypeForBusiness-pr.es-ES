---
title: Plan para alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Resumen: Leer este tema para aprender a planear para alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype Business Server 2015.'
ms.openlocfilehash: 2730d72b47d02772bf2c5c59c819bbe23e8816db
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plan para alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015
 
**Resumen:** Lea este tema para aprender a planear para alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype Business Server 2015.
  
Alta disponibilidad y recuperación ante desastres para el servidor de charla persistente requieren recursos adicionales más allá de lo que se necesita normalmente para una operación completa. 
  
> [!NOTE]
> El uso de Grupos de disponibilidad AlwaysOn de SQL no es compatible con las bases de datos del servidor de chat persistente. 
  
## <a name="resource-requirements"></a>Requisitos de recursos

Antes de configurar el servidor de charla persistente para alta disponibilidad y recuperación ante desastres, asegúrese de que tiene los siguientes recursos adicionales. 
  
- Una instancia de base de datos dedicado ubicada en el mismo centro de datos físico donde se encuentra el frontales de inicio del servicio del servidor de Chat persistentes. Esta base de datos servirá como la duplicación de SQL Server para la base de datos principal de Chat persistentes. Si lo desea, designe un SQL Server adicionales para servir como testigo espejado si desea un failover automático para la base de datos reflejada.
    
- Una instancia de base de datos dedicada ubicada en el otro centro de datos físico. Esta base de datos servirá como la base de datos secundaria trasvase de registros de SQL Server para la base de datos en el data center primario.
    
- Una instancia de base de datos dedicada a servir como la duplicación de SQL Server para la base de datos secundaria. Opcionalmente, puede designar un adicional de SQL Server al servidor como testigo espejado. Es preciso que ambos estén ubicados en el mismo centro de datos físico que la base de datos secundaria.
    
- Si está habilitado el cumplimiento del servidor de charla persistente, un tres instancias de base de datos dedicado adicional se requieren. Su distribución es las mismas que las descritas anteriormente para la base de datos persistente de charla. Mientras que es posible que la base de datos de cumplimiento de normas comparten la misma instancia de SQL Server como base de datos persistente de charla, se recomiendan las instancias independientes de alta disponibilidad y recuperación ante desastres.
    
- Debe crear un recurso compartido de archivos y designado para los registros de transacciones de trasvase de registros de SQL Server. Todos los servidores SQL en dos centros de datos que ejecutan bases de datos persistente de charla debe tener acceso de lectura/escritura a este archivo compartido. Este recurso compartido no está designado como parte del rol FileStore.
    
- Un recurso compartido de archivos en el servidor de base de datos secundaria para servir como carpeta de destino para los registros de transacciones de SQL Server que se copian desde el recurso compartido del servidor principal.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Soluciones de alta disponibilidad y recuperación ante desastres

Skype para Business Server admite varios modos de alta disponibilidad para su nuevo servidores de fondo, incluidos el espejado de la base de datos. Para obtener más información, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La solución de recuperación ante desastres para servidor de Chat persistentes descritas en este tema se basa en un grupo de servidores de charla persistente extendido. No hay ningún requisito para una red de área local virtual (VLAN) extendida. Mediante la expansión de un grupo de servidores de charla persistente, configurar un grupo en la topología lógica, pero físicamente se coloque los servidores en el grupo en dos diferentes centros de datos. Configure la creación de reflejos de SQL Server en la base de datos de la misma forma e implemente la base de datos y el reflejo en el mismo centro de datos. Tiene que configurar una base de datos de copia de seguridad en el centro de datos secundario (con un reflejo opcional para proporcionar alta disponibilidad durante la recuperación ante desastres). Esta es la base de datos de copia de seguridad que se usa para la conmutación por error durante la recuperación ante desastres. 
  
Para obtener más información acerca de cómo configurar alta disponibilidad y recuperación ante desastres para el servidor de charla persistente, consulte [configurar alta disponibilidad y recuperación ante desastres para el servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Las ilustraciones siguientes muestran cómo se puede configurar el grupo de servidor de charla persistente en dos topologías diferentes grupo extendida:
  
- Grupo de servidor de charla persistente estirado cuando data centers están ubicados geo con alto ancho de banda y baja latencia.
    
- Grupo de servidor de charla persistente estirado cuando data centers están ubicados geo con latencia de ancho de banda bajo o alto.
    
Figura 1 muestra una topología de grupo de servidor de charla persistente estirada en data centers están ubicados geo con alto ancho de banda y baja latencia. Supongamos lo siguiente para las topologías lógicas y físicas:
  
- La topología lógica incluye lo siguiente:
    
  - Un grupo de servidores de chat persistente en los sitios 1 y 2 que contiene los servidores de 1 a 8.
    
  - Un grupo de servidor Front-End, una base de datos persistente de charla, una base de datos reflejada y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) que se encuentran físicamente en sitio 1. 
    
  - Un segundo grupo de servidores front-end y una base de datos de copia de seguridad que reside físicamente en el sitio 2.
    
- La topología física consiste en los sitios 1 y 2 como sigue:
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 1 al 4, dos activos y dos inactivos en el sitio 1.
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 5 al 8, dos activos y dos inactivos en el sitio 2.
    
  - Un grupo de servidor Front-End, una base de datos persistente de charla, una base de datos reflejada y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) en el sitio 1.
    
  - Un grupo de servidores front-end, una base de datos de copia de seguridad, que es el destino del trasvase de registros de SQL en el sitio 2.
    
**Estirado grupo persistente Chat Server data centers están ubicados geo con alto ancho de banda y baja latencia**

![Grupo extendido de chat persistente con alto ancho de banda/baja latencia](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
Figura 2 muestra una topología de grupo de servidor de charla persistente extendida donde data centers están ubicados geo con latencia de ancho de banda bajo o alto.
  
- La topología lógica incluye lo siguiente:
    
  - Un grupo de servidores de chat persistente en los sitios 1 y 2 que contiene los servidores de 1 a 8.
    
  - Un grupo de servidor Front-End, una base de datos persistente de charla, una base de datos reflejada y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) que se encuentran físicamente en sitio 1. 
    
  - Un segundo grupo de servidores front-end y una base de datos de copia de seguridad que reside físicamente en el sitio 2.
    
- La topología física consiste en los sitios 1 y 2 como sigue:
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 1 al 4, todos activos en el sitio 1.
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 5 al 8, todos inactivos en el sitio 2.
    
  - Un grupo de servidor Front-End, una base de datos persistente de charla, una base de datos reflejada y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) en el sitio 1.
    
  - Un grupo de servidores front-end, una base de datos de copia de seguridad, que es el destino del trasvase de registros de SQL en el sitio 2.
    
**Estirado grupo persistente Chat Server data centers están ubicados geo con latencia baja de alto/ancho de banda**

![Grupo extendido de chat persistente con bajo ancho de banda/alta latencia](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

