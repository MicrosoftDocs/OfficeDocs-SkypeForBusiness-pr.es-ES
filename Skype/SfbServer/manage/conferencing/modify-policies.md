---
title: Modificar directivas de conferencia en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Resumen: Conozca cómo modificar directivas de conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: b0456db5d0c6131b3b3999a87fc824d6ee3b4b30
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="modify-conferencing-policies-in-skype-for-business-server-2015"></a>Modificar directivas de conferencia en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo modificar las directivas de la conferencia en Skype para Business Server 2015.
  
Puede modificar las directivas de conferencia utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificar directivas de conferencias mediante Skype para Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. En la lista de directivas de conferencia, haga clic en la directiva que desee cambiar y luego haga clic en **Editar** y en **Mostrar detalles**.
    
5. En **Editar directiva de conferencia**, modifique cualquier configuración de directivas, salvo el nombre de la directiva, que no se puede modificar.
    
6. Haga clic en **Confirmar**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificar directivas de conferencias mediante Skype para el Shell de administración de servidor empresarial

Para modificar las directivas de la conferencia, use el cmdlet **Set-CsConferencingPolicy** .
  
El siguiente ejemplo modifica un valor de propiedad de la directiva de conferencia SalesConferencingPolicy. El comando establece el valor de la propiedad AllowConferenceRecording en False:
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Para obtener más información, incluida la sintaxis completa y una lista de parámetros, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

