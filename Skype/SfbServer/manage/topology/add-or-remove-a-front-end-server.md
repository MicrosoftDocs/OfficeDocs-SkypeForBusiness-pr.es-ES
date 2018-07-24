---
title: Agregar o quitar un servidor Front-End en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Obtenga información sobre cómo agregar o quitar servidores Front-End en Skype para Business Server.'
ms.openlocfilehash: 07f23f3dfb913a353a72ac855915d4001ed02f24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018786"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server"></a>Agregar o quitar un servidor Front-End en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo agregar o quitar servidores Front-End en Skype para Business Server.
  
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