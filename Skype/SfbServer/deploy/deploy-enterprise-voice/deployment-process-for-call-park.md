---
title: Proceso de implementación del estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Proceso de implementación y los pasos para el parque de llamada en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 9d5df92a95e52612c3b0dee005072b10de5c244c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-call-park-in-skype-for-business-2015"></a>Proceso de implementación del estacionamiento de llamadas en Skype Empresarial 2015
 
Proceso de implementación y los pasos para el parque de llamada en Skype para Telefonía IP empresarial de Business Server.
  
Parque de llamada permite a un usuario de Telefonía IP empresarial poner una llamada en espera desde un teléfono y, a continuación, recuperar la llamada más tarde marcando un número interno (conocidas como una órbita llamada Park) desde cualquier teléfono.
  
Los componentes que usa la llamada Park automáticamente instalados y habilitados en el servidor Standard Edition o de servidor Front-End al implementar la Telefonía IP empresarial. Sin embargo, debe utilizar los pasos siguientes para configurar el parque de llamada antes de que esté disponible para los usuarios. 
  
**Proceso de implementación del parque de llamada**

|**Fase**|**Pasos**|**Roles y grupos requeridos**|**Documentación sobre la implementación**|
|:-----|:-----|:-----|:-----|
|Configurar los intervalos de órbitas del estacionamiento de llamadas en la tabla de órbitas  <br/> |Usar Skype para Panel de Control de servidor de negocios o el cmdlet **New-CSCallParkOrbit** para crear los rangos de la órbita de la tabla de llamada park órbita y asociarlos con el servicio de aplicación que hospeda la aplicación llamada Park. <br/> **Nota:** Para la integración transparente con los planes de marcado existentes, orbital rangos se configuran normalmente como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de órbita. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Crear o modificar un rango de órbita llamada Park en Skype para negocios 2015](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configurar opciones de estacionamiento de llamadas  <br/> | Utilice el cmdlet **Set-CsCpsConfiguration** para configurar las opciones de llamada Park. Como mínimo, se recomienda que configure la opción de **OnTimeoutURI** para configurar el destino reserva a utilizar cuando se agota el tiempo de espera de una llamada aparcada. También puede configurar las siguientes opciones: <br/>  (Opcional) **EnableMusicOnHold** para activar o desactivar la música en espera. <br/>  (Opcional) **MaxCallPickupAttempts** para determinar el número de veces que un timbres de llamada aparcadas al teléfono responde antes de reenviar la llamada a la reserva Uniform Resource Identifier (URI). <br/>  (Opcional) **CallPickupTimeoutThreshold** para determinar la cantidad de tiempo que transcurre después de una llamada ha sido estacionada antes de que suena el teléfono donde se respondió la llamada a. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurar los parámetros de llamada Park en Skype para negocios 2015](configure-call-park-settings.md) <br/> |
|De manera opcional, personalice la música en espera  <br/> |Utilice el cmdlet **Set-CsCallParkServiceMusicOnHoldFile** para personalizar y cargar un archivo de audio, si no desea utilizar la música de forma predeterminada en suspensión. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizar música llamada Park en suspensión inSkype de negocios 2015](customize-call-park-music-on-hold.md) <br/> |
|Configurar directiva de voz para activar llamada Park para usuarios  <br/> |Usar Skype para Panel de Control de servidor de negocios o el cmdlet **Set-CSVoicePolicy** con la opción **EnableCallPark** para habilitar parque de llamada para los usuarios de la directiva de voz. <br/> De forma predeterminada, llamada Park está deshabilitado para todos los usuarios.  <br/> Si existen varias directivas de voz, asegúrese de que la propiedad EnableCallPark se ha definido en todas ellas, no solo en la predeterminada.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Habilitar llamada parque de usuarios de Skype para negocios 2015](enable-call-park-for-users.md) <br/> |
|Comprobar las reglas de normalización para el estacionamiento de llamadas  <br/> |Las órbitas de estacionamiento de llamadas no necesitan estar normalizadas. Por lo tanto, compruebe que las reglas de normalización no contemplan ninguno de los intervalos de órbitas existentes. Si es posible, cree más reglas de normalización con el objeto de evitar que las órbitas se normalicen.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Compruebe las reglas de normalización para el parque de llamada en Skype para negocios 2015](verify-normalization-rules-for-call-park.md) <br/> |
|Comprobar la distribución de llamada Park  <br/> |Pruebe el estacionamiento y la recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado.  <br/> |-  <br/> |[(Opcional) Comprobar la implementación del parque llamada en Skype para negocios 2015](optional-verify-call-park-deployment.md) <br/> |
   

