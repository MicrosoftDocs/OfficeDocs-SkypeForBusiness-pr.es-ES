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
description: Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.
ms.openlocfilehash: f348fcc4fee6a48a41265da88fe432d9e4550b6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidad y administración del grupo de servidores front-end
 
Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.
  
In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End servers in the pool. We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planear la administración de grupos de servidores front-end

 Skype for Business Server uses a distributed systems model based on Windows Fabric. In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool. These three servers storing a certain set of data are calledreplicas.
  
With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function. There are two loss modes for a pool.
  
- Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group. Un grupo de enrutamiento es un conjunto de usuarios hospedados en el grupo. Cada grupo de enrutamiento tiene tres réplicas en el grupo: una principal y dos secundarias.
    
- Pool Level quorum loss, caused when not enough seed servers are running in the pool. 
    
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
   
Cada vez subsiguiente que se inicie el grupo, es preciso iniciar el 85 % de los servidores (tal como se muestra en la tabla anterior). If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress. For more information about how to use this cmdlet, see <link Reset-CsPoolRegistrarState>.
  
> [!NOTE]
> En los grupos de servidores con una cantidad par de servidores, Skype Empresarial Server usa la base de datos SQL principal como testigo. En un grupo como este, si apaga la base de datos principal, cambia a la copia reflejada y apaga una cantidad suficiente de servidores front-end para que no haya los suficientes en ejecución de acuerdo con la tabla anterior, todo el grupo de servidores quedará inactivo. For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Pérdida de cuórum en el grupo de servidores

For a Front End pool to function at all, it cannot be in pool-level quorum loss. Si la cantidad de servidores en ejecución está por debajo del nivel de funcionamiento (tal como se muestra en la tabla siguiente), los servidores restantes del grupo detendrán todos los servicios de Skype Empresarial Server. Note that the numbers in the following table assume that the Back End Servers in the pool are running.
  
|Total number of Front End Servers in the pool  <br/> |Cantidad de servidores que es preciso que estén en ejecución para que el grupo funcione  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |2 cualesquiera  <br/> |
|5-6  <br/> |3 cualesquiera  <br/> |
|7  <br/> |4 cualesquiera  <br/> |
|8-9  <br/> |4 cualesquiera de los primeros 7 servidores  <br/> |
|10-12  <br/> |5 cualesquiera de los primeros 9 servidores  <br/> |
   
In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time. To determine these servers, you can use the  `Get-CsComputer` cmdlet with the ` -PoolFqdn` option. Este cmdlet le mostrará los servidores en el orden en el que aparecen en la topología; los que se encuentran en la parte superior de la lista son los primeros servidores.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Pasos adicionales para comprobar si los grupos de servidores son funcionales

Es necesario tener en cuenta algunos otros factores a fin de asegurarse de que los grupos de servidores front-end sigan siendo funcionales.
  
- When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.
    
- Si establece una relación de emparejamiento entre este grupo de servidores y otro con fines de recuperación ante desastres, después de establecer dicha relación, necesitará asegurarse de que este grupo tiene tres servidores front-end ejecutándose simultáneamente en algún momento para sincronizar correctamente los datos con el servidor de copia de seguridad. For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Grupos de servidores front-end con dos servidores front-end

We do not recommend deploying a Front End pool that contains only two Front End Servers. Este grupo pequeño no ofrecerá una solución de alta disponibilidad sólida como lo haría un grupo más grande y requerirá más atención en su administración. Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well. If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.
  
If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:
  
- If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Del mismo modo, si necesita actualizar uno de los dos servidores, vuelva a ponerlo en línea tan pronto como termine la actualización.
    
- Si, por algún motivo, necesita detener los dos servidores en algún momento, realice lo siguiente cuando termine el tiempo de inactividad del grupo:
    
  - The best practice is to restart both Front End Servers at the same time. 
    
  - Si no se pueden reiniciar los dos servidores al mismo tiempo, será necesario ponerlos en funcionamiento nuevamente en el orden inverso al orden en que se detuvieron.
    
  - If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Cambios y errores de configuración en el grupo de servidores front-end

Si se produce un error en un servidor front-end y no es probable que se sustituya durante unos días, quite el servidor de la topología. Cuando el nuevo servidor front-end esté disponible, agréguelo a la topología.
  
Siempre que realice un cambio de configuración en un grupo de servidores front-end, como agregar o quitar servidores, es preciso seguir estas instrucciones:
  
- Después de publicar una topología nueva, necesita reiniciar cada uno de los servidores front-end del grupo. Reinícielos de uno en uno.
    
- If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

