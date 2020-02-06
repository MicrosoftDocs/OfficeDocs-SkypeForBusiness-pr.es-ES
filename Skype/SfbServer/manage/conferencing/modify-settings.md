---
title: Modificar la configuración de la reunión en Skype empresarial Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumen: Aprenda a modificar la configuración de la reunión en Skype empresarial Server.'
ms.openlocfilehash: 893e3fb8c9c441f8dc515eaf3a8a4aaa1ff04620
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818501"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificar la configuración de la reunión en Skype empresarial Server
 
**Resumen:** Aprenda a modificar la configuración de la reunión en Skype empresarial Server.
  
Puede modificar la configuración de la reunión mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar la configuración de la reunión con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la lista de configuraciones de la reunión, haga clic en la configuración que desee cambiar, luego, haga clic en **Editar** y, por último, en **Mostrar detalles**.
    
5. En **Editar configuración de reunión**, modifique cualquiera de las opciones de configuración, excepto el nombre de la configuración, que no se puede modificar.
    
6. Haga clic en **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar la configuración de la reunión mediante el shell de administración de Skype empresarial Server

Para modificar las opciones de configuración de la reunión, use el cmdlet **Set-CsMeetingConfiguration**.
  
El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio Redmond (-Identity site:Redmond). En este caso, el valor de la propiedad DesignateAsPresenter es Everyone (todos):
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obtener más información, incluida una lista completa de parámetros, consulte [set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

