---
title: Plan for high availability and disaster recovery for Persistent Chat Server in Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Summary: Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype Empresarial Server 2015.'
ms.openlocfilehash: 029258461e4248ccaebb6e3787f49d544f7fe4a2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391872"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plan for high availability and disaster recovery for Persistent Chat Server in Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo planear la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015.
  
La alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente requieren recursos adicionales más allá de lo que normalmente se necesita para una operación completa. 
  
> [!NOTE]
> El SQL los grupos de disponibilidad AlwaysOn no se admite con las bases de datos del servidor de chat persistente. 

> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015. 
  
## <a name="resource-requirements"></a>Requisitos de recursos

Antes de configurar el servidor de chat persistente para la alta disponibilidad y la recuperación ante desastres, asegúrese de que tiene los siguientes recursos adicionales. 
  
- Una instancia de base de datos dedicada ubicada en el mismo centro de datos físico en el que se encuentra el front-end principal del servicio de servidor de chat persistente. Esta base de datos servirá como reflejo SQL Server para la base de datos de chat persistente principal. Opcionalmente, designe un SQL Server adicional para que sirva como testigo de creación de reflejo si desea una conmutación por error automatizada en la base de datos reflejada.
    
- Una instancia de base de datos dedicada ubicada en el otro centro de datos físico. Esta base de datos servirá como la SQL Server secundaria de trasvase de registros para la base de datos en el centro de datos principal.
    
- Una instancia de base de datos dedicada para que sirva como SQL Server reflejo de la base de datos secundaria. Opcionalmente, designe una SQL Server adicional al servidor como testigo de creación de reflejo. Ambos deben estar ubicados en el mismo centro de datos físico que la base de datos secundaria.
    
- Si el cumplimiento del servidor de chat persistente está habilitado, se requieren tres instancias de base de datos dedicadas adicionales. Su distribución es la misma que las descritas anteriormente para la base de datos de chat persistente. Aunque es posible que la base de datos de cumplimiento comparta la misma instancia de SQL Server que la base de datos de chat persistente, se recomiendan instancias independientes para alta disponibilidad y recuperación ante desastres.
    
- Se debe crear y designar un recurso compartido de archivos para los SQL Server de transacciones de trasvase de registros. Todos los SQL en ambos centros de datos que ejecutan bases de datos de chat persistente deben tener acceso de lectura y escritura a este recurso compartido de archivos. Este recurso compartido no está designado como parte del rol FileStore.
    
- Un recurso compartido de archivos en el servidor de base de datos secundario para que sirva como carpeta de destino para los SQL Server de transacciones que se copian del recurso compartido de archivos del servidor principal.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Recuperación ante desastres y soluciones de alta disponibilidad

Skype Empresarial Server admite varios modos de alta disponibilidad para los servidores back-end, incluida la creación de reflejo de la base de datos. Para obtener más información, vea [Plan for high availability and disaster recovery in Skype Empresarial Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La solución de recuperación ante desastres para el servidor de chat persistente que se describe en este tema se basa en un grupo de servidores de chat persistente extendido. No hay ningún requisito para una red de área local virtual (VLAN) estirada. Al ampliar un grupo de servidores de chat persistente, se configura lógicamente un grupo de servidores en la topología, pero se coloca físicamente los servidores en el grupo de servidores en dos centros de datos diferentes. Puede configurar SQL Server creación de reflejo para la base de datos de la misma manera e implementar la base de datos y el reflejo en el mismo centro de datos. Debe configurar una base de datos de copia de seguridad en el centro de datos secundario (con un reflejo opcional para proporcionar alta disponibilidad durante la recuperación ante desastres). Esta es la base de datos de copia de seguridad usada para la conmutación por error durante la recuperación ante desastres. 
  
Para obtener más información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente, vea [Configure high availability and disaster recovery for Persistent Chat Server in Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Las siguientes cifras muestran cómo se puede configurar el grupo de servidores de chat persistente en dos topologías de grupo extendido diferentes:
  
- Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja
    
- Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta
    
La figura 1 muestra una topología de grupo de servidores de chat persistente estirada donde los centros de datos se ubican geográficamente con un ancho de banda alto/baja latencia. Supongamos lo siguiente para las topologías lógicas y físicas:
  
- La topología lógica consta de lo siguiente:
    
  - Un grupo de chat persistente en los sitios 1 y 2 que contienen servidores del 1 al 8.
    
  - Un grupo de servidores front-end, una base de datos de chat persistente, una base de datos reflejada y, opcionalmente, una base de datos testigo (no mostrada en el diagrama) que reside físicamente en el sitio 1. 
    
  - Un segundo grupo de servidores front-end y una base de datos de copia de seguridad que reside físicamente en el sitio 2.
    
- La topología física consta de los sitios 1 y 2 de la siguiente manera:
    
  - Un grupo de chat persistente, que contiene los servidores del 1 al 4, dos activos y dos inactivos en el sitio 1.
    
  - Un grupo de chat persistente, que contiene servidores del 5 al 8, dos activos, dos inactivos en el sitio 2.
    
  - Un grupo de servidores front-end, una base de datos de chat persistente, una base de datos reflejada y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) en el sitio 1.
    
  - Un grupo de servidores front-end y una base de datos de copia de seguridad, que es el SQL de trasvase de registros, en el sitio 2.
    
**Grupo de servidores de chat persistente extendido cuando los centros de datos están ubicados geográficamente con ancho de banda alto/baja latencia**

![Grupo extendido de chat persistente con ancho de banda alto/baja latencia.](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
La figura 2 muestra una topología de grupo de servidores de chat persistente estirada donde los centros de datos se ubican geográficamente con un ancho de banda bajo/latencia alta.
  
- La topología lógica consta de lo siguiente:
    
  - Un grupo de chat persistente en los sitios 1 y 2 que contienen servidores del 1 al 8.
    
  - Un grupo de servidores front-end, una base de datos de chat persistente, una base de datos reflejada y, opcionalmente, una base de datos testigo (no mostrada en el diagrama) que reside físicamente en el sitio 1. 
    
  - Un segundo grupo de servidores front-end y una base de datos de copia de seguridad que reside físicamente en el sitio 2.
    
- La topología física consta de los sitios 1 y 2 de la siguiente manera:
    
  - Un grupo de chat persistente, que contiene los servidores del 1 al 4, todos activos, en el sitio 1.
    
  - Un grupo de chat persistente, que contiene los servidores del 5 al 8, todos inactivos, en el sitio 2.
    
  - Un grupo de servidores front-end, una base de datos de chat persistente, una base de datos reflejada y, opcionalmente, una base de datos testigo (no se muestra en el diagrama) en el sitio 1.
    
  - Un grupo de servidores front-end y una base de datos de copia de seguridad, que es el SQL de trasvase de registros, en el sitio 2.
    
**Grupo de servidores de chat persistente extendido cuando los centros de datos se ubican geográficamente con bajo ancho de banda/alta latencia**

![Grupo extendido de chat persistente con bajo ancho de banda/alta latencia.](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

