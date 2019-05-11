---
title: Administrar las cuentas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.
ms.openlocfilehash: 86fb7356586c006e8d9f0831d98c9ceba5979180
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893374"
---
# <a name="manage-skype-room-system-accounts"></a>Administrar las cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype. 

> [!NOTE]
> Salones de los equipos de Microsoft es un producto distinto con dependencias diferentes y procedimientos de implementación. Para obtener información sobre las salas de los equipos de Microsoft, vea la [Introducción a la administración](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de salas de equipos de Microsoft.
  
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
  

