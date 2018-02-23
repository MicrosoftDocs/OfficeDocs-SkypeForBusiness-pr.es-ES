---
title: 'Ejemplo de script de PowerShell: Crear un equipo que abarque toda la empresa en Microsoft Teams'
author: ninadara
ms.author: ninadara
manager: lolaj
ms.date: 02/07/2018
ms.topic: article
ms.service: msteams
description: "Use este script de PowerShell para crear un equipo público que abarque toda la empresa en Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: a22eddd2051526753df86d32e833feb89ce0625f
ms.sourcegitcommit: 46ca433590a4c3aefbe2fb777542bb0b332563bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2018
---
<a name="powershell-script-sample---create-a-company-wide-team-in-microsoft-teams"></a>Ejemplo de script de PowerShell: Crear un equipo que abarque toda la empresa en Microsoft Teams
-------------------------------------------------------------------------

Este script de PowerShell crea un equipo público que abarque toda la empresa en Teams. El script hace uso del módulo de PowerShell para Microsoft Teams (en este momento está en fase beta) para crear un equipo público que abarque toda la empresa. También emplea el módulo de PowerShell para AzureAD para recuperar la lista de usuarios de su inquilino. 

Si desea obtener instrucciones completas sobre cómo se usa este script de PowerShell, eche un vistazo a nuestro tutorial, [Crear un equipo que abarque toda la empresa con PowerShell](../Company-wide-team-creation-powershell.yml).

Si es la primera vez que usa PowerShell y necesita ayuda para comenzar, consulte [Introducción a Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Ejemplo de script

> [!TIP]
> Un archivo de script de PowerShell es un archivo de texto con extensión .PS1. Para usar este script, tiene que hacer clic en **Copiar** y pegarlo después en un archivo de texto. Guárdelo con el nombre de archivo "CrearEquipoParaEmpresa.ps1". De este modo tendrá un script de PowerShell.

````powershell
<#
.SYNOPSIS
This script allows you to create a company-wide team.
.DESCRIPTION
Use this script with the MicrosoftTeams PowerShell version 0.9.0 beta module to create a team with members and channels that you specify. Also leverages the AzureAD module to find all members to add.
.PARAMETER Owners
The comma-separated list of owners for your Team, who handle team settings and membership management. The owners should be specified by their User Principal Name. You must specify a minimum of two owners.
.PARAMETER TeamName
The name of your company-wide team. For example, this could be your company name.
.PARAMETER TeamDescription
The description of your company-wide team, in quotes.
.PARAMETER Channels
The comma-separated list of names of all the initial channels you want to set up. For example: "Announcements","Social at Work","Teamwork at Contoso".
.PARAMETER GroupID
If you have already created the group for your company-wide team, specify its GroupID. You can get this value from the display of the “Get-AzureADGroup | Sort DisplayName | Select DisplayName,ObjectID” command. This script had an issue during the rest of the execution and stopped early. 
.PARAMETER Members
The comma-separated list of members for your team that you want to manually add. To use this script a minimum of two members must be added. The members should be specified by their User Principal Name. To manually just add a single member, use the “Add-TeamUser -GroupId $IdOfGroup -Role Member -User $member” command.
#>
param(
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Owners,
    [Parameter(Mandatory=$false)][System.String]$TeamName,
    [Parameter(Mandatory=$false)][System.String]$TeamDescription,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Channels,
    [Parameter(Mandatory=$false)][System.String]$GroupID,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Members
)

function Create-Team(){
    Write-Host("Starting Team Creation")
    $GroupID = (New-Team -DisplayName $TeamName -AccessType Public -Description $TeamDescription).GroupId

    if([string]::IsNullOrEmpty($GroupID)){
        Write-Host("Team creation failed, please investigate and try again")
        Return
    }

    Write-Host("Team GroupID:", $GroupID)

    return ,$GroupID
} 

 
function Add-Channels($IdOfGroup){
        Write-Host("Starting Channel addition")
    foreach($channel in $Channels)
        {
            Write-Host("Enter Channel Description for " + $channel + " channel")
            $channelDescription = Read-Host
            New-TeamChannel -GroupId $IdOfGroup -DisplayName $channel -Description $channelDescription
        }
}
 
 
function Add-Members ($IdOfGroup){
    Write-Host("Starting Member addition")
    $allUsersInTenant = $Members 

    ## Only fetch full user list, if one isn't supplied
    if([string]::IsNullOrEmpty($Members))
    {
        $Error.Clear()
 

        Write-Host("Starting connection to AzureAD module") 
        Connect-AzureAD
 
        if($Error){
            Write-Host("Unable to connect to AzureAD. Please investigate and try again. To install the commandlet, use this command: Install-Module AzureAD")
            Return
        }
    
        

       ## Fetch all the users and create the member list
        $allUsersInTenant = (Get-AzureADUser).UserPrincipalName 

 
        Disconnect-AzureAD
    } 
    
    $NotAddedMembers = [System.Collections.ArrayList]@()
    $existingTeamMembers = (Get-TeamUser -GroupId $IdOfGroup).User

    foreach($user in $allUsersInTenant){
        $Error.Clear()

        if(!$existingTeamMembers.Contains($user)){
            Write-Host($user)

            if($Owners.Contains($user)){
                Add-TeamUser -GroupId $IdOfGroup -Role Owner -User $user.ToString()
                
                if($Error){
                    $NotAddedMembers.Add([Tuple]::Create($user,"Owner"))
                }
            }
            else{
                Add-TeamUser -GroupId $IdOfGroup -Role Member -User $user.ToString()
                
                if($Error) {
                    $NotAddedMembers.Add([Tuple]::Create($user,"Member"))
                }
            }
        }
    } 

    if($NotAddedMembers.Count > 0) {
        Write-Host("There are some members that did not get added, please retry these specific users")
        Write-Host($NotAddedMembers)
    } 


    ##Clear member addition errors
    $Error.Clear()
}
 
 
 
 
##Main Script
$Error.Clear()
Write-Host("Starting connection to MicrosoftTeams module") 

Connect-MicrosoftTeams
 
if($Error){
    Write-Host("There was an error installing\connecting to the Microsoft Teams PowerShell module. Please investigate. To install the module use the follow command: Install-Module MicrosoftTeams ")
    Return
}

##Create the team if existing GroupID isn't supplied. It's possible a Tenant Wide team was created, but there was an error adding members.
if([string]::IsNullOrEmpty($GroupID)){

    if([string]::IsNullOrEmpty($TeamName)){
        Write-Host("Missing an argument for parameter 'TeamName' and 'GroupID'. Specify a parameter of type 'System.String' and try again for either GroupID or TeamName and TeamDescription")
        Return
    }
    $GroupID = Create-Team
} 
 
if($Channels.Count -gt 0){
    Add-Channels $GroupID
} 

Add-Members $GroupID 
 
Disconnect-MicrosoftTeams

````


## <a name="script-explanation"></a>Explicación del script


Si desea obtener instrucciones completas sobre cómo se usa este script de PowerShell, eche un vistazo a nuestro tutorial, [Crear un equipo que abarque toda la empresa con PowerShell](../Company-wide-team-creation-powershell.yml).

Hay 5 secciones en este script (enumerados en orden de arriba a abajo):
1. **Documentación y definiciones de variables**
2. **Función Create-Team**: crea un equipo, en caso necesario. Si no especifica un Id. de grupo, esta sección creará el equipo con el nombre y la descripción de equipo que se haya especificado.
3. **Función Add-Channels**: si ha especificado canales, será aquí donde se solicite la descripción del canal y, a continuación, se creará el canal. 
4. **Función Add-Members**: este se encarga de todo lo relacionado con la administración de miembros. Esta sección se conecta a AzureAD, recupera un conjunto de usuarios y los agrega al equipo, en caso de no haber proporcionado una lista de miembros. Gestiona la lógica de agregar propietarios y miembros en lugar de agregar miembros que ya pertenecen al equipo. 
5. **Programa principal**: es el orden en el que se ejecutan las funciones. 


