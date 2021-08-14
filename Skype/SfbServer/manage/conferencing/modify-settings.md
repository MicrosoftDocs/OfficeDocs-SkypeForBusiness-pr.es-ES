---
title: Modificar las opciones de configuración de reunión en Skype Empresarial Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Summary: Learn how to modify meeting configuration settings in Skype Empresarial Server.'
ms.openlocfilehash: e1b283c5d50c955464d4af9b8f92f9e210f60f35a1fad5320c9f6bb8b6ede11d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343464"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificar las opciones de configuración de reunión en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo modificar las opciones de configuración de reuniones en Skype Empresarial Server.
  
Puede modificar las opciones de configuración de reuniones mediante Skype Empresarial Server Panel de control o mediante Skype Empresarial Server Shell de administración.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar las opciones de configuración de reunión mediante Skype Empresarial Server Panel de control

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia y,** a continuación, haga clic en **Configuración de reunión.**
    
4. En la lista de configuraciones de reunión, haga clic en la configuración que desea cambiar, haga clic en **Editar** y, a continuación, haga clic **en Mostrar detalles.**
    
5. En **Editar configuración de reunión**, modifique cualquiera de las configuraciones de participación en reuniones, excepto el nombre, que no se puede modificar.

    
6. Haga clic en **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar las opciones de configuración de reunión mediante Skype Empresarial Server Shell de administración

Para modificar las opciones de configuración de reunión, use el cmdlet **Set-CsMeetingConfiguration.**
  
El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio redmond (-Identity site:Redmond). En este caso, el valor de la propiedad DesignateAsPresenter se establece en Todos:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obtener más información, incluida una lista completa de parámetros, vea [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
