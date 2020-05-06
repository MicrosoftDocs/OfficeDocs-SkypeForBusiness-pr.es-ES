---
title: Administrar el acceso de los usuarios a Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: Aprenda a administrar el acceso de los usuarios a los equipos asignando o quitando una licencia de Teams a los usuarios de su organización.
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ab8f68ef1c37fbb5cb724b322b4db0ee757b84
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042277"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="d90a3-103">Gestionar acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d90a3-103">Manage user access to Teams</span></span>

<span data-ttu-id="d90a3-104">Para administrar el acceso a los equipos en el nivel de usuario, asigne o quite una licencia de producto de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d90a3-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="d90a3-105">Cada usuario de su organización debe tener una licencia de Teams para poder usar Teams.</span><span class="sxs-lookup"><span data-stu-id="d90a3-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="d90a3-106">Puede asignar una licencia de Teams a los nuevos usuarios cuando se crean nuevas cuentas de usuario o a los usuarios con cuentas existentes.</span><span class="sxs-lookup"><span data-stu-id="d90a3-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="d90a3-107">De forma predeterminada, cuando un plan de licencias (por ejemplo, Microsoft 365 Enterprise E3 o Microsoft 365 Business Premium) se asigna a un usuario, se asigna automáticamente una licencia de Teams y el usuario habilita Teams.</span><span class="sxs-lookup"><span data-stu-id="d90a3-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="d90a3-108">Puede deshabilitar o habilitar Teams para un usuario si quita o asigna una licencia en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="d90a3-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="d90a3-109">Administra las licencias de Teams en el centro de administración de Microsoft 365 o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d90a3-109">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="d90a3-110">Para administrar las licencias, debe ser administrador global o administrador de administración de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d90a3-110">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="d90a3-111">Le recomendamos que habilite Teams para todos los usuarios, de modo que se puedan formar orgánicamente para proyectos y otras iniciativas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="d90a3-111">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="d90a3-112">Incluso si está ejecutando un proyecto piloto, puede que le resulte útil mantener equipos habilitados para todos los usuarios, pero solo las comunicaciones dirigidas al grupo piloto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d90a3-112">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d90a3-113">Usar el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d90a3-113">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d90a3-114">Use el centro de administración de Microsoft 365 para administrar licencias de Teams para usuarios individuales o conjuntos pequeños de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="d90a3-114">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="d90a3-115">Puede administrar las licencias de Teams en la página **licencias** (para un máximo de 20 usuarios a la vez) o en la página **usuarios activos** .</span><span class="sxs-lookup"><span data-stu-id="d90a3-115">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="d90a3-116">El método que elija dependerá de si desea administrar las licencias de producto para usuarios específicos o administrar licencias de usuario para productos específicos.</span><span class="sxs-lookup"><span data-stu-id="d90a3-116">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="d90a3-117">Si necesita administrar licencias de Teams para un gran número de usuarios, como cientos o miles de usuarios, [use PowerShell](#using-powershell) o [licencias basadas en grupos en Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="d90a3-117">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="d90a3-118">Asignar una licencia de Teams</span><span class="sxs-lookup"><span data-stu-id="d90a3-118">Assign a Teams license</span></span>

<span data-ttu-id="d90a3-119">Los pasos son diferentes dependiendo de si usa la página **licencias** o la página **usuarios activos** .</span><span class="sxs-lookup"><span data-stu-id="d90a3-119">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="d90a3-120">Para obtener instrucciones paso a paso, vea [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="d90a3-120">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Captura de pantalla de la licencia de Teams habilitada para un usuario](media/assign-teams-licenses-1.png)    | ![Captura de pantalla de la licencia de Teams habilitada para un usuario](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="d90a3-123">Quitar una licencia de Teams</span><span class="sxs-lookup"><span data-stu-id="d90a3-123">Remove a Teams license</span></span>

<span data-ttu-id="d90a3-124">Cuando quita una licencia de Teams de un usuario, Teams está deshabilitado para ese usuario y ya no verá equipos en el iniciador de aplicaciones o en la Página principal.</span><span class="sxs-lookup"><span data-stu-id="d90a3-124">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="d90a3-125">Para conocer los pasos detallados, vea [cancelar la asignación de licencias de usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span><span class="sxs-lookup"><span data-stu-id="d90a3-125">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Captura de pantalla de la licencia de Teams deshabilitada para un usuario](media/remove-teams-licenses-1.png)    | ![Captura de pantalla de la licencia de Teams deshabilitada para un usuario](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="d90a3-128">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90a3-128">Using PowerShell</span></span>

<span data-ttu-id="d90a3-129">Usar PowerShell para administrar licencias de Teams para usuarios en bloque.</span><span class="sxs-lookup"><span data-stu-id="d90a3-129">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="d90a3-130">Habilite y deshabilite Teams mediante PowerShell de la misma manera en que lo haría para cualquier otra licencia de plan de servicio.</span><span class="sxs-lookup"><span data-stu-id="d90a3-130">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="d90a3-131">Necesitará los identificadores de los planes de servicio para Teams, que son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d90a3-131">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="d90a3-132">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="d90a3-132">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="d90a3-133">Microsoft Teams para GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="d90a3-133">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="d90a3-134">Microsoft Teams para DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="d90a3-134">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="d90a3-135">Asignar licencias de Teams en masa</span><span class="sxs-lookup"><span data-stu-id="d90a3-135">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="d90a3-136">Para conocer los pasos detallados, vea [asignar licencias a cuentas de usuario con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d90a3-136">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="d90a3-137">Quitar licencias de Teams en masa</span><span class="sxs-lookup"><span data-stu-id="d90a3-137">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="d90a3-138">Para conocer los pasos detallados, vea [deshabilitar el acceso a servicios con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) y [deshabilitar el acceso a servicios al asignar licencias de usuario](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span><span class="sxs-lookup"><span data-stu-id="d90a3-138">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="d90a3-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d90a3-139">Example</span></span> 

<span data-ttu-id="d90a3-140">A continuación se describe un ejemplo de cómo usar los cmdlets [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) y [set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) para deshabilitar Teams para los usuarios que tienen un plan de licencias específico.</span><span class="sxs-lookup"><span data-stu-id="d90a3-140">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="d90a3-141">Por ejemplo, siga estos pasos para deshabilitar primero Teams para todos los usuarios que tengan un plan de licencias determinado.</span><span class="sxs-lookup"><span data-stu-id="d90a3-141">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="d90a3-142">A continuación, habilite Teams para cada usuario individual que debería tener acceso a teams.</span><span class="sxs-lookup"><span data-stu-id="d90a3-142">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d90a3-143">El cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) habilitará todos los servicios que se hayan deshabilitado anteriormente, a menos que se identifiquen explícitamente en el script personalizado.</span><span class="sxs-lookup"><span data-stu-id="d90a3-143">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="d90a3-144">Por ejemplo, si desea dejar Exchange y Sway deshabilitados, y deshabilitar también Teams, tendrá que incluirlos en la secuencia de comandos o Exchange y Sway estarán habilitados para los usuarios que haya identificado.</span><span class="sxs-lookup"><span data-stu-id="d90a3-144">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="d90a3-145">Ejecute el siguiente comando para mostrar todos los planes de licencias disponibles en su organización.</span><span class="sxs-lookup"><span data-stu-id="d90a3-145">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="d90a3-146">Para obtener más información, vea [ver licencias y servicios con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d90a3-146">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="d90a3-147">Ejecute los siguientes comandos, donde \<CompanyName: License> es el nombre de su organización y el identificador del plan de licencias que recuperó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="d90a3-147">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="d90a3-148">Por ejemplo, ContosoSchool: ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="d90a3-148">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="d90a3-149">Ejecute el siguiente comando para deshabilitar Teams para todos los usuarios que tienen una licencia activa para el plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="d90a3-149">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="d90a3-150">Administrar equipos en el nivel de la organización</span><span class="sxs-lookup"><span data-stu-id="d90a3-150">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="d90a3-151">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d90a3-151">Related topics</span></span>

- [<span data-ttu-id="d90a3-152">Licencias de complementos de Teams</span><span class="sxs-lookup"><span data-stu-id="d90a3-152">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="d90a3-153">Asignar licencias de complementos de Teams</span><span class="sxs-lookup"><span data-stu-id="d90a3-153">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="d90a3-154">Ver licencias y servicios con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90a3-154">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="d90a3-155">Nombres de productos e identificadores de planes de servicio para licencias</span><span class="sxs-lookup"><span data-stu-id="d90a3-155">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="d90a3-156">Referencia de SKU de educación</span><span class="sxs-lookup"><span data-stu-id="d90a3-156">Education SKU reference</span></span>](sku-reference-edu.md)