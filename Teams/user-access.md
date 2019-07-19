---
title: Administrar el acceso de los usuarios a Microsoft Teams
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
ms.openlocfilehash: 0858373bebabdb9df6c8a00463ac5a3db1834843
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792138"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="5a178-103">Administrar el acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a178-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="5a178-104">A nivel de usuario, el acceso a Microsoft Teams puede habilitarse o deshabilitarse por usuario, asignando o quitando la licencia de producto de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5a178-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="5a178-105">Use las directivas de mensajería, que se controlan desde el centro de administración de Teams, para controlar qué características de mensajería y canales están disponibles para los usuarios en Teams.</span><span class="sxs-lookup"><span data-stu-id="5a178-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="5a178-106">Puede usar la directiva predeterminada o bien crear una o más directivas de mensajería personalizadas para los miembros de su organización.</span><span class="sxs-lookup"><span data-stu-id="5a178-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="5a178-107">Para obtener más información, lea [Administrar directivas de mensajería en Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5a178-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="5a178-108">Microsoft recomienda que Teams se habilite para todos los usuarios de una empresa, de modo que los equipos puedan formarse de manera orgánica para proyectos y otras iniciativas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="5a178-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="5a178-109">Incluso si decide realizar un piloto, podría ser útil mantener Teams habilitado para todos los usuarios, pero solo enfocarse en las comunicaciones con el grupo piloto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="5a178-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="5a178-110">Administrar equipos a través del centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a178-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="5a178-111">Las licencias de nivel de usuario de Teams se administran directamente a través de las interfaces de administración de usuarios del centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a178-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="5a178-112">Un administrador puede asignar licencias a nuevos usuarios al crear cuentas de usuario, así como a los usuarios con cuentas existentes.</span><span class="sxs-lookup"><span data-stu-id="5a178-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="5a178-113">El administrador debe tener privilegios de Administrador global de Office 365 o de Administración de usuarios para administrar las licencias de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5a178-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="5a178-p104">Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="5a178-p104">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de pantalla de la sección licencias de producto en el centro de administración.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="5a178-117">Las licencias de usuario de Teams se pueden deshabilitar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="5a178-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="5a178-118">Una vez que la licencia se deshabilita, se evitará el acceso de los usuarios a Microsoft Teams y el usuario ya no podrá ver Teams en el iniciador de aplicaciones y la página de inicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5a178-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de pantalla que muestra equipos seleccionados en la sección licencias de producto.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="5a178-120">Administrar mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a178-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a178-121">New-MsolLicenseOptions habilitará todos los servicios que estaban deshabilitados a menos que se especifiquen explícitamente en el script personalizado.</span><span class="sxs-lookup"><span data-stu-id="5a178-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="5a178-122">Por ejemplo, si quiere dejar Exchange y Sway deshabilitados mientras a la vez que deshabilita Teams, tendría que incluir esto en el script o tanto Exchange como Sway se habilitarán para los usuarios que ha identificado.</span><span class="sxs-lookup"><span data-stu-id="5a178-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="5a178-123">Si quiere, puede utilizar una GUI para administrar esta funcionalidad, consulte: [Informes de licencia de Office 365 y herramienta de administración: asignar o quitar licencias de forma masiva](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="5a178-123">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="5a178-124">Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5a178-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="5a178-125">El nombre del plan de servicio es TEAMS1 para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5a178-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="5a178-126">Para GCC el nombre del plan de servicio es TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="5a178-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="5a178-127">Para GCC High el nombre del plan de servicio es TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="5a178-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="5a178-128">Para DoD el nombre del plan de servicio es TEAMS_DOD (consulte [Deshabilitar el acceso a servicios con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="5a178-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="5a178-129">**Muestra:** a continuación encontrará una muestra rápida de cómo se deshabilita Teams para todos los miembros en un tipo de licencia particular.</span><span class="sxs-lookup"><span data-stu-id="5a178-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="5a178-130">Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.</span><span class="sxs-lookup"><span data-stu-id="5a178-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="5a178-131">Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5a178-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="5a178-132">Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="5a178-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="5a178-133">Para deshabilitar Teams para todos los usuarios que tengan una licencia activa para su plan, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5a178-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="5a178-135">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="5a178-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="5a178-136">¿Cuál es el plan de su organización para comenzar a usar Teams en toda la organización?</span><span class="sxs-lookup"><span data-stu-id="5a178-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="5a178-137">(Piloto o abierto)</span><span class="sxs-lookup"><span data-stu-id="5a178-137">(Pilot or Open)</span></span></li></ul>         |
|![Un icono que representa los pasos siguientes](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="5a178-139">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="5a178-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="5a178-140">Si realiza la adopción a través de Piloto, decida si desea hacerlo a través de licencias o comunicación dirigida.</span><span class="sxs-lookup"><span data-stu-id="5a178-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="5a178-141">Según su decisión, realice los pasos para asegurarse de que solo los usuarios piloto puedan acceder a Teams (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="5a178-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="5a178-142">Documente qué usuarios tendrán (o no tendrán) acceso a Teams.</span><span class="sxs-lookup"><span data-stu-id="5a178-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="5a178-143">Administrar Teams en el nivel de espacio empresarial de Office 365</span><span class="sxs-lookup"><span data-stu-id="5a178-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

