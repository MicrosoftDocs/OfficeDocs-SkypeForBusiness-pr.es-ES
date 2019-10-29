---
title: Usar PowerShell para controlar el acceso de invitado a un equipo
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Use PowerShell para permitir el acceso de invitado a los equipos de Microsoft Teams o bloquearlo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90ca96b6a28b1a94c375af0b4b4166da5bbee9e9
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753335"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="8e1a4-103">Usar PowerShell para controlar el acceso de invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="8e1a4-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="8e1a4-104">Además de usar el centro de administración de Microsoft 365 y el portal de Azure Active Directory (Azure AD), puede usar Windows PowerShell para controlar el acceso de invitados.</span><span class="sxs-lookup"><span data-stu-id="8e1a4-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="8e1a4-105">Con PowerShell, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e1a4-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="8e1a4-106">Permitir o bloquear el acceso de invitados a todos los grupos de Teams y Office 365</span><span class="sxs-lookup"><span data-stu-id="8e1a4-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="8e1a4-107">Permitir que los invitados se agreguen a todos los grupos de equipos y de Office 365</span><span class="sxs-lookup"><span data-stu-id="8e1a4-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="8e1a4-108">Permitir o bloquear a usuarios invitados en un equipo o grupo específico de Office 365</span><span class="sxs-lookup"><span data-stu-id="8e1a4-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="8e1a4-109">Para obtener más información, vea "usar PowerShell para controlar el acceso de invitados" en [administrar el acceso de invitados en los grupos de Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="8e1a4-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>

  
<span data-ttu-id="8e1a4-110">También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio.</span><span class="sxs-lookup"><span data-stu-id="8e1a4-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="8e1a4-111">Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="8e1a4-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="8e1a4-112">Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="8e1a4-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="8e1a4-113">Para obtener más información, consulte [permitir o bloquear el acceso de invitados a grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="8e1a4-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="8e1a4-114">Si desea bloquear invitados en Teams y aún desea permitirles el acceso a sitios de SharePoint, puede usar los cmdlets de PowerShell de Azure AD para deshabilitar el parámetro AllowGuestsToAccessGroups en el objeto de la compañía, suponiendo que el uso compartido externo esté activado para los sitios de SharePoint .</span><span class="sxs-lookup"><span data-stu-id="8e1a4-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="8e1a4-115">Usar PowerShell para activar o desactivar el acceso de invitados</span><span class="sxs-lookup"><span data-stu-id="8e1a4-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="8e1a4-116">Descargue el módulo de PowerShell de Skype Empresarial Online en https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="8e1a4-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="8e1a4-117">Conecte una sesión de PowerShell al punto de conexión de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="8e1a4-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="8e1a4-118">Compruebe la configuración y si `AllowGuestUser` es `$False`, use el cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para establecerlo en `$True`.</span><span class="sxs-lookup"><span data-stu-id="8e1a4-118">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="8e1a4-119">Ahora puede tener usuarios invitados en Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="8e1a4-119">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="8e1a4-120">Acceso de invitado frente a acceso externo</span><span class="sxs-lookup"><span data-stu-id="8e1a4-120">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
