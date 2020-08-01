---
title: 'Ejemplo de script de PowerShell: crear & asignar Directiva de mensajería'
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Use este script de PowerShell para crear una directiva de mensajería en Teams y asignarla a los usuarios de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 318a430f6f59cbb28ffeda4336c36ae07533615b
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533745"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.

Use este script de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignarla a los usuarios. 

Para obtener más información sobre el uso de este script de PowerShell, consulte [Inicio rápido de Teams para el ámbito educativo](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Esta secuencia de comandos usa el cmdlet [Grant-CsTeamsMessagingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) que se encuentra en el módulo de PowerShell de Skype empresarial online. Vea la [información general de Teams PowerShell](../teams-powershell-overview.md) para obtener más información sobre la administración de equipos con PowerShell.


## <a name="before-you-start"></a>Antes de empezar

Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/download/details.aspx?id=39366)y, a continuación, reinicie el equipo si se le solicita.

Para obtener más información, vea [administrar Skype empresarial online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="sample-script"></a>Ejemplo de script

```powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
```

> [!NOTE]
> También puede asignar una directiva de mensajería directamente a los usuarios a escala a través de una asignación de Directiva por lotes o a un grupo del que son miembros los usuarios. Para obtener más información, vea [asignar directivas a grandes conjuntos de usuarios de la escuela](../batch-group-policy-assignment-edu.md) y [asignar directivas a los usuarios de Teams](../assign-policies.md).
