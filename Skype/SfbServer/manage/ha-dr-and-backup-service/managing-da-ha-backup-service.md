---
title: Administración de recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga más información sobre procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos de las agrupaciones frontales emparejadas.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303901"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Administración de la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad de Skype empresarial Server

Esta sección contiene procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos de las agrupaciones frontales emparejadas.

Los procedimientos de recuperación ante desastres, tanto de failover como failback, son manuales. Si se produce un desastre, el administrador debe invocar manualmente los procedimientos de conmutación por error. Lo mismo se aplica a la conmutación por recuperación después de reparar el grupo.

Los procedimientos de recuperación de desastres de esta sección suponen lo siguiente:

  - Tiene una implementación con las agrupaciones frontales emparejadas, que se encuentran en diferentes sitios, como se describe en [planear la alta disponibilidad y la recuperación ante desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). El servicio de copia de seguridad se ha ejecutado en estas agrupaciones emparejadas para mantenerlas sincronizadas.

  - Si el almacén central de administración se encuentra en cualquiera de las dos agrupaciones, se instalará y se ejecutará en ambos pools emparejados, con uno de esos grupos que alojen el maestro activo y el otro grupo que aloje al modo de espera.

> [!IMPORTANT]
> En los procedimientos siguientes, el parámetro *PoolFQDN* se refiere al FQDN del grupo de servidores que se ve afectado por el desastre, no al grupo desde el que se redirige a los usuarios afectados. Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo en cmdlets de conmutación por error y de conmutación por error (es decir, el grupo que ha alojado primero los usuarios antes de la conmutación por error).<BR><br>Por ejemplo, supongamos que se produjo un error en todos los usuarios alojados en un grupo P1 en el grupo de copia de seguridad, P2. Si el administrador desea mover todos los usuarios que actualmente son atendidas por P2, el administrador debe realizar los siguientes pasos: 
> <OL>
> <LI>
> <P>Realice la conmutación por recuperación de todos los usuarios originalmente alojados en P1 desde P2 a P1 con el cmdlet de conmutación por recuperación. En este caso, el *PoolFQDN* es P1's FQDN.</P>
> <LI>
> <P>Conmute por error a todos los usuarios que se hayan alojado originalmente en P2 a P1 mediante el cmdlet de conmutación por error. En este caso, el PoolFQDN es P2's FQDN.</P>
> <LI>
> <P>Si, posteriormente, el administrador desea volver a realizar la conmutación por error de esos usuarios P2 a P2, la PoolFQDN es P2's FQDN.</P></LI></OL><br>Tenga en cuenta que el paso 1 anterior debe realizarse antes del paso 2 para preservar la integridad del grupo. Si intenta paso 2 antes del paso 1, se producirá un error en el cmdlet paso 2.


## <a name="see-also"></a>Vea también

[Planificar la alta disponibilidad y la recuperación ante desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
