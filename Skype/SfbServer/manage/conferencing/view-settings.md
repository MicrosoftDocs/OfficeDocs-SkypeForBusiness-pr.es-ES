---
title: Ver la configuración de la reunión en Skype empresarial Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumen: Obtenga información sobre cómo ver la configuración de la reunión en Skype empresarial Server.'
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818461"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Ver la configuración de la reunión en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo ver la configuración de la reunión en Skype empresarial Server.
  
Puede ver la configuración de la reunión con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Ver la configuración de la reunión con el panel de control de Skype empresarial Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.
    
5. En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.
    
    **Editar la configuración de \<la\> reunión:** se abre la Directiva que muestra la configuración de la Directiva seleccionada.
    
    Para obtener más información sobre cómo configurar las opciones, consulte [crear opciones de configuración de reunión en Skype empresarial Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Ver la configuración de la reunión mediante el shell de administración de Skype empresarial Server
<a name="BKMK_ViewJoinSettings"> </a>

Para ver información sobre todas las configuraciones de reuniones, use el cmdlet **Get-CsMeetingConfiguration**:
  
```
Get-CsMeetingConfiguration
```

Este comando devolverá información similar a la siguiente:
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

Para obtener más información, incluida una lista completa de parámetros, vea [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

