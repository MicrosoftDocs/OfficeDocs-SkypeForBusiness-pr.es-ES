---
title: Una revisión o actualización de servidores Front-End en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Resumen: Obtenga información sobre cómo aplicar las actualizaciones o revisiones a servidores Front-End en Skype para Business Server.'
ms.openlocfilehash: cf209159391ef084d77b5adc639698ed766427ff
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371720"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a>Una revisión o actualización de servidores Front-End en Skype para Business Server
 
**Resumen:** obtener información sobre cómo aplicar las actualizaciones o revisiones a servidores Front-End en Skype para Business Server.
  
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
    

