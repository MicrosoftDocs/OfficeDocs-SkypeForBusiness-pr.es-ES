---
title: Modificar las opciones de configuración de reuniones en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumen: Conozca cómo modificar valores de configuración de Skype para Business Server 2015 de reunión.'
ms.openlocfilehash: 95f28f35859553f79fc6f74f8850f224bda54deb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Modificar las opciones de configuración de reuniones en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo modificar valores de configuración de Skype para Business Server 2015 de reunión.
  
Puede modificar valores de configuración de reunión utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor de Business.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificar valores de configuración de la reunión con Skype para Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la lista de configuraciones de la reunión, haga clic en la configuración que desee cambiar, luego, haga clic en **Editar** y, por último, en **Mostrar detalles**.
    
5. En **Editar configuración de reunión**, modifique cualquiera de las opciones de configuración, excepto el nombre de la configuración, que no se puede modificar.
    
6. Haga clic en **Confirmar**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificar valores de configuración de la reunión con Skype para el Shell de administración de servidor empresarial

Para modificar las opciones de configuración de la reunión, use el cmdlet **Set-CsMeetingConfiguration**.
  
El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio Redmond (-Identity site:Redmond). En este caso, el valor de la propiedad DesignateAsPresenter es Everyone (todos):
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Para obtener más información, incluida una lista completa de los parámetros, consulte [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

