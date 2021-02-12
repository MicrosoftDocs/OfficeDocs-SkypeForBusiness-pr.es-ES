---
title: 'Ejemplo de script de PowerShell: crear & asignar directiva de mensajería'
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: e3d1fa3ebe45785c088852c518ac5490263fa6aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804660"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.

Use este script de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignarla a los usuarios. 

Para obtener más información sobre el uso de este script de PowerShell, vea [Inicio rápido: Teams para el sector educativo.](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)

Este script usa el [cmdlet Grant-CsTeamsMessagingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) que se encuentra en el módulo PowerShell de Skype Empresarial Online. Consulte [Información general de PowerShell de](../teams-powershell-overview.md) Teams para obtener más información sobre la administración de equipos con PowerShell.


## <a name="before-you-start"></a>Antes de empezar

Descargue e instale el [módulo de PowerShell](https://www.microsoft.com/download/details.aspx?id=39366)de Skype Empresarial Online y, a continuación, reinicie el equipo si se le solicita.

Para obtener más información, consulte [Administrar Skype Empresarial Online con PowerShell de Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

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
> También puede asignar una directiva de mensajería directamente a los usuarios a escala a través de una asignación de directiva por lotes o a un grupo al que los usuarios son miembros. Para obtener más información, vea Asignar directivas a grandes [conjuntos de](../batch-group-policy-assignment-edu.md) usuarios de su escuela y Asignar directivas a los usuarios en [Teams.](../assign-policies.md)
