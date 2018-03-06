---
title: 'Ejemplo de script de PowerShell: Crear un equipo que abarque toda la empresa en Microsoft Teams'
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 02/07/2018
ms.topic: article
ms.service: msteams
description: "Use este script de PowerShell para crear un equipo público que abarque toda la empresa en Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 6092979771353a8edaad4229bbcd16a3f85bbb60
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
<a name="powershell-script-sample---create-a-company-wide-team-in-microsoft-teams"></a><span data-ttu-id="f3a44-103">Ejemplo de script de PowerShell: Crear un equipo que abarque toda la empresa en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3a44-103">PowerShell Script Sample - Create a company-wide team in Microsoft Teams</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="f3a44-104">Este script de PowerShell crea un equipo público que abarque toda la empresa en Teams.</span><span class="sxs-lookup"><span data-stu-id="f3a44-104">This PowerShell script creates a public, company-wide team in Teams.</span></span> <span data-ttu-id="f3a44-105">El script hace uso del módulo de PowerShell para Microsoft Teams (en este momento está en fase beta) para crear un equipo público que abarque toda la empresa.</span><span class="sxs-lookup"><span data-stu-id="f3a44-105">The script uses the MicrosoftTeams PowerShell module (currently in beta) to create a public, company-wide team.</span></span> <span data-ttu-id="f3a44-106">También emplea el módulo de PowerShell para AzureAD para recuperar la lista de usuarios de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="f3a44-106">It also uses the AzureAD PowerShell module to fetch the list of users in your tenant.</span></span> 

<span data-ttu-id="f3a44-107">Si desea obtener instrucciones completas sobre cómo se usa este script de PowerShell, eche un vistazo a nuestro tutorial, [Crear un equipo que abarque toda la empresa con PowerShell](../Company-wide-team-creation-powershell.yml).</span><span class="sxs-lookup"><span data-stu-id="f3a44-107">For complete instructions on using this PowerShell script, check out our tutorial, [Create a company-wide team in Teams using PowerShell](../Company-wide-team-creation-powershell.yml).</span></span>

<span data-ttu-id="f3a44-108">Si es la primera vez que usa PowerShell y necesita ayuda para comenzar, consulte [Introducción a Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="f3a44-108">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="f3a44-109">Ejemplo de script</span><span class="sxs-lookup"><span data-stu-id="f3a44-109">Sample script</span></span>

> [!TIP]
> <span data-ttu-id="f3a44-110">Un archivo de script de PowerShell es un archivo de texto con extensión .PS1.</span><span class="sxs-lookup"><span data-stu-id="f3a44-110">A PowerShell script file is a text file with a .PS1 extension.</span></span> <span data-ttu-id="f3a44-111">Para usar este script, tiene que hacer clic en **Copiar** y pegarlo después en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f3a44-111">To use this script, click **Copy** and then paste the code into a text file.</span></span> <span data-ttu-id="f3a44-112">Guárdelo con el nombre de archivo "CrearEquipoParaEmpresa.ps1". De este modo tendrá un script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3a44-112">Save it with the filename CreateCompanyWideTeam.ps1, and you've got a PowerShell script.</span></span>

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


## <a name="script-explanation"></a><span data-ttu-id="f3a44-113">Explicación del script</span><span class="sxs-lookup"><span data-stu-id="f3a44-113">Script explanation</span></span>


<span data-ttu-id="f3a44-114">Si desea obtener instrucciones completas sobre cómo se usa este script de PowerShell, eche un vistazo a nuestro tutorial, [Crear un equipo que abarque toda la empresa con PowerShell](../Company-wide-team-creation-powershell.yml).</span><span class="sxs-lookup"><span data-stu-id="f3a44-114">For complete instructions on using this PowerShell script, check out our tutorial, [Create a company-wide team in Teams using PowerShell](../Company-wide-team-creation-powershell.yml)</span></span>

<span data-ttu-id="f3a44-115">Hay 5 secciones en este script (enumerados en orden de arriba a abajo):</span><span class="sxs-lookup"><span data-stu-id="f3a44-115">There are 5 sections to this script (listed in order from top to bottom):</span></span>
1. <span data-ttu-id="f3a44-116">**Documentación y definiciones de variables**</span><span class="sxs-lookup"><span data-stu-id="f3a44-116">**Documentation and variable definitions**</span></span>
2. <span data-ttu-id="f3a44-117">**Función Create-Team**: crea un equipo, en caso necesario.</span><span class="sxs-lookup"><span data-stu-id="f3a44-117">**Function Create-Team**: Creates a team if necessary.</span></span> <span data-ttu-id="f3a44-118">Si no especifica un Id. de grupo, esta sección creará el equipo con el nombre y la descripción de equipo que se haya especificado.</span><span class="sxs-lookup"><span data-stu-id="f3a44-118">If you don't specify a GroupID, this section will create the team with the specified TeamName and TeamDescription.</span></span>
3. <span data-ttu-id="f3a44-119">**Función Add-Channels**: si ha especificado canales, será aquí donde se solicite la descripción del canal y, a continuación, se creará el canal.</span><span class="sxs-lookup"><span data-stu-id="f3a44-119">**Function Add-Channels**: If you've specified channels, this is where the channel description gets requested, and then the channel gets created.</span></span> 
4. <span data-ttu-id="f3a44-120">**Función Add-Members**: este se encarga de todo lo relacionado con la administración de miembros.</span><span class="sxs-lookup"><span data-stu-id="f3a44-120">**Function Add-Members**: This does all member management.</span></span> <span data-ttu-id="f3a44-121">Esta sección se conecta a AzureAD, recupera un conjunto de usuarios y los agrega al equipo, en caso de no haber proporcionado una lista de miembros.</span><span class="sxs-lookup"><span data-stu-id="f3a44-121">This section connects to AzureAD,  fetches a set of users, and adds them to the team if you don’t provide a member list.</span></span> <span data-ttu-id="f3a44-122">Gestiona la lógica de agregar propietarios y miembros en lugar de agregar miembros que ya pertenecen al equipo.</span><span class="sxs-lookup"><span data-stu-id="f3a44-122">It handles the logic of adding owners and members, and not adding members who already belong to the team.</span></span> 
5. <span data-ttu-id="f3a44-123">**Programa principal**: es el orden en el que se ejecutan las funciones.</span><span class="sxs-lookup"><span data-stu-id="f3a44-123">**Main program**: This is the order in which the functions get executed.</span></span> 


