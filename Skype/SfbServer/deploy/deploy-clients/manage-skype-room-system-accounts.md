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
description: Lea este tema para obtener información sobre cómo administrar cuentas del sistema de salón de Skype.
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093298"
---
# <a name="manage-skype-room-system-accounts"></a>Administrar cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo administrar cuentas del sistema de salón de Skype. 

> [!NOTE]
> Microsoft Teams Rooms es un producto diferente con diferentes dependencias y procedimientos de implementación. Para obtener información sobre salas de Microsoft Teams, vea la introducción a la administración de salas [de](/microsoftteams/rooms/rooms-manage)Microsoft Teams.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover la cuenta del sistema de sala de Skype entre grupos

Si necesita mover la cuenta del sistema de salón de Skype de un grupo de Skype Empresarial Server a otro (por ejemplo, durante las actualizaciones), use el siguiente comando para mover el grupo de cuentas del sistema de salón de Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deshabilitar la cuenta del sistema de sala de Skype para los servicios de Skype Empresarial

Si necesita deshabilitar una cuenta existente del sistema de sala de Skype desde los servicios de Skype Empresarial en un grupo de skype empresarial, use el siguiente comando para deshabilitar la cuenta: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: crear un grupo de administradores del sistema de salón de Skype en Active Directory

Cada cliente del sistema de salón de Skype que se une al dominio puede ser administrado completamente por un usuario de dominio con derechos de administrador local en el equipo del dispositivo sistema de sala de Skype. Por lo tanto, puede crear un grupo de administradores dedicado en Active Directory y dar a este grupo derechos administrativos durante la configuración del nuevo equipo del sistema de salón de Skype.
