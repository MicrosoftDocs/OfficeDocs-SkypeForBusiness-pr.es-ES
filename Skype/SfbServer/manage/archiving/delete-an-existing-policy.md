---
title: Eliminar una directiva de archivado existente en Skype Empresarial Server
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumen: obtenga información sobre cómo eliminar una directiva de archivado para Skype Empresarial Server.'
ms.openlocfilehash: 7d71fd9ca03f743cd51e0161cd1a3b437be43cb2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817620"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Eliminar una directiva de archivado existente en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo eliminar una directiva de archivado para Skype Empresarial Server.
  
Puede eliminar una directiva de usuario o de sitio, pero no la directiva global. Si elimina la directiva global, Skype Empresarial Server restablece automáticamente la directiva a los valores predeterminados.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Eliminar una directiva mediante el Panel de control

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
4. En la lista de directivas, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, a continuación, en **Eliminar**.
    
5. Haga clic en **Confirmar**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Eliminar una directiva mediante Windows PowerShell

También puede eliminar directivas de archivado con el cmdlet **Remove-CsArchivingPolicy.**
  
Por ejemplo, el siguiente comando elimina la directiva con el parámetro Identity site:Redmond. Cuando se elimina una directiva configurada en el nivel de sitio, los usuarios que anteriormente administraba la directiva de sitio se regirán automáticamente por la directiva de archivado global en su lugar:
  
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

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)
