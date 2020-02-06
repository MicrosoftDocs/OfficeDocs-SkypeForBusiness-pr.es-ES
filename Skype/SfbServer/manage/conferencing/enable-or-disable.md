---
title: Habilitar o deshabilitar las conferencias de acceso telefónico local en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumen: Aprenda a usar el panel de control o el shell de administración para habilitar o deshabilitar las conferencias de acceso telefónico local en Skype empresarial Server.'
ms.openlocfilehash: 8ce0fcfb4f785397075aa9d7b89b94eacb096167
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818561"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Habilitar o deshabilitar las conferencias de acceso telefónico local en Skype empresarial Server
 
**Resumen:** Aprenda a usar el panel de control o el shell de administración para habilitar o deshabilitar las conferencias de acceso telefónico local en Skype empresarial Server.
  
Puede habilitar las conferencias de acceso telefónico local con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Habilitar o deshabilitar las conferencias de acceso telefónico local con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
4. En la lista de directivas de conferencia, seleccione la directiva para la que desea habilitar la conferencia de acceso telefónico local, haga clic en **Editar** y luego en **Mostrar detalles**. 
    
5. Para permitir que los usuarios se unan a la reunión con acceso telefónico local, active la casilla **Habilitar conferencia de acceso telefónico local por RTC**. De forma predeterminada, los usuarios pueden acceder telefónicamente a las reuniones con la red telefónica conmutada (RTC).
    
6. Haga clic en **Confirmar**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Habilitar o deshabilitar las conferencias de acceso telefónico local con el shell de administración de Skype empresarial Server

Para habilitar o deshabilitar las conferencias de acceso telefónico local, use el cmdlet **Set-CsConferencingPolicy** con el parámetro EnableDialInConferencing como se muestra a continuación:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Para obtener más información, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

