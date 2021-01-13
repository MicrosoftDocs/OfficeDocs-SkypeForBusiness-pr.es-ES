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
description: Lea este tema para obtener información sobre cómo administrar cuentas del Sistema de sala de Skype.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805560"
---
# <a name="manage-skype-room-system-accounts"></a>Administrar cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo administrar cuentas del Sistema de sala de Skype. 

> [!NOTE]
> Salas de Microsoft Teams es un producto diferente con diferentes dependencias y procedimientos de implementación. Para obtener información sobre salas de Microsoft Teams, vea la introducción a la administración de salas [de](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)Microsoft Teams.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover la cuenta del Sistema de sala de Skype entre grupos de servidores

Si necesita mover la cuenta del Sistema de sala de Skype de un grupo de Skype Empresarial Server a otro (por ejemplo, durante las actualizaciones), use el siguiente comando para mover el grupo de cuentas del Sistema de sala de Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deshabilitar la cuenta del Sistema de sala de Skype para los servicios de Skype Empresarial

Si necesita deshabilitar una cuenta existente del Sistema de sala de Skype de los servicios de Skype Empresarial en un grupo de servidores de Skype Empresarial Server, use el siguiente comando para deshabilitar la cuenta: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: Crear un grupo de administradores del Sistema de sala de Skype en Active Directory

Cada cliente del Sistema de sala de Skype que se une al dominio puede ser administrado completamente por un usuario de dominio con derechos de administrador local en el equipo de dispositivo del Sistema de sala de Skype. Por lo tanto, puede crear un grupo de administradores dedicado en Active Directory y dar derechos administrativos a este grupo durante la configuración del nuevo equipo del Sistema de sala de Skype.
  

