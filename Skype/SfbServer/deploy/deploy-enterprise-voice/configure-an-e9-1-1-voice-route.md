---
title: Configurar una ruta de voz E9-1-1 en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configure las rutas de voz E9-1-1 en Skype empresarial Enterprise Voice.
ms.openlocfilehash: ca45ac924ce987113e5b88729dc074b112668caf
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768153"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Configurar una ruta de voz E9-1-1 en Skype empresarial Server
 
Configure las rutas de voz E9-1-1 en Skype empresarial Enterprise Voice. 
  
Para implementar E9-1-1, deberá configurar primero una ruta de voz para llamadas de emergencia. Para obtener detalles sobre la creación de rutas de voz, consulte [crear o modificar una ruta de voz en Skype empresarial](create-or-modify-a-voice-route.md). Puede definir más de una ruta si, por ejemplo, su implementación incluye un tronco SIP principal y otro secundario. 
  
> [!NOTE]
> Para incluir información de ubicación en una invitación E9-1-1, necesita configurar el tronco del SIP que se conecta al proveedor de servicios E9-1-1 para enrutar las llamadas de emergencia a través de la puerta de enlace. Para ello, establezca la marca EnablePIDFLOSupport en el cmdlet **set-CsTrunkConfiguration** en true. El valor predeterminado de EnablePIDFLOSupport es false. Por ejemplo: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` no es necesario habilitar ubicaciones de recepción de puertas de enlace de red de telefonía pública conmutada (RTC) y puertas de enlace de número de identificación de ubicación de emergencia (Elin).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Para configurar una ruta de voz de E9-1-1

1. Inicie sesión en el equipo con una cuenta que sea miembro de los grupos RTCUniversalServerAdmins o del rol administrativo CsVoiceAdministrator.
    
2.  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute el siguiente cmdlet para crear un nuevo registro de uso de RTC. 
    
    Debe ser el mismo nombre que vaya a usar para la configuración de **RTC** en la directiva de ubicación. Aunque la implementación va a tener varios registros de uso telefónico, en el siguiente ejemplo se agrega “Uso para emergencias” a la lista actual de usos de de RTC disponibles. Para obtener más información, vea [configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype empresarial](voice-and-pstn.md).
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Ejecute el siguiente cmdlet para crear una nueva ruta de voz usando el registro de uso de RTC creado en el paso anterior.
    
    El patrón numérico debe coincidir con el patrón numérico que se usa en la configuración de **Cadena de marcado de emergencia** en la directiva de ubicación. Es necesario un signo "+" porque Skype para empresas agrega "+" a las llamadas de emergencia. "Co1-pstngateway-1" es el identificador del servicio de tronco SIP del proveedor de servicios E9-11. En el siguiente ejemplo se usa “EmergencyRoute” como nombre de la ruta de voz.
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. De manera opcional, para conexiones de troncales SIP, le recomendamos que ejecute el siguiente cmdlet para crear una ruta local para las llamadas no gestionadas por el protocolo de enlace SIP del proveedor de servicios E9-1-1. Esta ruta se usará en el caso de que la conexión con el proveedor de servicios de E9-11 no esté disponible. 
    
    En el siguiente ejemplo se da por hecho que el usuario tiene un uso “Local” en su directiva de voz.
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


