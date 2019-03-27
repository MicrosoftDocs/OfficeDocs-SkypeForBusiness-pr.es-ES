---
title: Ver opciones de configuración en Skype para Business Server de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumen: Obtenga información sobre cómo ver los valores de configuración de Skype para Business Server de la reunión.'
ms.openlocfilehash: d7ef617050b31bd85732ee4a30d0faaed41f50d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899401"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Ver opciones de configuración en Skype para Business Server de reuniones
 
**Resumen:** Obtenga información sobre cómo ver los valores de configuración de Skype para Business Server de la reunión.
  
Puede ver opciones de configuración de la reunión mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Ver opciones de configuración de la reunión mediante el uso de Skype para el Panel de Control de servidor empresarial
<a name="BKMK_ViewJoinSettings"> </a>

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.
    
5. En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.
    
    **Editar configuración de reunión - \<directiva\> ** se abre mostrando la configuración para la directiva seleccionada.
    
    Para obtener información detallada acerca de cómo configurar la configuración, vea [crear una configuración de Skype para Business Server de reunión](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Ver opciones de configuración de la reunión mediante el uso de Skype para Shell de administración de servidor empresarial
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

Para obtener más información, incluida una lista completa de los parámetros, vea [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

