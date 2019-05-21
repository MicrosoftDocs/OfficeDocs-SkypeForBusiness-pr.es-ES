---
title: Proceso de implementación para el parque de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Proceso de implementación y pasos de la llamada en el parque de Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 972a8cec2794afeebc0f5ab65d89291e78b7211e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289016"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Proceso de implementación para el parque de llamadas en Skype empresarial
 
Proceso de implementación y pasos de la llamada en el parque de Skype empresarial Server Enterprise Voice.
  
El parque de llamadas permite a un usuario de telefonía empresarial poner una llamada en espera desde un teléfono y, a continuación, recuperar la llamada más adelante marcando un número interno (denominado Parque de llamadas órbitas) desde cualquier teléfono.
  
Los componentes que llaman a los usos de estacionamiento se instalan y se habilitan automáticamente en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial. Sin embargo, debe seguir estos pasos para configurar el parque de llamadas antes de que esté disponible para los usuarios. 
  
**Proceso de implementación del estacionamiento de llamadas**

|**Fase**|**Pasos**|**Grupos y roles necesarios**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar los intervalos de órbitas del estacionamiento de llamadas en la tabla de órbitas  <br/> |Use el panel de control de Skype empresarial Server o el cmdlet **New-CSCallParkOrbit** para crear rangos de órbita en la tabla llamada de Parque orbital y asociarlos con el servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas. <br/> **Nota:** Para una integración perfecta con los planes de marcado existentes, los intervalos de órbita se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de órbita. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Crear o modificar un intervalo de llamada de Parque orbital en Skype empresarial](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configurar opciones de estacionamiento de llamadas  <br/> | Use el cmdlet **set-CsCpsConfiguration** para configurar la configuración de estacionamiento de llamada. Como mínimo, le recomendamos que configure la opción **OnTimeoutURI** para configurar el destino de la reserva que se usará cuando se agote el tiempo de espera de una llamada aparcada. También puede configurar las siguientes opciones: <br/>  **EnableMusicOnHold** (opcional), con la que se habilita o deshabilita la música en espera. <br/>  **MaxCallPickupAttempts** (opcional), que determina la cantidad de veces que una llamada estacionada llama al teléfono de destino antes de reenviar la llamada al URI (identificador uniforme de recursos) de reserva. <br/>  **CallPickupTimeoutThreshold** (opcional), que determina la cantidad de tiempo que transcurre desde que una llamada se aparca hasta que vuelve a llamar al teléfono que recibió la llamada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurar la configuración de estacionamiento de llamadas en Skype empresarial](configure-call-park-settings.md) <br/> |
|De manera opcional, personalice la música en espera  <br/> |Use el cmdlet **Set-CsCallParkServiceMusicOnHoldFile** para personalizar y cargar un archivo de audio en caso de que no desee usar la música en espera predeterminada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizar la música de estacionamiento de llamadas en espera de Skype empresarial](customize-call-park-music-on-hold.md) <br/> |
|Configurar la Directiva de voz para habilitar el parque de llamadas para los usuarios  <br/> |Use el panel de control de Skype empresarial Server o el cmdlet **set-CSVoicePolicy** con la opción **EnableCallPark** para habilitar el parque de llamadas para los usuarios en la Directiva de voz. <br/> De forma predeterminada, el parque de llamadas está deshabilitado para todos los usuarios.  <br/> Si existen varias directivas de voz, asegúrese de que la propiedad EnableCallPark se ha definido en todas ellas, no solo en la predeterminada.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar el parque de llamadas para los usuarios de Skype empresarial](enable-call-park-for-users.md) <br/> |
|Comprobar las reglas de normalización para el estacionamiento de llamadas  <br/> |Las órbitas de estacionamiento de llamadas no necesitan estar normalizadas. Por lo tanto, compruebe que las reglas de normalización no contemplan ninguno de los intervalos de órbitas existentes. Si es posible, cree más reglas de normalización con el objeto de evitar que las órbitas se normalicen.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Comprobar reglas de normalización para el parque de llamadas en Skype empresarial](verify-normalization-rules-for-call-park.md) <br/> |
|Verificar la implementación del parque de llamadas  <br/> |Pruebe el estacionamiento y la recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado.  <br/> |-  <br/> |[Faculta Comprobar la implementación del parque de llamadas en Skype empresarial](optional-verify-call-park-deployment.md) <br/> |
   

