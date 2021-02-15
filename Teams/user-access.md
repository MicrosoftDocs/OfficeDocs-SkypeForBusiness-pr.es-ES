---
title: Administrar el acceso de los usuarios a Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso de los usuarios a Teams asignando o quitando una licencia de Teams a los usuarios de su organización.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d49b27de8fe6c6d13ef6ac626764b13e1fe36a0
ms.sourcegitcommit: 4e648c3dd71d9c38cbcb81fab9e8cb9d241fe79c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871019"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="44ade-103">Gestionar acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44ade-103">Manage user access to Teams</span></span>

<span data-ttu-id="44ade-104">Para administrar el acceso a Teams en el nivel de usuario, asigne o quite una licencia de producto de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="44ade-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="44ade-105">Excepto para unirse a reuniones de Teams de forma anónima, cada usuario de su organización debe tener una licencia de Teams para poder usar Teams.</span><span class="sxs-lookup"><span data-stu-id="44ade-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="44ade-106">Puede asignar una licencia de Teams para nuevos usuarios cuando se crean cuentas de usuario nuevas o para usuarios con cuentas existentes.</span><span class="sxs-lookup"><span data-stu-id="44ade-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="44ade-107">De forma predeterminada, cuando se asigna a un usuario un plan de licencias (por ejemplo, Microsoft 365 Enterprise E3 o Microsoft 365 Business Premium), se asigna automáticamente una licencia de Teams y se habilita al usuario para Teams.</span><span class="sxs-lookup"><span data-stu-id="44ade-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="44ade-108">Puede deshabilitar o habilitar Teams para un usuario quitando o asignando una licencia en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="44ade-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="44ade-109">Use las directivas de mensajería, administradas desde el Centro de administración <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de Teams,</a>para controlar las características de mensajería de canal y chat que están disponibles para los usuarios en Teams.</span><span class="sxs-lookup"><span data-stu-id="44ade-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="44ade-110">Puede usar la directiva predeterminada o bien crear una o más directivas de mensajería personalizadas para los miembros de su organización.</span><span class="sxs-lookup"><span data-stu-id="44ade-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="44ade-111">Para obtener más información, lea [Administrar directivas de mensajería en Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="44ade-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="44ade-112">Puede administrar las licencias de Teams en el Centro de administración de Microsoft 365 o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44ade-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="44ade-113">Debe ser administrador global o administrador de administración de usuarios para poder administrar las licencias.</span><span class="sxs-lookup"><span data-stu-id="44ade-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="44ade-114">Le recomendamos que habilite Teams para todos los usuarios para que los equipos se forme de forma organica para proyectos y otras iniciativas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="44ade-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="44ade-115">Incluso si está ejecutando un piloto, puede ser útil mantener Teams habilitado para todos los usuarios, pero solo dirigir las comunicaciones al grupo piloto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="44ade-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="44ade-116">Uso del Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44ade-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="44ade-117">Las licencias a nivel de usuario de Teams se administran directamente a través de las interfaces de administración de usuarios del Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44ade-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="44ade-118">Un administrador puede asignar licencias a nuevos usuarios al crear cuentas de usuario, así como a los usuarios con cuentas existentes.</span><span class="sxs-lookup"><span data-stu-id="44ade-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="44ade-119">El administrador debe tener privilegios de Administrador global o Administrador de administración de usuarios para poder administrar las licencias de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="44ade-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="44ade-120">Use el Centro de administración de Microsoft 365 para administrar las licencias de Teams para usuarios individuales o conjuntos pequeños de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="44ade-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="44ade-121">Puede administrar las licencias  de Teams en la página Licencias (para un máximo de 20 usuarios a la vez) o la página **Usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="44ade-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="44ade-122">El método que elija dependerá de si desea administrar las licencias de producto para usuarios específicos o administrar licencias de usuario para productos específicos.</span><span class="sxs-lookup"><span data-stu-id="44ade-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="44ade-123">Si necesita administrar licencias de Teams para un gran número de usuarios, como cientos o miles de usuarios, [use PowerShell](#using-powershell) o licencias basadas en grupos en [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="44ade-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="44ade-124">Asignar una licencia de Teams</span><span class="sxs-lookup"><span data-stu-id="44ade-124">Assign a Teams license</span></span>

<span data-ttu-id="44ade-125">Los pasos son diferentes dependiendo de si usa la página Licencias **o** la página **Usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="44ade-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="44ade-126">Para obtener instrucciones detalladas, consulte [Asignar licencias a usuarios.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="44ade-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Captura de pantalla de la licencia de Teams habilitada para un usuario](media/assign-teams-licenses-1.png)    | ![Captura de pantalla de la licencia de Teams habilitada para un usuario](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="44ade-129">Quitar una licencia de Teams</span><span class="sxs-lookup"><span data-stu-id="44ade-129">Remove a Teams license</span></span>

<span data-ttu-id="44ade-130">Al quitar una licencia de Teams a un usuario, Teams está deshabilitado para ese usuario y ya no verá Teams en el iniciador de aplicaciones o la página principal.</span><span class="sxs-lookup"><span data-stu-id="44ade-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="44ade-131">Para conocer los pasos detallados, consulte [La desasignación de licencias de usuarios.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)</span><span class="sxs-lookup"><span data-stu-id="44ade-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Captura de pantalla de la licencia de Teams deshabilitada para un usuario](media/remove-teams-licenses-1.png)    | ![Captura de pantalla de la licencia de Teams deshabilitada para un usuario](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="44ade-134">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="44ade-134">Using PowerShell</span></span>

<span data-ttu-id="44ade-135">Use PowerShell para administrar las licencias de Teams de los usuarios en masa.</span><span class="sxs-lookup"><span data-stu-id="44ade-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="44ade-136">Puede habilitar y deshabilitar Teams a través de PowerShell del mismo modo que lo haría con cualquier otra licencia de plan de servicio.</span><span class="sxs-lookup"><span data-stu-id="44ade-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="44ade-137">Necesitará los identificadores para los planes de servicio para Teams, que son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="44ade-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="44ade-138">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="44ade-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="44ade-139">Microsoft Teams para GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="44ade-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="44ade-140">Microsoft Teams para DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="44ade-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="44ade-141">Asignar licencias de Teams en masa</span><span class="sxs-lookup"><span data-stu-id="44ade-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="44ade-142">Para conocer los pasos detallados, consulte [Asignar licencias a cuentas de usuario con PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="44ade-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="44ade-143">Quitar licencias de Teams en masa</span><span class="sxs-lookup"><span data-stu-id="44ade-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="44ade-144">Para conocer los pasos detallados, vea Deshabilitar el acceso a los servicios con [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) y Deshabilitar el acceso a los servicios [al asignar licencias de usuario.](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)</span><span class="sxs-lookup"><span data-stu-id="44ade-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="44ade-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44ade-145">Example</span></span> 

<span data-ttu-id="44ade-146">El siguiente es un ejemplo de cómo usar los [cmdlets New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) y [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) para deshabilitar Teams para los usuarios que tienen un plan de licencias específico.</span><span class="sxs-lookup"><span data-stu-id="44ade-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="44ade-147">Por ejemplo, siga estos pasos para deshabilitar primero Teams para todos los usuarios que tienen un plan de licencias determinado.</span><span class="sxs-lookup"><span data-stu-id="44ade-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="44ade-148">Después, habilite Teams para cada usuario individual que deba tener acceso a Teams.</span><span class="sxs-lookup"><span data-stu-id="44ade-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44ade-149">El [cmdlet New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) habilitará todos los servicios previamente deshabilitados a menos que se identifiquen explícitamente en el script personalizado.</span><span class="sxs-lookup"><span data-stu-id="44ade-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="44ade-150">Por ejemplo, si quiere dejar Exchange y Sway deshabilitados mientras se deshabilita Teams, tendrá que incluirlo en el script o Exchange y Sway se habilitarán para los usuarios que identificó.</span><span class="sxs-lookup"><span data-stu-id="44ade-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="44ade-151">Ejecute el siguiente comando para mostrar todos los planes de licencias disponibles en su organización.</span><span class="sxs-lookup"><span data-stu-id="44ade-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="44ade-152">Para obtener más información, [vea Ver licencias y servicios con PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="44ade-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="44ade-153">Ejecute los comandos siguientes, donde se encuentra el nombre de la organización y el identificador del plan de licencias que resalte \<CompanyName:License> en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="44ade-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="44ade-154">Por ejemplo, ContosoSchool:ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="44ade-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="44ade-155">Ejecute el siguiente comando para deshabilitar Teams para todos los usuarios que tienen una licencia activa para el plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="44ade-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="44ade-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="44ade-156">Related topics</span></span>

- [<span data-ttu-id="44ade-157">Licencias de complementos de Teams</span><span class="sxs-lookup"><span data-stu-id="44ade-157">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="44ade-158">Asignar licencias de complementos de Teams</span><span class="sxs-lookup"><span data-stu-id="44ade-158">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="44ade-159">Ver licencias y servicios con PowerShell</span><span class="sxs-lookup"><span data-stu-id="44ade-159">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="44ade-160">Nombres de productos e identificadores de planes de servicio para licencias</span><span class="sxs-lookup"><span data-stu-id="44ade-160">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="44ade-161">Referencia de SKU para educación</span><span class="sxs-lookup"><span data-stu-id="44ade-161">Education SKU reference</span></span>](sku-reference-edu.md)
