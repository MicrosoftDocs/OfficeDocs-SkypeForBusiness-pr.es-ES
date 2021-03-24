---
title: Administrar servidores front-end en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Summary: Learn how to add, remove, patch, or update Front End Servers in Skype for Business Server.'
ms.openlocfilehash: 24527a5f973b21c35e386f0565ac6deb69e15070
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103196"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Administrar servidores front-end en Skype Empresarial Server
 
En este artículo se explica cómo agregar o quitar servidores front-end y cómo aplicar actualizaciones o revisiones a los servidores front-end.

  > [!NOTE]
> Skype Empresarial Server 2019 no admite grupos de servidores front-end Enterprise Edition con dos servidores front-end y no permitirá que la topología se publique en ese escenario.

## <a name="add-or-remove-front-end-servers"></a>Agregar o quitar servidores front-end
  
Cuando agrega un servidor front-end a un grupo o cuando quita un servidor front-end de un grupo, debe reiniciar el grupo. 
  
> [!IMPORTANT]
> Al agregar o quitar un servidor al grupo de servidores de la topología y, a continuación, publicar la topología actualizada, hará que todos los servidores del grupo se reinicien al mismo tiempo. Mientras los servidores reinician el grupo está sin conexión, lo que interrumpirá el servicio para los usuarios conectados a ese grupo. Para evitar cualquier interrupción del servicio a los usuarios, planee publicar la topología con el nuevo servidor en el grupo durante el horario no comercial. 
  
Puede usar el siguiente procedimiento al agregar o quitar un servidor front-end.
  
> [!NOTE]
> Si va a agregar nuevos servidores al grupo de servidores, actualice los nuevos servidores de grupo para que se actualicen en el mismo nivel de actualización acumulativa que los servidores existentes en el grupo de servidores. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para agregar o quitar servidores front-end

1. Si desea quitar servidores front-end, primero detenga las nuevas conexiones a esos servidores. Para ello, puede usar el siguiente cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Abra el Generador de topologías, y agregue o quite los servidores necesarios. 
    
3. Publique la topología.
    
    > [!IMPORTANT]
    > Al agregar o quitar un servidor al grupo de servidores de la topología y, a continuación, publicar la topología actualizada, hará que todos los servidores del grupo se reinicien al mismo tiempo. Mientras los servidores reinician el grupo está sin conexión, lo que interrumpirá el servicio para los usuarios conectados a ese grupo. Para evitar cualquier interrupción del servicio a los usuarios, planee publicar la topología con el nuevo servidor en el grupo durante el horario no comercial. 
  
  > [!NOTE]
> Además, al agregar o quitar un servidor al grupo de servidores, debe ejecutar el Asistente para la implementación de Skype Empresarial Server en cada equipo agregado o eliminado, para obtener más información, vea [Install Skype for Business Server on servers in the topology](../../deploy/install/install-skype-for-business-server.md)
  
4. Si ha cambiado el número de servidores del grupo de servidores front-end de cualquiera de las siguientes maneras, restablezca el grupo escribiendo el siguiente cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - De 2 a cualquiera
    
     - Cualquiera a 2
    
     - De 3 a cualquiera
    
     - Cualquiera a 3
    
5. Reinicie el grupo escribiendo el siguiente cmdlet
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Revisión o actualización de servidores front-end

Al aplicar una revisión a los servidores de un grupo de servidores front-end, lo hace de un servidor a la vez. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar una actualización a los servidores front-end de un grupo de servidores

1. Escriba el siguiente cmdlet:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Si este cmdlet muestra las réplicas que faltan, ejecute el siguiente cmdlet para recuperar el grupo antes de aplicar las revisiones.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. En el primer servidor que desea aplicar la revisión, ejecute el siguiente cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Este cmdlet mueve todos los servicios a otros servidores front-end del grupo de servidores y desconecta este servidor.
    
3. Aplique la actualización o la revisión a este servidor.
    
4. En el servidor actualizado, ejecute el siguiente cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    El servidor se devuelve al servicio.
    
5. Repita los pasos 2 a 4 para cada servidor que necesite actualizarse.
