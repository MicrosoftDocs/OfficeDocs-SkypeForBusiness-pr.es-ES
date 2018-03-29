---
title: Configurar una ruta de voz de E9-1-1 en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Configurar rutas de voz E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 17614a4daedfdfe437a09858649972ca1c3e779d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server-2015"></a>Configurar una ruta de voz de E9-1-1 en Skype Empresarial Server 2015
 
Configurar rutas de voz E9-1-1 en Skype para Telefonía IP empresarial de Business Server. 
  
Para implementar E9-1-1, deberá configurar primero una ruta de voz para llamadas de emergencia. Para obtener más información acerca de cómo crear rutas de voz, consulte [crear o modificar una ruta de voz de Skype para el año 2015 Business](create-or-modify-a-voice-route.md). Puede definir más de una ruta si, por ejemplo, su implementación incluye un tronco SIP principal y otro secundario. 
  
> [!NOTE]
> Para incluir información de ubicación en un invitar E9-1-1, necesitará configurar el tronco SIP que conecta con el proveedor de servicios de E9-1-1 para enrutar las llamadas de emergencia a través de la puerta de enlace. Para ello, establezca el indicador EnablePIDFLOSupport en el cmdlet **Set-CsTrunkConfiguration** en True. El valor predeterminado de EnablePIDFLOSupport es False. Por ejemplo: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` no es necesario habilitar las ubicaciones de recepción para reserva pública conmutada puertas de enlace de teléfono red (conmutada PSTN) y las puertas de enlace de número de identificación de ubicación de emergencia (ELIN).
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>Para configurar una ruta de voz de E9-1-1

1. Inicie sesión en el equipo con una cuenta que sea miembro de los grupos RTCUniversalServerAdmins o del rol administrativo CsVoiceAdministrator.
    
2.  Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute el siguiente cmdlet para crear un nuevo registro de uso de RTC. 
    
    Debe ser el mismo nombre que vaya a usar para la configuración de **RTC** en la directiva de ubicación. Aunque la implementación va a tener varios registros de uso telefónico, en el siguiente ejemplo se agrega “Uso para emergencias” a la lista actual de usos de de RTC disponibles. Para obtener más información, consulte [Configurar directivas de voz, registros de uso PSTN y rutas de voz de Skype para negocios 2015](voice-and-pstn.md).
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. Ejecute el siguiente cmdlet para crear una nueva ruta de voz usando el registro de uso de RTC creado en el paso anterior.
    
    El patrón numérico debe coincidir con el patrón numérico que se usa en la configuración de **Cadena de marcado de emergencia** en la directiva de ubicación. Un signo "+" es necesaria porque Skype para empresas agrega "+" para llamadas de emergencia. "Co1-pstngateway-1" es el identificador del servicio de tronco SIP del proveedor de servicios E9-11. En el siguiente ejemplo se usa “EmergencyRoute” como nombre de la ruta de voz.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

   ```

5. Opcionalmente, para las conexiones de troncal SIP, recomendamos que ejecute el siguiente cmdlet para crear una ruta local para las llamadas que no son controladas por el tronco SIP del proveedor de servicios de E9-1-1. Esta ruta se usará en el caso de que la conexión con el proveedor de servicios de E9-11 no esté disponible. 
    
    En el siguiente ejemplo se da por hecho que el usuario tiene un uso “Local” en su directiva de voz.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


