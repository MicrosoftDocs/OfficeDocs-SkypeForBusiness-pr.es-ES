---
title: Gestionar acceso de los usuarios a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Aprenda a habilitar o deshabilitar el acceso a nivel de usuario por cada usuario.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83d2b0710b811431546f0df9931d3a0b867d2b2b
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "30683887"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="64cb9-103">Gestionar acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64cb9-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="64cb9-104">En el nivel de usuario, acceso a Microsoft Teams puede habilitar o deshabilitar por usuario mediante la asignación o la eliminación de la licencia del producto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64cb9-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="64cb9-105">Use las directivas de mensajería, administradas desde el centro de administración de equipos, para controlar qué chat y canal de características de mensajería están disponibles para los usuarios en los equipos.</span><span class="sxs-lookup"><span data-stu-id="64cb9-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="64cb9-106">Puede usar la directiva predeterminada o crear una o varias directivas de mensajería personalizadas para las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="64cb9-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="64cb9-107">Para obtener más información, lea [Administrar directivas de mensajería en los equipos](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="64cb9-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="64cb9-108">Microsoft recomienda activar en los equipos de todos los usuarios de una compañía para que los equipos se pueden formar ecológicamente para proyectos y otras iniciativas dinámicos.</span><span class="sxs-lookup"><span data-stu-id="64cb9-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="64cb9-109">Incluso si se decide piloto, puede ser útil para mantener los equipos habilitados para todos los usuarios, pero sólo communications para el grupo piloto de usuarios de destino.</span><span class="sxs-lookup"><span data-stu-id="64cb9-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="64cb9-110">Administrar los equipos a través del centro de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="64cb9-110">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="64cb9-111">Licencias de nivel de usuario de los equipos se administran directamente a través de las interfaces de administración de usuario de Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="64cb9-111">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="64cb9-112">Un administrador puede asignar licencias a los nuevos usuarios cuando se crean nuevas cuentas de usuario o a los usuarios con cuentas existentes.</span><span class="sxs-lookup"><span data-stu-id="64cb9-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="64cb9-113">El administrador debe tener privilegios de administrador Global de Office 365 o administrador de usuario para administrar las licencias de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64cb9-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="64cb9-p104">Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="64cb9-p104">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="64cb9-117">Una licencia de usuario de los equipos se puede deshabilitar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="64cb9-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="64cb9-118">Una vez que la licencia está deshabilitada, se impedirá el acceso de usuarios a Microsoft Teams y el usuario ya no podrán ver los equipos en la página principal y del iniciador de aplicación de Office 365.</span><span class="sxs-lookup"><span data-stu-id="64cb9-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365, donde se ve Microsoft Teams seleccionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="64cb9-120">Administrar a través de PowerShell</span><span class="sxs-lookup"><span data-stu-id="64cb9-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64cb9-121">Nuevo MsolLicenseOptions permitirá a todos los servicios que estaban deshabilitados a menos que explictitly identitied en la secuencia de comandos personalizada.</span><span class="sxs-lookup"><span data-stu-id="64cb9-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="64cb9-122">Por ejemplo, si deseara deje ambos & Exchange balanceo deshabilitado mientras además deshabilitar los equipos, necesitará incluya esto en la secuencia de comandos o ambos & Exchange balanceo se habilitará para aquellos usuarios que ha identificado.</span><span class="sxs-lookup"><span data-stu-id="64cb9-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="64cb9-123">Si desea utilizar una interfaz gráfica de usuario para administrar esta funcionalidad, vea: [informes de licencia de Office 365 y la herramienta de administración-asignar licencias de quitar de forma masiva](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="64cb9-123">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="64cb9-124">Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="64cb9-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="64cb9-125">El nombre del plan de servicio es TEAMS1 para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64cb9-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="64cb9-126">GCC el nombre del plan de servicio es TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="64cb9-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="64cb9-127">Para GCC alta el nombre del plan de servicio es TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="64cb9-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="64cb9-128">DoD el nombre del plan de servicio es TEAMS_DOD (Véase [Deshabilitar acceso a los servicios con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información.)</span><span class="sxs-lookup"><span data-stu-id="64cb9-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="64cb9-129">**Ejemplo:** El siguiente es sólo un ejemplo rápido en cómo sería deshabilitar los equipos de todos los miembros de un tipo de licencia determinado.</span><span class="sxs-lookup"><span data-stu-id="64cb9-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="64cb9-130">Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.</span><span class="sxs-lookup"><span data-stu-id="64cb9-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="64cb9-131">Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="64cb9-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="64cb9-132">Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="64cb9-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="64cb9-133">Para deshabilitar los equipos de todos los usuarios con una licencia de activo para el plan con nombre, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="64cb9-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="64cb9-135">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="64cb9-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="64cb9-136">¿Qué es la planeación de la organización de la incorporación de los equipos en toda la organización?</span><span class="sxs-lookup"><span data-stu-id="64cb9-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="64cb9-137">(Piloto o abrir)</span><span class="sxs-lookup"><span data-stu-id="64cb9-137">(Pilot or Open)</span></span></li></ul>         |
|![Icono de Siguientes pasos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="64cb9-139">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="64cb9-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="64cb9-140">Si incorporación mediante una prueba piloto cerrada, decida si desea hacerlo a través de licencias, o dirigidas comunicación.</span><span class="sxs-lookup"><span data-stu-id="64cb9-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="64cb9-141">Dependiendo de la toma de decisiones, realice los pasos para asegurarse de que sólo los usuarios que tienen acceso los equipos (si es necesario) la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="64cb9-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="64cb9-142">Las instrucciones para que los usuarios que va a (o no) de documentos tienen acceso a los equipos.</span><span class="sxs-lookup"><span data-stu-id="64cb9-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="64cb9-143">Administrar los equipos en el nivel de inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="64cb9-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

