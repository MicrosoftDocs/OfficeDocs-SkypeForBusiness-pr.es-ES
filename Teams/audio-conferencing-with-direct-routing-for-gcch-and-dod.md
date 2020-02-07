---
title: Audioconferencias con enrutamiento directo para GCCH y DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: Aprenda a usar las conferencias de audio con el enrutamiento directo en entornos GCCH y DoD.
ms.openlocfilehash: 8304d18777739b4667c0f47b9dee3e9f8f6dcc38
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825658"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconferencia con enrutamiento directo para GCC High y DoD

Las conferencias de audio con enrutamiento directo para GCC High y DoD permiten a los participantes unirse a reuniones de Teams en su organización GCC High o DoD con un dispositivo telefónico. Es posible que los participantes de la reunión prefieran usar un dispositivo telefónico para unirse a reuniones de Teams en escenarios, como cuando la conexión a Internet es limitada o cuando los usuarios viajan y no tienen acceso a los equipos. Los participantes pueden elegir unirse a un número de teléfono de acceso telefónico local para su organización o hacer que la reunión llame a su dispositivo telefónico.

Con las videoconferencias con enrutamiento directo para GCC High y DoD, su organización usa números propios como números de teléfono de acceso telefónico local y todos los accesos a la reunión a los dispositivos telefónicos se enrutan a través del enrutamiento directo. Para habilitar el servicio, las organizaciones necesitan configurar el enrutamiento directo y configurar los números de teléfono que se pueden usar como números de teléfono de acceso telefónico. El requisito de usar el enrutamiento directo es diferente del servicio de audioconferencia ofrecido a organizaciones que no son de GCC y de alta calidad y no de DoD en los que Microsoft proporciona los números de teléfono de acceso telefónico local.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Implementar audioconferencias con enrutamiento directo para GCC High y DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Paso 1: obtener conferencias de audio con enrutamiento directo para las licencias de GCC High o DoD 

Para usar audioconferencia en GCC High o DoD, su organización y los usuarios de su organización necesitan tener una conferencia de audio con una licencia de enrutamiento directo asignada. Estas son las licencias que necesita para habilitar las conferencias de audio con enrutamiento directo para GCC High o DoD.

- GCC High: una licencia de multiinquilino de audioconferencias-GCC High tenant para su organización y Conferencia de audio-GCC: licencias altas para sus usuarios.

- DoD: una licencia de conferencia de audio-espacio empresarial DoD para su organización y las licencias de audio y las licencias DoD de los usuarios.

Para habilitar el servicio, se necesita una licencia de inquilino y al menos una licencia de usuario. No puede habilitar el servicio solo con la licencia de inquilino o con licencias de usuario. Para obtener licencias de servicio para su inquilino y los usuarios de su organización, póngase en contacto con el equipo de su cuenta.

> [!IMPORTANT]
> Los usuarios no pueden habilitarse para las conferencias de audio con enrutamiento directo hasta que se configuran los números de teléfono de acceso telefónico. Le recomendamos que no asigne conferencias de audio con enrutamiento directo para las licencias de GCC High o DoD a los usuarios hasta que configure los números de teléfono de acceso telefónico local, como se describe en este artículo.

### <a name="step-2-set-up-direct-routing"></a>Paso 2: configurar el enrutamiento directo

Para configurar el enrutamiento directo, consulte los artículos siguientes:

- [Planear el enrutamiento directo](direct-routing-plan.md)

- [Configurar el enrutamiento directo](direct-routing-configure.md)

> [!NOTE]
> Cuando configure el enrutamiento directo, recuerde usar los FQDN y puertos de GCC altos o específicos de DoD que se describen en estos dos artículos.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Paso 3: configurar números de teléfono de acceso telefónico local

Los números de teléfono de acceso telefónico local son los números de teléfono que están asociados a su puente de audioconferencia. Los participantes usan estos números para unirse a las reuniones programadas por los usuarios de su organización. Estos números también se incluyen en las invitaciones a reuniones de los usuarios que programan las reuniones de su organización y en la página "buscar un número local".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definir números de teléfono de servicio en su espacio empresarial

Puede usar el cmdlet de PowerShell New-csHybridTelephoneNumber para definir los números de teléfono de servicio de su inquilino que se pueden usar para enrutar llamadas al servicio de audioconferencia a través de enrutamiento directo. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Por ejemplo:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Asignar los números de teléfono de servicio al puente de audioconferencia de su organización

Puede asignar números de teléfono de servicio al puente de audioconferencia de su organización mediante el cmdlet de PowerShell Register-csOnlineDialInConferencingServiceNumber.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Puede ver el identificador de su puente de audioconferencia con get-CsOnlineDialInConferencingBridge. Por ejemplo:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Paso 4: asignar audioconferencias con enrutamiento directo para las licencias de GCC High o DoD a los usuarios

Para asignar conferencias de audio con enrutamiento directo para las licencias GCC High o DoD para el usuario, consulte [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Paso 5: (opcional) ver una lista de números de conferencias de audio en Teams

Para ver la lista de números de audioconferencia de su organización, vaya a [ver una lista de los números de audioconferencia en Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Paso 6: (opcional) establecer los idiomas del operador automático para los números de acceso telefónico de las conferencias de audio de la organización

Para cambiar los idiomas de los números de acceso telefónico de las conferencias de audio de su organización, consulte [establecer los idiomas del operador automático para audioconferencia en Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Paso 7: (opcional) cambiar la configuración del puente de audioconferencia de su organización

Para cambiar la configuración del puente de conferencias de audio de su organización, consulte [cambiar la configuración de un puente de audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Paso 8: (opcional) establecer los números de teléfono incluidos en las invitaciones a reuniones de los usuarios de su organización

Para cambiar el conjunto de números de teléfono que se incluyen en las invitaciones a reuniones de los usuarios es su organización, consulte [configurar los números de teléfono incluidos en los invitados en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) .

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Capacidades de audioconferencia no compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD

Las siguientes son capacidades de audioconferencia que no son compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD:

- Notificaciones de entrada y salida que usan la grabación de nombres. Para las conferencias de audio con enrutamiento directo, las notificaciones de entrada y salida se reproducen como tonos en la reunión.

- Directivas de restricciones de llamadas salientes para audioconferencia. Los controles de nivel de usuario para restringir las llamadas salientes no son aplicables a las llamadas de llamada salientes de las reuniones dirigidas por enrutamiento directo.

- Deshabilite el uso de números gratuitos para el organizador específico de las reuniones. Los controles de nivel de usuario para restringir el uso de números gratuitos para unirse a las reuniones de su organización no son aplicables a las llamadas enrutadas por enrutamiento directo.

- Envío de correos electrónicos de notificación a los usuarios cuando cambia la configuración. Los correos electrónicos de notificación de audioconferencia no son compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD.
