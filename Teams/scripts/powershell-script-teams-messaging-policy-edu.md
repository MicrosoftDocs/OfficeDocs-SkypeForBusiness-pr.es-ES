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
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="5e734-103">Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.</span><span class="sxs-lookup"><span data-stu-id="5e734-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="5e734-104">Use este script de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignarla a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5e734-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="5e734-105">Para obtener más información sobre el uso de este script de PowerShell, vea [Inicio rápido: Teams para el sector educativo.](../teams-quick-start-edu.yml)</span><span class="sxs-lookup"><span data-stu-id="5e734-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](../teams-quick-start-edu.yml).</span></span>

<span data-ttu-id="5e734-106">Este script usa el cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) que se encuentra en el módulo de PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="5e734-106">This script uses the [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="5e734-107">Vea [Información general de Teams PowerShell](../teams-powershell-overview.md) para obtener más información sobre cómo administrar Teams con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e734-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="5e734-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="5e734-108">Before you start</span></span>

<span data-ttu-id="5e734-109">Descargue e instale el [módulo PowerShell](https://www.microsoft.com/download/details.aspx?id=39366)de Skype Empresarial Online y reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="5e734-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="5e734-110">Para obtener más información, vea Administrar Skype Empresarial Online con PowerShell de [Office 365.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="5e734-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="5e734-111">Ejemplo de script</span><span class="sxs-lookup"><span data-stu-id="5e734-111">Sample script</span></span>

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
> <span data-ttu-id="5e734-112">También puede asignar una directiva de mensajería directamente a los usuarios a escala a través de una asignación de directiva por lotes o a un grupo del que los usuarios son miembros.</span><span class="sxs-lookup"><span data-stu-id="5e734-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="5e734-113">Para obtener más información, vea [Asignar directivas a grandes conjuntos](../batch-group-policy-assignment-edu.md) de usuarios de la escuela y Asignar directivas a los usuarios en [Teams.](../assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5e734-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>