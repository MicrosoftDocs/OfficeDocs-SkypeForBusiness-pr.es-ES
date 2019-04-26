---
title: Planeación de alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Resumen: Lea este tema para obtener información sobre cómo planear una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: 88584c43cb205d10d2baacb6cb31c4e8fdbb228a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213833"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planeación de alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo planear una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015.
  
Alta disponibilidad y recuperación ante desastres para servidor de Chat persistente requieran recursos adicionales más allá de lo que normalmente es necesaria para la operación completa. 
  
> [!NOTE]
> El uso de Grupos de disponibilidad AlwaysOn de SQL no es compatible con las bases de datos del servidor de chat persistente. 

> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 
  
## <a name="resource-requirements"></a>Requisitos de recursos

Antes de configurar el servidor de Chat persistente de alta disponibilidad y recuperación ante desastres, asegúrese de que tiene los siguientes recursos adicionales. 
  
- Una instancia de base de datos dedicada que se encuentra en el mismo centro de datos físico en el que se encuentra el cliente principal del servicio de servidor de Chat persistente de. Esta base de datos servirá como el reflejo de SQL Server para la base de datos principal de Chat persistente. De forma opcional, designar un servidor de SQL adicional que sirva como el testigo de reflejo, si desea que una conmutación por error automática a la base de datos reflejada.
    
- Una instancia de base de datos dedicada ubicada en el otro centro de datos físico. Esta base de datos servirá como la base de datos secundaria trasvase de registros de SQL Server para la base de datos en el centro de datos principal.
    
- Una instancia de base de datos dedicada para que sirva como el reflejo de SQL Server para la base de datos secundaria. De forma opcional, designar un servidor de SQL adicional al servidor como el testigo de reflejo. Es preciso que ambos estén ubicados en el mismo centro de datos físico que la base de datos secundaria.
    
- Si está habilitado el cumplimiento del servidor de Chat persistente, se requieren un tres instancias adicionales de base de datos dedicada. Su distribución es la misma que los descritos anteriormente para la base de datos de Chat persistente. Aunque es posible para la base de datos de cumplimiento compartir la misma instancia de SQL Server como la base de datos de Chat persistente, se recomiendan instancias independientes para alta disponibilidad y recuperación ante desastres.
    
- Un recurso compartido de archivos debe ser creado y designado para los registros de transacciones de trasvase de registros de SQL Server. Todos los servidores de SQL Server en ambos centros de datos que se ejecutan las bases de datos de Chat persistente deben tener acceso de lectura y escritura para este recurso compartido de archivos. Este recurso compartido no está designado como parte del rol FileStore.
    
- Un recurso compartido de archivos en el servidor de base de datos secundaria para que sirva como carpeta de destino para los registros de transacciones de SQL Server que se copian desde el recurso compartido del servidor principal.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Soluciones de alta disponibilidad y recuperación ante desastres

Skype para Business Server admite varios modos de alta disponibilidad para los servidores Back-End, incluidas la creación de reflejo de base de datos. Para más información, vea [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La solución de recuperación ante desastres para servidor de Chat persistente que se describen en este tema se basa en un grupo de servidores de Chat persistente. No hay ningún requisito para una red de área local virtual (VLAN) extendida. Mediante la expansión de un grupo de servidores de Chat persistente, configurar un grupo de servidores en la topología de forma lógica, pero físicamente colocar los servidores en el grupo de servidores en centros de datos diferentes dos. Configure la creación de reflejos de SQL Server en la base de datos de la misma forma e implemente la base de datos y el reflejo en el mismo centro de datos. Tiene que configurar una base de datos de copia de seguridad en el centro de datos secundario (con un reflejo opcional para proporcionar alta disponibilidad durante la recuperación ante desastres). Esta es la base de datos de copia de seguridad que se usa para la conmutación por error durante la recuperación ante desastres. 
  
Para obtener información detallada acerca de cómo configurar la alta disponibilidad y recuperación ante desastres para servidor de Chat persistente, vea [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Las ilustraciones siguientes muestran cómo se puede configurar el grupo de servidores de Chat persistente en dos topologías de grupo de servidores estirados:
  
- Conversaciones en grupo de servidores persistente cuando los centros de datos se ubican geográficamente con ancho de banda alto y baja latencia.
    
- Conversaciones en grupo de servidores persistente cuando los centros de datos se ubican geográficamente con bajo ancho de banda y latencia alta.
    
La figura 1 muestra una topología de grupo de servidores de servidor de Chat persistente expandida donde los centros de datos son ubican geográficamente con ancho de banda alto y baja latencia. Se supone lo siguiente para las topologías de lógicas y físicas:
  
- La topología lógica incluye lo siguiente:
    
  - Un grupo de servidores de chat persistente en los sitios 1 y 2 que contiene los servidores de 1 a 8.
    
  - Un grupo de servidores de servidor Front-End, una base de datos de Chat persistente, una base de datos reflejada, y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) que se encuentran físicamente en sitio 1. 
    
  - Un segundo grupo de servidores front-end y una base de datos de copia de seguridad que reside físicamente en el sitio 2.
    
- La topología física consta de sitios 1 y 2 de la siguiente manera:
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 1 al 4, dos activos y dos inactivos en el sitio 1.
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 5 al 8, dos activos y dos inactivos en el sitio 2.
    
  - Un grupo de servidores de servidor Front-End, una base de datos de Chat persistente, una base de datos reflejada y, opcionalmente, un testigo base de datos (no se muestra en el diagrama) en el sitio 1.
    
  - Un grupo de servidores front-end, una base de datos de copia de seguridad, que es el destino del trasvase de registros de SQL en el sitio 2.
    
**Grupo de servidores de chat persistente extendido donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja**

![Grupo extendido de chat persistente con alto ancho de banda/baja latencia](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
La figura 2 muestra una topología de grupo de servidores de servidor de Chat persistente expandida donde los centros de datos son ubican geográficamente con bajo ancho de banda y latencia alta.
  
- La topología lógica incluye lo siguiente:
    
  - Un grupo de servidores de chat persistente en los sitios 1 y 2 que contiene los servidores de 1 a 8.
    
  - Un grupo de servidores de servidor Front-End, una base de datos de Chat persistente, una base de datos reflejada, y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) que se encuentran físicamente en sitio 1. 
    
  - Un segundo grupo de servidores front-end y una base de datos de copia de seguridad que reside físicamente en el sitio 2.
    
- La topología física consta de sitios 1 y 2 de la siguiente manera:
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 1 al 4, todos activos en el sitio 1.
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 5 al 8, todos inactivos en el sitio 2.
    
  - Un grupo de servidores de servidor Front-End, una base de datos de Chat persistente, una base de datos reflejada y, opcionalmente, un testigo base de datos (no se muestra en el diagrama) en el sitio 1.
    
  - Un grupo de servidores front-end, una base de datos de copia de seguridad, que es el destino del trasvase de registros de SQL en el sitio 2.
    
**Grupo de servidores de chat persistente extendidos donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta**

![Grupo extendido de chat persistente con bajo ancho de banda/alta latencia](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

