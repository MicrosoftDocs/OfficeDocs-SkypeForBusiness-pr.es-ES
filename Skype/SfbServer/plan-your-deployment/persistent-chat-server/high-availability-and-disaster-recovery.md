---
title: Planear la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Resumen: Lea este tema para obtener información sobre cómo planear la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: b9e509b987a9fe3b8d7755ce8d92f35c82b7d386
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297081"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planear la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo planear la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015.
  
La alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente requieren recursos adicionales más allá de lo que normalmente se necesita para una completa operación. 
  
> [!NOTE]
> El uso de Grupos de disponibilidad AlwaysOn de SQL no es compatible con las bases de datos del servidor de chat persistente. 

> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 
  
## <a name="resource-requirements"></a>Requisitos de recursos

Antes de configurar el servidor de chat persistente para una alta disponibilidad y recuperación ante desastres, asegúrese de tener los siguientes recursos adicionales. 
  
- Una instancia de base de datos dedicada ubicada en el mismo centro de datos físico en el que se encuentra el front-end del servicio del servidor de chat persistente. Esta base de datos servirá de SQL Server Mirror para la base de datos de chat persistente principal. De manera opcional, designe un servidor SQL Server adicional para que sirva como testigo de creación de reflejos si desea una conmutación automática para la base de datos reflejada.
    
- Una instancia de base de datos dedicada ubicada en el otro centro de datos físico. Esta base de datos servirá como la base de datos secundaria de trasvase de registros de SQL Server para la base de datos en el centro de datos principal.
    
- Una instancia de base de datos dedicada que servirá como reflejo de SQL Server para la base de datos secundaria. De manera opcional, designe un servidor SQL Server adicional como testigo de creación de reflejos. Es preciso que ambos estén ubicados en el mismo centro de datos físico que la base de datos secundaria.
    
- Si el cumplimiento del servidor de chat persistente está habilitado, se necesitan tres instancias de base de datos dedicadas adicionales. Su distribución es la misma que la de la base de datos de chat persistente anterior. Aunque es posible que la base de datos de cumplimiento comparta la misma instancia de SQL Server que la base de datos de chat persistente, se recomiendan instancias independientes para una alta disponibilidad y recuperación ante desastres.
    
- Es necesario crear y designar un recurso compartido de archivos para los registros de transacciones de trasvase de registros de SQL Server. Todos los servidores SQL de ambos centros de datos que ejecutan bases de datos de chat persistentes deben tener acceso de lectura y escritura a este recurso compartido de archivos. Este recurso compartido no está designado como parte del rol FileStore.
    
- Un recurso compartido de archivos en el servidor de la base de datos secundaria para que sirva como carpeta de destino para los registros de transacciones de SQL Server que se copian desde el recurso compartido de archivos del servidor principal.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Soluciones de alta disponibilidad y recuperación ante desastres

Skype empresarial Server admite varios modos de alta disponibilidad para los servidores back-end, incluyendo la creación de reflejos de bases de datos. Para más información, vea [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La solución de recuperación ante desastres para el servidor de chat persistente que se describe en este tema se ha creado en un grupo de servidores de chat persistente ampliado. No hay ningún requisito para una red de área local virtual (VLAN) extendida. Al estirar un grupo de servidores de chat persistente, se configura un grupo en la topología de forma lógica, pero se colocan físicamente los servidores en el grupo en dos centros de datos diferentes. Configure la creación de reflejos de SQL Server en la base de datos de la misma forma e implemente la base de datos y el reflejo en el mismo centro de datos. Tiene que configurar una base de datos de copia de seguridad en el centro de datos secundario (con un reflejo opcional para proporcionar alta disponibilidad durante la recuperación ante desastres). Esta es la base de datos de copia de seguridad que se usa para la conmutación por error durante la recuperación ante desastres. 
  
Para obtener más información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente, consulte [configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Las figuras siguientes muestran cómo se puede configurar el grupo de servidores de chat persistente en dos topologías de grupo extendidas diferentes:
  
- Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en un gran ancho de banda y baja latencia.
    
- Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en una ubicación geográfica con un ancho de banda bajo y una latencia alta.
    
En la ilustración 1 se muestra una topología de grupo de servidores de chat persistente superpuesto en la que los centros de datos se encuentran en un alto ancho de banda y baja latencia. Para las topologías lógicas y físicas, supongamos lo siguiente:
  
- La topología lógica incluye lo siguiente:
    
  - Un grupo de servidores de chat persistente en los sitios 1 y 2 que contiene los servidores de 1 a 8.
    
  - Un grupo de servidores front-end, una base de datos de chat persistente, una base de datos reflejada y, opcionalmente, una base de datos testigo (que no se muestra en el diagrama) reside físicamente en el sitio 1. 
    
  - Un segundo grupo de servidores front-end y una base de datos de copia de seguridad que reside físicamente en el sitio 2.
    
- La topología física consta de los sitios 1 y 2 de la siguiente manera:
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 1 al 4, dos activos y dos inactivos en el sitio 1.
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 5 al 8, dos activos y dos inactivos en el sitio 2.
    
  - Un grupo de servidores front-end, una base de datos de chat persistente, una base de datos reflejada y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) en el sitio 1.
    
  - Un grupo de servidores front-end, una base de datos de copia de seguridad, que es el destino del trasvase de registros de SQL en el sitio 2.
    
**Grupo de servidores de chat persistente extendido donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja**

![Grupo extendido de chat persistente con alto ancho de banda/baja latencia](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
La figura 2 muestra una topología de grupo de servidores de chat persistente superpuesto donde los centros de datos se encuentran en una ubicación geográfica con un ancho de banda bajo y una latencia elevada.
  
- La topología lógica incluye lo siguiente:
    
  - Un grupo de servidores de chat persistente en los sitios 1 y 2 que contiene los servidores de 1 a 8.
    
  - Un grupo de servidores front-end, una base de datos de chat persistente, una base de datos reflejada y, opcionalmente, una base de datos testigo (que no se muestra en el diagrama) reside físicamente en el sitio 1. 
    
  - Un segundo grupo de servidores front-end y una base de datos de copia de seguridad que reside físicamente en el sitio 2.
    
- La topología física consta de los sitios 1 y 2 de la siguiente manera:
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 1 al 4, todos activos en el sitio 1.
    
  - Un grupo de servidores de chat persistente, que incluye los servidores del 5 al 8, todos inactivos en el sitio 2.
    
  - Un grupo de servidores front-end, una base de datos de chat persistente, una base de datos reflejada y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) en el sitio 1.
    
  - Un grupo de servidores front-end, una base de datos de copia de seguridad, que es el destino del trasvase de registros de SQL en el sitio 2.
    
**Grupo de servidores de chat persistente extendidos donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta**

![Grupo extendido de chat persistente con bajo ancho de banda/alta latencia](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

