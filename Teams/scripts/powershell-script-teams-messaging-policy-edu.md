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
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="4dfbe-103">Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.</span><span class="sxs-lookup"><span data-stu-id="4dfbe-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="4dfbe-104">Use este script de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignarla a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4dfbe-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="4dfbe-105">Para obtener más información sobre el uso de este script de PowerShell, consulte [Inicio rápido de Teams para el ámbito educativo](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="4dfbe-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="4dfbe-106">Si es la primera vez que usa PowerShell y necesita ayuda para comenzar, consulte [Introducción a Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="4dfbe-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="4dfbe-107">Ejemplo de script</span><span class="sxs-lookup"><span data-stu-id="4dfbe-107">Sample script</span></span>

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


