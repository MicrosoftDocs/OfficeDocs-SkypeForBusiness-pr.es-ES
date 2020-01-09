---
title: Crear una nueva Directiva de archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Resumen: Aprenda a crear una nueva Directiva de archivado para Skype empresarial Server.'
ms.openlocfilehash: 8542c31050cf4ca9383c22b39c83b28309d3ea32
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992737"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Crear una nueva Directiva de archivado en Skype empresarial Server

**Resumen:** Aprenda a crear una nueva Directiva de archivado para Skype empresarial Server.
  
Puede crear directivas de archivado por medio del Panel de control o por medio de los cmdlets de Windows PowerShell.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Crear una directiva de archivado con el Panel de control

Para crear una directiva de archivado con el Panel de control:
  
1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.
    
4. Haga clic en **Nuevo** y, luego, siga uno de estos procedimientos: 
    
   - Para crear una directiva de archivado de nivel de sitio, haga clic en **Directiva de sitio**, en **Seleccionar un sitio** y, después, haga clic en el sitio al que se va a aplicar la directiva.
    
   - Para crear una directiva de archivado de usuario, haga clic en **Directiva de usuario**.
    
5. En **Directiva de archivado nueva**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva (por ejemplo, externalContoso).
    
   - En **Descripción**, proporcione información detallada sobre la función de la directiva (por ejemplo, directiva de archivado de usuarios externos para Contoso).
    
   - Para controlar el archivado de comunicaciones con usuarios internos, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de comunicaciones externas, active o desactive la casilla **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
    > [!IMPORTANT]
    > La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva. Para obtener más información, vea [aplicar una directiva de archivado a los usuarios en Skype empresarial Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Crear una directiva de archivado con Windows PowerShell

Puede también crear una directiva de archivado con el cmdlet de Windows PowerShell **New-CsArchivingPolicy**. Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Crear una directiva de archivado en el ámbito de sitio

Este comando crea una directiva de archivado para el sitio Redmond:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Para crear una directiva de archivado por usuario

Para crear una directiva de archivado por usuario, simplemente especifique una identidad única al crear la directiva:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Para crear una directiva de archivado que permita el archivado de sesiones de comunicaciones internas

Ya que no se especifican parámetros (excepto el parámetro obligatorio Identity) en los comandos anteriores, las nuevas directivas usarán los valores predeterminados para todas sus propiedades. Para crear directivas que usen otros valores de propiedades, basta con incluir el parámetro y el valor de parámetro correspondiente. Por ejemplo, el siguiente comando crea una directiva de archivado que permite el archivado de sesiones de mensajería instantánea internas: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Para crear una directiva de archivado que permita el archivado de sesiones de comunicaciones tanto internas como externas

Con la inclusión de varios parámetros se pueden cambiar varios valores de propiedad. Por ejemplo, este comando configura la nueva directiva de archivado de sesiones de mensajería instantánea internas y externas:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
