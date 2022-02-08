---
title: Modificar directivas de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Summary: Learn how to modify conferencing policies in Skype Empresarial Server.'
ms.openlocfilehash: f7f32d227ca33a62ed389a2638f3d784839be8d9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385708"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modificar directivas de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo modificar directivas de conferencia en Skype Empresarial Server.
  
Puede modificar directivas de conferencia mediante Skype Empresarial Server Panel de control o mediante Skype Empresarial Server Shell de administración.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificar directivas de conferencia mediante Skype Empresarial Server Panel de control

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia y**, a continuación, haga clic **en Directiva de conferencia**.
    
4. En la lista de directivas de conferencia, haga clic en la directiva que desee cambiar y luego haga clic en **Editar** y en **Mostrar detalles**.
    
5. En **Editar directiva de conferencia**, modifique cualquier configuración de directivas, salvo el nombre de la directiva, que no se puede modificar.
    
6. Haga clic en **Confirmar**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificar directivas de conferencia mediante Skype Empresarial Server Shell de administración

Para modificar directivas de conferencia, use el cmdlet **Set-CsConferencingPolicy** .
  
En el siguiente ejemplo se modifica un valor de propiedad de la directiva de conferencia SalesConferencingPolicy. El comando establece el valor de la propiedad AllowConferenceRecording en False:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, vea [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
