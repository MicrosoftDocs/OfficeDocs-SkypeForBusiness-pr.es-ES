---
title: Habilitar la recogida de llamadas grupales para los usuarios y asignar un número de grupo en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Habilite usuarios para la recogida de llamadas grupales en Skype empresarial Server Enterprise Voice y asigne un número de grupo.
ms.openlocfilehash: bebddb5f71612cf23d442366c774d0e8d4b9f500
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767273"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Habilitar la recogida de llamadas grupales para los usuarios y asignar un número de grupo en Skype empresarial

Habilite usuarios para la recogida de llamadas grupales en Skype empresarial Server Enterprise Voice y asigne un número de grupo.

Después de agregar los números del grupo de recogida de llamadas a la tabla de llamadas en órbita, use la herramienta SEFAUtil para asignar los números de grupo a los usuarios y habilitar la recogida de llamadas grupales.

> [!NOTE]
> En una implementación híbrida, no asigne un grupo de recogida de llamadas grupal a los usuarios alojados en línea. Los usuarios alojados en Internet no pueden participar en la recogida de llamadas grupales. Es decir, otros usuarios no pueden contestar las llamadas y no pueden responder llamadas a otros usuarios.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para asignar un número de grupo y habilitar la recogida de llamadas grupales para un usuario

1. Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.

2. En la línea de comandos, ejecute:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Por ejemplo, para asignar el número de grupo 199 a un usuario:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Vea también

[Disable Group Pickup for Users](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

