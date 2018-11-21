---
title: Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Ejemplos de cómo usar PowerShell para establecer directivas en los equipos para controlar quién puede contener eventos en directo en la organización y las características que están disponibles en los eventos que crean
appliesto:
- Microsoft Teams
ms.openlocfilehash: c198711d918914bbd6a1929514d7c2e9aa7dfe00
ms.sourcegitcommit: ff0c4bef4d4cbc71d51fce941aff63739a0016e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2018
ms.locfileid: "26626226"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usar PowerShell para establecer directivas de eventos en directo en Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Puede usar los siguientes cmdlets de Windows PowerShell para establecer y asignar a configuraciones de directiva para eventos en directo en los equipos: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Nueva CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [GRANT CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Aquí tiene algunos ejemplos.

## <a name="allow-users-to-schedule-live-events"></a>Permitir a los usuarios programar eventos en directo 

> [!NOTE]
> Estos ejemplos son para los eventos de inicio rápido. Para los eventos de codificador externo, existen pasos adicionales que debe hacer. Para obtener más información, vea [Permitir a los usuarios programar eventos codificador externo](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).

**Permitir que un usuario programar eventos en directo**

Si el usuario se le asigna la directiva global, ejecute y compruebe que el parámetro *AllowBroadcastScheduling* está establecido en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
A continuación, asigne al usuario a la directiva global, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Escenarios de usuario
**Desea que todos los usuarios de la organización para poder programar eventos en directo**

Si los usuarios tienen asignados la directiva global, ejecute y compruebe que *AllowBroadcastScheduling* * está establecida en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si los usuarios se asignan a una directiva que no sea la directiva global, ejecute y compruebe que *- AllowBroadcastScheduling* está establecido en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Desea que los eventos en directo deshabilitarse en toda la organización de la programación**

Deshabilitar la programación de eventos en directo, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Asignar a todos los usuarios de la organización a la directiva global, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Desea que un gran número de usuarios puedan programar eventos en directo y evitar que un conjunto de usuarios de programación de las mismas**

Ejecute y compruebe que *AllowBroadcastScheduling* está establecido en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
A continuación, asignar un usuario o a los usuarios a la directiva global, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Crear una nueva directiva que no permite la programación de eventos en directo, ejecute:
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Deshabilitar la programación de eventos en directo, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
A continuación, asignar a usuarios a esta directiva, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Desea deshabilitar el evento en directo de programación para un gran número de los usuarios y permitir que un conjunto de usuarios a programarlas**

Deshabilitar la programación de eventos en directo, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
A continuación, asignar a los usuarios a la directiva global, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crear una directiva para permitir la programación de eventos en directo, ejecute:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilitar la programación de eventos en directo, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
A continuación, asignar a usuarios a esta directiva, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Conjunto que se puede unir a eventos en directo
 
Establecer la directiva global para permitir a los usuarios crear eventos de que todos los usuarios, incluidos los usuarios anónimos, puede asistir, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Establecer la opción de grabación de eventos en directo
> [!NOTE]
> Esta configuración se aplica sólo a los eventos de inicio rápido.

Establecer la directiva global para deshabilitar el registro de eventos en directo:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a>Establecer transcripción y traducción de eventos en directo (próximamente)
> [!NOTE]
> Esta configuración se aplica sólo a los eventos de inicio rápido. 

Establecer la directiva global para activar en transcripción y traducción para los asistentes de evento:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Temas relacionados
- [Configurar para los equipos de eventos en directo](set-up-for-teams-live-events.md)


