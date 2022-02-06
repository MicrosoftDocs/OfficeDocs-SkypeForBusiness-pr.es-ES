---
title: Administrar cuentas del Sistema de salas de Skype
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lea este tema para obtener información sobre cómo administrar Skype de sistema de sala.
---

# <a name="manage-skype-room-system-accounts"></a>Administrar cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo administrar Skype de sistema de sala. 

> [!NOTE]
> Salas de Microsoft Teams es un producto diferente con diferentes dependencias y procedimientos de implementación. Para obtener información sobre Salas de Microsoft Teams, vea la introducción Salas de Microsoft Teams [administración de aplicaciones](/microsoftteams/rooms/rooms-manage).
  
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
