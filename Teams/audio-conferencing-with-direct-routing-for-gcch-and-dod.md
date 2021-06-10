---
title: Audioconferencia con enrutamiento directo, GCCH y DoD
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
description: El administrador puede obtener información sobre cómo usar audioconferencias con enrutamiento directo en entornos GCCH y DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262625"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconferencia con enrutamiento directo para GCC High y DoD

Las audioconferencias con enrutamiento directo para GCC High y DoD permiten a los participantes unirse Teams reuniones en su organización de GCC High o DoD mediante un dispositivo telefónico. Es posible que los participantes de la reunión prefieran usar un dispositivo telefónico para unirse Teams reuniones en escenarios como cuando la conectividad a Internet es limitada o cuando los usuarios están de viaje y no tienen acceso Teams. Los participantes pueden elegir unirse a reuniones marcando en un número de teléfono de acceso telefónico local para su organización o haciendo que la reunión se llame a su dispositivo de teléfono.

Con las audioconferencias con enrutamiento directo para GCC High y DoD, su organización usa sus propios números como números de teléfono de acceso telefónico local y todas las llamadas de reunión a dispositivos telefónicos se enruta a través del enrutamiento directo. Para habilitar el servicio, las organizaciones deben configurar enrutamiento directo y configurar números de teléfono que se pueden usar como números de teléfono de acceso telefónico. El requisito de usar enrutamiento directo es diferente del servicio de audioconferencia que se ofrece GCC organizaciones que no son de nivel alto y no doD, donde Microsoft proporciona los números de teléfono de acceso telefónico local.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Implementar audioconferencias con enrutamiento directo para GCC alto y doD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Paso 1: Obtener audioconferencias con enrutamiento directo para GCC licencias de alta o doD 

Para usar las audioconferencias en GCC High o DoD, su organización y los usuarios de su organización necesitan tener asignada una audioconferencia con licencia de enrutamiento directo. Estas son las licencias que necesita para habilitar las audioconferencias con enrutamiento directo para GCC high o DoD.

- GCC Alta: Una audioconferencia : GCC licencia de inquilino alto para su organización y audioconferencias: GCC licencias high para los usuarios.

- DoD: Una audioconferencia: licencia de inquilino doD para su organización y audioconferencia: licencias doD para los usuarios.

Se requiere una licencia de inquilino y al menos una licencia de usuario para habilitar el servicio. No puede habilitar el servicio solo con la licencia de inquilino o solo con licencias de usuario. Para obtener licencias de servicio para su inquilino y los usuarios de su organización, póngase en contacto con el equipo de la cuenta.

> [!IMPORTANT]
> Los usuarios no se pueden habilitar para audioconferencias con enrutamiento directo hasta que se configuren los números de teléfono de acceso telefónico local. Le recomendamos que no asigne audioconferencias con enrutamiento directo para licencias de GCC High o DoD a los usuarios hasta que configure números de teléfono de acceso telefónico local como se describe en este artículo.  Si no sigue estas instrucciones, el teclado de marcado puede faltar por completo en el Teams cliente.

### <a name="step-2-set-up-direct-routing"></a>Paso 2: Configurar enrutamiento directo

Para configurar enrutamiento directo, vea los siguientes artículos:

- [Planear el enrutamiento directo](direct-routing-plan.md)

- [Configurar el enrutamiento directo](direct-routing-configure.md)

> [!NOTE]
> Al configurar enrutamiento directo, recuerde usar los FQDN y puertos GCC específicos de doD o alto que se describen en estos dos artículos.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Paso 3: Configurar números de teléfono de acceso telefónico telefónico

Los números de teléfono de acceso telefónico local son los números de teléfono asociados a su puente de audioconferencia. Estos números los usan los participantes para unirse a las reuniones programadas por los usuarios de su organización. Estos números también se incluyen en las invitaciones a reuniones de los usuarios que programan reuniones en su organización y en la página "Buscar un número local".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definir números de teléfono de servicio en el espacio empresarial

Puede usar el cmdlet de PowerShell New-csHybridTelephoneNumber para definir números de teléfono de servicio en el inquilino que se pueden usar para enrutar llamadas al servicio de audioconferencia mediante enrutamiento directo. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Por ejemplo:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Asignar los números de teléfono del servicio al puente de audioconferencias de su organización

Puede asignar números de teléfono de servicio al puente de conferencias de audio de su organización con el cmdlet de PowerShell Register-csOnlineDialInConferencingServiceNumber.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Puede ver el id. de su puente de audioconferencia con Get-CsOnlineDialInConferencingBridge. Por ejemplo:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Paso 4: Definir una directiva global de enrutamiento de voz para habilitar el enrutamiento de llamadas salientes desde reuniones

El enrutamiento de las llamadas salientes que se realizan a la RTC desde reuniones organizadas por usuarios de su organización se define mediante la directiva global de enrutamiento de voz de su organización. Si su organización tiene definida una directiva de enrutamiento de voz global, compruebe que la directiva de enrutamiento de voz global permite las llamadas salientes a la RTC que se espera que se inicien desde reuniones organizadas por los usuarios de su organización. Si su organización no tiene definida una directiva global de enrutamiento de voz, tendrá que definir una para habilitar el enrutamiento de llamadas salientes a la RTC desde reuniones organizadas por usuarios de su organización. Tenga en cuenta que la directiva global de enrutamiento de voz de su organización también se aplica a las llamadas uno a uno realizadas a la RTC por los usuarios de su organización. Si las llamadas uno a uno a la RTC están habilitadas para los usuarios de su organización, asegúrese de que la directiva global de enrutamiento de voz satisface las necesidades de su organización para ambos tipos de llamadas. 

> [!NOTE]
> Location-Based enrutamiento no está disponible en implementaciones Microsoft 365 Government Community Cloud (GCC) High o DoD. Al habilitar audioconferencias, compruebe que ningún usuario de audioconferencia en los entornos GCC High o DoD esté habilitado para Location-Based enrutamiento.

#### <a name="defining-a-global-voice-routing-policy"></a>Definir una directiva global de enrutamiento de voz

Una directiva de enrutamiento de voz global se puede definir definiendo un uso de RTC, una ruta de voz, una directiva de enrutamiento de voz y asignando la nueva directiva de enrutamiento de voz como la directiva global de enrutamiento de voz de su organización.

En los pasos siguientes se describe cómo definir una nueva directiva global de enrutamiento de voz para una organización sin una. Si su organización ya tiene definidas las directivas de enrutamiento de voz, compruebe que la configuración siguiente no entra en conflicto con las directivas de enrutamiento de voz existentes de su organización.

Para crear un nuevo uso de RTC en una sesión remota de PowerShell en Skype Empresarial Online, use el siguiente comando:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Para obtener más información, [vea Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).

Para crear una nueva ruta de voz, use el siguiente comando:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Al definir una nueva ruta de voz para su organización, especifique una o varias de las puertas de enlace RTC rtc en línea que se han definido para su organización durante la configuración de Enrutamiento directo. 

El patrón de número especifica qué llamadas se enrutarán a través de la lista especificada de puertas de enlace en función del número de teléfono de destino de la llamada. En el ejemplo anterior, las llamadas a cualquier destino del mundo coincidirán con la ruta de voz. Si desea restringir los números de teléfono que se pueden marcar desde las reuniones de los usuarios de su organización, puede cambiar el patrón de número para que la ruta de voz coincida solo con los patrones de número de los destinos permitidos. Tenga en cuenta que si no hay rutas de voz que coincidan con el patrón de número del número de teléfono de destino de una llamada determinada, la llamada no se dirigirá.

Para obtener más información, [vea New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).

Para crear una nueva directiva de enrutamiento de voz, use el siguiente comando:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Si se definen varios usos de RTC en la directiva de enrutamiento de voz, se evaluarán en el orden en que se definen. Se recomienda que los usos de RTC se definan en el orden de los más específicos a los más genéricos en términos de los patrones de número de las rutas de voz asociadas con los usos rtc. Por ejemplo, si se definió un uso de RTC para enrutar llamadas a Estados Unidos y se definió otro uso de RTC para enrutar llamadas a cualquier otra ubicación del mundo, el uso de RTC para llamadas a Estados Unidos debería aparecer en la directiva de enrutamiento de voz antes del uso de RTC para enrutar llamadas a cualquier otra ubicación del mundo.

Para obtener más información, [vea New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Para asignar la nueva ruta de voz a la directiva global de enrutamiento de voz de su organización, use el siguiente comando:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Para obtener más información, [vea Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Una vez definida la directiva de enrutamiento de voz global, las llamadas salientes realizadas desde reuniones organizadas por los usuarios de su organización se evaluarán en función de las rutas de voz asociadas a los usos rtc de la directiva global de enrutamiento de voz. Las llamadas salientes se enrutarán según la primera ruta de voz que coincida con el patrón de número del número de teléfono marcado.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Paso 5: Asignar audioconferencias con enrutamiento directo para GCC licencias De alta o doD a los usuarios

Para asignar audioconferencias con enrutamiento directo GCC licencias De alto o DoD a su usuario, vea Asignar licencias [a usuarios.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Paso 6: (Opcional) Vea una lista de números de audioconferencia en Teams

Para ver la lista de números de audioconferencia de su [organización,](see-a-list-of-audio-conferencing-numbers-in-teams.md)vaya a Ver una lista de números de audioconferencia en Microsoft Teams .

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Paso 7: (Opcional) Establecer idiomas de operador automático para los números de acceso telefónico local de audioconferencia de su organización

Para cambiar los idiomas de los números de acceso telefónico local de audioconferencia de su organización, vea Establecer idiomas de operador automático para [conferencias](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)de audio en Microsoft Teams .

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Paso 8: (opcional) Cambiar la configuración del puente de audioconferencia de su organización

Para cambiar la configuración del puente de audioconferencia de su organización, vea Cambiar la configuración de un puente [de audioconferencia.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Paso 9: (Opcional) Establecer los números de teléfono incluidos en las invitaciones de reunión de los usuarios de su organización

Para cambiar el conjunto de números de teléfono que se incluyen en las invitaciones de reunión de los usuarios es su organización, vea Establecer los números de teléfono incluidos en las [invitaciones en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Las capacidades de audioconferencia no son compatibles con audioconferencias con enrutamiento directo para GCC alta y doD

A continuación se descuido de las funcionalidades de audioconferencia que no son compatibles con audioconferencias con enrutamiento directo para GCC high y doD:

- Notificaciones de entrada y salida con la grabación de nombres. Para las audioconferencias con enrutamiento directo, las notificaciones de entrada y salida se reproducen en la reunión como tonos.

- Directivas de restricción de llamadas salientes para audioconferencias. Los controles de nivel de usuario para restringir las llamadas salientes no se aplican a las llamadas de acceso telefónico local de reuniones enrutadas a través del enrutamiento directo.

- Deshabilite el uso de números gratuitos para el organizador específico de las reuniones. Los controles de nivel de usuario para restringir el uso de números gratuitos para unirse a las reuniones de su organización no se aplican a las llamadas enrutadas a través del enrutamiento directo.

- Enviar correos electrónicos de notificación a los usuarios cuando cambie su configuración. Los correos electrónicos de notificación de audioconferencia no son compatibles con audioconferencias con enrutamiento directo para GCC alta y doD.