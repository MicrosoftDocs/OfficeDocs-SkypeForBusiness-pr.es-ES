---
title: Eliminar una directiva de archivado existente en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumen: Aprenda a eliminar una directiva de archivado para Skype empresarial Server.'
ms.openlocfilehash: c08b76996b3d54e8be07e731faae87dce0470cc1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992367"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Eliminar una directiva de archivado existente en Skype empresarial Server

**Resumen:** Aprenda a eliminar una directiva de archivado para Skype empresarial Server.
  
Puede eliminar una directiva de usuario o de sitio, pero no puede eliminar una directiva global. Si elimina la directiva global, Skype empresarial Server restablece automáticamente la Directiva a los valores predeterminados.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Eliminar una directiva con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
4. En la lista de directivas de archivado, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, luego, en **Eliminar**.
    
5. Haga clic en **Confirmar**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Eliminar una directiva con Windows PowerShell

También puede eliminar directivas de archivado con el cmdlet **Remove-CsArchivingConfiguration**.
  
Por ejemplo, el siguiente comando elimina la directiva con el sitio de identidad: Redmond. Cuando se elimina una directiva configurada en el nivel del sitio, los usuarios a los que anteriormente administraba esta directiva de sitio se regirán de forma automática por la directiva de archivado global:
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Este comando quita todas las directivas de archivado aplicadas al nivel por usuario:
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Este comando quita todas las directivas de archivado donde se deshabilitó el archivado interno:
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .
