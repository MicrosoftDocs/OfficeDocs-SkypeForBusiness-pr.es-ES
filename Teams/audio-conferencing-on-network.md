---
title: Conferencias en red para conferencias de audio
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
description: A continuación se describe la funcionalidad de Open Preview para las conferencias de audio en red.
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031866"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Abrir vista previa de conferencias en red para conferencias de audio

La vista previa abierta de las conferencias en red está disponible para todos los clientes. Conferencias en red permite a las organizaciones enviar llamadas de voz de audio entrantes y salientes a números de acceso telefónico de Microsoft mediante enrutamiento directo. Esta funcionalidad no está pensada para extender el soporte técnico de las audioconferencias a los números de acceso telefónico de terceros. Las conferencias en red no son compatibles si se usa para enrutar llamadas entrantes al servicio de audioconferencia a través de números de teléfono de acceso telefónico local de terceros.

En este artículo se describen los requisitos previos y los pasos de configuración necesarios para habilitar las conferencias en la red de su organización.

> [!IMPORTANT]
> Las conferencias en red no deben implementarse con ningún equipo de telefonía en la India.
  
## <a name="prerequisites"></a>Requisitos previos

Antes de configurar las conferencias en red, asegúrese de que su organización cumple los siguientes requisitos previos: 

- Asegúrese de que todos los usuarios de su organización que estén habilitados o que se habilitarán para las conferencias de audio usen Teams para todas las reuniones. El enrutamiento de llamadas de conferencia de audio entrantes y salientes a través de conferencias en red solo es compatible con las reuniones de Teams.

- Asigne licencias de audioconferencia a todos los usuarios que vayan a usar conferencias en la red.

- Configure el servicio audioconferencia. Para obtener más información, consulte [configurar audioconferencias para Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configure el controlador de borde de sesión (SBC) para el enrutamiento directo. Para obtener más información, consulte [planear el enrutamiento directo](direct-routing-plan.md) y [configurar el enrutamiento directo](direct-routing-configure.md). 

  Si está configurando el enrutamiento directo solo para fines de audioconferencia, solo necesita completar el paso 1: conectar su SBC "para las conferencias en red.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Habilitar el enrutamiento de llamadas de acceso telefónico para conferencias de audio de Microsoft a través del enrutamiento directo 

Para enrutar las llamadas de acceso telefónico realizadas por los usuarios locales en el servicio de audioconferencia mediante enrutamiento directo, debe configurar las reglas de enrutamiento apropiadas para sus PBX y las Exchange (s) privadas (PBX).

Debe configurar el equipo de telefonía de sus sitios para que enrute las llamadas a cualquier número de servicio del puente de conferencia de su organización a través de un tronco de enrutamiento directo.

Puede encontrar los números de servicio en el centro de administración de Teams en **reuniones-> puentes de conferencia** o mediante el cmdlet de PowerShell de Skype empresarial online Get-CsOnlineDialInConferencingBridge. Para obtener más información, consulte una lista de [números de audioconferencia en Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Esta característica no está disponible para los usuarios con la licencia de conferencia de audio por minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Habilitar el enrutamiento de las llamadas de llamada de reunión de los equipos mediante enrutamiento directo

Los equipos que reúnen las llamadas de acceso telefónico se inician desde una reunión de su organización a números RTC, incluidas las llamadas y llamadas en persona, y las llamadas para incluir a nuevos participantes en una reunión. 

Para habilitar a los equipos a hacer reuniones de acceso telefónico saliente a través del enrutamiento directo a los usuarios de la red, debe crear y asignar una directiva de enrutamiento de audioconferencia denominada "OnlineAudioConferencingRoutingPolicy". 

La Directiva OnlineAudioConferencingRoutingPolicy es equivalente a la CsOnlineVoiceRoutingPolicy para llamadas RTC de 1:1 a través de enrutamiento directo. La Directiva OnlineAudioConferencingRoutingPolicy se puede administrar con los siguientes cmdlets:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Para obtener más información sobre el enrutamiento para enrutamiento directo, consulte [configurar el enrutamiento de voz para enrutamiento directo](direct-routing-voice-routing.md).


Para habilitar el enrutamiento de llamadas de acceso telefónico de la reunión a través del enrutamiento directo, debe hacer lo siguiente: 

- Configurar directivas de enrutamiento de audioconferencia
- Configurar el enrutamiento en el equipo de telefonía de su organización
- Faculta Configurar un plan de marcado

Las llamadas de acceso telefónico de las reuniones de Teams provienen del número de servicio predeterminado del puente de conferencia. Para obtener más información sobre el número de servicio predeterminado de su puente de audioconferencia, consulte [cambiar los números de teléfono en el puente de audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configurar directivas de enrutamiento de audioconferencia

La Directiva de enrutamiento de audioconferencia OnlineAudioConferencingRoutingPolicy determina qué llamadas de llamada salientes de la reunión se enrutan a troncos de enrutamiento directos. Si está familiarizado con la Directiva CsOnlineVoiceRoutingPolicy, esta directiva funciona de manera muy similar.

Para configurar las directivas de enrutamiento de audioconferencia, debe seguir estos pasos:
1.  Crear usos de RTC
2.  Configurar rutas de voz
3.  Crear directivas de enrutamiento de voz de audioconferencia
4.  Asignar una directiva a los usuarios


#### <a name="create-pstn-usages"></a>Crear usos de RTC

Los usos de RTC son colecciones de rutas de voz. Cuando se inicia una llamada de acceso telefónico desde la reunión de un organizador determinado, las rutas de voz se usarán para determinar la ruta de enrutamiento de la llamada en función de los usos de RTC asociados al usuario a través de la Directiva de enrutamiento de voz del usuario.

Puede crear un uso de RTC mediante el cmdlet "Set-CsOnlinePstnUsage". Por ejemplo:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurar rutas de voz

Las rutas de voz determinan la puerta de enlace PSTN que debe usarse para enrutar una llamada según el número de teléfono que se marca desde una reunión de Teams. Las rutas de voz determinan la puerta de enlace PSTN que debe usarse para enrutar una llamada determinada haciendo coincidir el número de teléfono marcado desde una reunión de Teams con un patrón de Regex. Al crear una ruta de voz, la ruta debe estar asociada a uno o varios usos de RTC.

Puede crear una ruta de voz y definir los regex y las puertas de enlace que se van a asociar a la ruta de voz mediante el cmdlet "New-CsOnlineVoiceRoute". Por ejemplo:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Crear directivas de enrutamiento de voz de audioconferencia

Las directivas de enrutamiento de voz de audioconferencia determinan las rutas posibles que se pueden usar para enrutar una llamada originada desde las reuniones de un organizador basándose en el número de teléfono objetivo de la llamada de llamada de salida de la reunión. Las directivas de enrutamiento de voz de audioconferencia están asociadas a uno o más usos de RTC, que a su vez determinan las rutas posibles que se intentarán usar para las llamadas de acceso telefónico de la reunión de los organizadores asociados a la Directiva.

Puede crear una directiva de enrutamiento de voz de audioconferencia con el cmdlet "New-CsOnlineAudioConferencingRoutingPolicy". Por ejemplo:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Una vez que se ha asignado la Directiva a un usuario, y cuando se inicia una llamada de acceso telefónico de la reunión desde una de las reuniones del usuario, se evaluarán las rutas de voz de los usos de RTC asociados al organizador a través de la Directiva de enrutamiento de voz del usuario. Si el destino de la llamada de llamada de salida de la reunión coincide con un regex en una de las rutas de voz asociadas al organizador, la llamada de acceso telefónico de reunión se redirigirá a la puerta de enlace RTC definida en la ruta de voz. Si el destino de la llamada de aceptación de la reunión no coincide con ninguna de las rutas de voz asociadas al organizador, Microsoft redirigirá la llamada de llamada de salida de la reunión.

#### <a name="assign-a-policy-to-your-users"></a>Asignar una directiva a los usuarios

Una vez definidas las directivas de enrutamiento de audioconferencia, ahora puede asignarlas a los usuarios. Una vez que se les asignan las directivas, las llamadas de llamada salientes de la reunión se evaluarán para determinar su ruta de enrutamiento. Las directivas de enrutamiento de audioconferencia siempre se evalúan según el organizador de la reunión, independientemente del usuario de la reunión que inicia una llamada de acceso telefónico de la reunión.

Puede asignar una directiva de enrutamiento de voz de audioconferencia a un usuario mediante el cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Por ejemplo:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurar el enrutamiento en el equipo de telefonía de su organización

En el equipo de telefonía de su organización, debe asegurarse de que las llamadas de acceso telefónico de la reunión enrutadas a través del enrutamiento directo se enruten al destino en la red previsto.


### <a name="optional-configure-a-dial-plan"></a>Faculta Configurar un plan de marcado

Un plan de marcado es un conjunto de reglas de normalización que convierten los números de teléfono marcados por un usuario individual en un formato alternativo (por lo general, E. 164) para fines de autorización de llamadas y enrutamiento de llamadas.

De forma predeterminada, los usuarios de Teams pueden llamar a números de RTC en formato E. 164, es decir, + \<country code\> \<number\> . Sin embargo, los planes de marcado se pueden usar para permitir a los usuarios marcar números de teléfono en otros formatos, por ejemplo, las extensiones de 4 dígitos.

Si desea habilitar el marcado basado en extensión a través de conferencias en red, puede configurar planes de marcado para que coincidan con el patrón de marcado de números de teléfono del número de teléfono de su organización. Para configurar planes de marcado, vea [crear y administrar planes de marcado](create-and-manage-dial-plans.md).


## <a name="known-issues-in-open-preview"></a>Problemas conocidos en abrir vista previa

A continuación se muestra una lista de los problemas conocidos que se encuentran actualmente en la versión preliminar abierta de conferencias en red. Microsoft está trabajando en resolver estos problemas.

| Problema | Solución alternativa |
| :--- | :--- |
| Las llamadas de acceso telefónico con identificadores de llamadas anónimos y ocultos que se enrutan a través de conferencias en red no se pueden conectar a la reunión. | Si es posible, establezca una configuración en su PBX o SBC para enviar siempre un identificador de llamada para llamadas enrutadas a través de conferencias en red.|
| En algunos casos, el mensaje de bienvenida que se reproduce a los usuarios al llamar al servicio ("Bienvenido al servicio de audioconferencias...") se trunca y los usuarios no escuchan la palabra "bienvenida".| Por el momento, no hay ninguna solución para este problema. |




## <a name="related-topics"></a>Temas relacionados


