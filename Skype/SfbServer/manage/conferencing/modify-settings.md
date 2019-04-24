---
title: Modificar valores de configuración de Skype para Business Server de la reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumen: Obtenga información sobre cómo modificar los valores de configuración de Skype para Business Server de la reunión.'
ms.openlocfilehash: 73127bfce04c8c124ce8036222d755de6bc37058
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199958"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificar valores de configuración de Skype para Business Server de la reunión
 
**Resumen:** Obtenga información sobre cómo modificar los valores de configuración de Skype para Business Server de la reunión.
  
Puede modificar una configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar una configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la lista de configuraciones de la reunión, haga clic en la configuración que desee cambiar, luego, haga clic en **Editar** y, por último, en **Mostrar detalles**.
    
5. En **Editar configuración de reunión**, modifique cualquiera de las opciones de configuración, excepto el nombre de la configuración, que no se puede modificar.
    
6. Haga clic en **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar una configuración de reunión mediante el uso de Skype para Shell de administración de servidor empresarial

Para modificar las opciones de configuración de la reunión, use el cmdlet **Set-CsMeetingConfiguration**.
  
El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio Redmond (-Identity site:Redmond). En este caso, el valor de la propiedad DesignateAsPresenter es Everyone (todos):
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obtener más información, incluida una lista completa de los parámetros, consulte [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

