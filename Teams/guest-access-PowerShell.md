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
ms.openlocfilehash: b7e2833d1afedb975edf2532fb69c4fdbbdb31d4
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655911"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="89f22-103">Usar PowerShell para controlar el acceso de invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="89f22-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="89f22-104">Además de usar el centro de administración de Microsoft 365 y el portal de Azure Active Directory (Azure AD), puede usar Windows PowerShell para controlar el acceso de invitados.</span><span class="sxs-lookup"><span data-stu-id="89f22-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="89f22-105">Con PowerShell, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89f22-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="89f22-106">Permitir o bloquear el acceso de invitados a todos los equipos y grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89f22-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="89f22-107">Permitir que los invitados se agreguen a todos los equipos y grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89f22-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="89f22-108">Permitir o bloquear usuarios invitados de un equipo específico o de un grupo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89f22-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="89f22-109">Para obtener más información, vea "usar PowerShell para controlar el acceso de invitados" en [administrar el acceso de invitados en grupos de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="89f22-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="89f22-110">También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio.</span><span class="sxs-lookup"><span data-stu-id="89f22-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="89f22-111">Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="89f22-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="89f22-112">Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos.</span><span class="sxs-lookup"><span data-stu-id="89f22-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="89f22-113">Para obtener más información, consulte [permitir o bloquear el acceso de invitados a grupos de Microsoft 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="89f22-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="89f22-114">Si desea bloquear invitados en Teams y aún desea permitirles el acceso a los sitios de SharePoint, puede usar los cmdlets de PowerShell de Azure AD para deshabilitar el parámetro AllowGuestsToAccessGroups en el objeto Company, suponiendo que el uso compartido externo esté activado para los sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="89f22-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="89f22-115">Usar PowerShell para activar o desactivar el acceso de invitados</span><span class="sxs-lookup"><span data-stu-id="89f22-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="89f22-116">Descargue el módulo de PowerShell de Skype Empresarial Online en https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="89f22-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="89f22-117">Conecte una sesión de PowerShell al punto de conexión de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="89f22-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```powershell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="89f22-118">Compruebe la configuración y si `AllowGuestUser` es `$False`, use el cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para establecerlo en `$True`.</span><span class="sxs-lookup"><span data-stu-id="89f22-118">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="89f22-119">Ahora puede tener usuarios invitados en Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="89f22-119">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="89f22-120">Acceso de invitado frente a acceso externo</span><span class="sxs-lookup"><span data-stu-id="89f22-120">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
