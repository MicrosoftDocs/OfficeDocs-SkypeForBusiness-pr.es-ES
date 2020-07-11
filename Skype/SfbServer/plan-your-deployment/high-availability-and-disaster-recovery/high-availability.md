---
title: Alta disponibilidad y administración del grupo de servidores front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Obtenga información sobre la administración de grupos de servidores front-end en Skype empresarial Server, incluida la administración de grupos, la pérdida de quórum y los pasos especiales para grupos de servidores con solo dos servidores front-end.
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098438"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidad y administración del grupo de servidores front-end
 
Obtenga información sobre la administración de grupos de servidores front-end en Skype empresarial Server, incluida la administración de grupos, la pérdida de quórum y los pasos especiales para grupos de servidores con solo dos servidores front-end.
  
En Skype empresarial Server, la arquitectura de los grupos de servidores front-end usa un modelo de sistemas distribuidos, con todos los datos de cada usuario en un máximo de tres servidores front-end en el grupo. Se recomienda que todos los grupos de servidores front-end Enterprise Edition incluyan al menos tres servidores front-end.

> [!NOTE]
> Skype empresarial Server 2019 no es compatible con grupos de servidores front-end Enterprise Edition con dos servidores front-end y no permite que la topología se publique en ese escenario.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planeación de la administración de grupos de servidores front-end

 Skype empresarial Server usa un modelo de sistemas distribuidos basado en Windows fabric. En este modelo, los datos importantes para cada usuario y Conferencia se almacenan en tres servidores front-end en un grupo de servidores front-end. Estos tres servidores que almacenan un determinado conjunto de datos son calledreplicas.
  
Con el modelo distribuido para los grupos de servidores front-end, se deben ejecutar determinados números de servidores de un grupo para que el grupo funcione. Hay dos modos de pérdida para un grupo de servidores.
  
- Pérdida de quórum de nivel de grupo de enrutamiento, debido a que no hay suficientes servidores de réplica para un grupo de enrutamiento en particular. Un grupo de enrutamiento es un conjunto de usuarios hospedados en el grupo de servidores. Cada grupo de enrutamiento tiene tres réplicas en el Grupo: una réplica principal y dos réplicas secundarias.
    
- Pérdida de quórum de nivel de grupo de servidores, que se produce cuando no hay suficientes servidores semilla ejecutándose en el grupo. 
    
### <a name="routing-group-level-quorum-loss"></a>Pérdida de quórum en el nivel de grupo de enrutamiento

La primera vez que inicie un nuevo grupo de servidores front-end, es esencial que 85% de los servidores estén en funcionamiento, como se muestra en la siguiente tabla. Si se están ejecutando menos servidores, es posible que los servicios estén atascados en el estado inicial y que el grupo no se inicie.
  
|Número total de servidores del grupo  <br/> |Número de servidores que deben estar en ejecución para que el grupo se inicie por primera vez  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **para Skype empresarial Server 2019** <br/> |12   <br/> |


   
Cada vez que se inicia el grupo, se debe iniciar el 85% de los servidores (como se muestra en la tabla anterior). Si no se puede iniciar este número de servidores (pero se pueden iniciar suficientes servidores para que no se pierda el quórum en el nivel de grupo), puede usar el `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet para permitir que el grupo se recupere de esta pérdida de quórum en el nivel de grupo de enrutamiento y realice el progreso. Para obtener más información acerca de cómo usar este cmdlet, consulte [RESET-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> En los grupos con un número par de servidores, Skype empresarial Server usa la base de datos SQL principal como testigo. En un grupo de este tipo, si se apaga la base de datos principal y se cambia a la copia reflejada, y se apagan los servidores front-end suficientes para que no haya suficiente la ejecución según la tabla anterior, se producirá todo el grupo. Para obtener más información, consulte [testigo de creación de reflejo](https://go.microsoft.com/fwlink/?LinkId=393672)de la base de datos. 
  
#### <a name="pool-level-quorum-loss"></a>Pérdida de quórum de nivel de grupo de servidores

Para que un grupo de servidores front-end funcione, no puede estar en pérdida de quórum en el nivel de grupo. Si el número de servidores que se ejecutan está por debajo del nivel funcional, como se muestra en la siguiente tabla, los demás servidores del grupo detendrán todos los servicios de Skype empresarial Server. Tenga en cuenta que los números de la siguiente tabla suponen que se están ejecutando los servidores back-end del grupo.
  
|Número total de servidores front-end en el grupo  <br/> |Número necesario de servidores en ejecución para que el grupo sea funcional  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |Cualquier 2  <br/> |
|5-6  <br/> |Cualquier 3  <br/> |
|7   <br/> |Cualquier 4  <br/> |
|8-9  <br/> |4 de los primeros 7 servidores  <br/> |
|10-12  <br/> |5 de los primeros 9 servidores  <br/> |
|12-16 **para Skype empresarial Server 2019**  <br/> |Cualquiera de los 7 de los primeros 12 servidores  <br/> |
   
En la tabla anterior, los "primeros servidores" son los servidores que se pusieron en primer lugar, de forma cronológica, cuando se inició el grupo por primera vez. Para determinar estos servidores, puede usar el `Get-CsComputer` cmdlet con la `-PoolFqdn` opción. Este cmdlet mostrará los servidores en el orden en que aparecen en la topología y los que se encuentran en la parte superior de la lista son los primeros servidores.
  
> [!IMPORTANT]
> El número máximo de servidores front-end se ha incrementado a 16 en [Skype empresarial Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Pasos adicionales para garantizar que los grupos de servidores son funcionales

Debe vigilar un par de otros factores para asegurarse de que los grupos de servidores front-end sigan siendo funcionales.
  
- Al mover usuarios al grupo por primera vez, asegúrese de que al menos tres de los servidores front-end se están ejecutando.
    
- Si establece una relación de emparejamiento entre este grupo de servidores y otro grupo para fines de recuperación ante desastres, después de establecer esa relación, debe asegurarse de que este grupo tenga tres servidores front-end que se ejecuten simultáneamente para sincronizar correctamente los datos con el grupo de copia de seguridad. Para obtener más información sobre el emparejamiento de grupos de servidores y las características de recuperación ante desastres, consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Grupo de servidores front-end con dos servidores front-end

No se recomienda implementar un grupo de servidores front-end que contenga solo dos servidores front-end. Este pequeño grupo no proporcionará una solución sólida de alta disponibilidad como un grupo más grande y necesitará más atención en la administración. Además, si se desactivó el servidor back-end de un grupo de dos servidores, lo más probable es que también se desactivara todo el grupo. Si desea implementar solo uno o dos servidores que ejecutan Skype empresarial Server, le recomendamos que los implemente como servidores Standard Edition.
  
Si alguna vez necesita implementar un grupo con dos servidores front-end, siga estas instrucciones:
  
- Si uno de los dos servidores front-end deja de funcionar, debería intentar volver a conectar el servidor con el error tan pronto como sea posible. De forma similar, si necesita actualizar uno de los dos servidores, vuelva a conectarlo tan pronto como finalice la actualización.
    
- Si, por algún motivo, necesita poner ambos servidores al mismo tiempo, haga lo siguiente cuando finalice el tiempo de inactividad del Grupo:
    
  - El procedimiento recomendado es reiniciar ambos servidores front-end al mismo tiempo. 
    
  - Si no se pueden reiniciar los dos servidores al mismo tiempo, deberá ponerlos en marcha de nuevo en el orden inverso al orden en que se encontraban.
    
  - Si no puede realizar una copia de seguridad en ese orden, use el siguiente cmdlet antes de volver a poner el grupo de servidores:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Errores y cambios de configuración del grupo de servidores front-end

Si se produce un error en un servidor front-end y es improbable que se reemplace durante unos cuantos días o más, quite el servidor de la topología. Agregue el nuevo servidor front-end a la topología cuando vuelva a estar disponible.
  
Siempre que realice un cambio de configuración en un grupo de servidores front-end, como agregar o quitar servidores, debe seguir estas instrucciones:
  
- Una vez publicada la nueva topología, debe reiniciar cada uno de los servidores front-end del grupo. Reinícielo a la vez.
    
- Si todo el grupo de servidores ha estado inactivo durante el cambio de configuración, ejecute el siguiente cmdlet después de publicar la nueva topología:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

