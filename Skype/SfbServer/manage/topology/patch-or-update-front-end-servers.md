---
title: Aplicar parches a servidores front-end o actualizarlos en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/4/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Resumen: Conozca cómo aplicar actualizaciones o revisiones a servidores frontales en Skype para Business Server.'
ms.openlocfilehash: 1f5ccd6531338d1e6b47dd8363b9386bcbeba0fc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server-2015"></a>Aplicar parches a servidores front-end o actualizarlos en Skype Empresarial Server 2015
 
**Resumen:** obtener información sobre cómo aplicar actualizaciones o revisiones a servidores frontales en Skype para Business Server.
  
Cuando la revisión en los servidores de un grupo de servidores Front-End, hacer por lo que un servidor en un momento. 
  
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

    Este cmdlet mueve todos los servicios a otros servidores frontales en la agrupación y desconecta este servidor.
    
3. Aplique la actualización o revisión en el servidor desconectado.
    
4. En el servidor actualizado, ejecute el cmdlet siguiente:
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    El servidor vuelve al servicio.
    
5. Repita los pasos 2 a 4 para cada servidor que necesite una actualización.
    

