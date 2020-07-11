---
title: Administración de servidores front-end en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Obtenga información sobre cómo agregar, quitar, aplicar revisiones o actualizar los servidores front-end en Skype empresarial Server.'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098418"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Administración de servidores front-end en Skype empresarial Server
 
En este artículo se explica cómo agregar o quitar servidores front-end y cómo aplicar actualizaciones o revisiones a los servidores front-end.

  > [!NOTE]
> Skype empresarial Server 2019 no es compatible con grupos de servidores front-end Enterprise Edition con dos servidores front-end y no permite que la topología se publique en ese escenario.

## <a name="add-or-remove-front-end-servers"></a>Agregar o quitar servidores front-end
  
Cuando agrega un servidor front-end a un grupo o cuando quita un servidor front-end de un grupo, debe reiniciar el grupo. 
  
> [!IMPORTANT]
> Al agregar o quitar un servidor del grupo de servidores de la topología y, a continuación, publicar la topología actualizada, se reiniciarán todos los servidores del grupo al mismo tiempo. Mientras los servidores se reinician, el grupo de servidores está sin conexión, lo que interrumpirá el servicio para los usuarios conectados a ese grupo. Para evitar cualquier interrupción del servicio a los usuarios, planee publicar la topología con el nuevo servidor en el grupo de servidores durante el horario no comercial. 
  
Puede usar el siguiente procedimiento al agregar o quitar un servidor front-end.
  
> [!NOTE]
> Si va a agregar nuevos servidores al grupo, actualice los nuevos servidores de grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes en el grupo. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para agregar o quitar servidores front-end

1. If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Abra el Generador de topologías, y agregue o quite los servidores necesarios. 
    
3. Publique la topología.
    
    > [!IMPORTANT]
    > Al agregar o quitar un servidor del grupo de servidores de la topología y, a continuación, publicar la topología actualizada, se reiniciarán todos los servidores del grupo al mismo tiempo. Mientras los servidores se reinician, el grupo de servidores está sin conexión, lo que interrumpirá el servicio para los usuarios conectados a ese grupo. Para evitar cualquier interrupción del servicio a los usuarios, planee publicar la topología con el nuevo servidor en el grupo de servidores durante el horario no comercial. 
  
  > [!NOTE]
> Además, al agregar o quitar un servidor del grupo, debe ejecutar el Asistente para la implementación de Skype empresarial Server en cada equipo que se haya agregado o quitado, para obtener más información, consulte [instalar Skype empresarial Server en los servidores de la topología](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .
  
4. Si ha cambiado el número de servidores en el grupo de servidores front-end de cualquiera de las siguientes maneras, restablezca el grupo con el siguiente cmdlet: RESET-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 a cualquier
    
     - De uno a dos
    
     - 3 a cualquier
    
     - De uno a tres
    
5. Reinicie el grupo de servidores; para ello, escriba el siguiente cmdlet
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Revisión o actualización de los servidores front-end

Cuando se revisan los servidores de un grupo de servidores front-end, lo hace en un servidor cada vez. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar una actualización a los servidores front-end de un grupo de servidores

1. Escriba el siguiente cmdlet:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Si este cmdlet muestra las réplicas que faltan, ejecute el siguiente cmdlet para recuperar el grupo antes de aplicar cualquier revisión.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. En el primer servidor que quiera revisar, ejecute el siguiente cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Este cmdlet mueve todos los servicios a otros servidores front-end del grupo y desconecta el servidor.
    
3. Aplique la actualización o la revisión a este servidor.
    
4. En el servidor actualizado, ejecute el siguiente cmdlet:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    El servidor se devuelve al servicio.
    
5. Repita los pasos 2-4 para cada servidor que deba actualizarse.
    
