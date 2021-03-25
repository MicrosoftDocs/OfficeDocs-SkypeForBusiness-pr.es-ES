---
title: Habilitar la recogida de llamadas de grupo para los usuarios y asignar un número de grupo en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Habilite a los usuarios para la recogida de llamadas en grupo en Skype Empresarial Server Telefonía IP empresarial y asigne un número de grupo.
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111836"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Habilitar la recogida de llamadas de grupo para los usuarios y asignar un número de grupo en Skype Empresarial

Habilite a los usuarios para la recogida de llamadas en grupo en Skype Empresarial Server Telefonía IP empresarial y asigne un número de grupo.

Después de agregar números de grupo de recogida de llamadas a la tabla de órbitas de estacionamiento de llamadas, use la herramienta SEFAUtil para asignar los números de grupo a los usuarios y habilitar la recogida de llamadas de grupo para ellos.

> [!NOTE]
> En una implementación híbrida, no asigne un grupo de recogida de llamadas de grupo a los usuarios que estén en línea. Los usuarios que están en línea no pueden participar en la recogida de llamadas en grupo. Es decir, otros usuarios no pueden responder sus llamadas y no pueden responder llamadas a otros usuarios.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para asignar un número de grupo y habilitar la recogida de llamadas de grupo para un usuario

1. Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.

2. En la línea de comandos, ejecute:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Por ejemplo, para asignar el número de grupo 199 a un usuario:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Ver también

[Deshabilitar la recogida de grupos para usuarios](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)