---
title: Eliminar opciones de configuración de reuniones en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumen: Conozca cómo eliminar valores de configuración de Skype para Business Server 2015 de reunión.'
ms.openlocfilehash: dec2e51dfe6ae0b9983515d849bc9fc416e9bcc4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Eliminar opciones de configuración de reuniones en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo eliminar valores de configuración de Skype para Business Server 2015 de reunión.
  
Puede eliminar configuración de reunión utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial.
  
Puede eliminar una configuración de sitio o de usuario, pero no puede eliminar la configuración global. Si intenta eliminar la configuración global, esta se restablece automáticamente a sus valores predeterminados.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminar valores de configuración de la reunión con Skype para Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la lista de configuraciones de reunión, haga clic en la configuración de sitio o de grupo que desea eliminar, haga clic en **Editar** y después en **Eliminar**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminar valores de configuración de la reunión con Skype para el Shell de administración de servidor empresarial

Para eliminar la configuración de la reunión, use el cmdlet **Remove-CsMeetingConfiguration**.
  
El siguiente comando elimina las opciones de configuración de reunión aplicadas al sitio Redmond:
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

El siguiente comando quita todas las opciones de configuración de reunión que se aplican al ámbito del sitio:
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Para obtener más información, incluida una lista completa de los parámetros, vea [Quitar CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

