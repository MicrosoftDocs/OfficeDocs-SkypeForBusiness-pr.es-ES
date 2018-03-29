---
title: Habilitar el estacionamiento de llamadas para los usuarios en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilitar a usuarios para retener llamadas en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 3af13e59541799a75c58f6e796bf07e7a978065e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a>Habilitar el estacionamiento de llamadas para los usuarios en Skype Empresarial 2015
 
Habilitar a usuarios para retener llamadas en Skype para Telefonía IP empresarial de Business Server.
  
De forma predeterminada, llamada Park está deshabilitado para todos los usuarios. Los usuarios no pueden aparcar llamadas o recuperar llamadas aparcadas hasta que están habilitados para el parque de llamada en la directiva de voz.
  
Puede habilitar la llamada Park en el ámbito global o en el ámbito del sitio o ámbito de usuario. El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global. Si dispone de varias directivas de voz, revise todas las directivas para habilitar llamada Park, no sólo la directiva global.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Usar Skype para Panel de Control de servidor empresarial para habilitar llamada Park para los usuarios

1. Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Haga clic en la pestaña **Directiva de voz**.
    
5. Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.
    
6. En **Características de llamada**, seleccione **Habilitar estacionamiento de llamadas**.
    
7. Haga clic en **Aceptar** para guardar la directiva de voz.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar Cmdlets para habilitar la llamada en espera para los usuarios

1. Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute:
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Por ejemplo, para habilitar el parque de llamada para la directiva predeterminada de voz global:
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Vea también

#### 

[Crear o modificar una directiva de voz y configurar registros de uso PSTN en Skype para negocios 2015](voice-policy-and-pstn-usage-records.md)

