---
title: Modificar directivas de conferencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumen: Aprenda a modificar directivas de conferencia en Skype empresarial Server.'
ms.openlocfilehash: 4f78a956754e4375ac1dfa7460222b1fb1bbf9ef
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818511"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modificar directivas de conferencia en Skype empresarial Server
 
**Resumen:** Aprenda a modificar directivas de conferencia en Skype empresarial Server.
  
Puede modificar las directivas de conferencia con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificar directivas de conferencia con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. En la lista de directivas de conferencia, haga clic en la directiva que desee cambiar y luego haga clic en **Editar** y en **Mostrar detalles**.
    
5. En **Editar directiva de conferencia**, modifique cualquier configuración de directivas, salvo el nombre de la directiva, que no se puede modificar.
    
6. Haga clic en **Confirmar**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificar directivas de conferencia con el shell de administración de Skype empresarial Server

Para modificar las directivas de conferencia, use el cmdlet **set-CsConferencingPolicy** .
  
El siguiente ejemplo modifica un valor de propiedad de la directiva de conferencia SalesConferencingPolicy. El comando establece el valor de la propiedad AllowConferenceRecording en False:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

