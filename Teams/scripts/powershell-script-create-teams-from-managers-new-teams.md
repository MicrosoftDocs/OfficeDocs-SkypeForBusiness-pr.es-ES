---
title: 'Ejemplo de script de PowerShell: Crear nuevos equipos de administradores de personas'
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: brandber
ms.service: msteams
audience: admin
description: Use este script de PowerShell para crear un equipo para cada administrador que dirija como miembros del equipo.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f17ccf2372b10d8b0a14e4259faf9db22fc72ce
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583117"
---
# <a name="powershell-script-sample---create-new-people-manager-teams"></a>Ejemplo de script de PowerShell: Crear nuevos equipos de administradores de personas

Use este script de PowerShell para crear un equipo para cada administrador que dirija como miembros del equipo. Antes de ejecutar este script, ejecute el script [Administradores](powershell-script-create-teams-from-managers-export-managers.md) de exportación para exportar (desde Active Directory) una lista de los administradores y sus responsables para la organización.

Para obtener información sobre este script de PowerShell, lea [Crear equipos de administrador de personas.](../create-manager-directs-teams.md)

Si es la primera vez que usa PowerShell y necesita ayuda para comenzar, consulte [Introducción a Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="create-new-people-manager-teams"></a>Crear nuevos equipos de administradores de personas 

```powershell
<# 
.SYNOPSIS 
  Name: New-TeamsFromManagers.ps1 
  This sample script creates a new team for each people manager that includes the manager and their direct reports, based off the ExportedManagerDirects.txt file. 
   
.DESCRIPTION 
 This sample script create new Teams based on the tab delimited .txt file you provide of managers and direct reports.
 
.NOTES 
  &copy; 2020 Microsoft Corporation.  All rights reserved.  This document is provided 
    "as-is." Information and views expressed in this document, including URL and 
    other Internet Web site references, may change without notice.
 
.EXAMPLE 
  New-TeamsFromManagers.ps1 -Input .\TeamsToCreate.txt
#>

#region Configurable Inputs
$InputFile = "ExportedManagersDirects.txt"
$ChannelName = "Just for Fun"
#endregion

#region Data Model
class DirectReport {
    [ValidateNotNullOrEmpty()] $UserPrincipalName
    [bool] $TeamsEnabled
}
class Manager {
    [ValidateNotNullOrEmpty()] [string] $UserPrincipalName
    [string] $DisplayName
    [string] $Alias
    [System.Collections.ObjectModel.Collection[DirectReport]]$DirectReports
    [bool] $TeamsEnabled
    [bool] $PassedPrereqs

    Manager (){
        $this.DirectReports = New-Object -TypeName System.Collections.ObjectModel.Collection["DirectReport"]
        $this.PassedPrereqs = $false
    }
}
#endregion

#region Helper Functions
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}
Function IsTeamsEnabled([string] $upn) {
    $user = Get-AzureADUser -ObjectId $upn
    foreach ($plan in $user.AssignedPlans) {
        if (($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") -and ($plan.CapabilityStatus -eq "Enabled")) {
            return $true
        }
    }
    return $false
}
Function ProcessData ($Managers) {
    $output = New-Object -type System.Collections.ObjectModel.Collection["Manager"]

    #Iterate through each manager
    foreach ($manager in $Managers) {
        $boss = New-Object -TypeName Manager
        $boss.UserPrincipalName = $manager.Name
        $boss.DisplayName = $manager.DisplayName
        $boss.TeamsEnabled = IsTeamsEnabled $boss.UserPrincipalName
        $countNonEnabled = 0

        #Iterate over each manager's direct reports
        foreach ($directReport in $manager.Directs) {
            $directs = $manager.Directs.Split(",")
            #Iterate over each direct report
            foreach ($direct in $directs) {
                if ($null -ne $direct) {
                    $person = New-Object -TypeName DirectReport
                    $person.UserPrincipalName = $direct
                    $person.TeamsEnabled = IsTeamsEnabled $person.UserPrincipalName
                    if ($person.TeamsEnabled -eq $false) {
                        $countNonEnabled++
                        Write-Verbose "$(Get-Timestamp) Warning: $($person.UserPrincipalName) is not enabled for Teams."                        
                    }
                    $boss.DirectReports.Add($person)
                }
            }
        }
        if ($countNonEnabled -eq 0) {
            $boss.PassedPrereqs = $true
        }
        #Add output of Manager/Directs to collection
        $output.Add($boss)
    }
    return $output
}

Function CreateChannel([string] $GroupId, [string] $ChannelDisplayName) {
    if (($null -ne $GroupId) -and ($null -ne $ChannelDisplayName)) {
        New-TeamChannel -GroupId $newTeam.GroupId -DisplayName $ChannelDisplayName | Out-Null
        Write-Verbose "$(Get-Timestamp) Info: Created '$($ChannelDisplayName)' Channel within GroupId($($newTeam.GroupId))."
    }
}

Function AddDirectToTeam([string] $GroupId, [string] $UserPrincipalName) {
    Add-TeamUser -GroupId $newTeam.GroupId -User $direct.UserPrincipalName
    Write-Host "$(Get-Timestamp) Info: Added $($direct.UserPrincipalName) as a Member of GroupId($($newTeam.GroupId))."
}

Function GetNonEnabledTeamsUsers ([manager] $Manager) {
    if ($manager.TeamsEnabled -eq $false) {
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: Manager:$($Manager.UserPrincipalName) not enabled for Teams."
    }
    foreach ($direct in $Manager.DirectReports) {
        if ($direct.TeamsEnabled -eq $false) {
            Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: User:$($direct.UserPrincipalName) not enabled for Teams. Manager:$($Manager.UserPrincipalName)."
        }
    }
}

Function CreateTeam ([manager] $Manager) {
    #Validate both the Manager and Directs are enabled for Teams
    if ($Manager.PassedPrereqs) {
        $alias = $Manager.UserPrincipalName.Split('@')
        $teamName = "$($Manager.DisplayName)'s Team"
        $mailNickName = "$($alias[0])Team"
        if ($Teams.Keys -notcontains $teamName) {
            if ($Teams.Values -notcontains $mailNickName) {
                #Create Team
                $newTeam = New-Team -DisplayName $teamName -MailNickName $mailNickName -Visibility "Private" -Owner $Manager.UserPrincipalName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Created new team for $($Manager.UserPrincipalName) with GroupId: ($($newTeam.GroupId))."

                #Create desired Channel
                CreateChannel $newTeam.GroupId $ChannelName

                if ($null -ne $newTeam) {
                    foreach ($direct in $Manager.DirectReports) {
                        #Add Direct to Team
                        AddDirectToTeam $newTeam.GroupId $direct.UserPrincipalName
                    }
                }
            }
            else {
                    Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: Mailnickname $($mailNickName) already in use. Skipping creating team for $($Manager.UserPrincipalName)."
            }
        }
        else {
            Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: Team already exists for $($Manager.UserPrincipalName). No Team created."
        }
    }
    else {
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Warning: Manager:$($Manager.UserPrincipalName) has the following users not enabled for Teams. No Team created."
        GetNonEnabledTeamsUsers $Manager
    }
}
#endregion

#region Script Execution
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 1: Processing input file."
$Input = import-csv .\"$($InputFile)" -Delimiter `t
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 1: Completed."

Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 2: Processing Team Pre-requisites."
$Managers = ProcessData $Input
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 2: Completed."

Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 3: Creating Teams for each Manager, adding Directs and creating custom Channels."
#This may take awhile, but is needed to ensure Teams are not duplicated.
$AllTeams = Get-Team
$Teams = @{}
if ($null -ne $AllTeams) {
    foreach ($team in $AllTeams) {
        $Teams.Add($team.DisplayName,$team.MailNickName)
    }
}
foreach ($Manager in $Managers) {
    CreateTeam $Manager
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Step 3: Completed."
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Exiting.."
#endregion

```


