---
title: Habilitar la respuesta de llamadas grupales para los usuarios y asignar un número de grupo en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilitar a usuarios de grupo llamar recogida en Skype para Telefonía IP empresarial de Business Server y asignar a un número de grupo.
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a>Habilitar la respuesta de llamadas grupales para los usuarios y asignar un número de grupo en Skype Empresarial 2015
 
Habilitar a usuarios de grupo llamar recogida en Skype para Telefonía IP empresarial de Business Server y asignar a un número de grupo.
  
Después de agregar números de grupo recogida de llamada a la tabla de llamada park órbita, utilice la herramienta SEFAUtil para asignar a los números de grupo a los usuarios y habilitar recogida de grupo llame para ellos.
  
> [!NOTE]
> En una implementación híbrida, no asigne a un grupo de recogida de llamar al grupo a los usuarios que están alojados en línea. Los usuarios que están alojados en línea no pueden participar en la recogida de llamar al grupo. Es decir, no se puede contestar a sus llamadas por otros usuarios y no puede responder a las llamadas a otros usuarios. 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para asignar a un número de grupo y habilitar recogida de grupo llame para un usuario

1. Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.
    
2. En la línea de comandos, ejecute:
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Por ejemplo, para asignar el número de grupo 199 a un usuario:
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a>Vea también

#### 

[Recogida de grupo deshabilitar para usuarios](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

