---
title: Modificar las directivas de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumen: Obtenga información sobre cómo modificar las directivas de conferencia en Skype para Business Server.'
ms.openlocfilehash: 36b6cb92ddb1a6628186198906da87c5dec29532
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197796"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modificar las directivas de conferencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo modificar las directivas de conferencia en Skype para Business Server.
  
Puede modificar las directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificar las directivas de conferencia mediante Skype para el Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. En la lista de directivas de conferencia, haga clic en la directiva que desee cambiar y luego haga clic en **Editar** y en **Mostrar detalles**.
    
5. En **Editar directiva de conferencia**, modifique cualquier configuración de directivas, salvo el nombre de la directiva, que no se puede modificar.
    
6. Haga clic en **Confirmar**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificar las directivas de conferencia mediante Skype para Shell de administración de servidor empresarial

Para modificar las directivas de conferencia, use el cmdlet **Set-CsConferencingPolicy** .
  
El siguiente ejemplo modifica un valor de propiedad de la directiva de conferencia SalesConferencingPolicy. El comando establece el valor de la propiedad AllowConferenceRecording en False:
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

