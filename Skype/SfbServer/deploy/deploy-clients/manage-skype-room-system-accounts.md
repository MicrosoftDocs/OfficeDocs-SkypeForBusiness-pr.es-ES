---
title: Administrar las cuentas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
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
description: Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.
ms.openlocfilehash: b6d61f4ddc9fe5e296ffd98b685e1000151d5db2
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768663"
---
# <a name="manage-skype-room-system-accounts"></a>Administrar las cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype. 

> [!NOTE]
> Salas de Microsoft Teams es un producto diferente con diferentes dependencias y procedimientos de implementación. Para obtener información sobre las salas de Microsoft Teams, consulte la [información general de administración](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)de salas de Microsoft Teams.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mover la cuenta del sistema de salas de Skype entre los grupos

Si necesita mover la cuenta del sistema de salas de Skype de un grupo de servidores de Skype empresarial a otro (por ejemplo, durante las actualizaciones), use el siguiente comando para mover el grupo de cuentas del sistema de salas de Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deshabilitar la cuenta del sistema de Skype Room para servicios de Skype empresarial

Si necesita deshabilitar una cuenta del sistema de Skype Room existente en los servicios de Skype empresarial en un grupo de servidores de Skype empresarial, use el siguiente comando para deshabilitar la cuenta: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: crear un grupo de administradores de sistemas de salas de Skype en Active Directory

Cada cliente del sistema de salas de Skype que se une al dominio puede ser administrado por un usuario de dominio con derechos de administrador local en el equipo del sistema de la sala de Skype. Por lo tanto, puede crear un grupo de administradores dedicado en Active Directory y otorgar a este grupo derechos administrativos durante la configuración del nuevo equipo del sistema de salas de Skype.
  

