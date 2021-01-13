---
title: Implementar la alta disponibilidad y la recuperación ante desastres
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos de servidores y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor.
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830620"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Implementar la alta disponibilidad y la recuperación ante desastres
 
Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos de servidores y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor. 
  
La alta disponibilidad hace referencia a asegurarse de que los servicios de Skype Empresarial Server están disponibles incluso si uno o más servidores no están disponibles. La recuperación ante desastres se refiere a mantener los servicios en el caso de un desastre natural o causado por personas, y conservar tantos datos de antes del desastre como sea posible.
  
En esta sección se explica cómo implementar estas características y también se tratan los pasos que puede seguir para la alta disponibilidad y la recuperación ante desastres para algunos de los otros roles de servidor.

> [!NOTE]
> SQL mirroring está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error son preferidos con Skype Empresarial Server 2019.
  
## <a name="related-sections"></a>Secciones relacionadas

[Planear la alta disponibilidad y la recuperación ante desastres en Skype Empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Ver también

[Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server](alwayson-availability-group.md)

[Implementar grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server](front-end-pools-for-disaster-recovery.md)
  
[Implementar SQL creación de reflejos para alta disponibilidad del servidor back-end en Skype Empresarial Server 2015](sql-mirroring-for-high-availability.md)
  
