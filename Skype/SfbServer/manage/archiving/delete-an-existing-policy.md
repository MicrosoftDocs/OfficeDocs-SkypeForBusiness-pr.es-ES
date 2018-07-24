---
title: Eliminar una directiva en Skype de archivado para Business Server existente
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumen: Obtenga información sobre cómo eliminar una directiva de archivado para Skype para Business Server.'
ms.openlocfilehash: 0446999923b462311f941b6653157b41000b1f43
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973104"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Eliminar una directiva en Skype de archivado para Business Server existente

**Resumen:** Obtenga información sobre cómo eliminar una directiva de archivado para Skype para Business Server.
  
Puede eliminar una directiva de usuario o de sitio, pero no puede eliminar una directiva global. Si se elimina la directiva global, Skype para Business Server restablece automáticamente la directiva a los valores predeterminados.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Eliminar una directiva con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
4. En la lista de directivas de archivado, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, luego, en **Eliminar**.
    
5. Haga clic en **Confirmar**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Eliminar una directiva con Windows PowerShell

También puede eliminar directivas de archivado con el cmdlet **Remove-CsArchivingConfiguration**.
  
Por ejemplo, el siguiente comando elimina la directiva con el sitio de identidad: Redmond. Cuando se elimina una directiva configurada en el nivel del sitio, los usuarios a los que anteriormente administraba esta directiva de sitio se regirán de forma automática por la directiva de archivado global:
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

Este comando quita todas las directivas de archivado aplicadas al nivel por usuario:
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Este comando quita todas las directivas de archivado donde se deshabilitó el archivado interno:
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .