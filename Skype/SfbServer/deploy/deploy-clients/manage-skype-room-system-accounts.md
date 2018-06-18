---
title: Administrar las cuentas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.
ms.openlocfilehash: 4d3535c9583481273f7a511143244b511cdb5819
ms.sourcegitcommit: 0f089f0c1bc641793c61928fb1c8fa62b2dfabee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2018
ms.locfileid: "19927791"
---
# <a name="manage-skype-room-system-accounts"></a>Administrar las cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype. 

> [!NOTE]
> Sistemas de salón de Skype v2 es un producto diferente con dependencias diferentes y procedimientos de implementación. Para obtener información sobre los sistemas de la sala de Skype v2, vea el de v2 [Introducción a la administración](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de sistemas de salón de Skype.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover la cuenta del sistema de salas de Skype entre grupos de servidores

Si necesita mover la cuenta del sistema de salas de Skype de uno Skype para el grupo de servidores de negocio a otra (por ejemplo, durante las actualizaciones), use el siguiente comando para mover el grupo de servidores de la cuenta del sistema de salas de Skype: 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deshabilitar la cuenta del sistema de salas de Skype para Skype para servicios de negocios

Si necesita deshabilitar una sistema de salas de Skype cuenta existente de Skype para servicios de negocios en un Skype para grupo de servidores de negocio, use el siguiente comando para deshabilitar la cuenta: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: Crear un grupo de administrador del sistema de salas de Skype en Active Directory

Cada cliente del sistema de salas de Skype que se une al dominio puede ser totalmente administrado por un usuario de dominio con derechos de administrador local en el dispositivo del sistema de salas de Skype PC. Por lo tanto, puede crear grupo dedicado de un administradores en Active Directory y da como resultado este derechos administrativos de grupo durante conjunto de copia de seguridad de la nueva máquina de sistema de salas de Skype.
  

