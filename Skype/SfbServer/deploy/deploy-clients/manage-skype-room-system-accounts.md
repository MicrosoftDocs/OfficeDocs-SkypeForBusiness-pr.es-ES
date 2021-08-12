---
title: Administrar cuentas del Sistema de salas de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lea este tema para obtener información sobre cómo administrar Skype de sistema de sala.
ms.openlocfilehash: 416a211ec9954dd2c2a8c856a67c72226209f3e7dd6114536574e63c5520b841
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279468"
---
# <a name="manage-skype-room-system-accounts"></a>Administrar cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo administrar Skype de sistema de sala. 

> [!NOTE]
> Salas de Microsoft Teams es un producto diferente con diferentes dependencias y procedimientos de implementación. Para obtener información sobre Salas de Microsoft Teams, vea el Salas de Microsoft Teams [de administración.](/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover la cuenta Skype sistema de sala entre grupos

Si necesita mover la cuenta del sistema de sala Skype de un grupo de servidores de Skype Empresarial Server a otro (por ejemplo, durante las actualizaciones), use el siguiente comando para mover el grupo de cuentas del sistema de sala Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deshabilitar la cuenta Skype sistema de sala de Skype Empresarial servicios

Si necesita deshabilitar una cuenta existente del sistema de Skype desde Skype Empresarial de un grupo de servidores de Skype Empresarial Server, use el siguiente comando para deshabilitar la cuenta: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: crear un grupo Skype administrador del sistema de sala en Active Directory

Cada Skype del sistema de sala que se une al dominio puede ser administrado por completo por un usuario de dominio con derechos de administrador local en el equipo del Skype del sistema de sala. Por lo tanto, puede crear un grupo de administradores dedicado en Active Directory y dar a este grupo derechos administrativos durante la configuración del nuevo equipo Skype room system.
