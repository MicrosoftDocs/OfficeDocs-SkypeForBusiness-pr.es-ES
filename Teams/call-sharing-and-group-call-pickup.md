---
title: Compartir llamadas y atender llamadas grupales
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: El uso compartido de llamadas y la recogida de llamadas grupales en Microsoft Teams permiten a los usuarios compartir llamadas entrantes con compañeros para que las llamadas se puedan capturar cuando el usuario no esté disponible.
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613852"
---
# <a name="call-sharing-and-group-call-pickup"></a>Compartir llamadas y atender llamadas grupales

Las características de uso compartido de llamadas y recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con compañeros para que los compañeros puedan responder a las llamadas que se produzcan mientras el usuario no está disponible.

La recogida de llamadas de grupo es menos perjudicial para los destinatarios que otras formas de uso compartido de llamadas, ya que los usuarios pueden configurar cómo quieren recibir una notificación de una llamada compartida entrante y pueden decidir si responderla. El orden en el que se notifica a los miembros del grupo de llamadas sobre la llamada entrante se puede especificar como simultánea o en orden (con 5 miembros o menos).

> [!IMPORTANT]
> Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar en el modo de implementación Solo teams. Para obtener más información sobre los modos de implementación de Teams, consulte [Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licencia necesaria

Los usuarios deben tener asignada una licencia del sistema Teléfono Microsoft Teams para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales. Para obtener más información sobre el modelo de licencias, consulta [Esto es lo que obtienes con Phone System](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="limitations"></a>Limitaciones

Un usuario solo puede ser el propietario de un grupo de llamadas. Cada grupo de llamadas configurado puede tener un máximo de 25 usuarios o 32.768 caracteres. Un usuario puede ser miembro de un máximo de 25 grupos de llamadas.

Ten en cuenta que los dispositivos móviles solo recibirán una notificación si están configurados para el banner y el tono.

## <a name="enable-the-use-of-group-call-pickup"></a>Habilitar el uso de la recogida de llamadas grupales

Para habilitar los grupos de llamadas, configure la configuración **de TeamsCallingPolicy AllowCallGroups** para un usuario. Puede usar el Centro de administración de Teams o PowerShell. Cuando está habilitado, el usuario puede configurar sus grupos de llamadas en el cliente de Teams. 

Importante: Al desactivar los grupos de llamadas para los usuarios, debe limpiar las relaciones de grupo de llamadas de los usuarios en el Centro de administración de Teams para evitar un enrutamiento de llamada incorrecto. 

## <a name="use-teams-admin-center"></a>Usar el Centro de administración de Teams

Para configurar la recogida de llamadas en grupo para los usuarios mediante el Centro de administración de Teams, consulte [Configurar las opciones de llamada para los usuarios](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Usar PowerShell

Para configurar grupos de llamadas para los usuarios, use los siguientes cmdlets del módulo PowerShell de Teams:

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>Ejemplos

En el ejemplo siguiente se crea un grupo de llamadas para user1@contoso.com con los miembros user2@contoso.com y user3@contoso.com, y se establece el desvío inmediato de llamadas al grupo de llamadas para user1@contoso.com:

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

En el ejemplo siguiente se muestra cómo actualizar el grupo de llamadas de user1@contoso.com para agregar user5@contoso.com y quitar user6@contoso.com:

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>Más información

[Desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[Directiva de llamadas de Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
