---
title: Usar PowerShell para establecer directivas de eventos en directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Ejemplos de cómo usar PowerShell para establecer directivas en Teams para controlar quién puede tener eventos en directo en su organización y las características disponibles en los eventos.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ece22b6debd3c7d6209df96983d1d66ed5f6f3ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815630"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams

Puede usar los siguientes cmdlets Windows PowerShell para establecer y asignar configuraciones de directiva para eventos en directo en Teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Estos son algunos ejemplos.

> [!NOTE]
> Antes de ejecutar estos cmdlets, debe estar conectado a PowerShell de Skype Empresarial Online. Para obtener más información, [consulte Administrar Skype Empresarial Online con Microsoft 365 u Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="allow-users-to-schedule-live-events"></a>Permitir a los usuarios programar eventos en directo 

> [!NOTE]
> Estos ejemplos son para eventos producidos en Teams. Para eventos producidos con una aplicación o dispositivo externo, hay pasos adicionales que debe realizar. Para obtener más información, vea [Permitir a los usuarios programar eventos producidos con una aplicación o dispositivo externos.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)

**Permitir que un usuario programe eventos en directo**

Si se asigna al usuario la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* está establecido en *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Después, asigne al usuario a la directiva global y ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Escenarios de usuario
**Desea que todos los usuarios de su organización puedan programar eventos en directo**

Si se asigna a los usuarios la directiva global, ejecute y compruebe que *AllowBroadcastScheduling* *está establecido en *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si a los usuarios se les asigna una directiva que no sea la directiva global, ejecute y compruebe que *-AllowBroadcastScheduling* está establecido en *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Quiere que la programación de eventos en directo se deshabilite en toda la organización**

Para deshabilitar la programación de eventos en directo, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Para asignar todos los usuarios de la organización a la directiva global, ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Desea que un gran número de usuarios pueda programar eventos en directo e impedir que un conjunto de usuarios los programe**

Ejecute y compruebe que *AllowBroadcastScheduling* está establecido en *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Después, asigne un usuario o usuarios a la directiva global y ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Para crear una nueva directiva que no permita la programación de eventos en directo, ejecute:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Para deshabilitar la programación de eventos en directo, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Después, asigne usuarios a esta directiva y ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Desea deshabilitar la programación de eventos en directo para un gran número de usuarios y permitir que un conjunto de usuarios los programe**

Para deshabilitar la programación de eventos en directo, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Después, asigne esos usuarios a la directiva global y ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Para crear una directiva para permitir la programación de eventos en directo, ejecute:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Para habilitar la programación de eventos en directo, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Después, asigne usuarios a esta directiva y ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Establecer quién puede unirse a eventos en directo
 
Establezca la directiva global para permitir a los usuarios crear eventos a los que todos los usuarios, incluidos los usuarios anónimos, puedan asistir, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Establecer la opción de grabación para eventos en directo
> [!NOTE]
> Esta configuración se aplica solo a los eventos producidos en Teams.

Establezca la directiva global para deshabilitar la grabación de eventos en directo:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Establecer subtítulos en directo y subtítulos en eventos en directo
> [!NOTE]
> Esta configuración se aplica solo a los eventos producidos en Teams. 

Establezca la directiva global para activar los subtítulos en directo y los subtítulos (transcripción) para los asistentes al evento:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Temas relacionados
- [Configuración de Eventos en Directo de Teams](set-up-for-teams-live-events.md)
- [Descripción de PowerShell para Teams](../teams-powershell-overview.md)

