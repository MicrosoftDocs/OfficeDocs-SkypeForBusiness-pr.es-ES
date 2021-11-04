---
title: Configurar una ruta de voz E9-1-1 en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configure las rutas de voz de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: ae44eca22212de41a2c4edc9da31b88a112525b9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769708"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configurar una ruta de voz E9-1-1 en Skype Empresarial Server
 
Configure las rutas de voz de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial. 
  
Para implementar E9-1-1, deberá configurar primero una ruta de voz para llamadas de emergencia. Para obtener más información sobre cómo crear rutas de voz, vea [Create or modify a voice route in Skype Empresarial](create-or-modify-a-voice-route.md). Puede definir más de una ruta si, por ejemplo, su implementación incluye un tronco SIP principal y otro secundario. 
  
> [!NOTE]
> Para incluir información de ubicación en una INVITACIÓN de E9-1-1, debe configurar el tronco SIP que se conecta al proveedor de servicios E9-1-1 para enrutar llamadas de emergencia a través de la puerta de enlace. Para ello, establezca la marca EnablePIDFLOSupport en el cmdlet **Set-CsTrunkConfiguration** en True. El valor predeterminado de EnablePIDFLOSupport es False. Por ejemplo: no es necesario habilitar ubicaciones de recepción para puertas de enlace de red telefónica conmutada (RTC) y puertas de enlace de número de identificación de ubicación de `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` emergencia (ELIN).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Para configurar una ruta de voz de E9-1-1

1. Inicie sesión en el equipo con una cuenta que sea miembro de los grupos RTCUniversalServerAdmins o del rol administrativo CsVoiceAdministrator.
    
2.  Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Ejecute el siguiente cmdlet para crear un nuevo registro de uso de RTC. 
    
    Debe ser el mismo nombre que vaya a usar para la configuración de **RTC** en la directiva de ubicación. Aunque la implementación va a tener varios registros de uso telefónico, en el siguiente ejemplo se agrega “Uso para emergencias” a la lista actual de usos de de RTC disponibles. Para obtener más información, vea [Configure voice policies, PSTN usage records, and voice routes in Skype Empresarial](voice-and-pstn.md).
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Ejecute el siguiente cmdlet para crear una nueva ruta de voz usando el registro de uso de RTC creado en el paso anterior.
    
    El patrón numérico debe coincidir con el patrón numérico que se usa en la configuración de **Cadena de marcado de emergencia** en la directiva de ubicación. Se necesita un signo "+" porque Skype Empresarial agrega "+" a las llamadas de emergencia. "Co1-pstngateway-1" es el identificador del servicio de tronco SIP del proveedor de servicios E9-11. En el siguiente ejemplo se usa “EmergencyRoute” como nombre de la ruta de voz.
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. Opcionalmente, para las conexiones troncales SIP, se recomienda ejecutar el siguiente cmdlet para crear una ruta local para las llamadas que no están manejadas por el tronco SIP del proveedor de servicios E9-1-1. Esta ruta se usará en el caso de que la conexión con el proveedor de servicios de E9-11 no esté disponible. 
    
    En el siguiente ejemplo se da por hecho que el usuario tiene un uso “Local” en su directiva de voz.
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


