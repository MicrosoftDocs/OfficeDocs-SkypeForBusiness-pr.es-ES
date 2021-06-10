---
title: Conferencias en red para audioconferencias
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: A continuación se describen las funciones De vista previa abierta para audioconferencias en red.
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637842"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Abrir vista previa de conferencias en red para audioconferencias

La vista previa abierta de conferencias en red está disponible para todos los clientes. Las conferencias en red permiten a las organizaciones enviar llamadas de audioconferencia entrantes y salientes a números de acceso telefónico local de Microsoft mediante enrutamiento directo. Esta capacidad no está pensada para extender la compatibilidad de audioconferencias a números de acceso telefónico local de terceros. Las conferencias en red no son compatibles si se usan para enrutar las llamadas entrantes al servicio de audioconferencia a través de números de teléfono de acceso telefónico local de terceros o llamadas salientes a la RTC desde el puente de audioconferencia de Microsoft. 

En este artículo se describen los requisitos previos y los pasos de configuración necesarios para habilitar las conferencias en red para su organización.

> [!IMPORTANT]
> Las conferencias en red NO deben implementarse con ningún equipo de telefonía en india.
  
## <a name="prerequisites"></a>Requisitos previos

Antes de configurar conferencias en red, asegúrese de que su organización cumple los siguientes requisitos previos: 

- Asegúrese de que todos los usuarios de su organización que estén habilitados o que estén habilitados para las audioconferencias usen Teams para todas las reuniones. El enrutamiento de las llamadas de audioconferencia entrantes y salientes a través de conferencias en red solo es compatible con Teams reuniones.

- Asigne licencias de conferencias de audio a todos los usuarios que usen conferencias en red.

- Configure el servicio de audioconferencia. Para obtener más información, vea [Configurar audioconferencias para Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configure el controlador de borde de sesión (SBC) para enrutamiento directo. Para obtener más información, vea [Planear enrutamiento directo](direct-routing-plan.md) y Configurar enrutamiento [directo.](direct-routing-configure.md) 

  Si está configurando enrutamiento directo solo para los fines de las audioconferencias, solo necesita completar "Paso 1: Conectar su SBC" para conferencias en red.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Habilitar el enrutamiento de llamadas de acceso telefónico local a Las audioconferencias de Microsoft a través del enrutamiento directo 

Para enrutar las llamadas de acceso telefónico local realizadas por los usuarios locales al servicio de audioconferencia a través del enrutamiento directo, debe configurar reglas de enrutamiento adecuadas para los SBC y las Exchange(s) de sucursales privadas (PBX).

Debe configurar el equipamiento de telefonía de sus sitios para enrutar las llamadas a cualquier número de servicio del puente de conferencia de su organización a través de un tronco de enrutamiento directo.

Puede encontrar los números de servicio en el centro de administración de Teams en Reuniones **-> Puentes** de conferencia o mediante el cmdlet de PowerShell de Skype Empresarial Online Get-CsOnlineDialInConferencingBridge. Para obtener información adicional, vea una lista de números [de audioconferencia en Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Esta característica no está disponible para los usuarios con la licencia de audioconferencia de pago por minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Habilitar el enrutamiento de llamadas Teams llamadas de llamada de reunión mediante enrutamiento directo

Teams llamadas de acceso telefónico local de la reunión se inician desde una reunión de su organización a números RTC, incluidas las llamadas de llamada y las llamadas para que los nuevos participantes se unan a una reunión. 

Para habilitar Teams de acceso telefónico local de una reunión mediante enrutamiento directo a usuarios en red, debe crear y asignar una directiva de enrutamiento de audioconferencia denominada "OnlineAudioConferencingRoutingPolicy". 

La directiva OnlineAudioConferencingRoutingPolicy equivale a CsOnlineVoiceRoutingPolicy para llamadas RTC 1:1 a través del enrutamiento directo. La directiva OnlineAudioConferencingRoutingPolicy se puede administrar mediante los cmdlets siguientes:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Para obtener más información sobre el enrutamiento para enrutamiento directo, vea [Configurar enrutamiento de voz para enrutamiento directo.](direct-routing-voice-routing.md)


Para habilitar el enrutamiento de llamadas de llamada de reunión a través de Enrutamiento directo, debe: 

- Configurar directivas de enrutamiento de audioconferencias
- Configurar el enrutamiento en el equipo de telefonía de su organización
- (Opcional) Configurar un plan de marcado

Las llamadas de llamada de Teams reuniones vienen del número de servicio predeterminado en el puente de conferencia. Para obtener información adicional sobre el número de servicio predeterminado de su puente de audioconferencia, vea Cambiar los números de teléfono en el puente [de audioconferencia.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

### <a name="configure-audio-conferencing-routing-policies"></a>Configurar directivas de enrutamiento de audioconferencias

La directiva de enrutamiento de audioconferencia OnlineAudioConferencingRoutingPolicy determina qué llamadas de acceso telefónico saliente de reunión se enruta a los troncos de enrutamiento directo. Si está familiarizado con la directiva CsOnlineVoiceRoutingPolicy, esta directiva funciona de forma muy similar.

Para configurar las directivas de enrutamiento de audioconferencias, se necesitan los pasos siguientes:
1.  Crear usos de RTC
2.  Configurar rutas de voz
3.  Crear directivas de enrutamiento de voz de audioconferencia
4.  Asignar una directiva a los usuarios


#### <a name="create-pstn-usages"></a>Crear usos de RTC

Los usos RTC son colecciones de rutas de voz. Cuando se inicia una llamada de acceso telefónico local desde la reunión de un organizador determinado, las rutas de voz se usarán para determinar la ruta de enrutamiento de la llamada en función de los usos RTC asociados al usuario a través de la directiva de enrutamiento de voz del usuario.

Puede crear un uso rtc mediante el cmdlet "Set-CsOnlinePstnUsage". Por ejemplo:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurar rutas de voz

Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada en función del número de teléfono que se marca desde una Teams reunión. Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada determinada haciendo coincidir el número de teléfono marcado desde una reunión de Teams con un patrón regex. Al crear una ruta de voz, la ruta debe estar asociada a uno o varios usos de RTC.

Puede crear una ruta de voz y definir el regex y las puertas de enlace que se asociarán a la ruta de voz con el cmdlet "New-CsOnlineVoiceRoute". Por ejemplo:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Crear directivas de enrutamiento de voz de audioconferencia

Las directivas de enrutamiento de voz de audioconferencia determinan las posibles rutas que se pueden usar para enrutar una llamada procedente de las reuniones de un organizador en función del número de teléfono de destino de la llamada de acceso telefónico local de la reunión. Las directivas de enrutamiento de voz de audioconferencia están asociadas a uno o varios usos de RTC, que a su vez determinan las posibles rutas que se van a intentar usar para las llamadas de acceso telefónico local de reunión de los organizadores asociados a la directiva.

Puede crear una directiva de enrutamiento de voz de audioconferencia mediante el cmdlet "New- CsOnlineAudioConferencingRoutingPolicy". Por ejemplo:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Una vez asignada la directiva a un usuario y cuando se inicia una llamada de acceso telefónico local desde una de las reuniones del usuario, se evaluarán las rutas de voz en los usos rtc asociados al organizador a través de la directiva de enrutamiento de voz del usuario. Si el destino de la llamada de acceso telefónico local de la reunión coincide con un regex en una de las rutas de voz asociadas al organizador, la llamada de acceso telefónico local de la reunión se dirigirá a la puerta de enlace RTC definida en la ruta de voz. Si el destino de la llamada de salida de reunión no coincide con ninguna de las rutas de voz asociadas al organizador, Microsoft dirigirá la llamada de llamada de salida de la reunión.

#### <a name="assign-a-policy-to-your-users"></a>Asignar una directiva a los usuarios

Una vez definidas las directivas de enrutamiento de audioconferencias, ahora puede asignarlas a los usuarios. Una vez asignadas las directivas, se evaluarán las llamadas de acceso telefónico local de la reunión para determinar su ruta de enrutamiento. Las directivas de enrutamiento de audioconferencia siempre se evalúan en función del organizador de la reunión, independientemente del usuario de la reunión que inicia una llamada de acceso telefónico local de la reunión.

Puede asignar una directiva de enrutamiento de voz de audioconferencia a un usuario mediante el cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Por ejemplo:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurar el enrutamiento en el equipo de telefonía de su organización

En el equipo de telefonía de su organización, debe asegurarse de que las llamadas de acceso telefónico local de la reunión enrutadas a través del enrutamiento directo se enrutan al destino previsto en la red.


### <a name="optional-configure-a-dial-plan"></a>(Opcional) Configurar un plan de marcado

Un plan de marcado es un conjunto de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (normalmente, E.164) para fines de autorización de llamadas y enrutamiento de llamadas.

De forma predeterminada, Teams usuarios pueden llamar a números RTC en formato E.164, es decir, + \<country code\> \<number\> . Sin embargo, los planes de marcado se pueden usar para permitir a los usuarios marcar números de teléfono en otros formatos, por ejemplo, extensiones de 4 dígitos.

Si desea habilitar la marcación basada en extensiones a través de conferencias en red, puede configurar los planes de marcado para que coincidan con el patrón de marcado de extensión con los intervalos de número de teléfono del número de teléfono de su organización. Para configurar planes de marcado, vea [Crear y administrar planes de marcado.](create-and-manage-dial-plans.md)


## <a name="known-issues-in-open-preview"></a>Problemas conocidos en Open Preview

A continuación se muestra una lista de los problemas conocidos que están presentes actualmente en la versión de Open Preview de las conferencias en red. Microsoft está trabajando para solucionar estos problemas.

| Problema | Solución alternativa |
| :--- | :--- |
| Las llamadas de acceso telefónico local con identificadores de llamadas anónimos u ocultos que se enruta a través de conferencias en red no se pueden conectar a la reunión. | Si es posible, establezca una configuración en su PBX o SBC para enviar siempre un identificador de llamada para las llamadas enrutadas a través de conferencias en red.|
| En algunos casos, el mensaje de bienvenida que se reproduce para los usuarios al llamar al servicio ("Bienvenido al servicio de audioconferencia...") se trunca y los usuarios no escuchan la palabra "Bienvenido".| No hay soluciones alternativas para este problema en este momento. |




## <a name="related-topics"></a>Temas relacionados


