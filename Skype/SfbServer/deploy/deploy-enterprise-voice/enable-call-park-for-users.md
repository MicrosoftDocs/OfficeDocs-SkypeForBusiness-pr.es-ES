---
title: Habilitar el parque de llamadas para los usuarios de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilitar a los usuarios para el parque de llamadas en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: c3ad2bcf70c7b175ba372ba2834e56209de9f664
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002560"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Habilitar el parque de llamadas para los usuarios de Skype empresarial
 
Habilitar a los usuarios para el parque de llamadas en Skype empresarial Server Enterprise Voice.
  
De forma predeterminada, el parque de llamadas está deshabilitado para todos los usuarios. Los usuarios no pueden detener llamadas ni recuperar llamadas estacionadas hasta que estén habilitadas para el parque de llamadas en la Directiva de voz.
  
Puede habilitar el parque de llamadas en el ámbito global o en el ámbito del sitio o ámbito de usuario. El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global. Si tiene varias directivas de voz, revise todas las directivas para habilitar el parque de llamadas, no solo la directiva global.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Para usar el panel de control de Skype empresarial Server para habilitar el parque de llamadas para los usuarios

1. Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Haga clic en la pestaña **Directiva de voz**.
    
5. Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.
    
6. En **Características de llamada**, seleccione **Habilitar estacionamiento de llamadas**.
    
7. Haga clic en **Aceptar** para guardar la directiva de voz.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar cmdlets para habilitar el parque de llamadas para los usuarios

1. Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Por ejemplo, para habilitar el parque de llamadas para la Directiva de voz global predeterminada:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Vea también



[Crear o modificar una directiva de voz y configurar los registros de uso de RTC en Skype empresarial](voice-policy-and-pstn-usage-records.md)

