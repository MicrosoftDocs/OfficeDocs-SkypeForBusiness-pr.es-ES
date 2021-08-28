---
title: Habilitar estacionamiento de llamadas para usuarios en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilitar usuarios para estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: bb83631b86171ad113a1009c5efc927b754411ba
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585682"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Habilitar estacionamiento de llamadas para usuarios en Skype Empresarial
 
Habilitar usuarios para estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
  
De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios. Los usuarios no pueden estacionar llamadas ni recuperar llamadas estacionadas hasta que estén habilitadas para el estacionamiento de llamadas en la directiva de voz.
  
Puede habilitar el estacionamiento de llamadas en el ámbito global, en el ámbito del sitio o en el ámbito de usuario. El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global. Si tiene varias directivas de voz, revise todas las directivas para habilitar el estacionamiento de llamadas, no solo la directiva global.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Para usar Skype Empresarial Server panel de control para habilitar el estacionamiento de llamadas para los usuarios

1. Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins**, o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Haga clic en la pestaña **Directiva de voz**.
    
5. Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.
    
6. En **Características de llamada**, seleccione **Habilitar Estacionamiento de llamadas**.
    
7. Haga clic en **Aceptar** para guardar la directiva de voz.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar cmdlets para habilitar el estacionamiento de llamadas para usuarios

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Ejecute: 
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Por ejemplo, para habilitar el estacionamiento de llamadas para la directiva de voz global predeterminada:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Consulte también



[Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial](voice-policy-and-pstn-usage-records.md)

