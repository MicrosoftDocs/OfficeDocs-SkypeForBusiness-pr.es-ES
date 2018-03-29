---
title: Agregar o quitar un servidor front-end en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Conozca cómo agregar o quitar servidores frontales de Skype para Business Server.'
ms.openlocfilehash: aed52becf5d4cc97307f9788a81f8d6563d1d25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a>Agregar o quitar un servidor front-end en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a agregar o quitar servidores frontales de Skype para Business Server.
  
Cuando agregue un servidor Front-End a un grupo, o quitar un servidor Front-End de un grupo, debe reiniciar el grupo. 
  
> [!IMPORTANT]
> Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial. 
  
Puede utilizar el procedimiento siguiente al agregar o quitar un servidor Front-End.
  
> [!NOTE]
> Si agrega nuevos servidores al grupo, actualice los nuevos servidores del grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes del grupo. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Para agregar o quitar servidores frontales

1. Si desea quitar los servidores frontales, detener nuevas conexiones a los servidores. Para ello, puede usar el siguiente cmdlet:
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Abrir el generador de topología y agregar o quitar los servidores necesarios. 
    
3. Publique la topología.
    
    > [!IMPORTANT]
    > Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial. 
  
4. Si ha cambiado el número de servidores en el grupo de servidores Front-End en cualquiera de las siguientes formas, restablecer el fondo con escribiendo el siguiente cmdlet: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn 
    
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


