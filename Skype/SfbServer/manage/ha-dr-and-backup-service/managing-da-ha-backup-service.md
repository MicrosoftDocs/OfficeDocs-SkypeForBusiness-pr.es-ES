---
title: Administración de recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información acerca de los procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos en grupos de servidores Front-End emparejados.
ms.openlocfilehash: 9215dba11b388b3ffbd3e5c0f3de4ccf1cb85c7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903133"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Administración de Skype para recuperación ante desastres de servidor empresarial, alta disponibilidad y servicio de copia de seguridad

Esta sección contiene procedimientos para operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos en grupos de servidores Front-End emparejados.

Procedimientos de recuperación ante desastres, conmutación por error y conmutación por recuperación, son manuales. Si no hay un desastre, el administrador debe invocar manualmente los procedimientos de conmutación por error. El mismo se aplica a la conmutación por recuperación una vez reparado el grupo de servidores.

Los procedimientos de recuperación ante desastres en esta sección suponen lo siguiente:

  - Tiene una implementación con grupos de servidores Front-End emparejados, que se encuentra en sitios diferentes, tal como se describe en el [Plan de alta disponibilidad y recuperación ante desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). El servicio de copia de seguridad se ha ejecutado en estos grupos de servidores emparejados para mantenerlos sincronizados.

  - Si el almacén de Administración Central está hospedado en cualquier grupo de servidores, está instalado y se está ejecutando en ambos de los grupos de servidores emparejados con uno de esos grupos de servidores que hospedan al maestro activo y el grupo de hospedaje el estado de espera.

> [!IMPORTANT]
> En los siguientes procedimientos, el parámetro *PoolFQDN* hace referencia al FQDN del grupo de servidores que se ve afectada por ante desastres, no el grupo de servidores que afecta a los usuarios se redirigen desde. Para el mismo conjunto de usuarios afectados, hace referencia al mismo grupo de servidores en los cmdlets de conmutación por error y conmutación por recuperación (es decir, el grupo de servidores que hospedados en primer lugar los usuarios antes de la conmutación por error).<BR><br>Por ejemplo, supongamos que un caso en el que todos los usuarios alojados en un grupo de servidores P1 se conmuta por error para el grupo de copia de seguridad, P2. Si el administrador desea mover todos los usuarios que actualmente atendidos por P2 a se pasarán por P1, el administrador debe realizar los siguientes pasos: 
> <OL>
> <LI>
> <P>Fail hacer una copia de todos los usuarios hospedados originalmente en P1 de P2 a P1 mediante el cmdlet de la conmutación por recuperación. En este caso, el *PoolFQDN* es P1 FQDN.</P>
> <LI>
> <P>Conmutar por error todos los usuarios hospedados originalmente en P2 a P1 mediante el cmdlet de conmutación por error. En este caso, el PoolFQDN es P2 FQDN.</P>
> <LI>
> <P>Si más adelante, el administrador desea conmutar por recuperación los usuarios de P2 a P2, el PoolFQDN es P2 FQDN.</P></LI></OL><br>Tenga en cuenta ese paso 1 anterior debe realizarse antes del paso 2 para conservar la integridad del grupo de servidores. Si intenta paso 2 antes del paso 1, se producirá un error en el cmdlet del paso 2.


## <a name="see-also"></a>Vea también

[Planificar la alta disponibilidad y la recuperación ante desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
