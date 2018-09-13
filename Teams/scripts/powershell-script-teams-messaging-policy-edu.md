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
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 399cc6cf20554cd8ab23e6d75b66b2d6251e46de
ms.sourcegitcommit: 31918f51e8220950af6437a16d8beeb637fba2b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "23961902"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="48dc2-103">Ejemplo de script de PowerShell: crear y asignar una directiva de mensajería</span><span class="sxs-lookup"><span data-stu-id="48dc2-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="48dc2-104">Utilice esta secuencia de comandos de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="48dc2-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="48dc2-105">Para obtener más información acerca del uso de esta secuencia de comandos de PowerShell, vea la [Guía de inicio rápido - los equipos para el ámbito educativo](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="48dc2-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="48dc2-106">Si es la primera vez que usa PowerShell y necesita ayuda para comenzar, consulte [Introducción a Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="48dc2-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="48dc2-107">Ejemplo de script</span><span class="sxs-lookup"><span data-stu-id="48dc2-107">Sample script</span></span>

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


