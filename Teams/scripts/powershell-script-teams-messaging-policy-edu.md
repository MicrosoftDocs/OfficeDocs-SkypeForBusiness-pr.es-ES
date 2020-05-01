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
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951065"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="ed02e-103">Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería.</span><span class="sxs-lookup"><span data-stu-id="ed02e-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="ed02e-104">Use este script de PowerShell para crear una directiva de mensajería en Microsoft Teams y asignarla a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed02e-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="ed02e-105">Para obtener más información sobre el uso de este script de PowerShell, consulte [Inicio rápido de Teams para el ámbito educativo](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="ed02e-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="ed02e-106">Esta secuencia de comandos usa el cmdlet [Grant-CsTeamsMessagingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) que se encuentra en el módulo de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="ed02e-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="ed02e-107">Vea la [información general de Teams PowerShell](../teams-powershell-overview.md) para obtener más información sobre la administración de equipos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed02e-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="ed02e-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ed02e-108">Before you start</span></span>

<span data-ttu-id="ed02e-109">Descargue e instale el [módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/download/details.aspx?id=39366)y, a continuación, reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="ed02e-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="ed02e-110">Para obtener más información, vea [administrar Skype empresarial online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="ed02e-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>


## <a name="sample-script"></a><span data-ttu-id="ed02e-111">Ejemplo de script</span><span class="sxs-lookup"><span data-stu-id="ed02e-111">Sample script</span></span>

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
> <span data-ttu-id="ed02e-112">También puede usar la asignación de Directiva por lotes para asignar una directiva de mensajería a grandes conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed02e-112">You can also use batch policy assignment to assign a messaging policy to large sets of users.</span></span> <span data-ttu-id="ed02e-113">Para obtener más información, vea [asignar directivas a grandes conjuntos de usuarios de la escuela](../batch-policy-assignment-edu.md) y [asignar directivas a los usuarios de Teams](../assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ed02e-113">For more information see [Assign policies to large sets of users in your school](../batch-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
