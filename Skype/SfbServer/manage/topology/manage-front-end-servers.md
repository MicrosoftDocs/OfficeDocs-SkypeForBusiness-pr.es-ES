---
title: Administrar servidores Front-End de Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Obtenga información sobre cómo agregar, quitar, revisión o actualizar los servidores Front-End en Skype para Business Server.'
ms.openlocfilehash: c77049d72b394b58b7c1b84a3207b443ef106b46
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222831"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Administrar servidores Front-End de Skype para Business Server
 
En este artículo se explica cómo agregar o quitar servidores Front-End y cómo aplicar las actualizaciones o revisiones a servidores Front-End.

## <a name="add-or-remove-front-end-servers"></a>Agregar o quitar servidores Front-End
  
Al agregar un servidor Front-End a un grupo de servidores, o quitar un servidor Front-End de un grupo de servidores, debe reiniciar el grupo de servidores. 
  
> [!IMPORTANT]
> Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial. 
  
Puede usar el siguiente procedimiento al agregar o quitar un servidor Front-End.
  
> [!NOTE]
> Si agrega nuevos servidores al grupo, actualice los nuevos servidores del grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes del grupo. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para agregar o quitar servidores Front-End

1. Si va a quitar los servidores Front-End, en primer lugar detenga nuevas conexiones a esos servidores. Para ello, puede usar el siguiente cmdlet:
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Abra el generador de topologías y agregar o quitar los servidores necesarios. 
    
3. Publique la topología.
    
    > [!IMPORTANT]
    > Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial. 
  
4. Si ha cambiado el número de servidores en el grupo de servidores Front-End en cualquiera de las siguientes maneras, a continuación, restablecer el grupo de servidores con escribiendo el siguiente cmdlet: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - De 2 a ninguno
    
     - De ninguno a 2
    
     - De 3 a ninguno
    
     - De ninguno a 3
    
5. Reinicie el grupo al escribir el siguiente cmdlet
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Aplicar parches a servidores front-end o actualizarlos

Revisión en los servidores de un grupo de servidores Front-End, se realiza por lo que un servidor a la vez. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar una actualización a los servidores front-end de un grupo de servidores

1. Escriba el siguiente cmdlet:
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Si este cmdlet muestra alguna réplica que falte, ejecute el siguiente cmdlet para recuperar el grupo antes de aplicar cualquier parche:
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Ejecute el siguiente cmdlet en el primer servidor al que desee aplicar un parche:
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Este cmdlet mueve todos los servicios a otros servidores Front-End del grupo de servidores y desconecta este servidor.
    
3. Aplique la actualización o revisión en el servidor desconectado.
    
4. En el servidor actualizado, ejecute el cmdlet siguiente:
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    El servidor vuelve al servicio.
    
5. Repita los pasos 2 a 4 para cada servidor que necesite una actualización.
    
