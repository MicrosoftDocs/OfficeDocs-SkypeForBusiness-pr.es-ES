---
title: Audioconferencia con enrutamiento directo, M.C.CH y DoD
author: cichur
ms.author: v-cichur
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
description: El administrador puede obtener información sobre cómo usar audioconferencia con enrutamiento directo en entornos GCCH y DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 818b36e379532e361fd3991b002bc899156af056
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812920"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconferencia con enrutamiento directo para GCC High y DoD

Las audioconferencias con enrutamiento directo para GCC High y DoD permiten a los participantes unirse a las reuniones de Teams en su organización de GCC High o DoD con un dispositivo telefónico. Los participantes de la reunión podrían preferir usar un dispositivo telefónico para unirse a reuniones de Teams en situaciones como cuando la conectividad a Internet es limitada o cuando los usuarios están de viaje y no tienen acceso a Teams. Los participantes pueden elegir unirse a las reuniones mediante acceso telefónico local para su organización o haciendo que la reunión llame a su dispositivo de teléfono.

Con las audioconferencias con enrutamiento directo para GCC High y DoD, su organización usa sus propios números como números de teléfono de acceso telefónico local y todas las llamadas a las llamadas a los dispositivos telefónicos se enruta a través del enrutamiento directo. Para habilitar el servicio, las organizaciones necesitan configurar el enrutamiento directo y los números de teléfono que se pueden usar como números de teléfono de acceso telefónico. El requisito de usar enrutamiento directo es diferente del servicio de Audioconferencia que se ofrece a organizaciones que no son GCC High y que no son DoD donde Microsoft proporciona los números de teléfono de acceso telefónico local.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Implementar Audioconferencia con enrutamiento directo para GCC High y DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Paso 1: Obtener Audioconferencia con enrutamiento directo para licencias GCC High o DoD 

Para usar Audioconferencia en GCC High o DoD, su organización y los usuarios de su organización necesitan tener asignada una licencia de Audioconferencia con enrutamiento directo. Estas son las licencias que necesita para habilitar Audioconferencia con enrutamiento directo para GCC High o DoD.

- GCC High: Una licencia de Audioconferencia - Inquilino alto de GCC para su organización y Audioconferencia - licencias de GCC High para sus usuarios.

- DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.

Se requiere una licencia de espacio empresarial y al menos una licencia de usuario para habilitar el servicio. No puede habilitar el servicio solo con la licencia del espacio empresarial o solo con licencias de usuario. Para obtener licencias de servicio para su inquilino y los usuarios de su organización, póngase en contacto con el equipo de cuentas.

> [!IMPORTANT]
> No se puede habilitar a los usuarios para Audioconferencia con enrutamiento directo hasta que no se configuren los números de teléfono de acceso telefónico local. Le recomendamos que no asigne audioconferencias con enrutamiento directo para licencias GCC High o DoD a los usuarios hasta que configure los números de teléfono de acceso telefónico local como se describe en este artículo.

### <a name="step-2-set-up-direct-routing"></a>Paso 2: Configurar el enrutamiento directo

Para configurar enrutamiento directo, vea los artículos siguientes:

- [Planear el enrutamiento directo](direct-routing-plan.md)

- [Configurar el enrutamiento directo](direct-routing-configure.md)

> [!NOTE]
> Al configurar enrutamiento directo, recuerde usar los FQDN y puertos específicos de GCC High o DoD que se describen en estos dos artículos.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Paso 3: Configurar los números de teléfono de acceso telefónico

Los números de teléfono de acceso telefónico local son los que están asociados a su puente de Audioconferencia. Los participantes usan estos números para unirse a reuniones programadas por los usuarios de su organización. Estos números también se incluyen en las invitaciones a reuniones de los usuarios que programan reuniones en su organización y en la página "Buscar un número local".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definir números de teléfono de servicio en el inquilino

Puede usar el cmdlet de PowerShell New-csHybridTelephoneNumber para definir los números de teléfono de servicio del inquilino que se pueden usar para enrutar llamadas al servicio de Audioconferencia a través del enrutamiento directo. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Por ejemplo:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Asignar los números de teléfono de servicio al puente de audioconferencia de su organización

Puede asignar números de teléfono de servicio al puente de Audioconferencia de su organización mediante el cmdlet Register-csOnlineDialInConferencingServiceNumber PowerShell.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Puede ver el id. de su puente de Audioconferencia con Get-CsOnlineDialInConferencingBridge. Por ejemplo:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Paso 4: Definir una directiva global de enrutamiento de voz para habilitar el enrutamiento de llamadas salientes desde reuniones

El enrutamiento de las llamadas salientes que se realizan a la RTC desde reuniones organizadas por los usuarios de su organización se define en la directiva global de enrutamiento de voz de su organización. Si su organización tiene definida una directiva global de enrutamiento de voz, compruebe que la directiva global de enrutamiento de voz permite que las llamadas salientes a la RTC se inicien desde reuniones organizadas por los usuarios de su organización. Si su organización no tiene definida una directiva global de enrutamiento de voz, tendrá que definir una para habilitar el enrutamiento de llamadas salientes a la RTC desde reuniones organizadas por los usuarios de su organización. Tenga en cuenta que la directiva global de enrutamiento de voz de su organización también se aplica a las llamadas uno a uno realizadas a RTC por los usuarios de su organización. Si las llamadas uno a uno a la RTC están habilitadas para los usuarios de su organización, asegúrese de que la directiva global de enrutamiento de voz cumple las necesidades de su organización para ambos tipos de llamadas. 

> [!NOTE]
> Location-Based de correo electrónico no está disponible en las implementaciones de Microsoft 365 Government Community Cloud (GCC) High o DoD. Al habilitar Audioconferencia, compruebe que no haya usuarios de Audioconferencia en GCC High ni en los entornos doD habilitados para el Location-Based usuario.

#### <a name="defining-a-global-voice-routing-policy"></a>Definir una directiva global de enrutamiento de voz

Para definir una directiva global de enrutamiento de voz, defina un uso de RTC, una ruta de voz, una directiva de enrutamiento de voz y asigne la nueva directiva de enrutamiento de voz como directiva global de enrutamiento de voz de su organización.

En los pasos siguientes se describe cómo definir una nueva directiva global de enrutamiento de voz para una organización sin una. Si su organización ya tiene definidas directivas de enrutamiento de voz, compruebe que la siguiente configuración no entre en conflicto con las directivas de enrutamiento de voz existentes de la organización.

Para crear un nuevo uso de RTC en una sesión remota de PowerShell en Skype Empresarial Online, use el siguiente comando:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Para obtener información adicional, [vea Set-CsOnlinePstnUsage.](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)

Para crear una nueva ruta de voz, use el comando siguiente:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Al definir una nueva ruta de voz para su organización, especifique una o varias de las puertas de enlace RTC en línea definidas para su organización durante la configuración del enrutamiento directo. 

El patrón de números especifica las llamadas que se enrutarán a través de la lista especificada de puertas de enlace en función del número de teléfono de destino de la llamada. En el ejemplo anterior, las llamadas a cualquier destino del mundo coincidirán con la ruta de voz. Si desea restringir los números de teléfono que se pueden marcar desde las reuniones de usuarios de su organización, puede cambiar el patrón de números para que la ruta de voz coincida solo con los patrones de número de los destinos permitidos. Tenga en cuenta que si no hay rutas de voz que coincidan con el patrón de número del número de teléfono de destino de una llamada determinada, la llamada no se enruta.

Para obtener información adicional, [vea New-CsOnlineVoiceRoute.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)

Para crear una nueva directiva de enrutamiento de voz, use el comando siguiente:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Si se definen varios usos de RTC en la directiva de enrutamiento de voz, se evaluarán en el orden en que se definen. Se recomienda que los usos de RTC se definan en el orden más específico de los más genéricos en términos de los patrones de número de las rutas de voz asociadas con los usos de RTC. Por ejemplo, si se definió un uso de RTC para enrutar llamadas a Estados Unidos y se definió otro uso de RTC para enrutar llamadas a cualquier otra ubicación del mundo, el uso de RTC para llamadas a Estados Unidos debería aparecer en la directiva de enrutamiento de voz antes del uso de RTC para enrutar las llamadas a cualquier otra ubicación del mundo.

Para obtener más información, [consulte New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

Para asignar la nueva ruta de voz a la directiva global de enrutamiento de voz de su organización, use el siguiente comando:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Para obtener más información, [consulte Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

Una vez definida la directiva global de enrutamiento de voz, las llamadas salientes realizadas desde reuniones organizadas por los usuarios de su organización se evaluarán en función de las rutas de voz asociadas a los usos de RTC de la directiva global de enrutamiento de voz. Las llamadas salientes se enrutarán según la primera ruta de voz que coincida con el patrón de número del número de teléfono marcado.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Paso 5: Asignar Audioconferencia con enrutamiento directo para licencias GCC High o DoD a los usuarios

Para asignar audioconferencias con enrutamiento directo para licencias GCC High o DoD a un usuario, consulte [Asignar licencias a usuarios.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Paso 6: (Opcional) Ver una lista de números de Audioconferencia en Teams

Para ver la lista de números de Audioconferencia de su organización, vaya a Ver una lista de números de [Audioconferencia en Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Paso 7: (opcional) Establecer los idiomas del operador automático para los números de acceso telefónico de audioconferencia de su organización

Para cambiar los idiomas de los números de acceso telefónico local de Audioconferencia de su organización, vea Establecer los idiomas del operador automático para [Audioconferencia en Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Paso 8: (Opcional) Cambiar la configuración del puente de audioconferencia de su organización

Para cambiar la configuración del puente de audioconferencia de su organización, vea Cambiar la configuración de un puente de [Audioconferencia.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Paso 9: (opcional) Establecer los números de teléfono incluidos en las invitaciones de reunión de los usuarios de su organización

Para cambiar el conjunto de números de teléfono que se incluyen en las invitaciones de reunión de los usuarios es su organización, consulte Establecer los números de teléfono incluidos en las invitaciones [en Microsoft Teams.](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Capacidades de Audioconferencia no admitidas en Audioconferencia con enrutamiento directo para GCC High y DoD

Las siguientes son funciones de Audioconferencia que no son compatibles con Audioconferencia con enrutamiento directo para GCC High y DoD:

- Notificaciones de entrada y salida con la grabación de nombres. Para las audioconferencias con enrutamiento directo, las notificaciones de entrada y salida se reproducen en la reunión como tonos.

- Directivas de restricción de llamadas salientes para Audioconferencia. Los controles de nivel de usuario para restringir las llamadas salientes no se aplican a las llamadas salientes de reunión enrutadas a través del enrutamiento directo.

- Deshabilite el uso de números gratuitos para el organizador específico de las reuniones. Los controles a nivel de usuario para restringir el uso de números gratuitos para unirse a las reuniones de su organización no se aplican a las llamadas enrutadas a través del enrutamiento directo.

- Enviar correos electrónicos de notificación a los usuarios cuando cambie su configuración. Los correos electrónicos de notificación de Audioconferencia no son compatibles con Audioconferencia con enrutamiento directo para GCC High y DoD.
