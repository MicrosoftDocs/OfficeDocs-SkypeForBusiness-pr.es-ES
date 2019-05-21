---
title: Planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype empresarial Server ofrece alta disponibilidad con la agrupación de servidores, la recuperación ante desastres con emparejamiento de bloque y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y el clúster de conmutación por error de SQL.
ms.openlocfilehash: 3ed1a3e5eff5d793f835c901e2cc5683da22bc77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297466"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server
 
Skype empresarial Server ofrece alta disponibilidad con la agrupación de servidores, la recuperación ante desastres con emparejamiento de bloque y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y el clúster de conmutación por error de SQL. 
  
La alta disponibilidad se refiere a asegurarse de que los servicios de Skype empresarial Server estén disponibles incluso si uno o más servidores están desactivados. Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
Como en las versiones anteriores de Lync Server, la característica de alta disponibilidad principal para la mayoría de los roles de servidor de Skype empresarial Server es la redundancia de servidores a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.
  
Skype empresarial Server también proporciona opciones de recuperación ante desastres para las agrupaciones front end. Puede configurar dos grupos de servidores en distintas áreas geográficas para que funcionen como copias de seguridad entre ellas. Así pues, si tiene todo un grupo de servidores o un sitio y dejan de funcionar, el grupo de copia de seguridad puede seguir suministrando el servicio a los usuarios en ambos sitios.
  
Skype empresarial Server también admite cuatro modos de alta disponibilidad para los servidores back-end: SQL Mirroring, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) siempre y clústeres de conmutación por error de SQL.
  
> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn, y los métodos de clúster de conmutación por error de SQL son preferidos con Skype empresarial Server 2019.

> [!NOTE]
> Los grupos de disponibilidad AlwaysOn no son compatibles con los servidores de chat persistentes. 
  
En esta sección se explican estas características y trata además los pasos que puede tomar en la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor. 
  
## <a name="see-also"></a>Vea también

[Alta disponibilidad y administración del grupo de servidores front-end](high-availability.md)
  
[Recuperación ante desastres del grupo de servidores front-end en Skype empresarial Server](disaster-recovery.md)
  
[Experiencia de usuario durante la falla de un grupo de servidores de Skype empresarial](user-experience.md)
  
[Servidor back-end de alta disponibilidad en Skype empresarial Server](back-end-server.md)
  
[Alta disponibilidad del uso compartido de archivos en Skype empresarial Server](file-sharing.md)
