---
title: Ver opciones de configuración de reuniones en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Resumen: Conozca cómo ver los valores de configuración de Skype para Business Server 2015 de reunión.'
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Ver opciones de configuración de reuniones en Skype Empresarial Server 2015
 
**Resumen:** Para ver cómo satisfacer los valores de configuración de Skype para Business Server 2015.
  
Puede ver opciones de configuración de reunión utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor de Business.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Ver opciones de configuración de la reunión con Skype para Panel de Control de servidor empresarial
<a name="BKMK_ViewJoinSettings"> </a>

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
4. En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.
    
5. En **Editar filtro de archivo**, active la casilla **Mostrar detalles**.
    
    **Modificar la configuración de reunión - \<directiva\> ** se abre mostrando la configuración para la directiva seleccionada.
    
    Para obtener más información acerca de cómo configurar las opciones, consulte [crear opciones de configuración de Skype para Business Server 2015 de reunión](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Ver configuración de reuniones utilizando Skype para el Shell de administración de servidor empresarial
<a name="BKMK_ViewJoinSettings"> </a>

Para ver información sobre todas las configuraciones de reuniones, use el cmdlet **Get-CsMeetingConfiguration**:
  
```
Get-CsMeetingConfiguration
```

Este comando devolverá información similar a la siguiente:
  
```
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

```

Para obtener más información, incluida una lista completa de los parámetros, vea [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

