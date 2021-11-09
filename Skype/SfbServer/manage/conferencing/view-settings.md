---
title: Ver las opciones de configuración de reunión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Summary: Learn how to view meeting configuration settings in Skype Empresarial Server.'
ms.openlocfilehash: 4d55d4213b0eb7cbd89045960d87c05340520cbc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837632"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Ver las opciones de configuración de reunión en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo ver las opciones de configuración de reuniones en Skype Empresarial Server.
  
Puede ver las opciones de configuración de reuniones mediante Skype Empresarial Server Panel de control o mediante Skype Empresarial Server Shell de administración.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Ver las opciones de configuración de reunión mediante Skype Empresarial Server Panel de control
<a name="BKMK_ViewJoinSettings"> </a>

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia y,** a continuación, haga clic en **Configuración de reunión.**
    
4. En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.
    
5. En **Editar filtro de archivos,** active la casilla **Mostrar** detalles.
    
    **Editar configuración \<policy\> de reunión:** abre mostrando la configuración de la directiva seleccionada.
    
    Para obtener más información sobre cómo configurar las opciones, consulte [Create meeting configuration settings in Skype Empresarial Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Ver las opciones de configuración de reuniones mediante Skype Empresarial Server Shell de administración
<a name="BKMK_ViewJoinSettings"> </a>

Para ver información sobre todas las opciones de configuración de la reunión, use el cmdlet **Get-CsMeetingConfiguration:**
  
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

Para obtener más información, incluida una lista completa de parámetros, [vea Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
