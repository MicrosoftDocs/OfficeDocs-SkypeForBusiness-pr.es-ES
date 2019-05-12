---
title: Eliminar directivas de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumen: Obtenga información sobre cómo eliminar las directivas de conferencia en Skype para Business Server.'
ms.openlocfilehash: 534dc52e730051b82c7f5edcb1bd2564be7dde2f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919440"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Eliminar directivas de conferencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo eliminar las directivas de conferencia en Skype para Business Server.
  
Puede eliminar las directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Eliminar directivas de conferencia mediante Skype para el Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. En la lista de directivas de conferencia, haga clic en la directiva de usuario o en el sitio que desea eliminar, haga clic en **Editar** y, después, en **Eliminar**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Eliminar directivas de conferencia mediante Skype para Shell de administración de servidor empresarial

Para eliminar las directivas de conferencia, use el cmdlet **Remove-CsConferencingPolicy**.
  
El comando siguiente quita la directiva de conferencia con el valor de identidad RedmondConferencingPolicy:
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

El comando siguiente quita cualquier directiva de conferencia que permita que usuarios externos graben la conferencia:
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, consulte [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

