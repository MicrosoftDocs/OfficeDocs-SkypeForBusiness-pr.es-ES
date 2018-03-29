---
title: Cambiar una directiva de archivado existente en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumen: Conozca cómo cambiar usuario políticas de archiving para Skype para Business Server 2015.'
ms.openlocfilehash: f03ddc0799868e825c46fad2f93ba93d3b8a071a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server-2015"></a>Cambiar una directiva de archivado existente en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a cambiar usuario políticas de archiving para Skype para Business Server 2015.
  
Al implementar en primer lugar Skype para Business Server 2015, configurar políticas de archiving iniciales que determinan cómo se implementa el archivado de los usuarios en la implementación. Este tema describe cómo administrar y corregir directivas. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Cambiar las directivas de archivado con el Panel de control

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
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
    > La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva. Para obtener más información, vea [aplicar una directiva de archivado para los usuarios de Skype para Business Server 2015](apply-a-policy-to-users.md). 
  
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

Para habilitar el archivado de las sesiones de comunicación interna y externa, establezca el valor de los parámetros de la ArchiveInternal y la ArchiveExternal como True: 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

```

### <a name="disable-archiving-policies"></a>Deshabilitar las directivas de archivado

Para deshabilitar el archivado por completo, establezca el valor de los parámetros ArchiveInternal y ArchiveExternal en False ($False): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False

```