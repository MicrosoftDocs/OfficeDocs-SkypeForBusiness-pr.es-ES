---
title: Cambiar los modos de barreras de la información con un script de PowerShell
description: Use este script de PowerShell después de implementar barreras de información para actualizar el modo de abierto a implícito para todos los grupos de su inquilino.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63403c5e5ee495a7a110aa9239868fd6a9bb5803
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047130"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>Cambiar los modos de barreras de la información con un script de PowerShell

Use este script de PowerShell para actualizar el modo de barreras de la información (IB) para todos los grupos conectados a Teams en su inquilino. Tendrá que actualizar el modo para estos grupos después de implementar las barreras de la información. Los grupos aprovisionados antes de habilitar IB se asignan al modo *Abierto* . En el modo *abierto* , no hay ninguna directiva IB aplicable. Después de habilitar IB, *Implicit* se convierte en el modo predeterminado para los nuevos grupos que cree. Sin embargo, los grupos existentes siguen teniendo la configuración *del modo Abierto* . Ejecute este script para cambiar estos grupos existentes al modo *implícito* .

En este script, usará el cmdlet [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup), que se encuentra en el módulo Exchange Online PowerShell para actualizar el modo. Para obtener más información sobre cómo administrar Teams con PowerShell, consulte [Introducción a Teams PowerShell](./teams-powershell-overview.md).

## <a name="sample-script"></a>Ejemplo de script

Tendrá que usar una cuenta profesional o educativa a la que se le haya asignado el rol de administrador global para que el inquilino ejecute este script.

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```