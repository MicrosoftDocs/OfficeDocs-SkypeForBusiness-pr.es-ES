---
title: Planeación de alta disponibilidad y recuperación ante desastres en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype para Business Server proporcione una alta disponibilidad con servidor de agrupación, recuperación ante desastres con el emparejamiento de grupo de servidores y varios modos de alta disponibilidad de servidor Back-End, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y agrupación en clústeres de conmutación por error SQL.
ms.openlocfilehash: 8ab0d41b93a47782fce4a44acf1e8305a9ad13e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910336"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planeación de alta disponibilidad y recuperación ante desastres en Skype para Business Server
 
Skype para Business Server proporcione una alta disponibilidad con servidor de agrupación, recuperación ante desastres con el emparejamiento de grupo de servidores y varios modos de alta disponibilidad de servidor Back-End, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y agrupación en clústeres de conmutación por error SQL. 
  
Alta disponibilidad hace referencia a asegurándose de que Skype para servicios de Business Server están disponibles incluso si uno o más servidores deja de funcionar. Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
Al igual que en versiones anteriores de Lync Server, la característica principal de alta disponibilidad para la mayoría de roles de servidor de Skype para Business Server es la redundancia de servidor a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.
  
Skype para Business Server también proporciona opciones de recuperación de grupos de servidores Front-End de ante desastres. Puede configurar dos grupos de servidores en distintas áreas geográficas para que funcionen como copias de seguridad entre ellas. Así pues, si tiene todo un grupo de servidores o un sitio y dejan de funcionar, el grupo de copia de seguridad puede seguir suministrando el servicio a los usuarios en ambos sitios.
  
Skype para Business Server también admite cuatro modos de alta disponibilidad para los servidores Back-End: SQL la creación de reflejos, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y agrupación en clústeres de conmutación por error SQL.
  
> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. Los métodos de agrupación en clústeres de conmutación por error de grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL son preferidos con Skype para Business Server 2019.

> [!NOTE]
> Grupos de disponibilidad AlwaysOn no son compatibles con servidores de Chat persistente. 
  
En esta sección se explican estas características y trata además los pasos que puede tomar en la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor. 
  
## <a name="see-also"></a>Vea también

[Alta disponibilidad y administración del grupo de servidores front-end](high-availability.md)
  
[Front-recuperación de desastres de grupo de servidores de final en Skype para Business Server](disaster-recovery.md)
  
[Experiencia del usuario durante error de grupo de servidores en Skype para Business Server](user-experience.md)
  
[Back-End alta disponibilidad del servidor en Skype para Business Server](back-end-server.md)
  
[Archivo de uso compartido de alta disponibilidad en Skype para Business Server](file-sharing.md)
