---
title: Audioconferencias con enrutamiento directo, GCCH y DoD
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
description: Administrador puede aprender a usar las conferencias de audio con enrutamiento directo en entornos GCCH y DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262497"
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
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
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


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Paso 4: definir una directiva de enrutamiento de voz global para habilitar el enrutamiento de llamadas salientes desde reuniones

El enrutamiento de las llamadas salientes que se realizan a la RTC desde las reuniones organizadas por los usuarios de su organización se define mediante la Directiva de enrutamiento de voz global de su organización. Si su organización tiene definida una directiva de enrutamiento de voz global, compruebe que la Directiva de enrutamiento de voz global permita las llamadas salientes a la RTC que se espera que se inicien desde las reuniones organizadas por los usuarios de su organización. Si su organización no tiene definida una directiva de enrutamiento de voz global, tendrá que definir una para habilitar el enrutamiento de llamadas salientes a la RTC desde las reuniones organizadas por los usuarios de su organización. Tenga en cuenta que la Directiva de enrutamiento de voz global de su organización también se aplica a las llamadas individuales hechas a la RTC por los usuarios de su organización. Si las llamadas de uno a uno a la RTC están habilitadas para los usuarios de su organización, asegúrese de que la Directiva de enrutamiento de voz global cumpla con las necesidades de su organización para ambos tipos de llamadas. 

> [!NOTE]
> El enrutamiento basado en la ubicación no está disponible en las implementaciones High o DoD de la comunidad de Microsoft 365 pública Cloud (GCC). Al habilitar la audioconferencia, compruebe que no hay usuarios de conferencias de audio en los entornos GCC High o DoD habilitados para el enrutamiento basado en la ubicación.

#### <a name="defining-a-global-voice-routing-policy"></a>Definir una directiva de enrutamiento de voz global

Se puede definir una directiva de enrutamiento de voz global definiendo un uso de RTC, una ruta de voz, una directiva de enrutamiento de voz y asignando la nueva Directiva de enrutamiento de voz como la Directiva de enrutamiento de voz global de su organización.

Los pasos siguientes describen cómo definir una nueva Directiva de enrutamiento de voz global para una organización sin una. Si su organización ya tiene directivas de enrutamiento de voz definidas, compruebe que la siguiente configuración no entra en conflicto con las directivas de enrutamiento de voz existentes de su organización.

Para crear un nuevo uso de RTC en una sesión de PowerShell remota en Skype empresarial online, use el siguiente comando:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Para obtener más información, consulte [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).

Para crear una nueva ruta de voz, use el siguiente comando:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Al definir una nueva ruta de voz para su organización, especifique una o varias de las puertas de enlace RTC en línea RTC que haya definido para su organización durante la configuración del enrutamiento directo. 

El patrón de número especifica qué llamadas se redirigirán a través de la lista especificada de puertas de enlace basándose en el número de teléfono de destino de la llamada. En el ejemplo anterior, las llamadas a cualquier destino del mundo coincidirán con la ruta de voz. Si desea restringir los números de teléfono que se pueden marcar desde las reuniones de los usuarios de su organización, puede cambiar el patrón de número para que la ruta de voz coincida solo con los patrones de número de los destinos permitidos. Ten en cuenta que si no hay rutas de voz que coincidan con el patrón de número del número de teléfono de destino de una llamada determinada, la llamada no se redirigirá.

Para obtener más información, consulte [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).

Para crear una nueva Directiva de enrutamiento de voz, use el siguiente comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Si se definen varios usos de RTC en la Directiva de enrutamiento de voz, se evaluarán en el orden en que se hayan definido. Se recomienda que los usos de RTC se definan en el orden más específico para el más genérico, en cuanto a los patrones de número de las rutas de voz asociadas con los usos de RTC. Por ejemplo, si se definió un uso de RTC para enrutar llamadas a los Estados Unidos y otro uso de RTC se definió para enrutar llamadas a cualquier otra ubicación del mundo, el uso de RTC para llamadas a Estados Unidos debe mostrarse en la Directiva de enrutamiento de voz antes del uso de la RTC para enrutar llamadas a cualquier otra ubicación del mundo.

Para obtener más información, consulte [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Para asignar la nueva ruta de voz a la Directiva de enrutamiento de voz global de su organización, use el siguiente comando:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Para obtener más información, consulte [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Una vez que se haya definido la Directiva de enrutamiento de voz global, cualquier llamada saliente realizada por los usuarios de su organización se evaluará con las rutas de voz asociadas a los usos de RTC de la Directiva de enrutamiento de voz global. Las llamadas salientes se redirigirán según la primera ruta de voz que coincida con el patrón de número del número de teléfono marcado.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Paso 5: asignar audioconferencias con enrutamiento directo para las licencias de GCC High o DoD a los usuarios

Para asignar conferencias de audio con enrutamiento directo para las licencias GCC High o DoD para el usuario, consulte [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Paso 6: (opcional) ver una lista de números de conferencias de audio en Teams

Para ver la lista de números de audioconferencia de su organización, vaya a [ver una lista de los números de audioconferencia en Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Paso 7: (opcional) establecer los idiomas del operador automático para los números de acceso telefónico de las conferencias de audio de la organización

Para cambiar los idiomas de los números de acceso telefónico de las conferencias de audio de su organización, consulte [establecer los idiomas del operador automático para audioconferencia en Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Paso 8: (opcional) cambiar la configuración del puente de audioconferencia de su organización

Para cambiar la configuración del puente de conferencias de audio de su organización, consulte [cambiar la configuración de un puente de audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Paso 9: (opcional) establecer los números de teléfono incluidos en las invitaciones a reuniones de los usuarios de su organización

Para cambiar el conjunto de números de teléfono que se incluyen en las invitaciones a reuniones de los usuarios es su organización, consulte [configurar los números de teléfono incluidos en los invitados en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Capacidades de audioconferencia no compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD

Las siguientes son capacidades de audioconferencia que no son compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD:

- Notificaciones de entrada y salida que usan la grabación de nombres. Para las conferencias de audio con enrutamiento directo, las notificaciones de entrada y salida se reproducen como tonos en la reunión.

- Directivas de restricciones de llamadas salientes para audioconferencia. Los controles de nivel de usuario para restringir las llamadas salientes no son aplicables a las llamadas de llamada salientes de las reuniones dirigidas por enrutamiento directo.

- Deshabilite el uso de números gratuitos para el organizador específico de las reuniones. Los controles de nivel de usuario para restringir el uso de números gratuitos para unirse a las reuniones de su organización no son aplicables a las llamadas enrutadas por enrutamiento directo.

- Envío de correos electrónicos de notificación a los usuarios cuando cambia la configuración. Los correos electrónicos de notificación de audioconferencia no son compatibles con las conferencias de audio con enrutamiento directo para GCC High y DoD.
