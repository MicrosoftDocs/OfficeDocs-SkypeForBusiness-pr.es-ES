---
title: Enrutamiento de llamadas a números sinsignar
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Obtenga información sobre cómo enrutar llamadas a números sinsignar en su organización.
ms.openlocfilehash: 2574a0ac734ed6caee1eadf5a5ee006111713055
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537001"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Enrutamiento de llamadas a números sinsignar

> [!NOTE]
> Esta característica está disponible como versión de vista previa pública.

Como administrador, puede enrutar las llamadas a números sinsignar en su organización. Por ejemplo, es posible que desee enrutar las llamadas a números sinsignar de la siguiente manera: 

- Enruta todas las llamadas a un número determinado sinsignar a un anuncio personalizado.

- Enruta todas las llamadas a un número determinado sinsignar a la centralita principal.

Puede enrutar las llamadas a números sin asignación a un usuario, a una cuenta de recursos asociada con un Operador automático o una cola de llamadas, o a un servicio de anuncios que reproducirá un archivo de audio personalizado al autor de la llamada.

## <a name="configuration"></a>Configuración

Para enrutar llamadas a un número sinsignar, use el cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponible en Teams módulo de PowerShell 2.5.1 o posterior.

Debe especificar el número o rango de números denominados y el enrutamiento asociado para las llamadas a estos números. Por ejemplo, el siguiente comando especifica que todas las llamadas al número +1 (555) 222-3333 se enrutarán a la cuenta de recursos aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

En el ejemplo siguiente se especifica que todas las llamadas al rango de números +1 (555) 333-0000 a +1 (555) 333-9999 se enrutarán al servicio de anuncios, que reproducirá el archivo de audio MainAnnouncement.wav al autor de la llamada.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Notas

- Si el enrutamiento a un anuncio, el archivo de audio se reproducirá una vez al autor de la llamada.

- Para enrutar llamadas a números de suscriptores de Microsoft Calling Plan sinsignar, el inquilino debe tener créditos [de comunicaciones disponibles.](what-are-communications-credits.md)

- Para enrutar llamadas a números de servicio de Microsoft Calling Plan sinsignar, el inquilino debe tener al menos una Sistema telefónico: licencia de usuario virtual.

## <a name="related-topics"></a>Temas relacionados

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)