---
title: Planificación de la alta disponibilidad y de la recuperación ante desastres en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype para Business Server ofrece alta disponibilidad con agrupación, recuperación ante desastres con grupo de emparejamiento y varios modos de alta disponibilidad del servidor de extremo atrás, incluidos grupos de disponibilidad AlwaysOn, creación de reflejos de base de datos y organización por clústeres de conmutación por error SQL del servidor.
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a>Planificación de la alta disponibilidad y de la recuperación ante desastres en Skype Empresarial Server 2015
 
Skype para Business Server ofrece alta disponibilidad con agrupación, recuperación ante desastres con grupo de emparejamiento y varios modos de alta disponibilidad del servidor de extremo atrás, incluidos grupos de disponibilidad AlwaysOn, creación de reflejos de base de datos y organización por clústeres de conmutación por error SQL del servidor. 
  
Alta disponibilidad se refiere a asegurarse de que Skype para servicios Business Server están disponibles incluso si uno o más servidores deja de funcionar. La recuperación ante desastres se basa en preservar los servicios en caso de que ocurra un desastre natural o un error humano, intentando resguardar la mayor cantidad de datos que sea posible.
  
Como en versiones anteriores de Lync Server, la característica principal de alta disponibilidad para la mayoría de funciones de servidor en Skype para Business Server es la redundancia de servidor a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.
  
Skype para Business Server también proporciona opciones de recuperación de grupos de Front-End de desastres. Puede configurar dos grupos de servidores en distintas áreas geográficas para que funcionen como copias de seguridad entre ellas. Así pues, si tiene todo un grupo de servidores o un sitio y dejan de funcionar, el grupo de copia de seguridad puede seguir suministrando el servicio a los usuarios en ambos sitios.
  
Skype para Business Server también admite cuatro modos de alta disponibilidad para los servidores de fondo atrás: la creación de reflejo de base de datos, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error AlwaysOn (FCI) y organización por clústeres de conmutación por error SQL.
  
> [!NOTE]
> No se admiten grupos de disponibilidad AlwaysOn con servidores de charla persistente. 
  
En esta sección se explican estas características y trata además los pasos que puede tomar en la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor. 
  
## <a name="see-also"></a>Vea también

#### 

[Administración y frontal grupo de servidores de alta disponibilidad](high-availability.md)
  
[Frontal de recuperación de desastres de grupo final en Skype para Business Server 2015](disaster-recovery.md)
  
[Experiencia del usuario durante la falla de grupo en Skype para Business Server 2015](user-experience.md)
  
[Back End alta disponibilidad del servidor en Skype para Business Server 2015](back-end-server.md)
  
[Compartimiento de archivos alta disponibilidad en Skype para Business Server 2015](file-sharing.md)

