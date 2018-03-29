---
title: Eliminar directivas de conferencia en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Summary: Learn how to delete conferencing policies in Skype for Business Server 2015.'
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a>Eliminar directivas de conferencia en Skype Empresarial Server 2015
 
**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.
  
You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Delete conferencing policies by using Skype for Business Server Control Panel

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Open Skype for Business Server Control Panel.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. En la lista de directivas de conferencia, haga clic en la directiva de usuario o en el sitio que desea eliminar, haga clic en **Editar** y, después, en **Eliminar**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Delete conferencing policies by using Skype for Business Server Management Shell

Para eliminar las directivas de conferencia, use el cmdlet **Remove-CsConferencingPolicy**.
  
El comando siguiente quita la directiva de conferencia con el valor de identidad RedmondConferencingPolicy:
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

El comando siguiente quita cualquier directiva de conferencia que permita que usuarios externos graben la conferencia:
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

