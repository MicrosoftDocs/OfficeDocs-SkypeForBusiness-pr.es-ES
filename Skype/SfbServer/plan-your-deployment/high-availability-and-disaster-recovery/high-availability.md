---
title: Alta disponibilidad y administración del grupo de servidores front-end
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Obtenga información acerca de la administración de grupo de servidores Front-End en Skype para Business Server, incluida la administración de grupos, pérdida de quórum y pasos especiales para grupos con sólo dos servidores frontales.
ms.openlocfilehash: f348fcc4fee6a48a41265da88fe432d9e4550b6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidad y administración del grupo de servidores front-end
 
Obtenga información acerca de la administración de grupo de servidores Front-End en Skype para Business Server, incluida la administración de grupos, pérdida de quórum y pasos especiales para grupos con sólo dos servidores frontales.
  
En Skype para Business Server, la arquitectura de grupos de Front-End utiliza un modelo de sistemas distribuidos, con los datos de cada usuario mantenidos en hasta tres servidores Front-End del grupo. Se recomienda que todos los grupos de Front-End de Enterprise Edition incluyen al menos tres servidores frontales. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planear la administración de grupos de servidores front-end

 Skype para Business Server utiliza un modelo de sistemas distribuidos basado en Fabric de Windows. En este modelo, los datos importantes para cada usuario y conferencia se almacenan en tres servidores frontales en un grupo de servidores Front-End. Estos tres servidores de almacenamiento de un determinado conjunto de datos son calledreplicas.
  
Con el modelo distribuido para pools de Front-End, debe ejecutar un determinado número de servidores de un grupo para el grupo a la función. Hay dos modos de pérdida para un grupo.
  
- Pérdida de quórum de nivel de grupo de enrutamiento, la causa no hay suficientes servidores de réplica para un determinado grupo de enrutamiento. Un grupo de enrutamiento es un conjunto de usuarios hospedados en el grupo. Cada grupo de enrutamiento tiene tres réplicas en el grupo: una principal y dos secundarias.
    
- Pérdida de quórum nivel grupo, causada cuando no hay suficientes servidores semilla se ejecutan en el grupo. 
    
### <a name="routing-group-level-quorum-loss"></a>Pérdida de cuórum en el grupo de enrutamiento

La primera vez que inicia un nuevo grupo de servidores front-end, es fundamental que el 85 % de los servidores estén en funcionamiento, tal como se muestra en la tabla siguiente. Si hay menos servidores en ejecución, es posible que los servicios queden interrumpidos en el estado de inicio y que el grupo no se inicie.
  
|Cantidad total de servidores en el grupo  <br/> |Cantidad de servidores que necesitan estar en ejecución para que el grupo se inicie por primera vez  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6  <br/> |5  <br/> |
|7  <br/> |5  <br/> |
|8  <br/> |6  <br/> |
|9  <br/> |7  <br/> |
|10  <br/> |8  <br/> |
|11  <br/> |9  <br/> |
|12  <br/> |10  <br/> |
   
Cada vez subsiguiente que se inicie el grupo, es preciso iniciar el 85 % de los servidores (tal como se muestra en la tabla anterior). Si no se puede iniciar este número de servidores (pero se pueden iniciar suficientes servidores de modo que no está en la pérdida de quórum de nivel de grupo), puede utilizar el `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet de para habilitar el grupo para recuperarse de esta pérdida de quórum de nivel de grupo enrutamiento y hacer progresos. Para obtener más información acerca de cómo usar este cmdlet, consulte <link Reset-CsPoolRegistrarState>.
  
> [!NOTE]
> En los grupos de servidores con una cantidad par de servidores, Skype Empresarial Server usa la base de datos SQL principal como testigo. En un grupo como este, si apaga la base de datos principal, cambia a la copia reflejada y apaga una cantidad suficiente de servidores front-end para que no haya los suficientes en ejecución de acuerdo con la tabla anterior, todo el grupo de servidores quedará inactivo. Para obtener más información, vea [Testigo de reflejo de base de datos](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Pérdida de cuórum en el grupo de servidores

Para que un pool de Front-End funcionar en absoluto, no puede ser pérdida de quórum de nivel de grupo. Si la cantidad de servidores en ejecución está por debajo del nivel de funcionamiento (tal como se muestra en la tabla siguiente), los servidores restantes del grupo detendrán todos los servicios de Skype Empresarial Server. Tenga en cuenta que los números en la tabla siguiente se supone que ejecuta los servidores de fondo detrás del grupo.
  
|Número total de servidores frontales de la piscina  <br/> |Cantidad de servidores que es preciso que estén en ejecución para que el grupo funcione  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |2 cualesquiera  <br/> |
|5-6  <br/> |3 cualesquiera  <br/> |
|7  <br/> |4 cualesquiera  <br/> |
|8-9  <br/> |4 cualesquiera de los primeros 7 servidores  <br/> |
|10-12  <br/> |5 cualesquiera de los primeros 9 servidores  <br/> |
   
En la tabla anterior, el "primer servidores" son los que fueron criados en primer lugar, cronológicamente, cuando el grupo se inició por primera vez. Para determinar estos servidores, puede utilizar el `Get-CsComputer` cmdlet con la ` -PoolFqdn` opción. Este cmdlet le mostrará los servidores en el orden en el que aparecen en la topología; los que se encuentran en la parte superior de la lista son los primeros servidores.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Pasos adicionales para comprobar si los grupos de servidores son funcionales

Es necesario tener en cuenta algunos otros factores a fin de asegurarse de que los grupos de servidores front-end sigan siendo funcionales.
  
- Al mover los usuarios al grupo por primera vez, asegúrese de al menos que tres de los servidores frontales están ejecutando.
    
- Si establece una relación de emparejamiento entre este grupo de servidores y otro con fines de recuperación ante desastres, después de establecer dicha relación, necesitará asegurarse de que este grupo tiene tres servidores front-end ejecutándose simultáneamente en algún momento para sincronizar correctamente los datos con el servidor de copia de seguridad. Para obtener más información sobre el grupo de funciones de recuperación ante desastres y de emparejamiento, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Grupos de servidores front-end con dos servidores front-end

No es recomendable implementar un grupo de servidores Front-End que contiene sólo dos servidores frontales. Este grupo pequeño no ofrecerá una solución de alta disponibilidad sólida como lo haría un grupo más grande y requerirá más atención en su administración. Además, si se desactivó el servidor de fondo detrás de una agrupación de dos servidores, el propio grupo entero probablemente pronto dirigiría hacia abajo también. Si desea implementar uno o dos servidores ejecutando Skype para Business Server, se recomienda que implementar como servidores Standard Edition.
  
Si alguna vez necesita implementar un grupo con dos servidores frontales, siga estas instrucciones:
  
- Si uno de los dos servidores frontales deja de funcionar, debe intentar poner el servidor error al hacer copia de seguridad tan pronto como pueda. Del mismo modo, si necesita actualizar uno de los dos servidores, vuelva a ponerlo en línea tan pronto como termine la actualización.
    
- Si, por algún motivo, necesita detener los dos servidores en algún momento, realice lo siguiente cuando termine el tiempo de inactividad del grupo:
    
  - Lo mejor es reiniciar ambos servidores frontales al mismo tiempo. 
    
  - Si no se pueden reiniciar los dos servidores al mismo tiempo, será necesario ponerlos en funcionamiento nuevamente en el orden inverso al orden en que se detuvieron.
    
  - Si no puede poner su copia de seguridad en ese orden, a continuación, utilice el siguiente cmdlet antes de poner el grupo de copia de seguridad:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Cambios y errores de configuración en el grupo de servidores front-end

Si se produce un error en un servidor front-end y no es probable que se sustituya durante unos días, quite el servidor de la topología. Cuando el nuevo servidor front-end esté disponible, agréguelo a la topología.
  
Siempre que realice un cambio de configuración en un grupo de servidores front-end, como agregar o quitar servidores, es preciso seguir estas instrucciones:
  
- Después de publicar una topología nueva, necesita reiniciar cada uno de los servidores front-end del grupo. Reinícielos de uno en uno.
    
- Si todo el grupo ha estado inactivo durante el cambio de configuración, ejecute el cmdlet siguiente después de que se publique la nueva topología:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

