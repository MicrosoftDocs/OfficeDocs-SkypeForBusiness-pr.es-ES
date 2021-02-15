---
title: Modificar las opciones de configuración de reuniones en Skype Empresarial Server
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
description: 'Resumen: obtenga información sobre cómo modificar las opciones de configuración de reuniones en Skype Empresarial Server.'
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828000"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificar las opciones de configuración de reuniones en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo modificar las opciones de configuración de reuniones en Skype Empresarial Server.
  
Puede modificar las opciones de configuración de reuniones con el Panel de control de Skype Empresarial Server o con el Shell de administración de Skype Empresarial Server.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar las opciones de configuración de reuniones mediante el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Configuración **de reunión.**
    
4. En la lista de configuraciones de reunión, haga clic en la configuración que desea cambiar, haga clic en Editar **y,** a continuación, haga clic **en Mostrar detalles.**
    
5. En **Editar configuración de reunión**, modifique cualquiera de las configuraciones de participación en reuniones, excepto el nombre, que no se puede modificar.

    
6. Haga clic en **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar las opciones de configuración de reuniones mediante el Shell de administración de Skype Empresarial Server

Para modificar las opciones de configuración de reuniones, use el cmdlet **Set-CsMeetingConfiguration.**
  
El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio redmond (-Identity site:Redmond). En este caso, el valor de la propiedad DesignateAsPresenter se establece en Todos:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obtener más información, incluida una lista completa de parámetros, vea [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

