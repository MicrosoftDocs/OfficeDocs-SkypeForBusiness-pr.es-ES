---
title: Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Ejemplos de uso de PowerShell para establecer directivas en Teams para controlar quién puede contener eventos en directo en la organización y características que están disponibles en los eventos que crean
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb43e2a7420ef6c121cea93fd4cd8e4cc40ddfb2
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102361"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams

Puede usar los siguientes cmdlets de Windows PowerShell para establecer y asignar la configuración de directiva para eventos en directo de Teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Nuevo: CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

A continuación se muestran algunos ejemplos.

> [!NOTE]
> Para poder ejecutar estos cmdlets, debe estar conectado a Skype empresarial online PowerShell. Para obtener más información, vea [administrar Skype empresarial online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Permitir a los usuarios programar eventos en vivo 

> [!NOTE]
> Estos ejemplos son para eventos producidos en Teams. Para los eventos generados con una aplicación externa o un dispositivo, hay pasos adicionales que debe realizar. Para obtener más información, vea [permitir a los usuarios programar eventos generados con una aplicación o un dispositivo externo](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Permitir que un usuario programe eventos en vivo**

Si se asigna al usuario la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* se establece en *true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
A continuación, asigne el usuario a la directiva global, ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Escenarios de usuario
**Desea que todos los usuarios de su organización puedan programar eventos en vivo**

Si los usuarios tienen asignada la directiva global, ejecute y compruebe que *AllowBroadcastScheduling* * se establece en *verdadero*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si a los usuarios se les asigna una directiva distinta de la directiva global, ejecute y compruebe que *-AllowBroadcastScheduling* esté establecido en *true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Desea que la programación de eventos en directo se deshabilite en toda la organización**

Deshabilitar la programación de eventos en directo, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Asignar todos los usuarios de la organización a la directiva global, ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Desea que un gran número de usuarios pueda programar eventos en vivo e impedir que un grupo de usuarios los programe**

Ejecute y compruebe que *AllowBroadcastScheduling* se establece en *true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
A continuación, asigne un usuario o usuarios a la directiva global, ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Crear una nueva directiva que no permita programar eventos en vivo, ejecute lo siguiente:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Deshabilitar la programación de eventos en directo, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
A continuación, asigne usuarios a esta Directiva, ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Desea deshabilitar la programación de eventos en vivo para un gran número de usuarios y permitir que un conjunto de usuarios los programe**

Deshabilitar la programación de eventos en directo, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
A continuación, asigne esos usuarios a la directiva global, ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crear una directiva para permitir la programación de eventos en directo, ejecute:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilitar la programación de eventos en directo, ejecute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
A continuación, asigne usuarios a esta Directiva, ejecute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Establecer quién puede unirse a eventos en directo
 
Establezca la directiva global para permitir a los usuarios crear eventos que todos los usuarios, incluidos los anónimos, pueden asistir, ejecutar:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Establecer la opción de grabación de eventos en directo
> [!NOTE]
> Esta configuración se aplica solo a los eventos generados en Teams.

Establezca la directiva global para deshabilitar la grabación de eventos en directo:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Establecer subtítulos en vivo y subtítulos en eventos en directo
> [!NOTE]
> Esta configuración se aplica solo a los eventos generados en Teams. 

Establezca la directiva global para activar los subtítulos en vivo y los subtítulos (transcripción) para los asistentes del evento:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Temas relacionados
- [Configuración de eventos en directo en Teams](set-up-for-teams-live-events.md)
- [Descripción de PowerShell para Teams](../teams-powershell-overview.md)

