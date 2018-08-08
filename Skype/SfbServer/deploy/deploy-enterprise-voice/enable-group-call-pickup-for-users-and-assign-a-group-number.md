---
title: Habilitar la recogida de llamadas de grupo para los usuarios y asignar a un número de grupo en Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Permitir a los usuarios para su grupo de llamada recogida en Skype para Business Server Enterprise Voice y asignar a un número de grupo.
ms.openlocfilehash: 5a4173a16a40557742a7cdbd47edb917f89b4737
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006523"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Habilitar la recogida de llamadas de grupo para los usuarios y asignar a un número de grupo en Skype para la empresa 
 
Permitir a los usuarios para su grupo de llamada recogida en Skype para Business Server Enterprise Voice y asignar a un número de grupo.
  
Después de agregar números de llamada pickup grupo a la tabla de órbitas de estacionamiento de llamada, use la herramienta SEFAUtil para asignar a los números de grupo a los usuarios y habilitar recogida de llamadas de grupo para ellos.
  
> [!NOTE]
> En una implementación híbrida, no asigne a un grupo de recogida de llamadas de grupo a los usuarios que están hospedados en línea. Los usuarios que están hospedados en línea no pueden participar en recogida de llamadas de grupo. Es decir, sus llamadas no pueden ser atendidas por otros usuarios y no pueden atender las llamadas a otros usuarios. 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para asignar a un número de grupo y habilitar recogida de llamadas de grupo para un usuario

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

[Recogida de deshabilitar grupo para los usuarios](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

