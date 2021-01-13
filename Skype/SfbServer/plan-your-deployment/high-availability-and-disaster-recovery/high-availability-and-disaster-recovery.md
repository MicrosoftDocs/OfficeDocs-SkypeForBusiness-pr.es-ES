---
title: Planear la alta disponibilidad y la recuperación ante desastres en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos de servidores y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802820"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planear la alta disponibilidad y la recuperación ante desastres en Skype Empresarial Server
 
Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos de servidores y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor. 
  
La alta disponibilidad hace referencia a asegurarse de que los servicios de Skype Empresarial Server están disponibles incluso si uno o más servidores no están disponibles. La recuperación ante desastres se refiere a mantener los servicios en el caso de un desastre natural o causado por personas, y conservar tantos datos de antes del desastre como sea posible.
  
Al igual que en versiones anteriores de Lync Server, la principal característica de alta disponibilidad para la mayoría de los roles de servidor en Skype Empresarial Server es la redundancia de servidores mediante agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor. Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores.
  
Skype Empresarial Server también proporciona opciones de recuperación ante desastres para grupos de servidores front-end. Puede configurar dos grupos de servidores en diferentes áreas geográficas para que sirvan como copias de seguridad entre sí. A continuación, si tiene un grupo de servidores o un sitio completo, el grupo de copia de seguridad puede seguir brindando servicio a los usuarios de ambos sitios.
  
Skype Empresarial Server también admite cuatro modos de alta disponibilidad para los servidores back-end: creación de reflejos de SQL, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y clústeres de conmutación SQL conmutación por error.
  
> [!NOTE]
> SQL mirroring está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error son preferidos con Skype Empresarial Server 2019.

> [!NOTE]
> Los grupos de disponibilidad AlwaysOn no son compatibles con los servidores de chat persistente. 
  
En esta sección se explican estas características y también se explican los pasos que puede seguir para la alta disponibilidad y la recuperación ante desastres para algunos de los otros roles de servidor. 
  
## <a name="see-also"></a>Vea también

[Alta disponibilidad y administración del grupo de servidores front-end](high-availability.md)
  
[Recuperación ante desastres del grupo de servidores front-end en Skype Empresarial Server](disaster-recovery.md)
  
[Experiencia del usuario durante el error del grupo en Skype Empresarial Server](user-experience.md)
  
[Alta disponibilidad del servidor back-end en Skype Empresarial Server](back-end-server.md)
  
[Alta disponibilidad de uso compartido de archivos en Skype Empresarial Server](file-sharing.md)
