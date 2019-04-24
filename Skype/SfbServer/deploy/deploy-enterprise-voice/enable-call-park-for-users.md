---
title: Habilitar estacionamiento de llamadas para los usuarios de Skype para la empresa
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilitar a los usuarios para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 98b02294beb633e5d9a0147fcce7257a4497753d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212512"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Habilitar estacionamiento de llamadas para los usuarios de Skype para la empresa
 
Habilitar a los usuarios para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
  
De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios. Los usuarios no se pueden estacionar llamadas ni recuperar llamadas estacionadas mientras estén habilitados para estacionamiento de llamadas en la directiva de voz.
  
Puede habilitar estacionamiento de llamadas en el ámbito global o en el ámbito de sitio o el ámbito de usuario. El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global. Si tiene varias directivas de voz, revise todas las directivas para habilitar estacionamiento de llamadas, no sólo la directiva global.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Usar Skype para el Panel de Control de servidor empresarial para habilitar estacionamiento de llamadas para los usuarios

1. Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Haga clic en la pestaña **Directiva de voz**.
    
5. Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.
    
6. En **Características de llamada**, seleccione **Habilitar estacionamiento de llamadas**.
    
7. Haga clic en **Aceptar** para guardar la directiva de voz.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar Cmdlets para habilitar estacionamiento de llamadas para los usuarios

1. Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute:
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Por ejemplo, para habilitar estacionamiento de llamadas para la directiva de voz global predeterminada:
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Vea también



[Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa](voice-policy-and-pstn-usage-records.md)

