---
title: Eliminar una directiva de archivado existente en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumen: Conozca cómo eliminar una directiva de archivado para Skype para Business Server 2015.'
ms.openlocfilehash: aeb640cc832bffbded4765e5b6cc931a17365215
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server-2015"></a>Eliminar una directiva de archivado existente en Skype Empresarial Server 2015

**Resumen:** Obtenga información acerca de cómo eliminar una directiva de archivado para Skype para Business Server 2015.
  
Puede eliminar una directiva de usuario o de sitio, pero no puede eliminar una directiva global. Si elimina la directiva global, Skype para Business Server restablece automáticamente la directiva a los valores predeterminados.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Eliminar una directiva con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
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