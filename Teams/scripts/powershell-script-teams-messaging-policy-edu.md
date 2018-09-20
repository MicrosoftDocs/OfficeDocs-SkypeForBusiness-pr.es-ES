---
title: 'Ejemplo de script de PowerShell: crear y asignar una directiva de mensajería'
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: Use este script de PowerShell para crear una directiva de mensajería en los equipos y asignar a los usuarios de su organización.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 108272636925daadfb361c1e79ff14b9c04f514a
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021861"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Ejemplo de script de PowerShell: crear y asignar una directiva de mensajería
-------------------------------------------------------------------------

Utilice esta secuencia de comandos de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignar a los usuarios. 

Para obtener más información acerca del uso de esta secuencia de comandos de PowerShell, vea la [Guía de inicio rápido - los equipos para el ámbito educativo](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

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


