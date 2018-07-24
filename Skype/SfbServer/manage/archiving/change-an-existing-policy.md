---
title: Cambiar una directiva en Skype de archivado para Business Server existente
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumen: Obtenga información sobre cómo cambiar las directivas de archivado para Skype para Business Server de usuarios.'
ms.openlocfilehash: 6c92d4f7e4c2a464d248f6b981165de000615432
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974654"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Cambiar una directiva en Skype de archivado para Business Server existente
 
**Resumen:** Obtenga información sobre cómo cambiar las directivas de archivado para Skype para Business Server de usuarios.
  
Cuando se implementa en primer lugar Skype para Business Server, configuración de directivas de archivado iniciales que determinan cómo se implementa el archivado para los usuarios de la implementación. Este tema describe cómo administrar y corregir directivas. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Cambiar las directivas de archivado con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
4. En la lista de directivas, siga uno de estos pasos: 
    
   - Para cambiar la directiva de toda la implementación, haga clic en **Global** en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.
    
   - Para cambiar la directiva de un solo sitio, haga clic en el nombre del sitio en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.
    
   - Para cambiar la directiva de solo usuario o grupo de usuarios, haga clic en el nombre del usuario o del grupo de usuarios en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.
    
5. En la página **Editar directiva de archivado**, haga lo siguiente:
    
   - Para habilitar o deshabilitar el archivado interno para la directiva, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para habilitar o deshabilitar el archivado externo para la directiva, active o desactiva la casilla **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
    > [!IMPORTANT]
    > La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva. Para obtener información detallada, vea [aplicar una directiva de archivado para los usuarios de Skype para Business Server](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Cambiar las directivas de archivado con Windows PowerShell

También puede cambiar las directivas de archivado con el cmdlet **Set-CsArchivingPolicy** de Windows PowerShell.
  
### <a name="enable-archiving-policies"></a>Habilitar las directivas de archivado

Para habilitar el archivado de sesiones de comunicación internas, establezca el valor del parámetro ArchiveInternal en True ($True): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Para habilitar el archivado de sesiones de comunicación externas, establezca el valor del parámetro ArchiveExternal en True ($True): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Para habilitar el archivado de sesiones de comunicación internas y externas, establezca el valor de los parámetros de la ArchiveInternal y ArchiveExternal en True: 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Deshabilitar las directivas de archivado

Para deshabilitar el archivado por completo, establezca el valor de los parámetros ArchiveInternal y ArchiveExternal en False ($False): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```