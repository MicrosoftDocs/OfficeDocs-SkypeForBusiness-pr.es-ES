---
title: Gestionar acceso de los usuarios a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Aprenda a habilitar o deshabilitar el acceso a nivel de usuario por cada usuario.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7d30f5516ba0b44bc5ff854fcc9f5482fdf24c2
ms.sourcegitcommit: c12afd4dd5509a4552b2999430953273d36db039
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2018
ms.locfileid: "21779514"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="81f92-103">Gestionar acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81f92-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="81f92-104">En el nivel de usuario, acceso a Microsoft Teams puede habilitar o deshabilitar por usuario mediante la asignación o la eliminación de la licencia del producto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81f92-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="81f92-105">Actualmente, no hay ninguna opción de directiva para activar los equipos o un subconjunto de las características de los equipos, o desactivar en un nivel de usuario individual fuera de licencias.</span><span class="sxs-lookup"><span data-stu-id="81f92-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="81f92-106">Microsoft recomienda activar en los equipos de todos los usuarios de una compañía para que los equipos se pueden formar ecológicamente para proyectos y otras iniciativas dinámicos.</span><span class="sxs-lookup"><span data-stu-id="81f92-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="81f92-107">Incluso si se decide piloto, puede ser útil para mantener los equipos habilitados para todos los usuarios, pero sólo communications para el grupo piloto de usuarios de destino.</span><span class="sxs-lookup"><span data-stu-id="81f92-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="81f92-108">Administrar los equipos a través del centro de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="81f92-108">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="81f92-109">Licencias de nivel de usuario de los equipos se administran directamente a través de las interfaces de administración de usuario de Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="81f92-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="81f92-110">Un administrador puede asignar licencias a los nuevos usuarios cuando se crean nuevas cuentas de usuario o a los usuarios con cuentas existentes.</span><span class="sxs-lookup"><span data-stu-id="81f92-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="81f92-111">El administrador debe tener privilegios de administrador Global de Office 365 o administrador de usuario para administrar las licencias de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81f92-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="81f92-p103">Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="81f92-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="81f92-115">Una licencia de usuario de los equipos se puede deshabilitar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="81f92-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="81f92-116">Una vez que la licencia está deshabilitada, se impedirá el acceso de usuarios a Microsoft Teams y el usuario ya no podrán ver los equipos en la página principal y del iniciador de aplicación de Office 365.</span><span class="sxs-lookup"><span data-stu-id="81f92-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365, donde se ve Microsoft Teams seleccionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="81f92-118">Administrar a través de PowerShell</span><span class="sxs-lookup"><span data-stu-id="81f92-118">Manage via PowerShell</span></span>

<span data-ttu-id="81f92-119">Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81f92-119">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="81f92-120">El nombre del plan de servicio es TEAMS1 para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81f92-120">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="81f92-121">Para organizaciones de gobierno, el nombre del plan de servicio es TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="81f92-121">For Government the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="81f92-122">(Consulte [Deshabilitar el acceso a los servicios con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="81f92-122">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="81f92-123">**Ejemplo:** El siguiente es sólo un ejemplo rápido en cómo sería deshabilitar los equipos de todos los miembros de un tipo de licencia determinado.</span><span class="sxs-lookup"><span data-stu-id="81f92-123">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="81f92-124">Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.</span><span class="sxs-lookup"><span data-stu-id="81f92-124">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="81f92-125">Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="81f92-125">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="81f92-126">Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="81f92-126">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="81f92-127">Para deshabilitar los equipos de todos los usuarios con una licencia de activo para el plan con nombre, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="81f92-127">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="81f92-129">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="81f92-129">Decision Point</span></span>         |<ul><li><span data-ttu-id="81f92-130">¿Qué es la planeación de la organización de la incorporación de los equipos en toda la organización?</span><span class="sxs-lookup"><span data-stu-id="81f92-130">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="81f92-131">(Piloto o abrir)</span><span class="sxs-lookup"><span data-stu-id="81f92-131">(Pilot or Open)</span></span></li></ul>         |
|![Icono de Siguientes pasos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="81f92-133">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="81f92-133">Next Steps</span></span>         |<ul><li><span data-ttu-id="81f92-134">Si realiza la adopción a través de Piloto, decida si desea hacerlo a través de licencias o comunicación dirigida.</span><span class="sxs-lookup"><span data-stu-id="81f92-134">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="81f92-135">Dependiendo de la toma de decisiones, realice los pasos para asegurarse de que sólo los usuarios que tienen acceso los equipos (si es necesario) la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="81f92-135">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="81f92-136">Las instrucciones para que los usuarios que va a (o no) de documentos tienen acceso a los equipos.</span><span class="sxs-lookup"><span data-stu-id="81f92-136">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="81f92-137">Administrar los equipos en el nivel de inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="81f92-137">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

