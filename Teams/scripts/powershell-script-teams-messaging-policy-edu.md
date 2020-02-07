---
title: 'Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.'
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
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06f2dee7e7dbc4e15d544433057a8bb12b75b7c4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827418"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.
-------------------------------------------------------------------------

Use este script de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignarla a los usuarios. 

Para obtener más información sobre el uso de este script de PowerShell, consulte [Inicio rápido de Teams para el ámbito educativo](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Si es la primera vez que usa PowerShell y necesita ayuda para comenzar, consulte [Introducción a Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Ejemplo de script

````powershell
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
````


