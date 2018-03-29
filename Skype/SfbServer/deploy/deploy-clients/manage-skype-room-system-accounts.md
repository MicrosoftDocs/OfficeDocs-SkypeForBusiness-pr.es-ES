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
ms.openlocfilehash: c47765b617e0856d1db25c7ed4902fe0af9924f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-system-accounts"></a>Administrar las cuentas del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo administrar las cuentas de Sistema de salas de Skype.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Mueva la cuenta de sistema del sitio de Skype entre grupos

Si necesita mover la cuenta de sistema del sitio de Skype de uno Skype para el grupo de servidores empresariales a otro (por ejemplo, durante las actualizaciones), utilice el siguiente comando para mover el grupo de la cuenta de sistema del sitio de Skype: 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Deshabilitar la cuenta de sistema del sitio de Skype de Skype para servicios de negocios

Si necesita deshabilitar una cuenta ya existente sistema de sala de Skype de Skype servicios comerciales en un Skype para el grupo de servidores empresariales, utilice el siguiente comando para deshabilitar la cuenta: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Opcional: Crear un grupo de administrador de sistema de sala de Skype en Active Directory

Cada cliente de sistema de sala de Skype que se une al dominio puede ser totalmente administrado por un usuario de dominio con derechos de administrador local en el dispositivo de sistema de sala de Skype PC. Por lo tanto, puede crear un dedicado grupo en Active Directory y renunciar a este derechos administrativos de grupo durante la configuración del nuevo equipo de sistema del sitio de Skype.
  

