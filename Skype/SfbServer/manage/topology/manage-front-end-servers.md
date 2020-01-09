---
title: Administrar servidores front-end en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Aprenda a agregar, quitar, aplicar revisiones o actualizar servidores front-end en Skype empresarial Server.'
ms.openlocfilehash: 3689b869ba715f431ebcf0b537b4106a66177c62
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991535"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Administrar servidores front-end en Skype empresarial Server
 
En este artículo se explica cómo agregar o quitar servidores front-end y cómo aplicar actualizaciones o revisiones a los servidores front-end.

## <a name="add-or-remove-front-end-servers"></a>Agregar o quitar servidores front-end
  
Al agregar un servidor front-end a un grupo o quitar un servidor front-end de un grupo, debe reiniciar el grupo. 
  
> [!IMPORTANT]
> Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial. 
  
Puede usar el siguiente procedimiento al agregar o quitar un servidor front-end.
  
> [!NOTE]
> Si agrega nuevos servidores al grupo, actualice los nuevos servidores del grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes del grupo. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para agregar o quitar servidores front-end

1. Si va a quitar los servidores front-end, primero detenga las conexiones nuevas a esos servidores. Para ello, puede usar el siguiente cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Abra el generador de topologías y agregue o quite los servidores necesarios. 
    
3. Publique la topología.
    
    > [!IMPORTANT]
    > Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial. 
  
  > [!NOTE]
> Además, cuando agregue o quite un servidor a la agrupación, debe ejecutar el Asistente para la implementación de Skype empresarial Server en cada uno de los equipos agregados o eliminados, para obtener más información, consulte [instalar Skype empresarial Server en servidores de la topología](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Si ha cambiado el número de servidores en el grupo de servidores front-end de cualquiera de las siguientes maneras, restablezca el grupo con el siguiente cmdlet: RESET-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - De 2 a ninguno
    
     - De ninguno a 2
    
     - De 3 a ninguno
    
     - De ninguno a 3
    
5. Reinicie el grupo al escribir el siguiente cmdlet
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Aplicar parches a servidores front-end o actualizarlos

Cuando se revisan los servidores de un grupo de servidores front-end, lo hace de un servidor a la vez. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar una actualización a los servidores front-end de un grupo de servidores

1. Escriba el siguiente cmdlet:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Si este cmdlet muestra alguna réplica que falte, ejecute el siguiente cmdlet para recuperar el grupo antes de aplicar cualquier parche:
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Ejecute el siguiente cmdlet en el primer servidor al que desee aplicar un parche:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Este cmdlet mueve todos los servicios a otros servidores front-end del grupo y desconecta este servidor.
    
3. Aplique la actualización o revisión en el servidor desconectado.
    
4. En el servidor actualizado, ejecute el cmdlet siguiente:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    El servidor vuelve al servicio.
    
5. Repita los pasos 2 a 4 para cada servidor que necesite una actualización.
    
