---
title: Eliminar la configuración de la reunión en Skype empresarial Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumen: Aprenda a eliminar la configuración de la reunión en Skype empresarial Server.'
ms.openlocfilehash: dd07d3239b212f09391e9bc8c66f29bca62b2c3f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818591"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Eliminar la configuración de la reunión en Skype empresarial Server
 
**Resumen:** Aprenda a eliminar la configuración de la reunión en Skype empresarial Server.
  
Puede eliminar la configuración de la reunión con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
Puede eliminar una configuración de sitio o de usuario, pero no puede eliminar la configuración global. Si intenta eliminar la configuración global, esta se restablece automáticamente a sus valores predeterminados.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminar la configuración de la reunión con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la lista de configuraciones de reunión, haga clic en la configuración de sitio o de grupo que desea eliminar, haga clic en **Editar** y después en **Eliminar**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminar la configuración de la reunión mediante el shell de administración de Skype empresarial Server

Para eliminar la configuración de la reunión, use el cmdlet **Remove-CsMeetingConfiguration**.
  
El siguiente comando elimina las opciones de configuración de reunión aplicadas al sitio Redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

El siguiente comando quita todas las opciones de configuración de reunión que se aplican al ámbito del sitio:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Para obtener más información, incluida una lista completa de parámetros, consulte [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

