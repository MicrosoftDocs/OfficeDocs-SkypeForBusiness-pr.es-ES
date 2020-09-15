---
title: Usar PowerShell para controlar el acceso de invitado a un equipo
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo usar PowerShell para permitir o bloquear el acceso de invitados a todos los equipos o a determinados equipos de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8a2e23f5c03420c4b0ce644a80e0733f9f69a5
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814339"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="8a73e-103">Usar PowerShell para controlar el acceso de invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="8a73e-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="8a73e-104">Además de usar el centro de administración de Microsoft 365 y el portal de Azure Active Directory (Azure AD), puede usar Windows PowerShell para controlar el acceso de invitados.</span><span class="sxs-lookup"><span data-stu-id="8a73e-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="8a73e-105">Con PowerShell, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a73e-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="8a73e-106">Permitir o bloquear el acceso de invitados a todos los equipos y grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a73e-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="8a73e-107">Permitir que los invitados se agreguen a todos los equipos y grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a73e-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="8a73e-108">Permitir o bloquear usuarios invitados de un equipo específico o de un grupo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a73e-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="8a73e-109">Para obtener más información, vea "usar PowerShell para controlar el acceso de invitados" en [administrar el acceso de invitados en grupos de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="8a73e-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="8a73e-110">También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio.</span><span class="sxs-lookup"><span data-stu-id="8a73e-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="8a73e-111">Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="8a73e-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="8a73e-112">Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="8a73e-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="8a73e-113">Para obtener más información, consulte [permitir o bloquear el acceso de invitados a grupos de Microsoft 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="8a73e-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="8a73e-114">Si desea bloquear invitados en Teams y aún desea permitirles el acceso a los sitios de SharePoint, puede usar los cmdlets de PowerShell de Azure AD para deshabilitar el parámetro AllowGuestsToAccessGroups en el objeto Company, suponiendo que el uso compartido externo esté activado para los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a73e-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="8a73e-115">Usar PowerShell para activar o desactivar el acceso de invitados</span><span class="sxs-lookup"><span data-stu-id="8a73e-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="8a73e-116">Descargue el módulo de PowerShell de Skype Empresarial Online en https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="8a73e-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="8a73e-117">Conecte una sesión de PowerShell al punto de conexión de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="8a73e-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="8a73e-118">En este momento, el conector de Skype empresarial online forma parte del módulo de PowerShell más reciente de Teams.</span><span class="sxs-lookup"><span data-stu-id="8a73e-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="8a73e-119">Si está usando la [versión pública de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)más reciente de PowerShell, no necesita instalar el conector de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="8a73e-119">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```powershell
    Import-Module -Name MicrosoftTeams
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="8a73e-120">Compruebe la configuración y si `AllowGuestUser` es `$False`, use el cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para establecerlo en `$True`.</span><span class="sxs-lookup"><span data-stu-id="8a73e-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```powershell
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
<span data-ttu-id="8a73e-121">Ahora puede tener usuarios invitados en Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="8a73e-121">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="8a73e-122">Acceso de invitado frente a acceso externo</span><span class="sxs-lookup"><span data-stu-id="8a73e-122">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
