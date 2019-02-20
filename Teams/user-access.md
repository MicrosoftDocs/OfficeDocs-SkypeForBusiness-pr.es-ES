---
title: Gestionar acceso de los usuarios a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: ritikag
search.appverid: MET150
description: Aprenda a habilitar o deshabilitar el acceso a nivel de usuario por cada usuario.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdaa51072df7ffeeb2aeb2c66e73f07b0c0c0569
ms.sourcegitcommit: d8a68433949edfbbece628dd0e1c0ce9205ba0a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087823"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="249ad-103">Gestionar acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="249ad-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="249ad-104">En el nivel de usuario, acceso a Microsoft Teams puede habilitar o deshabilitar por usuario mediante la asignación o la eliminación de la licencia del producto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="249ad-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="249ad-105">Actualmente, no hay ninguna opción de directiva para activar los equipos o un subconjunto de las características de los equipos, o desactivar en un nivel de usuario individual fuera de licencias.</span><span class="sxs-lookup"><span data-stu-id="249ad-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="249ad-106">Microsoft recomienda activar en los equipos de todos los usuarios de una compañía para que los equipos se pueden formar ecológicamente para proyectos y otras iniciativas dinámicos.</span><span class="sxs-lookup"><span data-stu-id="249ad-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="249ad-107">Incluso si se decide piloto, puede ser útil para mantener los equipos habilitados para todos los usuarios, pero sólo communications para el grupo piloto de usuarios de destino.</span><span class="sxs-lookup"><span data-stu-id="249ad-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="249ad-108">Administrar los equipos a través del centro de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="249ad-108">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="249ad-109">Licencias de nivel de usuario de los equipos se administran directamente a través de las interfaces de administración de usuario de Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="249ad-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="249ad-110">Un administrador puede asignar licencias a los nuevos usuarios cuando se crean nuevas cuentas de usuario o a los usuarios con cuentas existentes.</span><span class="sxs-lookup"><span data-stu-id="249ad-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="249ad-111">El administrador debe tener privilegios de administrador Global de Office 365 o administrador de usuario para administrar las licencias de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="249ad-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="249ad-p103">Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="249ad-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="249ad-115">Una licencia de usuario de los equipos se puede deshabilitar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="249ad-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="249ad-116">Una vez que la licencia está deshabilitada, se impedirá el acceso de usuarios a Microsoft Teams y el usuario ya no podrán ver los equipos en la página principal y del iniciador de aplicación de Office 365.</span><span class="sxs-lookup"><span data-stu-id="249ad-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365, donde se ve Microsoft Teams seleccionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="249ad-118">Administrar a través de PowerShell</span><span class="sxs-lookup"><span data-stu-id="249ad-118">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="249ad-119">Nuevo MsolLicenseOptions permitirá a todos los servicios que estaban deshabilitados a menos que explictitly identitied en la secuencia de comandos personalizada.</span><span class="sxs-lookup"><span data-stu-id="249ad-119">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="249ad-120">Por ejemplo, si deseara deje ambos & Exchange balanceo deshabilitado mientras además deshabilitar los equipos, necesitará incluya esto en la secuencia de comandos o ambos & Exchange balanceo se habilitará para aquellos usuarios que ha identificado.</span><span class="sxs-lookup"><span data-stu-id="249ad-120">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="249ad-121">Si desea utilizar una interfaz gráfica de usuario para administrar esta funcionalidad, vea: [informes de licencia de Office 365 y la herramienta de administración-asignar licencias de quitar de forma masiva](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="249ad-121">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="249ad-122">Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="249ad-122">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="249ad-123">El nombre del plan de servicio es TEAMS1 para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="249ad-123">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="249ad-124">GCC el nombre del plan de servicio es TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="249ad-124">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="249ad-125">Para GCC alta el nombre del plan de servicio es TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="249ad-125">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="249ad-126">DoD el nombre del plan de servicio es TEAMS_DOD (Véase [Deshabilitar acceso a los servicios con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información.)</span><span class="sxs-lookup"><span data-stu-id="249ad-126">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="249ad-127">**Ejemplo:** El siguiente es sólo un ejemplo rápido en cómo sería deshabilitar los equipos de todos los miembros de un tipo de licencia determinado.</span><span class="sxs-lookup"><span data-stu-id="249ad-127">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="249ad-128">Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.</span><span class="sxs-lookup"><span data-stu-id="249ad-128">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="249ad-129">Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="249ad-129">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="249ad-130">Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="249ad-130">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="249ad-131">Para deshabilitar los equipos de todos los usuarios con una licencia de activo para el plan con nombre, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="249ad-131">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="249ad-133">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="249ad-133">Decision Point</span></span>         |<ul><li><span data-ttu-id="249ad-134">¿Qué es la planeación de la organización de la incorporación de los equipos en toda la organización?</span><span class="sxs-lookup"><span data-stu-id="249ad-134">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="249ad-135">(Piloto o abrir)</span><span class="sxs-lookup"><span data-stu-id="249ad-135">(Pilot or Open)</span></span></li></ul>         |
|![Icono de Siguientes pasos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="249ad-137">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="249ad-137">Next Steps</span></span>         |<ul><li><span data-ttu-id="249ad-138">Si incorporación mediante una prueba piloto cerrada, decida si desea hacerlo a través de licencias, o dirigidas comunicación.</span><span class="sxs-lookup"><span data-stu-id="249ad-138">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="249ad-139">Dependiendo de la toma de decisiones, realice los pasos para asegurarse de que sólo los usuarios que tienen acceso los equipos (si es necesario) la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="249ad-139">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="249ad-140">Las instrucciones para que los usuarios que va a (o no) de documentos tienen acceso a los equipos.</span><span class="sxs-lookup"><span data-stu-id="249ad-140">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="249ad-141">Administrar los equipos en el nivel de inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="249ad-141">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

