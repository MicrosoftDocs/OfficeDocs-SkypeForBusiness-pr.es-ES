---
title: Alta disponibilidad y administración del grupo de servidores front-end
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Obtenga información acerca de la administración de grupo de servidores Front-End en Skype para Business Server, incluida la administración de grupos de servidores, pérdida de quórum y pasos especiales para grupos de servidores con sólo dos servidores Front-End.
ms.openlocfilehash: ba15e090829256188763a0e7791cebb29f097422
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005249"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidad y administración del grupo de servidores front-end
 
Obtenga información acerca de la administración de grupo de servidores Front-End en Skype para Business Server, incluida la administración de grupos de servidores, pérdida de quórum y pasos especiales para grupos de servidores con sólo dos servidores Front-End.
  
En Skype para Business Server, la arquitectura de grupos de servidores Front-End usa un modelo de sistemas distribuidos, con los datos de cada usuario mantenidos hasta tres servidores Front-End del grupo de servidores. Se recomienda que todos los grupos de Front-End de Enterprise Edition incluyen al menos tres servidores Front-End. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planear la administración de grupos de servidores front-end

 Skype para Business Server usa un modelo de sistemas distribuidos basado en Windows Fabric. En este modelo, los datos importantes para cada usuario y la conferencia se almacenan en tres servidores de Front-End de un grupo de servidores Front-End. Estos tres servidores de almacenamiento de un determinado conjunto de datos son calledreplicas.
  
Con el modelo distribuido para grupos de servidores Front-End, debe ejecutar un determinado número de servidores de un grupo de servidores para el grupo de servidores a la función. Hay dos modos de pérdida de un grupo de servidores.
  
- Pérdida de cuórum en el grupo de enrutamiento, provocada por una cantidad insuficiente de servidores de réplicas para un determinado grupo de enrutamiento. Un grupo de enrutamiento es un conjunto de usuarios hospedados en el grupo. Cada grupo de enrutamiento tiene tres réplicas en el grupo: una principal y dos secundarias.
    
- Pérdida de cuórum en el grupo de servidores, que ocurre cuando no hay una cantidad suficiente de servidores semilla en ejecución en el grupo. 
    
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
   
Cada vez subsiguiente que se inicie el grupo, es preciso iniciar el 85 % de los servidores (tal como se muestra en la tabla anterior). Si no se puede iniciar este número de servidores (pero se pueden iniciar suficientes servidores de modo que no se encuentra en pérdida de quórum del grupo de servidores), puede usar el `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet para habilitar el grupo de servidores para recuperarse de esta pérdida de quórum de nivel de grupo de enrutamiento y realizar el progreso. Para obtener más información acerca de cómo usar este cmdlet, consulte <link Reset-CsPoolRegistrarState>.
  
> [!NOTE]
> En los grupos de servidores con una cantidad par de servidores, Skype Empresarial Server usa la base de datos SQL principal como testigo. En un grupo como este, si apaga la base de datos principal, cambia a la copia reflejada y apaga una cantidad suficiente de servidores front-end para que no haya los suficientes en ejecución de acuerdo con la tabla anterior, todo el grupo de servidores quedará inactivo. Para obtener más información, vea [El testigo de la creación de reflejo de base de datos](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Pérdida de cuórum en el grupo de servidores

Para que un grupo de servidores Front-End funcionar en absoluto, no puede ser en pérdida de quórum del grupo de servidores. Si la cantidad de servidores en ejecución está por debajo del nivel de funcionamiento (tal como se muestra en la tabla siguiente), los servidores restantes del grupo detendrán todos los servicios de Skype Empresarial Server. Tenga en cuenta que los números en la tabla siguiente se suponen que se están ejecutando los servidores Back-End del grupo de servidores.
  
|Número total de servidores Front-End del grupo de servidores  <br/> |Cantidad de servidores que es preciso que estén en ejecución para que el grupo funcione  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |2 cualesquiera  <br/> |
|5-6  <br/> |3 cualesquiera  <br/> |
|7  <br/> |4 cualesquiera  <br/> |
|8-9  <br/> |4 cualesquiera de los primeros 7 servidores  <br/> |
|10-12  <br/> |5 cualesquiera de los primeros 9 servidores  <br/> |
   
En la tabla anterior, "servidores primera" son los que se han de la mano de copia de seguridad en primer lugar, cronológico, cuando se inició el grupo de servidores por primera vez. Para determinar estos servidores, puede usar el `Get-CsComputer` cmdlet con la ` -PoolFqdn` opción. Este cmdlet le mostrará los servidores en el orden en el que aparecen en la topología; los que se encuentran en la parte superior de la lista son los primeros servidores.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Pasos adicionales para comprobar si los grupos de servidores son funcionales

Es necesario tener en cuenta algunos otros factores a fin de asegurarse de que los grupos de servidores front-end sigan siendo funcionales.
  
- Al mover los usuarios al grupo de servidores por primera vez, asegúrese de al menos que tres de los servidores Front-End se ejecutan.
    
- Si establece una relación de emparejamiento entre este grupo de servidores y otro con fines de recuperación ante desastres, después de establecer dicha relación, necesitará asegurarse de que este grupo tiene tres servidores front-end ejecutándose simultáneamente en algún momento para sincronizar correctamente los datos con el servidor de copia de seguridad. Para obtener más información sobre las funciones de recuperación ante desastres y el emparejamiento de grupo de servidores, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Grupos de servidores front-end con dos servidores front-end

No se recomienda implementar un grupo de servidores Front-End que contiene sólo dos servidores Front-End. Este grupo pequeño no ofrecerá una solución de alta disponibilidad sólida como lo haría un grupo más grande y requerirá más atención en su administración. Además, si el servidor Back-End de un grupo de servidores de dos servidores se detuvieron, al propio grupo todo debería es probable que pronto conducir hacia abajo también. Si desea implementar uno o dos servidores que ejecuta Skype para Business Server, se recomienda que implementar como servidores Standard Edition.
  
Si alguna vez necesita implementar un grupo de servidores con dos servidores Front-End, siga estas instrucciones:
  
- Si uno de los dos servidores de Front-End deja de funcionar, debe intentar conectar el servidor con errores copia de seguridad tan pronto como sea posible. Del mismo modo, si necesita actualizar uno de los dos servidores, vuelva a ponerlo en línea tan pronto como termine la actualización.
    
- Si, por algún motivo, necesita detener los dos servidores en algún momento, realice lo siguiente cuando termine el tiempo de inactividad del grupo:
    
  - El procedimiento recomendado consiste en reiniciar ambos servidores Front-End al mismo tiempo. 
    
  - Si no se pueden reiniciar los dos servidores al mismo tiempo, será necesario ponerlos en funcionamiento nuevamente en el orden inverso al orden en que se detuvieron.
    
  - Si no puede ponerlos copia de seguridad en ese orden, a continuación, use el siguiente cmdlet antes de poner el grupo de copia de seguridad:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Cambios y errores de configuración en el grupo de servidores front-end

Si se produce un error en un servidor front-end y no es probable que se sustituya durante unos días, quite el servidor de la topología. Cuando el nuevo servidor front-end esté disponible, agréguelo a la topología.
  
Siempre que realice un cambio de configuración en un grupo de servidores front-end, como agregar o quitar servidores, es preciso seguir estas instrucciones:
  
- Después de publicar una topología nueva, necesita reiniciar cada uno de los servidores front-end del grupo. Reinícielos de uno en uno.
    
- Si el grupo entero ha estado inactivo durante el cambio de configuración, a continuación, ejecute el siguiente cmdlet después de publica la nueva topología:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

