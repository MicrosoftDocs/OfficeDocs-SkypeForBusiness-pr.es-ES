---
title: Eliminar una configuración de Skype para Business Server de reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumen: Obtenga información sobre cómo eliminar una configuración de Skype para Business Server de reunión.'
ms.openlocfilehash: 47cde99751c90b71a52b70a0bde9aaf15acf0154
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222761"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Eliminar una configuración de Skype para Business Server de reunión
 
**Resumen:** Obtenga información sobre cómo eliminar una configuración de Skype para Business Server de reunión.
  
Puede eliminar una configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.
  
Puede eliminar una configuración de sitio o de usuario, pero no puede eliminar la configuración global. Si intenta eliminar la configuración global, esta se restablece automáticamente a sus valores predeterminados.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminar una configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la lista de configuraciones de reunión, haga clic en la configuración de sitio o de grupo que desea eliminar, haga clic en **Editar** y después en **Eliminar**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminar una configuración de reunión mediante el uso de Skype para Shell de administración de servidor empresarial

Para eliminar la configuración de la reunión, use el cmdlet **Remove-CsMeetingConfiguration**.
  
El siguiente comando elimina las opciones de configuración de reunión aplicadas al sitio Redmond:
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

El siguiente comando quita todas las opciones de configuración de reunión que se aplican al ámbito del sitio:
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Para obtener más información, incluida una lista completa de los parámetros, consulte [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

