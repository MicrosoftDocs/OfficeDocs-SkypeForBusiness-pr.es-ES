---
title: Eliminar directivas de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumen: obtenga información sobre cómo eliminar directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119509"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Eliminar directivas de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo eliminar directivas de conferencia en Skype Empresarial Server.
  
Puede eliminar directivas de conferencia mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Eliminar directivas de conferencia mediante el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**
    
4. En la lista de directivas de conferencia, haga clic en el sitio o la directiva de usuario que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Eliminar directivas de conferencia mediante el Shell de administración de Skype Empresarial Server

Para eliminar directivas de conferencia, use el cmdlet **Remove-CsConferencingPolicy.**
  
El comando siguiente quita la directiva de conferencia con el valor de identidad RedmondConferencingPolicy:
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

El siguiente comando elimina las directivas de conferencia que permiten a los usuarios externos grabar la conferencia:
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, [vea Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
