---
title: Alta disponibilidad y administración del grupo de servidores front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Obtenga más información sobre la administración de grupos de servidores front-end en Skype empresarial Server, como la administración de grupos, pérdida de quórum y pasos especiales para grupos de servidores con tan solo dos servidores front-end.
ms.openlocfilehash: d54474b6e3013b2d092f55b80000f5578e266f81
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435183"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidad y administración del grupo de servidores front-end
 
Obtenga más información sobre la administración de grupos de servidores front-end en Skype empresarial Server, como la administración de grupos, pérdida de quórum y pasos especiales para grupos de servidores con tan solo dos servidores front-end.
  
En Skype empresarial Server, la arquitectura de los grupos front-end usa un modelo de sistemas distribuidos, con los datos de cada usuario en un máximo de tres servidores front-end en el grupo. Recomendamos que todos los grupos de servidores front-end Enterprise Edition incluyan al menos tres servidores frontales. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planear la administración de grupos de servidores front-end

 Skype empresarial Server usa un modelo de sistemas distribuidos basado en Windows fabric. En este modelo, los datos importantes de cada usuario y Conferencia se almacenan en tres servidores front-end en un grupo de servidores front-end. Estos tres servidores que almacenan un determinado conjunto de datos son calledreplicas.
  
Con el modelo distribuido para los grupos de servidores front-end, debe estar ejecutándose un determinado número de servidores de un grupo para que el grupo funcione. Hay dos modos de pérdida para un grupo.
  
- Pérdida de cuórum en el grupo de enrutamiento, provocada por una cantidad insuficiente de servidores de réplicas para un determinado grupo de enrutamiento. Un grupo de enrutamiento es un conjunto de usuarios hospedados en el grupo. Cada grupo de enrutamiento tiene tres réplicas en el grupo: una principal y dos secundarias.
    
- Pérdida de cuórum en el grupo de servidores, que ocurre cuando no hay una cantidad suficiente de servidores semilla en ejecución en el grupo. 
    
### <a name="routing-group-level-quorum-loss"></a>Pérdida de cuórum en el grupo de enrutamiento

La primera vez que inicia un nuevo grupo de servidores front-end, es fundamental que el 85 % de los servidores estén en funcionamiento, tal como se muestra en la tabla siguiente. Si hay menos servidores en ejecución, es posible que los servicios queden interrumpidos en el estado de inicio y que el grupo no se inicie.
  
|Cantidad total de servidores en el grupo  <br/> |Cantidad de servidores que necesitan estar en ejecución para que el grupo se inicie por primera vez  <br/> |
|:-----|:-----|
|1  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6  <br/> |5  <br/> |
|7  <br/> |5  <br/> |
|4,8  <br/> |6  <br/> |
|99,999  <br/> |7  <br/> |
|base10  <br/> |4,8  <br/> |
|once  <br/> |99,999  <br/> |
|2007  <br/> |base10  <br/> |
|16 **para Skype empresarial Server 2019** <br/> |2007  <br/> |


   
Cada vez subsiguiente que se inicie el grupo, es preciso iniciar el 85 % de los servidores (tal como se muestra en la tabla anterior). Si no se puede iniciar este número de servidores (pero se pueden iniciar suficientes servidores para que no se encuentre en pérdida de quórum en el nivel de grupo), `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` puede usar el cmdlet para permitir que el grupo se recupere de esta pérdida de quórum en el nivel de grupo de enrutamiento y realice el progreso. Para obtener más información sobre cómo usar este cmdlet, consulte [RESET-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> En los grupos de servidores con una cantidad par de servidores, Skype Empresarial Server usa la base de datos SQL principal como testigo. En un grupo como este, si apaga la base de datos principal, cambia a la copia reflejada y apaga una cantidad suficiente de servidores front-end para que no haya los suficientes en ejecución de acuerdo con la tabla anterior, todo el grupo de servidores quedará inactivo. Para obtener más información, consulte [testigo de creación de reflejo de base de datos](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Pérdida de cuórum en el grupo de servidores

Para que un grupo de servidores front-end funcione, no puede estar en pérdida de quórum en el nivel de grupo. Si la cantidad de servidores en ejecución está por debajo del nivel de funcionamiento (tal como se muestra en la tabla siguiente), los servidores restantes del grupo detendrán todos los servicios de Skype Empresarial Server. Tenga en cuenta que los números de la tabla siguiente suponen que los servidores de servicios de fondo del grupo se están ejecutando.
  
|Número total de servidores front-end en el grupo  <br/> |Cantidad de servidores que es preciso que estén en ejecución para que el grupo funcione  <br/> |
|:-----|:-----|
|1  <br/> |1  <br/> |
|3-4  <br/> |2 cualesquiera  <br/> |
|5-6  <br/> |3 cualesquiera  <br/> |
|7  <br/> |4 cualesquiera  <br/> |
|8-9  <br/> |4 cualesquiera de los primeros 7 servidores  <br/> |
|10-12  <br/> |5 cualesquiera de los primeros 9 servidores  <br/> |
|12-16 **para Skype empresarial Server 2019**  <br/> |Los 7 de los primeros 12 servidores  <br/> |
   
En la tabla anterior, los "primeros servidores" son los servidores que se pusieron en primer lugar, cronológicamente, cuando el grupo se inició por primera vez. Para determinar estos servidores, puede usar el `Get-CsComputer` cmdlet con la `-PoolFqdn` opción. Este cmdlet le mostrará los servidores en el orden en el que aparecen en la topología; los que se encuentran en la parte superior de la lista son los primeros servidores.
  
> [!IMPORTANT]
> La cantidad máxima de servidores de aplicaciones para el usuario se ha incrementado a 16 en [Skype empresarial Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Pasos adicionales para comprobar si los grupos de servidores son funcionales

Es necesario tener en cuenta algunos otros factores a fin de asegurarse de que los grupos de servidores front-end sigan siendo funcionales.
  
- Al mover usuarios al grupo por primera vez, asegúrese de que al menos tres de los servidores front-end se estén ejecutando.
    
- Si establece una relación de emparejamiento entre este grupo de servidores y otro con fines de recuperación ante desastres, después de establecer dicha relación, necesitará asegurarse de que este grupo tiene tres servidores front-end ejecutándose simultáneamente en algún momento para sincronizar correctamente los datos con el servidor de copia de seguridad. Para obtener más información sobre el emparejamiento de pools y las características de recuperación de desastres, consulte [Plan for Disaster Availability and Disaster Recovery in Skype empresarial Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Grupos de servidores front-end con dos servidores front-end

No se recomienda implementar un grupo de servidores front-end que contenga solo dos servidores front-end. Este grupo pequeño no ofrecerá una solución de alta disponibilidad sólida como lo haría un grupo más grande y requerirá más atención en su administración. Además, si el servidor back-end de un grupo de dos servidores se desactivara, todo el grupo sería muy probable que pronto se desactivara. Si desea implementar solo uno o dos servidores que ejecuten Skype empresarial Server, le recomendamos que los implemente como servidores Standard Edition.
  
Si alguna vez necesita implementar un grupo con dos servidores front-end, siga estas pautas:
  
- Si uno de los dos servidores de solicitudes de cliente deja de funcionar, debe intentar volver a ponerlo en marcha tan pronto como pueda. Del mismo modo, si necesita actualizar uno de los dos servidores, vuelva a ponerlo en línea tan pronto como termine la actualización.
    
- Si, por algún motivo, necesita detener los dos servidores en algún momento, realice lo siguiente cuando termine el tiempo de inactividad del grupo:
    
  - Lo mejor es reiniciar ambos servidores front-end al mismo tiempo. 
    
  - Si no se pueden reiniciar los dos servidores al mismo tiempo, será necesario ponerlos en funcionamiento nuevamente en el orden inverso al orden en que se detuvieron.
    
  - Si no puede hacer una copia de seguridad en ese orden, use el siguiente cmdlet antes de volver a poner el grupo de servidores:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Cambios y errores de configuración en el grupo de servidores front-end

Si se produce un error en un servidor front-end y no es probable que se sustituya durante unos días, quite el servidor de la topología. Cuando el nuevo servidor front-end esté disponible, agréguelo a la topología.
  
Siempre que realice un cambio de configuración en un grupo de servidores front-end, como agregar o quitar servidores, es preciso seguir estas instrucciones:
  
- Después de publicar una topología nueva, necesita reiniciar cada uno de los servidores front-end del grupo. Reinícielos de uno en uno.
    
- Si se ha desactivado todo el grupo durante el cambio de configuración, ejecute el siguiente cmdlet una vez publicada la nueva topología:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

