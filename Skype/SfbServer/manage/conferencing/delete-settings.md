---
title: Eliminar las opciones de configuración de reunión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Summary: Learn how to delete meeting configuration settings in Skype Empresarial Server.'
ms.openlocfilehash: 44b1808c5e5d27bb7dd8aef7ebcef9e26923bb6c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737836"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Eliminar las opciones de configuración de reunión en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo eliminar las opciones de configuración de reuniones en Skype Empresarial Server.
  
Puede eliminar las opciones de configuración de reuniones mediante Skype Empresarial Server Panel de control o mediante Skype Empresarial Server Shell de administración.
  
Puede eliminar un sitio o una configuración de usuario, pero no puede eliminar la configuración global. Si intenta eliminar la configuración global, se restablece automáticamente a los valores predeterminados.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminar las opciones de configuración de reunión mediante Skype Empresarial Server Panel de control

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia y,** a continuación, haga clic en **Configuración de reunión.**
    
4. En la lista de configuraciones de reunión, haga clic en la configuración del sitio o grupo de servidores que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminar las opciones de configuración de reuniones mediante Skype Empresarial Server Shell de administración

Para eliminar la configuración de reunión, use el cmdlet **Remove-CsMeetingConfiguration.**
  
El siguiente comando quita las opciones de configuración de reunión aplicadas al sitio redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

El siguiente comando quita todas las opciones de configuración de reunión aplicadas al ámbito del sitio:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Para obtener más información, incluida una lista completa de parámetros, vea [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
