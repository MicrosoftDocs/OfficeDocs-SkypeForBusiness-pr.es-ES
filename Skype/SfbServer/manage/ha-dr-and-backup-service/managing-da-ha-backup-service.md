---
title: 'Administración de recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad'
ms.reviewer: null
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Obtenga información sobre los procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos en grupos de servidores front-end emparejados.'
---


# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Administración Skype Empresarial Server recuperación ante desastres, alta disponibilidad y servicio de copia de seguridad

Esta sección contiene procedimientos para las operaciones de recuperación ante desastres, así como para mantener el servicio de copia de seguridad, que sincroniza los datos en grupos de servidores front-end emparejados.

Los procedimientos de recuperación ante desastres, tanto de conmutación por error, como por recuperación, son manuales. Si se produce un desastre, el administrador deberá invocar manualmente los procedimientos de conmutación por error. Y lo mismo ocurre con la conmutación por recuperación después de la reparación del grupo de servidores.

Los procedimientos de recuperación ante desastres de esta sección suponen lo siguiente:

  - Tiene una implementación con grupos de servidores front-end emparejados, ubicados en diferentes sitios, como se describe en [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). El Servicio de copia de seguridad se ha estado ejecutando en estos grupos emparejados para mantenerlos sincronizados.

  - Si el almacén de administración central se hospeda en cualquiera de los grupos de servidores, se instala y se ejecuta en ambos grupos de servidores emparejados, con uno de esos grupos que hospeda el patrón activo y el otro grupo de servidores que hospeda la espera.

> [!IMPORTANT]
> En los procedimientos siguientes, el parámetro *PoolFQDN* hace referencia al FQDN del grupo afectado por el desastre y no al grupo desde el cual se redirige a los usuarios afectados. Para el mismo conjunto de usuarios afectados, se refiere al mismo grupo tanto en los cmdlets de conmutación por error, como de conmutación por recuperación (es decir, el grupo de servidores que hospedó en primer lugar a los usuarios antes de la conmutación por error).<BR><br>Por ejemplo, supongamos que se hizo de la conmutación por error de todos los usuarios hospedados en el grupo P1 al grupo de servidores de reserva, el P2. Si el administrador quiere mover a todos los usuarios que actualmente están siendo atendidos por P2 a P1, el administrador deberá dar los siguientes pasos: 
> <OL>
> <LI>
> <P>Conmutar por recuperación a todos los usuarios hospedados inicialmente en P1 de P2 a P1 usando el cmdlet de conmutación por recuperación. En este caso, el *PoolFQDN* es el FQDN de P1.</P>
> <LI>
> <P>Conmutar por error a todos los usuarios hospedados inicialmente en P2 a P1 usando el cmdlet de conmutación por error. En este caso, el PoolFQDN es el FQDN de P2.</P>
> <LI>
> <P>Si después el administrador desea llevar a cabo la conmutación por recuperación de los usuarios de P2 de vuelta a P2, el PoolFQDN será el FQDN de P2.</P></LI></OL><br>Observe que el paso 1 anterior se debe llevar a cabo antes que el paso 2 para mantener la integridad del grupo de servidores. Si intenta realizar el paso 2 antes que el paso 1, el cmdlet del paso 2 no se completará correctamente.


## <a name="see-also"></a>Vea también

[Planear la alta disponibilidad y la recuperación ante desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
