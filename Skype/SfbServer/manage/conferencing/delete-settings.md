---
title: Eliminar las opciones de configuración de reunión en Skype Empresarial Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Summary: Learn how to delete meeting configuration settings in Skype for Business Server.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119499"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Eliminar las opciones de configuración de reunión en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo eliminar las opciones de configuración de reuniones en Skype Empresarial Server.
  
Puede eliminar las opciones de configuración de reuniones mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.
  
Puede eliminar un sitio o una configuración de usuario, pero no puede eliminar la configuración global. Si intenta eliminar la configuración global, se restablece automáticamente a los valores predeterminados.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminar las opciones de configuración de reunión mediante el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia y,** a continuación, haga clic en **Configuración de reunión.**
    
4. En la lista de configuraciones de reunión, haga clic en la configuración del sitio o grupo de servidores que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminar las opciones de configuración de reuniones mediante el Shell de administración de Skype Empresarial Server

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
