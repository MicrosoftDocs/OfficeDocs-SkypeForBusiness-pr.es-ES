---
title: 'Ejemplo de script de PowerShell: crear & directiva de mensajería'
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
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117278"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.

Use este script de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignarla a los usuarios. 

Para obtener más información sobre el uso de este script de PowerShell, vea [Inicio rápido: Teams para el sector educativo.](../teams-quick-start-edu.yml)

Este script usa el cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) que se encuentra en el módulo de PowerShell de Skype Empresarial Online. Vea [Información general de Teams PowerShell](../teams-powershell-overview.md) para obtener más información sobre cómo administrar Teams con PowerShell.


## <a name="before-you-start"></a>Antes de empezar

Descargue e instale el [módulo PowerShell](https://www.microsoft.com/download/details.aspx?id=39366)de Skype Empresarial Online y reinicie el equipo si se le solicita.

Para obtener más información, vea Administrar Skype Empresarial Online con PowerShell de [Office 365.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

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
> También puede asignar una directiva de mensajería directamente a los usuarios a escala a través de una asignación de directiva por lotes o a un grupo del que los usuarios son miembros. Para obtener más información, vea [Asignar directivas a grandes conjuntos](../batch-group-policy-assignment-edu.md) de usuarios de la escuela y Asignar directivas a los usuarios en [Teams.](../assign-policies.md)