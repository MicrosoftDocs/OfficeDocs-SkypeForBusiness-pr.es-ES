---
title: 'Ejemplo de script de PowerShell: crear & asignar directiva de mensajería'
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Use este script de PowerShell para crear una directiva de mensajería en Teams y asignarla a los usuarios de su organización.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 09254f9ed85f69551ee825dbeb8ae063a010f780
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823711"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.

Use este script de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignarla a los usuarios. 

Para obtener más información sobre el uso de este script de PowerShell, vea [Inicio rápido: Teams para Educación](../teams-quick-start-edu.yml).

Este script usa el cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) que se encuentra en el módulo de PowerShell de Skype Empresarial Online. Vea [Teams información general de PowerShell](../teams-powershell-overview.md) para obtener más información sobre cómo administrar Teams con PowerShell.


## <a name="before-you-start"></a>Antes de empezar

Descargue e instale el [módulo Skype Empresarial PowerShell en línea](https://www.microsoft.com/download/details.aspx?id=54616) y, a continuación, reinicie el equipo si se le solicita.

Para obtener más información, consulte [Administrar Skype Empresarial en línea con Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

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
> También puede asignar una directiva de mensajería directamente a los usuarios a escala a través de una asignación de directiva de lote o a un grupo del que los usuarios son miembros. Para obtener más información, vea [Asignar directivas a grandes conjuntos de usuarios de su centro educativo](../batch-group-policy-assignment-edu.md) y [Asignar directivas a los usuarios de Teams](../policy-assignment-overview.md).