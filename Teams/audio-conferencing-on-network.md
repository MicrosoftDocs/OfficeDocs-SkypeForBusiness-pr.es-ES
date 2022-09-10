---
title: Conferencia en red para Audioconferencia
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: A continuación se describe En la red para Audioconferencia.
ms.openlocfilehash: 56e2addc3b924d7d73df7475ad217a999dc0aca0
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641881"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Conferencia en red para Audioconferencia

Las conferencias en la red permiten a las organizaciones enviar llamadas de Audioconferencia entrantes y salientes a números de acceso telefónico local de Microsoft a través del enrutamiento directo. Esta capacidad no está pensada para ampliar la compatibilidad de Audioconferencia a números de acceso telefónico local de terceros. Las conferencias en la red no son compatibles si se usan para redirigir llamadas entrantes al servicio audioconferencia a través de números de teléfono de acceso telefónico local de terceros o llamadas salientes a la RTC desde el puente de audioconferencia de Microsoft.

En este artículo se describen los requisitos previos y los pasos de configuración necesarios para habilitar la conferencia en la red para su organización.

> [!IMPORTANT]
> Las conferencias en la red NO se deben implementar con ningún equipo de telefonía en india.

## <a name="prerequisites"></a>Requisitos previos

Antes de configurar conferencias en la red, asegúrese de que su organización cumple los siguientes requisitos previos:

- Asegúrese de que todos los usuarios de su organización que estén habilitados o habilitados para audioconferencia usen Teams para todas las reuniones. El enrutamiento de llamadas de audioconferencia entrantes y salientes a través de conferencias en red solo es compatible con las reuniones de Teams.

- Asigne licencias de Audioconferencia a todos los usuarios que usarán conferencias en la red.

- Configure el servicio de Audioconferencia. Para obtener más información, consulte [Configurar Audioconferencia para Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configure el controlador de borde de sesión (SBC) para el enrutamiento directo. Para obtener más información, consulte [Planear el enrutamiento directo](direct-routing-plan.md) y [configurar el enrutamiento directo](direct-routing-configure.md).

  Si está configurando enrutamiento directo solo para audioconferencia, solo necesita completar "Paso 1: Conectar su SBC" para conferencia en la red.

## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Habilitar el enrutamiento de llamadas de acceso telefónico local a Audioconferencia de Microsoft a través del enrutamiento directo

Para redirigir las llamadas de acceso telefónico local realizadas por los usuarios locales al servicio de Audioconferencia a través del enrutamiento directo, debe configurar las reglas de enrutamiento adecuadas para sus SBCs y las centrales de intercambio (PBX).

Debe configurar el equipo de telefonía de los sitios para redirigir las llamadas a cualquier número de servicio del puente de conferencia de su organización a través de un tronco de enrutamiento directo.

Puede encontrar los números de servicio en el Centro de administración de Teams en **Reuniones -> Puentes de conferencia** o mediante el cmdlet de PowerShell de Teams Get-CsOnlineDialInConferencingBridge. Para obtener más información, consulte una lista de [números de Audioconferencia en Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Esta característica no está disponible para los usuarios con la licencia de Audioconferencia de pago por minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Habilitar el enrutamiento de llamadas de llamadas de reunión de Teams a través del enrutamiento directo

Las llamadas de llamada de salida de las reuniones de Teams se inician desde una reunión de su organización a números RTC, incluidas llamadas de llamadas y llamadas para llevar a nuevos participantes a una reunión.

Para habilitar el enrutamiento de acceso telefónico local de las reuniones de Teams a través del enrutamiento directo a los usuarios de la red, debe crear y asignar una directiva de enrutamiento de Audioconferencia denominada "OnlineAudioConferencingRoutingPolicy".

La directiva OnlineAudioConferencingRoutingPolicy es equivalente a CsOnlineVoiceRoutingPolicy para llamadas RTC 1:1 a través de enrutamiento directo. La directiva OnlineAudioConferencingRoutingPolicy se puede administrar mediante los cmdlets siguientes:

- New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Para obtener más información sobre el enrutamiento para enrutamiento directo, consulte [Configurar el enrutamiento de voz para enrutamiento directo](direct-routing-voice-routing.md).

Para habilitar el enrutamiento de llamadas de salida de reuniones a través del enrutamiento directo, debe:

- Configurar directivas de enrutamiento de Audioconferencia
- Configurar el enrutamiento en el equipo de telefonía de su organización
- (Opcional) Configurar un plan de marcado

Las llamadas de llamada desde las reuniones de Teams proceden del número de servicio predeterminado del puente de conferencia. Para obtener más información sobre el número de servicio predeterminado del puente de Audioconferencia, vea [Cambiar los números de teléfono del puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configurar directivas de enrutamiento de Audioconferencia

La directiva de enrutamiento de Audioconferencia OnlineAudioConferencingRoutingPolicy determina qué llamadas de llamada de reunión se enrutan a troncos de enrutamiento directo. Si está familiarizado con la directiva CsOnlineVoiceRoutingPolicy, esta política funciona de forma muy similar.

Los siguientes pasos son necesarios para configurar las directivas de enrutamiento de Audioconferencia:

1. Crear usos de RTC
1. Configurar rutas de voz
1. Crear directivas de enrutamiento de voz para audioconferencias
1. Asignar una directiva a los usuarios

#### <a name="create-pstn-usages"></a>Crear usos de RTC

Los usos de RTC son colecciones de rutas de voz. Cuando se inicia una llamada de llamada de salida desde la reunión de un organizador determinado, las rutas de voz se usarán para determinar la ruta de enrutamiento de la llamada en función de los usos de RTC asociados al usuario a través de la directiva de enrutamiento de voz del usuario.

Puede crear un uso de RTC mediante el cmdlet "Set-CsOnlinePstnUsage". Por ejemplo:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurar rutas de voz

Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada en función del número de teléfono marcado desde una reunión de Teams. Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada determinada haciendo coincidir el número de teléfono marcado desde una reunión de Teams con un patrón regex. Al crear una ruta de voz, la ruta debe estar asociada a uno o varios usos de RTC.

Puede crear una ruta de voz y definir las puertas de enlace y regex que se asociarán con la ruta de voz mediante el cmdlet "New-CsOnlineVoiceRoute". Por ejemplo:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Crear directivas de enrutamiento de voz para audioconferencias

Las directivas de enrutamiento de voz de audioconferencia determinan las posibles rutas que se pueden usar para redirigir una llamada que proviene de las reuniones de un organizador en función del número de teléfono de destino de la llamada de salida de la reunión. Las directivas de enrutamiento de voz de audioconferencia están asociadas a uno o varios usos de RTC que, a su vez, determinan las posibles rutas que se intentarán usar para las llamadas de llamada de salida de la reunión de los organizadores asociados a la directiva.

Puede crear una directiva de enrutamiento de voz de Audioconferencia mediante el cmdlet "New- CsOnlineAudioConferencingRoutingPolicy". Por ejemplo:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Después de asignar la directiva a un usuario, y cuando se inicia una llamada de llamada de salida de una reunión desde una de las reuniones del usuario, se evaluarán las rutas de voz en los usos de RTC que están asociados al organizador a través de la directiva de enrutamiento de voz del usuario. Si el destino de la llamada de llamada de salida de la reunión coincide con una expresión de registro en una de las rutas de voz asociadas al organizador, la llamada de llamada de salida de la reunión se enrutará a la puerta de enlace RTC definida en la ruta de voz. Si el destino de la llamada de llamada de salida de la reunión no coincide con ninguna de las rutas de voz asociadas al organizador, Microsoft enrutará la llamada de salida de la reunión.

#### <a name="assign-a-policy-to-your-users"></a>Asignar una directiva a los usuarios

Después de definir las directivas de enrutamiento de Audioconferencia, ahora puede asignarlas a los usuarios. Después de asignarles directivas, las llamadas de llamada de salida de la reunión se evaluarán en ella para determinar su ruta de enrutamiento. Las directivas de enrutamiento de audioconferencia siempre se evalúan según el organizador de la reunión, independientemente del usuario de la reunión que inicia una llamada de salida de la reunión.

Puede asignar una directiva de enrutamiento de voz de Audioconferencia a un usuario mediante el cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Por ejemplo:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1"
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurar el enrutamiento en el equipo de telefonía de su organización

En el equipo de telefonía de su organización, debe asegurarse de que las llamadas de llamada de salida de la reunión enrutadas a través del enrutamiento directo se enrute al destino de red previsto.

### <a name="optional-configure-a-dial-plan"></a>(Opcional) Configurar un plan de marcado

Un plan de marcado es un conjunto de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (típicamente E.164) con fines de autorización y enrutamiento de llamadas.

De forma predeterminada, los usuarios de Teams pueden llamar a números RTC en formato E.164, es decir, +\<country code\>\<number\>. Sin embargo, los planes de marcado se pueden usar para permitir a los usuarios marcar números de teléfono en otros formatos, por ejemplo extensiones de 4 dígitos.

Si desea habilitar la marcación basada en extensiones a través de conferencias en red, puede configurar planes de marcado para que coincidan con el patrón de marcado de extensión con los intervalos de números de teléfono del número de teléfono de su organización. Para configurar planes de marcado, consulte [Crear y administrar planes de marcado](create-and-manage-dial-plans.md).

## <a name="related-topics"></a>Temas relacionados
