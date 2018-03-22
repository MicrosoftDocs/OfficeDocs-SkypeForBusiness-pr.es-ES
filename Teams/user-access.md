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
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="08ed0-103">Gestionar acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08ed0-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="08ed0-104">En el nivel de usuario, acceso a Teams de Microsoft puede habilitar o deshabilitar en cada usuario asignar o quitando la licencia del producto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08ed0-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="08ed0-105">Actualmente, no hay ninguna opción de directiva para activar equipos o un subconjunto de características de los equipos, o desactivar en un nivel de usuario individual fuera de licencias.</span><span class="sxs-lookup"><span data-stu-id="08ed0-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="08ed0-106">Microsoft recomienda activar equipos para todos los usuarios de una empresa para que los equipos se pueden formar orgánicamente para proyectos y otras iniciativas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="08ed0-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="08ed0-107">Incluso si decide a piloto, puede ser útil mantener equipos habilitados para todos los usuarios, pero sólo comunicaciones con el grupo piloto de usuarios de destino.</span><span class="sxs-lookup"><span data-stu-id="08ed0-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-directly-through-the-office-365-admin-center"></a><span data-ttu-id="08ed0-108">Administrar directamente a través del centro de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="08ed0-108">Manage directly through the Office 365 admin center</span></span>

<span data-ttu-id="08ed0-109">Licencias de nivel de usuario de los equipos se administran directamente a través de las interfaces de administración de Office 365 admin center usuario.</span><span class="sxs-lookup"><span data-stu-id="08ed0-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="08ed0-110">Un administrador puede asignar licencias a nuevos usuarios cuando se crean nuevas cuentas de usuario o los usuarios con cuentas existentes.</span><span class="sxs-lookup"><span data-stu-id="08ed0-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="08ed0-111">El administrador debe tener privilegios de administrador del usuario o de administrador Global de Office 365 para administrar las licencias de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08ed0-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="08ed0-p103">Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="08ed0-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="08ed0-115">Una licencia de usuario de equipos puede desactivarse en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="08ed0-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="08ed0-116">Una vez que la licencia se deshabilita, se impedirá el acceso de los usuarios a Teams de Microsoft y el usuario ya no podrá ver los equipos en la página principal y el iniciador de la aplicación de Office 365.</span><span class="sxs-lookup"><span data-stu-id="08ed0-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365, donde se ve Microsoft Teams seleccionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="08ed0-118">Gestionar a través de PowerShell</span><span class="sxs-lookup"><span data-stu-id="08ed0-118">Manage via PowerShell</span></span>

<span data-ttu-id="08ed0-119">Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="08ed0-119">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="08ed0-120">El nombre del plan de servicio es TEAMS1 para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08ed0-120">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="08ed0-121">(Consulte [Deshabilitar el acceso a los servicios con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="08ed0-121">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="08ed0-122">**Ejemplo:** A continuación es sólo una muestra rápida sobre cómo deshabilitaría equipos para todos los miembros de un tipo de licencia particular.</span><span class="sxs-lookup"><span data-stu-id="08ed0-122">**Sample:** Below is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="08ed0-123">Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.</span><span class="sxs-lookup"><span data-stu-id="08ed0-123">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="08ed0-124">Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="08ed0-124">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="08ed0-125">Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="08ed0-125">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="08ed0-126">Para deshabilitar los equipos para todos los usuarios con una licencia activa para su plan con nombre, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="08ed0-126">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="08ed0-128">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="08ed0-128">Decision Point</span></span>         |<ul><li><span data-ttu-id="08ed0-129">¿Cuál es el plan de la organización para la incorporación de equipos en toda la organización?</span><span class="sxs-lookup"><span data-stu-id="08ed0-129">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="08ed0-130">(Prueba piloto o abrir)</span><span class="sxs-lookup"><span data-stu-id="08ed0-130">(Pilot or Open)</span></span></li></ul>         |
|![Icono de Siguientes pasos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="08ed0-132">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="08ed0-132">Next Steps</span></span>         |<ul><li><span data-ttu-id="08ed0-133">Si realiza la adopción a través de Piloto, decida si desea hacerlo a través de licencias o comunicación dirigida.</span><span class="sxs-lookup"><span data-stu-id="08ed0-133">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="08ed0-134">Dependiendo de la decisión, tome pasos para asegurarse de que sólo los usuarios autorizados para tener acceso a los equipos (si es necesario) del piloto.</span><span class="sxs-lookup"><span data-stu-id="08ed0-134">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="08ed0-135">Documentar las directrices para que los usuarios que serán (o no) tener acceso a los equipos.</span><span class="sxs-lookup"><span data-stu-id="08ed0-135">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a><span data-ttu-id="08ed0-136">Gestionar a través de interruptor del nivel del Sku de Office</span><span class="sxs-lookup"><span data-stu-id="08ed0-136">Manage via Office Sku level switch</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  <span data-ttu-id="08ed0-137">Inicie sesión en el [Centro de administración de Office 365](https://go.microsoft.com/fwlink/?linkid=854614) con una cuenta que tenga privilegios de administrador global.</span><span class="sxs-lookup"><span data-stu-id="08ed0-137">Sign in to the [Office 365 Admin center](https://go.microsoft.com/fwlink/?linkid=854614) with an account that has Global Administrator privileges.</span></span>

2.  <span data-ttu-id="08ed0-138">Vaya a **Configuración** > **Servicios y complementos**.</span><span class="sxs-lookup"><span data-stu-id="08ed0-138">Go to **Settings** > **Services & add-ins**.</span></span>

    ![<span data-ttu-id="08ed0-139">Captura de pantalla de la sección Configuración del Centro de administración de Office 365 con Servicios y complementos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="08ed0-139">Screenshot of the Settings section in the Office 365 admin center with Services & add-ins selected.</span></span> ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  <span data-ttu-id="08ed0-140">En la página Servicios y complementos, haga clic en **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="08ed0-140">On the Services & add-ins page, click **Microsoft Teams**.</span></span>

    ![Captura de pantalla de la página Servicios y complementos con Microsoft Teams seleccionado.](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  <span data-ttu-id="08ed0-142">Para activar Teams para la organización, use el selector de licencias, seleccione cada licencia, después establezca el botón de alternancia en **Activado** y finalmente haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="08ed0-142">To turn on Teams for the organization use the license picker and select each license then set the toggle to **On** and then click **Save**.</span></span>

    ![Captura de pantalla de la página de configuración de Microsoft Teams donde se ve el botón de alternancia establecido en Activado para habilitar Microsoft Teams.](media/Services-and-addins-control-Microsoft-Teams.PNG)
