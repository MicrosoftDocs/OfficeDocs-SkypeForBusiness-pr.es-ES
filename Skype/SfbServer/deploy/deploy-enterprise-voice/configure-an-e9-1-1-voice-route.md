---
title: Configurar una ruta de voz de E9-1-1 en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurar rutas de voz de E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 85259b6490b0f14d94d4d7c26f343d638911d909
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988751"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configurar una ruta de voz de E9-1-1 en Skype para Business Server
 
Configurar rutas de voz de E9-1-1 en Skype para Business Server Enterprise Voice. 
  
Para implementar E9-1-1, deberá configurar primero una ruta de voz para llamadas de emergencia. Para obtener información detallada sobre la creación de rutas de voz, vea [crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md). Puede definir más de una ruta si, por ejemplo, su implementación incluye un tronco SIP principal y otro secundario. 
  
> [!NOTE]
> Para incluir información de ubicación en un invitar E9-1-1, debe configurar el tronco SIP que se conecta al proveedor de servicios E9-1-1 para enrutar las llamadas de emergencia a través de la puerta de enlace. Para ello, establezca el indicador de EnablePIDFLOSupport en el cmdlet **Set-CsTrunkConfiguration** en True. El valor predeterminado de EnablePIDFLOSupport es False. Por ejemplo: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` no es necesario habilitar la recepción de ubicaciones para reserva conmutada puertas de enlace de teléfono RTC (red) y las puertas de enlace de número de identificación de ubicación de emergencia (ELIN).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Para configurar una ruta de voz de E9-1-1

1. Inicie sesión en el equipo con una cuenta que sea miembro de los grupos RTCUniversalServerAdmins o del rol administrativo CsVoiceAdministrator.
    
2.  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute el siguiente cmdlet para crear un nuevo registro de uso de RTC. 
    
    Debe ser el mismo nombre que vaya a usar para la configuración de **RTC** en la directiva de ubicación. Aunque la implementación va a tener varios registros de uso telefónico, en el siguiente ejemplo se agrega “Uso para emergencias” a la lista actual de usos de de RTC disponibles. Para obtener información detallada, vea [Configurar directivas de voz, registros de uso de RTC y rutas de voz de Skype para la empresa](voice-and-pstn.md).
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Ejecute el siguiente cmdlet para crear una nueva ruta de voz usando el registro de uso de RTC creado en el paso anterior.
    
    El patrón numérico debe coincidir con el patrón numérico que se usa en la configuración de **Cadena de marcado de emergencia** en la directiva de ubicación. Se necesita un signo "+" porque agrega Skype para la empresa "+" para las llamadas de emergencia. "Co1-pstngateway-1" es el identificador del servicio de tronco SIP del proveedor de servicios E9-11. En el siguiente ejemplo se usa “EmergencyRoute” como nombre de la ruta de voz.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. De forma opcional, para conexiones de enlace troncal SIP, se recomienda que ejecute el cmdlet siguiente para crear una ruta local para las llamadas que no se controlan mediante el tronco SIP del proveedor de servicios E9-1-1. Esta ruta se usará en el caso de que la conexión con el proveedor de servicios de E9-11 no esté disponible. 
    
    En el siguiente ejemplo se da por hecho que el usuario tiene un uso “Local” en su directiva de voz.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


