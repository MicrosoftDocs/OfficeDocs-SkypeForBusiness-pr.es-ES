---
title: Crear una nueva directiva de archivado en Skype Empresarial Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Resumen: obtenga información sobre cómo crear una nueva directiva de archivado para Skype Empresarial Server.'
ms.openlocfilehash: fe3a80708d3810a085f1814e6d16ff3cd4c6057c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095424"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Crear una nueva directiva de archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo crear una nueva directiva de archivado para Skype Empresarial Server.
  
Puede crear nuevas directivas de archivado mediante el Panel de control o mediante Windows PowerShell cmdlets.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Crear una nueva directiva de archivado mediante el Panel de control

Para crear una nueva directiva de archivado mediante el Panel de control:
  
1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna. 
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.
    
4. Haga clic en **Nuevo** y luego siga uno de estos procedimientos: 
    
   - Para crear una directiva de archivado de nivel de sitio, haga clic en Directiva de sitio y, a continuación, en Seleccionar un sitio, haga clic en el sitio al que se va **a** aplicar la directiva.
    
   - Para crear una directiva de archivado de nivel de usuario, haga clic en **Directiva de usuario**.
    
5. En **Directiva de archivado nueva**, haga lo siguiente:
    
   - En **Nombre**, especifique un nombre para la nueva directiva (por ejemplo, externalContoso).
    
   - En **Descripción**, proporcione información detallada sobre la función de la directiva (por ejemplo, directiva de archivado de usuarios externos para Contoso).
    
   - Para controlar el archivado de comunicaciones con usuarios internos, active o desactive la casilla **Archivar comunicaciones internas**.
    
   - Para controlar el archivado de comunicaciones externas, active o desactive la casilla **Archivar comunicaciones externas**.
    
6. Haga clic en **Confirmar**.
    
    > [!IMPORTANT]
    > La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva. Para obtener más información, [vea Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Crear una nueva directiva de archivado mediante Windows PowerShell

También puede crear nuevas directivas de archivado mediante el Windows PowerShell **cmdlet New-CsArchivingPolicy.** Para obtener más información, vea el tema de ayuda del cmdlet [New-CsArchivingPolicy.](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Para crear una nueva directiva de archivado en el nivel de sitio

Este comando crea una nueva directiva de archivado para el sitio Redmond:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Para crear una nueva directiva de archivado en el nivel por usuario

Para crear una nueva directiva de archivado en el nivel por usuario, simplemente especifique una identidad única al crear la directiva:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Para crear una nueva directiva de archivado que permita el archivado de sesiones de comunicación interna

Ya que no se especifican parámetros (excepto el parámetro obligatorio de identidad) en los comandos anteriores, las nuevas directivas usarán los valores predeterminados para todas sus propiedades. Para crear directivas que usen otros valores de propiedades, basta con incluir el parámetro y el valor de parámetro. Por ejemplo, el siguiente comando crea una directiva de archivado que permite el archivado de sesiones internas de mensajería instantánea: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Para crear una nueva directiva de archivado que permita el archivado de sesiones de comunicación internas y externas

Puede cambiar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando configura la nueva directiva para archivar sesiones de mensajería instantánea internas y externas:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```