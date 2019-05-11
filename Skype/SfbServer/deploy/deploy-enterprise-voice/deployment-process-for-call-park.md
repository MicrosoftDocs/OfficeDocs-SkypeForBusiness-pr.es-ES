---
title: Proceso de implementación de estacionamiento de llamadas en Skype para la empresa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Proceso de implementación y los pasos para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: b30f569ca44d4051638103e9a5d13280113916bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892611"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Proceso de implementación de estacionamiento de llamadas en Skype para la empresa
 
Proceso de implementación y los pasos para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
  
Estacionamiento de llamadas permite a un usuario de Enterprise Voice poner una llamada en espera desde un teléfono y, a continuación, recuperar la llamada más adelante marcando un número interno (conocido como una órbita de estacionamiento de llamadas) desde cualquier teléfono.
  
Los componentes que usa el estacionamiento de llamadas automáticamente instalados y habilitados en el servidor Front-End o Standard Edition al implementar Enterprise Voice. Sin embargo, debe usar los siguientes pasos para configurar el estacionamiento de llamadas antes de que esté disponible para los usuarios. 
  
**Proceso de implementación del estacionamiento de llamadas**

|**Fase**|**Pasos**|**Grupos y roles necesarios**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar los intervalos de órbitas del estacionamiento de llamadas en la tabla de órbitas  <br/> |Usar Skype para el Panel de Control de servidor empresarial o el cmdlet **New-CSCallParkOrbit** para crear los intervalos de Órbitas en la tabla de órbitas de estacionamiento de llamadas y asociar con el servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas. <br/> **Nota:** Para una integración perfecta con planes de marcado existentes, los intervalos de Órbitas se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de órbita. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Creación o modificación de un intervalo de órbitas de estacionamiento de llamadas en Skype para la empresa](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configurar opciones de estacionamiento de llamadas  <br/> | Use el cmdlet **Set-CsCpsConfiguration** para configurar las opciones de estacionamiento de llamadas. Como mínimo, se recomienda que configure la opción **OnTimeoutURI** para configurar el destino de reserva para usar cuando se agota el tiempo de espera de una llamada estacionada. También puede configurar las siguientes opciones: <br/>  **EnableMusicOnHold** (opcional), con la que se habilita o deshabilita la música en espera. <br/>  **MaxCallPickupAttempts** (opcional), que determina la cantidad de veces que una llamada estacionada llama al teléfono de destino antes de reenviar la llamada al URI (identificador uniforme de recursos) de reserva. <br/>  **CallPickupTimeoutThreshold** (opcional), que determina la cantidad de tiempo que transcurre desde que una llamada se aparca hasta que vuelve a llamar al teléfono que recibió la llamada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configuración del estacionamiento de llamadas en Skype para la empresa](configure-call-park-settings.md) <br/> |
|De manera opcional, personalice la música en espera  <br/> |Use el cmdlet **Set-CsCallParkServiceMusicOnHoldFile** para personalizar y cargar un archivo de audio en caso de que no desee usar la música en espera predeterminada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personaliza la música de estacionamiento de llamadas en espera inSkype para la empresa](customize-call-park-music-on-hold.md) <br/> |
|Configurar directiva de voz para habilitar estacionamiento de llamadas para los usuarios  <br/> |Usar Skype para el Panel de Control de servidor empresarial o el cmdlet **Set-CSVoicePolicy** con la opción **EnableCallPark** para habilitar estacionamiento de llamadas para los usuarios en la directiva de voz. <br/> De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios.  <br/> Si existen varias directivas de voz, asegúrese de que la propiedad EnableCallPark se ha definido en todas ellas, no solo en la predeterminada.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar estacionamiento de llamadas para los usuarios de Skype para la empresa](enable-call-park-for-users.md) <br/> |
|Comprobar las reglas de normalización para el estacionamiento de llamadas  <br/> |Las órbitas de estacionamiento de llamadas no necesitan estar normalizadas. Por lo tanto, compruebe que las reglas de normalización no contemplan ninguno de los intervalos de órbitas existentes. Si es posible, cree más reglas de normalización con el objeto de evitar que las órbitas se normalicen.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Compruebe las reglas de normalización para el estacionamiento de llamadas en Skype para la empresa](verify-normalization-rules-for-call-park.md) <br/> |
|Comprobar la implementación de estacionamiento de llamadas  <br/> |Pruebe el estacionamiento y la recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado.  <br/> |-  <br/> |[(Opcional) Comprobación de la implementación de estacionamiento de llamadas en Skype para la empresa](optional-verify-call-park-deployment.md) <br/> |
   

