---
title: Proceso de implementación del estacionamiento de llamadas en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Proceso de implementación y pasos para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 0ddc46c391d362fde922e682db0813ad1c0d72bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812360"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Proceso de implementación del estacionamiento de llamadas en Skype Empresarial
 
Proceso de implementación y pasos para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
  
El estacionamiento de llamadas permite a un usuario de Telefonía IP empresarial poner una llamada en espera desde un teléfono y, a continuación, recuperar la llamada más adelante marcando un número interno (conocido como órbita de estacionamiento de llamadas) desde cualquier teléfono.
  
Los componentes que usa el estacionamiento de llamadas se instalan y habilitan automáticamente en el servidor front-end o en el servidor Standard Edition al implementar Telefonía IP empresarial. Sin embargo, debe seguir los pasos siguientes para configurar el estacionamiento de llamadas antes de que esté disponible para los usuarios. 
  
**Proceso de implementación de estacionamiento de llamadas**

|**Fase**|**Pasos**|**Grupos y roles necesarios**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar los intervalos de órbitas del estacionamiento de llamadas en la tabla de órbitas  <br/> |Use el Panel de control de Skype Empresarial Server o el cmdlet **New-CSCallParkOrbit** para crear los intervalos de órbitas en la tabla de órbitas de estacionamiento de llamadas y asociarlos con el servicio de aplicación que hospeda la aplicación Estacionamiento de llamadas. <br/> **Nota:** Para una integración perfecta con los planes de marcado existentes, los intervalos de órbitas suelen configurarse como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de órbita. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Skype Empresarial](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configurar opciones de estacionamiento de llamadas  <br/> | Use el cmdlet **Set-CsCpsConfiguration** para configurar el estacionamiento de llamadas. Como mínimo, te recomendamos que configures la opción **OnTimeoutURI** para configurar el destino de reserva que se usará cuando se cierre el tiempo de espera de una llamada estacionada. También puede configurar las siguientes opciones: <br/>  **EnableMusicOnHold** (opcional), con la que se habilita o deshabilita las música en espera. <br/>  **MaxCallPickupAttempts** (opcional), que determina el número de veces que una llamada estacionada llama al teléfono de destino antes de reenviar la llamada al URI (identificador uniforme de recursos) de reserva. <br/>  **CallPickupTimeoutThreshold** (opcional), que determina la cantidad de tiempo que transcurre desde que una llamada se aparca hasta que vuelve a llamar al teléfono que recibió la llamada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurar las opciones de estacionamiento de llamadas en Skype Empresarial](configure-call-park-settings.md) <br/> |
|De manera opcional, personalice la música en espera  <br/> |Use el cmdlet **Set-CsCallParkServiceMusicOnHoldFile** para personalizar y cargar un archivo de audio en caso de que no desee usar la música en espera predeterminada. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizar la música en espera del estacionamiento de llamadas enSkype para empresas](customize-call-park-music-on-hold.md) <br/> |
|Configurar la directiva de voz para habilitar el estacionamiento de llamadas para los usuarios  <br/> |Use el Panel de control de Skype Empresarial Server o el cmdlet **Set-CSVoicePolicy** con la opción **EnableCallPark** para habilitar el estacionamiento de llamadas para los usuarios de la directiva de voz. <br/> De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios.  <br/> Si existen varias directivas de voz, asegúrese de que la propiedad EnableCallPark se ha definido en todas ellas, no solo en la predeterminada.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar el estacionamiento de llamadas para los usuarios de Skype Empresarial](enable-call-park-for-users.md) <br/> |
|Comprobar las reglas de normalización para el estacionamiento de llamadas  <br/> |Las órbitas de estacionamiento de llamadas no deben estar normalizadas. Por lo tanto, compruebe que las reglas de normalización no contemplan ninguno de los intervalos de órbitas existentes. Si procede, cree más reglas de normalización con objeto de evitar que las órbitas se normalicen.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial](verify-normalization-rules-for-call-park.md) <br/> |
|Comprobar la implementación del estacionamiento de llamadas  <br/> |Pruebe el estacionamiento y la recuperación de llamadas para asegurarse de que la configuración funciona según lo esperado.  <br/> |-  <br/> |[(Opcional) Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial](optional-verify-call-park-deployment.md) <br/> |
   

