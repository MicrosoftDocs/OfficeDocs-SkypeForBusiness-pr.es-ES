---
title: Alta disponibilidad y administración del grupo de servidores front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Obtenga información sobre la administración de grupos de servidores front-end en Skype Empresarial Server, incluida la administración de grupos de servidores, la pérdida de quórum y los pasos especiales para grupos de servidores con solo dos servidores front-end.
ms.openlocfilehash: 3f1924b7a8ad26b880f8674ada4f0c99a1bc4596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802800"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidad y administración del grupo de servidores front-end
 
Obtenga información sobre la administración de grupos de servidores front-end en Skype Empresarial Server, incluida la administración de grupos de servidores, la pérdida de quórum y los pasos especiales para grupos de servidores con solo dos servidores front-end.
  
En Skype Empresarial Server, la arquitectura de los grupos de servidores front-end usa un modelo de sistemas distribuidos, en el que los datos de cada usuario se mantienen en hasta tres servidores front-end del grupo. Se recomienda que todos los grupos de servidores front-end de Enterprise Edition incluyan al menos tres servidores front-end.

> [!NOTE]
> Skype Empresarial Server 2019 no admite grupos de servidores front-end Enterprise Edition con dos servidores front-end y no permitirá que la topología se publique en ese escenario.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planeación de la administración de grupos de servidores front-end

 Skype Empresarial Server usa un modelo de sistemas distribuidos basado en Windows Fabric. En este modelo, los datos importantes para cada usuario y conferencia se almacenan en tres servidores front-end de un grupo de servidores front-end. Estos tres servidores que almacenan un determinado conjunto de datos se denominanreplicaciones.
  
Con el modelo distribuido para grupos de servidores front-end, debe ejecutarse un número determinado de servidores de un grupo para que funcione. Hay dos modos de pérdida para un grupo de servidores.
  
- Pérdida de quórum en el nivel de grupo de enrutamiento, causada por la falta de suficientes servidores de réplica para un grupo de enrutamiento determinado. Un grupo de enrutamiento es un conjunto de usuarios que se encuentra en el grupo de servidores. Cada grupo de enrutamiento tiene tres réplicas en el grupo: una réplica principal y dos réplicas secundarias.
    
- Pérdida de quórum de nivel de grupo, causada cuando no hay suficientes servidores de edr en ejecución en el grupo. 
    
### <a name="routing-group-level-quorum-loss"></a>Pérdida de quórum en el nivel de grupo de enrutamiento

La primera vez que inicie un nuevo grupo de servidores front-end, es esencial que el 85 % de los servidores estén en funcionamiento, como se muestra en la tabla siguiente. Si se ejecutan menos servidores, es posible que los servicios estén bloqueados en el estado inicial y que el grupo no se inicie.
  
|Número total de servidores del grupo  <br/> |Número de servidores que deben ejecutarse para que el grupo se pueda iniciar por primera vez  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10    <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10    <br/> |
|16 **Para Skype Empresarial Server 2019** <br/> |12   <br/> |


   
Cada vez que se inicia el grupo de servidores, se debe iniciar el 85 % de los servidores (como se muestra en la tabla anterior). Si no se puede iniciar este número de servidores (pero se pueden iniciar suficientes servidores para que no esté en la pérdida de quórum en el nivel de grupo), puede usar el cmdlet para permitir que el grupo se recupere de esta pérdida de quórum de nivel de grupo de enrutamiento y  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` avance. Para obtener más información acerca de cómo usar este cmdlet, vea [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> En grupos con un número par de servidores, Skype Empresarial Server usa la base de datos principal SQL como testigo. En un grupo de servidores como este, si apaga la base de datos principal y cambia a la copia reflejada, y apaga suficientes servidores front-end para que no se ejecuten suficientes de acuerdo con la tabla anterior, todo el grupo de servidores se apagará. Para obtener más información, vea [Testigo de creación de reflejo de la base de datos.](https://go.microsoft.com/fwlink/?LinkId=393672) 
  
#### <a name="pool-level-quorum-loss"></a>Pérdida de quórum en el nivel de grupo

Para que un grupo de servidores front-end funcione, no puede estar en pérdida de quórum en el nivel de grupo. Si el número de servidores que se ejecutan está por debajo del nivel funcional, como se muestra en la tabla siguiente, los servidores restantes del grupo de servidores detendrán todos los servicios de Skype Empresarial Server. Tenga en cuenta que los números de la tabla siguiente suponen que se están ejecutando los servidores back-end del grupo de servidores.
  
|Número total de servidores front-end en el grupo  <br/> |Número necesario de servidores en ejecución para que el grupo sea funcional  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |Cualquiera 2  <br/> |
|5-6  <br/> |Cualquiera 3  <br/> |
|7   <br/> |Cualquiera de 4  <br/> |
|8-9  <br/> |Cualquiera de los 4 de los primeros 7 servidores  <br/> |
|10-12  <br/> |Cualquiera de los 5 de los primeros 9 servidores  <br/> |
|12-16  **Para Skype Empresarial Server 2019**  <br/> |Cualquiera de los 7 de los 12 primeros servidores  <br/> |
   
En la tabla anterior, los "primeros servidores" son los servidores que se han presentado primero, cronológicamente, cuando el grupo se inició por primera vez. Para determinar estos servidores, puede usar el  `Get-CsComputer` cmdlet con la `-PoolFqdn` opción. Este cmdlet mostrará los servidores en el orden en que aparecen en la topología y los que están en la parte superior de la lista son los primeros servidores.
  
> [!IMPORTANT]
> El número máximo de servidores front-end se ha aumentado a 16 [en Skype Empresarial Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Pasos adicionales para garantizar que los grupos sean funcionales

Debe tener en cuenta otros dos factores para garantizar que los grupos de servidores front-end sigan funcionando.
  
- Cuando mueva usuarios al grupo por primera vez, asegúrese de que al menos tres de los servidores front-end se estén ejecutando.
    
- Si establece una relación de emparejamiento entre este grupo y otro grupo con fines de recuperación ante desastres, después de establecer esa relación, debe asegurarse de que este grupo tiene tres servidores front-end ejecutándose simultáneamente en algún momento para sincronizar correctamente los datos con el grupo de copia de seguridad. Para obtener más información sobre el emparejamiento de grupos de servidores y las características de recuperación ante desastres, consulte [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Grupo de servidores front-end con dos servidores front-end

No se recomienda implementar un grupo de servidores front-end que contenga solo dos servidores front-end. Este grupo pequeño no proporcionará una solución sólida de alta disponibilidad como lo haría un grupo de servidores más grande y necesita especial cuidado en la administración. Además, si el servidor back-end de un grupo de servidores de dos servidores se deshizo, es probable que todo el grupo de servidores también también se deshizo pronto. Si desea implementar solo uno o dos servidores que ejecuten Skype Empresarial Server, le recomendamos que los implemente como servidores Standard Edition.
  
Si alguna vez necesita implementar un grupo de servidores con dos servidores front-end, siga estas instrucciones:
  
- Si uno de los dos servidores front-end se cae, debe intentar que el servidor con errores vuelva a estar lo antes posible. Del mismo modo, si necesita actualizar uno de los dos servidores, vuelva a ponerla en línea en cuanto finalice la actualización.
    
- Si por algún motivo necesita reducir ambos servidores al mismo tiempo, haga lo siguiente cuando finalice el tiempo de inactividad del grupo de servidores:
    
  - El procedimiento recomendado es reiniciar ambos servidores front-end al mismo tiempo. 
    
  - Si los dos servidores no se pueden reiniciar al mismo tiempo, debe traerlos de nuevo en el orden inverso en el orden en que se deshizo.
    
  - Si no puede realizar una copia de seguridad en ese orden, use el siguiente cmdlet antes de hacer una copia de seguridad del grupo de servidores:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Errores y cambios en la configuración del grupo de servidores front-end

Si se produce un error en un servidor front-end y es poco probable que se reemplazó durante unos días o más, quite el servidor de la topología. Agregue el nuevo servidor front-end a la topología cuando esté disponible de nuevo.
  
Siempre que realice un cambio de configuración en un grupo de servidores front-end, como agregar o quitar servidores, debe seguir estas instrucciones:
  
- Una vez publicada la nueva topología, debe reiniciar cada servidor front-end del grupo de servidores. Reinícielos de uno en uno.
    
- Si todo el grupo de servidores ha estado sin funcionar durante el cambio de configuración, ejecute el siguiente cmdlet después de publicar la nueva topología:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

