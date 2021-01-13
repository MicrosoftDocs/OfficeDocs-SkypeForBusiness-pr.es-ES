---
title: Cambiar una directiva de archivado existente en Skype Empresarial Server
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumen: obtenga información sobre cómo cambiar las directivas de archivado de usuarios para Skype Empresarial Server.'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817710"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Cambiar una directiva de archivado existente en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo cambiar las directivas de archivado de usuarios para Skype Empresarial Server.
  
Cuando implementa Skype Empresarial Server por primera vez, configura directivas de archivado iniciales que determinan cómo se implementa el archivado para los usuarios de su implementación. En este tema se describe cómo administrar y modificar directivas. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Cambiar las directivas de archivado mediante el Panel de control

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
4. En la lista de directivas, siga uno de estos pasos: 
    
   - Para cambiar la directiva de toda la implementación, haga clic en **Global** en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.
    
   - Para cambiar la directiva de un solo sitio, haga clic en el nombre del sitio en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.
    
   - Para cambiar la directiva de solo usuario o grupo de usuarios, haga clic en el nombre del usuario o del grupo de usuarios en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.
    
5. En la página **Editar directiva de archivado**, haga lo siguiente:
    
   - Para habilitar o deshabilitar el archivado interno para la directiva, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para habilitar o deshabilitar el archivado externo para la directiva, active o desactiva la casilla **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
    > [!IMPORTANT]
    > La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva. Para obtener más información, [consulte Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server.](apply-a-policy-to-users.md) 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Cambiar las directivas de archivado mediante Windows PowerShell

También puede cambiar las directivas de archivado con Windows PowerShell **Cmdlet Set-CsArchivingPolicy.**
  
### <a name="enable-archiving-policies"></a>Habilitar directivas de archivado

Para habilitar el archivado de sesiones de comunicación internas, establezca el valor del parámetro ArchiveInternal en True ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Para habilitar el archivado de sesiones de comunicación externas, establezca el valor del parámetro ArchiveExternal en True ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Para habilitar el archivado de sesiones de comunicación internas y externas, establezca el valor de los parámetros ArchiveInternal y ArchiveExternal en True: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Deshabilitar directivas de archivado

Para deshabilitar el archivado por completo, establezca el valor de los parámetros ArchiveInternal y ArchiveExternal en False ($False): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
