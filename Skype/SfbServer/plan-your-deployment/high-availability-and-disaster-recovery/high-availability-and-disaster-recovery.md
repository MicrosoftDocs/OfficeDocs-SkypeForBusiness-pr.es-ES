---
title: Planear la alta disponibilidad y la recuperación ante desastres en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de bases de datos y la creación de clústeres SQL conmutación por error.
ms.openlocfilehash: 37baa5627ef638c0a6835053bca9094564359d1a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828693"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planear la alta disponibilidad y la recuperación ante desastres en Skype Empresarial Server
 
Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de bases de datos y la creación de clústeres SQL conmutación por error. 
  
La alta disponibilidad se refiere a asegurarse de que Skype Empresarial Server servicios están disponibles incluso si uno o varios servidores se desvía. La recuperación ante desastres se refiere a mantener los servicios en caso de desastre natural o causado por personas y conservar tantos datos de antes del desastre como sea posible.
  
Al igual que en versiones anteriores de Lync Server, la característica principal de alta disponibilidad para la mayoría de los roles de servidor en Skype Empresarial Server es la redundancia de servidor mediante agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor. Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores.
  
Skype Empresarial Server también proporciona opciones de recuperación ante desastres para grupos de servidores front-end. Puede configurar dos grupos de servidores en áreas geográficas diferentes para que sirvan de copias de seguridad entre sí. A continuación, si tiene un grupo o sitio completo, el grupo de copia de seguridad puede seguir brindando servicio a los usuarios de ambos sitios.
  
Skype Empresarial Server admite cuatro modos de alta disponibilidad para los servidores back-end: creación de reflejos de SQL, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y clústeres de conmutación por error SQL servidor.
  
> [!NOTE]
> SQL La creación de reflejos está disponible Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error se prefieren Skype Empresarial Server 2019.

> [!NOTE]
> Los grupos de disponibilidad AlwaysOn no se admiten con servidores de chat persistente. 
  
En esta sección se explican estas características y también se explican los pasos que puede seguir para la alta disponibilidad y la recuperación ante desastres para algunos de sus otros roles de servidor. 
  
## <a name="see-also"></a>Consulte también

[Administración y alta disponibilidad del grupo de servidores front-end](high-availability.md)
  
[Recuperación ante desastres del grupo front-end en Skype Empresarial Server](disaster-recovery.md)
  
[Experiencia del usuario durante el error del grupo en Skype Empresarial Server](user-experience.md)
  
[Alta disponibilidad del servidor back-end en Skype Empresarial Server](back-end-server.md)
  
[Alta disponibilidad de uso compartido de archivos en Skype Empresarial Server](file-sharing.md)
