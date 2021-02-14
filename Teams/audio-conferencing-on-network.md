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
description: A continuación se describe la función Vista previa abierta para audioconferencias en red.
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031866"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Vista previa abierta de conferencias en red para audioconferencias

La vista previa abierta de las conferencias en red está disponible para todos los clientes. Las conferencias en red permiten a las organizaciones enviar llamadas entrantes y salientes de Audioconferencia a números de acceso telefónico local de Microsoft a través del enrutamiento directo. Esta función no está pensada para extender la compatibilidad de Audioconferencia a números de acceso telefónico local de terceros. Las conferencias en red no se admiten si se usan para enrutar llamadas entrantes al servicio de Audioconferencia a través de números de teléfono de acceso telefónico local de terceros.

En este artículo se describen los requisitos previos y los pasos de configuración necesarios para habilitar las conferencias en la red para su organización.

> [!IMPORTANT]
> Las conferencias en la red NO deben implementarse con ningún equipo de telefonía en India.
  
## <a name="prerequisites"></a>Requisitos previos

Antes de configurar las conferencias en la red, asegúrese de que su organización cumple los siguientes requisitos previos: 

- Asegúrese de que todos los usuarios de su organización habilitados o habilitados para Audioconferencia usen Teams para todas las reuniones. El enrutamiento de llamadas entrantes y salientes de Audioconferencia a través de conferencias en red solo se admite para las reuniones de Teams.

- Asigne licencias de Audioconferencia a todos los usuarios que usarán conferencias en red.

- Configure el servicio audioconferencia. Para obtener información adicional, [consulte Configurar Audioconferencia para Microsoft Teams.](set-up-audio-conferencing-in-teams.md)

- Configure el controlador de borde de sesión (SBC) para el enrutamiento directo. Para obtener más información, vea [Planear el enrutamiento directo y](direct-routing-plan.md) configurar el enrutamiento [directo.](direct-routing-configure.md) 

  Si configura enrutamiento directo solo para los fines de Audioconferencia, solo necesita completar el "Paso 1: Conectar el SBC" para las conferencias en red.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Habilitar el enrutamiento de llamadas de acceso telefónico local a Audioconferencia de Microsoft mediante enrutamiento directo 

Para enrutar las llamadas de acceso telefónico local realizadas por los usuarios locales al servicio de Audioconferencia a través del enrutamiento directo, debe configurar reglas de enrutamiento apropiadas para sus SBC y las centrales de conexiones de sucursal privadas (PBX).

Necesita configurar el equipo de telefonía de sus sitios para enrutar las llamadas a cualquier número de servicio del puente de conferencia de su organización a través de un tronco de enrutamiento directo.

Encontrará los números de servicio en el Centro de administración de Teams en Reuniones **-> Puentes** de conferencia o mediante el cmdlet get-CsOnlineDialInConferencingBridge de Skype Empresarial Online. Para obtener información adicional, consulte una lista de [números de Audioconferencia en Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

> [!NOTE]
> Esta característica no está disponible para los usuarios con la licencia de Audioconferencia de pago por minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Habilitar el enrutamiento de llamadas salientes de reuniones de Teams a través del enrutamiento directo

Las llamadas de llamada saliente de reuniones de Teams se inician desde una reunión de su organización a números RTC, incluidas las llamadas de llamada al mes y las llamadas para que los nuevos participantes se unan a una reunión. 

Para habilitar el enrutamiento de llamada de salida a las reuniones de Teams a través del enrutamiento directo a los usuarios en la red, debe crear y asignar una directiva de enrutamiento de Audioconferencia denominada "OnlineAudioConferencingRoutingPolicy". 

La directiva OnlineAudioConferencingRoutingPolicy equivale a CsOnlineVoiceRoutingPolicy para llamadas RTC de uno a uno a través del enrutamiento directo. La directiva OnlineAudioConferencingRoutingPolicy se puede administrar con los cmdlets siguientes:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Para obtener más información sobre el enrutamiento de enrutamiento directo, vea [Configurar enrutamiento de voz para enrutamiento directo.](direct-routing-voice-routing.md)


Para habilitar el enrutamiento de llamadas salientes de reuniones a través del enrutamiento directo, debe: 

- Configurar directivas de enrutamiento de Audioconferencia
- Configurar el enrutamiento en el equipo de telefonía de su organización
- (Opcional) Configurar un plan de marcado

Las llamadas salientes de las reuniones de Teams se llegan desde el número de servicio predeterminado del puente de conferencia. Para obtener información adicional sobre el número de servicio predeterminado de su puente de Audioconferencia, vea Cambiar los números de teléfono del puente de [Audioconferencia.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

### <a name="configure-audio-conferencing-routing-policies"></a>Configurar directivas de enrutamiento de Audioconferencia

La directiva de enrutamiento de Audioconferencia OnlineAudioConferencingRoutingPolicy determina qué llamadas de llamada de salida de la reunión se enrutar a troncos de enrutamiento directo. Si está familiarizado con la directiva CsOnlineVoiceRoutingPolicy, esta directiva funciona de forma muy similar.

Para configurar las directivas de enrutamiento de Audioconferencia, es necesario seguir estos pasos:
1.  Crear usos de RTC
2.  Configurar rutas de voz
3.  Crear directivas de enrutamiento de voz de Audioconferencia
4.  Asignar una directiva a los usuarios


#### <a name="create-pstn-usages"></a>Crear usos de RTC

Los usos de RTC son colecciones de rutas de voz. Cuando se inicia una llamada de acceso telefónico local desde la reunión de un organizador determinado, las rutas de voz se usarán para determinar la ruta de enrutamiento de la llamada en función de los usos de RTC que están asociados al usuario a través de la directiva de enrutamiento de voz del usuario.

Puede crear un uso de RTC mediante el cmdlet "Set-CsOnlinePstnUsage". Por ejemplo:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurar rutas de voz

Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada basándose en el número de teléfono que se marca desde una reunión de Teams. Las rutas de voz determinan la puerta de enlace RTC que se debe usar para enrutar una llamada determinada haciendo coincidir el número de teléfono marcado desde una reunión de Teams con un patrón Regex. Al crear una ruta de voz, la ruta debe estar asociada a uno o varios usos de RTC.

Puede crear una ruta de voz y definir el registro y las puertas de enlace que se asociarán con la ruta de voz mediante el cmdlet "New-CsOnlineVoiceRoute". Por ejemplo:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Crear directivas de enrutamiento de voz de Audioconferencia

Las directivas de enrutamiento de voz de Audioconferencia determinan las posibles rutas que se pueden usar para enrutar una llamada que se origina a partir de las reuniones de un organizador según el número de teléfono de destino de la llamada de llamada de salida de la reunión. Las directivas de enrutamiento de voz de Audioconferencia están asociadas a uno o varios usos de RTC que, a su vez, determinan las posibles rutas que se intentarán usar para las llamadas salientes de reunión de los organizadores asociados a la directiva.

Puede crear una directiva de enrutamiento de voz de Audioconferencia mediante el cmdlet "New- CsOnlineAudioConferencingRoutingPolicy". Por ejemplo:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Una vez asignada la directiva a un usuario y cuando se inicia una llamada de llamada de salida de una reunión desde una de las reuniones del usuario, se evaluarán las rutas de voz en los usos de RTC que están asociados al organizador a través de la directiva de enrutamiento de voz del usuario. Si el destino de llamada de salida de la reunión coincide con una expresión regular en una de las rutas de voz asociadas al organizador, la llamada de llamada de salida de la reunión se dirigirá a la puerta de enlace RTC definida en la ruta de voz. Si el destino de llamada de salida de la reunión no coincide con ninguna de las rutas de voz asociadas al organizador, Microsoft enruta la llamada de salida de la reunión.

#### <a name="assign-a-policy-to-your-users"></a>Asignar una directiva a los usuarios

Después de definir las directivas de enrutamiento de Audioconferencia, ahora puede asignarlas a los usuarios. Una vez asignadas las directivas, se evaluarán las llamadas de llamada saliente de la reunión para determinar su ruta de enrutamiento. Las directivas de enrutamiento de Audioconferencia siempre se evalúan en función del organizador de la reunión, independientemente del usuario en la reunión que inicia una llamada de llamada de salida de la reunión.

Puede asignar una directiva de enrutamiento de voz de Audioconferencia a un usuario mediante el cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Por ejemplo:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurar el enrutamiento en el equipo de telefonía de su organización

En el equipo de telefonía de su organización, necesita asegurarse de que las llamadas de llamada saliente de la reunión enrutadas a través del enrutamiento directo se enrutar al destino previsto en la red.


### <a name="optional-configure-a-dial-plan"></a>(Opcional) Configurar un plan de marcado

Un plan de marcado es un conjunto de reglas de normalización que traducen los números de teléfono marcados por un usuario individual a un formato alternativo (normalmente E.164) para fines de autorización y enrutamiento de llamadas.

De forma predeterminada, los usuarios de Teams pueden llamar a números RTC en formato E.164, es decir, + \<country code\> \<number\> . Sin embargo, los planes de marcado pueden usarse para permitir que los usuarios marquen números de teléfono en otros formatos, por ejemplo, extensiones de 4 dígitos.

Si desea habilitar la marcación basada en extensión a través de conferencias en red, puede configurar planes de marcado para que coincidan con el patrón de marcado de extensión con los intervalos de números de teléfono del número de teléfono de su organización. Para configurar planes de marcado, vea [Crear y administrar planes de marcado.](create-and-manage-dial-plans.md)


## <a name="known-issues-in-open-preview"></a>Problemas conocidos de Open Preview

A continuación, se muestra una lista de los problemas conocidos que están presentes actualmente en la versión de Vista previa abierta de las conferencias en red. Microsoft está trabajando para solucionar estos problemas.

| Problema | Solución alternativa |
| :--- | :--- |
| Las llamadas de acceso telefónico local con identificadores de llamada anónimos u ocultos que se enrutar a través de conferencias en la red no se pueden conectar a la reunión. | Si es posible, establezca una configuración en su PBX o SBC para enviar siempre un identificador de llamada para las llamadas enrutadas a través de conferencias en red.|
| En algunos casos, el mensaje de bienvenida que se reproduce a los usuarios al llamar al servicio ("Bienvenido al servicio de Audioconferencia...") se trunca y los usuarios no escuchan la palabra "Bienvenido".| No hay ninguna solución alternativa para este problema en este momento. |




## <a name="related-topics"></a>Temas relacionados


