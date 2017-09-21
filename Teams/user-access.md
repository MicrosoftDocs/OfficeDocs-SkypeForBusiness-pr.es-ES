---
title: "Gestionar el acceso de los usuarios a Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: Aprenda a habilitar o deshabilitar el acceso a nivel de usuario por cada usuario.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: be6ceeef286b2346464bcd05d51ea5faf0e54545
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="f3b69-103">Gestionar acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3b69-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="f3b69-104">A nivel de usuario, el acceso a Microsoft Teams puede habilitarse o deshabilitarse por usuario, asignando o quitando la licencia de producto de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3b69-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="f3b69-105">Actualmente, no hay opciones de directiva para activar a desactivar características, o un subconjunto de características, de Microsoft Teams a nivel de un usuario individual fuera de la licencia.</span><span class="sxs-lookup"><span data-stu-id="f3b69-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>

| | |
|---------|---------|
|![](media/Manage_user_access_to_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="f3b69-106">Nota</span><span class="sxs-lookup"><span data-stu-id="f3b69-106">Note</span></span> |<span data-ttu-id="f3b69-p101">Microsoft recomienda que Microsoft Teams se habilite para todos los usuarios de una empresa, de modo que los equipos puedan formarse de manera orgánica para proyectos y otras iniciativas dinámicas. Incluso si decide realizar un piloto, podría ser útil mantener Microsoft Teams habilitado para todos los usuarios, pero solo enfocarse en las comunicaciones con el grupo piloto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3b69-p101">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives. Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span> |

<span data-ttu-id="f3b69-p102">Las licencias de Microsoft Teams se gestionan directamente a nivel de usuario a través de las interfaces de gestión de usuarios del centro de administración de Office 365 Un administrador puede asignar licencias a nuevos usuarios cuando se crean nuevas cuentas, o bien a usuarios con cuentas existentes. El administrador debe tener privilegios de administrador de control de usuarios y de administrador global para Office 365 para poder gestionar licencias de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3b69-p102">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces. An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts. The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="f3b69-p103">Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="f3b69-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

<span data-ttu-id="f3b69-114">![](media/Manage_user_access_to_Microsoft_Teams_image2.png) ![](media/Manage_user_access_to_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="f3b69-114"></span></span>

<span data-ttu-id="f3b69-p104">Una licencia de usuario de Microsoft Teams puede deshabilitarse en cualquier momento. Una vez que la licencia se deshabilita, se evitará el acceso de los usuarios a Microsoft Teams y el usuario ya no podrá ver Microsoft Teams en el iniciador de aplicaciones y la página de inicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3b69-p104">A Microsoft Teams user license can be disabled at any time. Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="f3b69-p105">Además de usar el centro de administración de Office 365, los administradores de Office 365 también pueden usar Office 365 PowerShell para asignar y quitar licencias. Para asignar una licencia a un usuario, utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f3b69-p105">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses. To assign a license to a user, use the following syntax:</span></span>

<span data-ttu-id="f3b69-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span><span class="sxs-lookup"><span data-stu-id="f3b69-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span></span>

<span data-ttu-id="f3b69-120">En el siguiente ejemplo se asigna una licencia del plan de licencias litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) al usuario belindan@litwareinc.com sin licencia.</span><span class="sxs-lookup"><span data-stu-id="f3b69-120">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

<span data-ttu-id="f3b69-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="f3b69-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="f3b69-122">Para obtener más detalles y ejemplos, consulte [*Asignar licencias a cuentas de usuario con PowerShell de Office 365*](https://go.microsoft.com/fwlink/?linkid=855755)</span><span class="sxs-lookup"><span data-stu-id="f3b69-122">For more details and examples, see [*Assign licenses to user accounts with Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="f3b69-123">Para quitar licencias de una cuenta de usuario existente, utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f3b69-123">To remove licenses from an existing user account, use the following syntax:</span></span>

<span data-ttu-id="f3b69-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span><span class="sxs-lookup"><span data-stu-id="f3b69-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span></span>

<span data-ttu-id="f3b69-125">En el siguiente ejemplo se elimina la licencia litwareinc:ENTERPRISEPACK de la cuenta de usuario BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f3b69-125">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

<span data-ttu-id="f3b69-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="f3b69-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="f3b69-127">Para obtener más detalles y ejemplos, consulte [*Eliminar licencias de cuentas de usuario con PowerShell de Office 365*](https://go.microsoft.com/fwlink/?linkid=855756)</span><span class="sxs-lookup"><span data-stu-id="f3b69-127">For more details and examples, see [*Remove licenses from user accounts with office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="f3b69-128">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="f3b69-128">Decision Point</span></span>         |<ul><li><span data-ttu-id="f3b69-p106">¿Cuál es el plan de su organización para comenzar a usar Microsoft Teams en toda la organización?  (Piloto o Abierto)</span><span class="sxs-lookup"><span data-stu-id="f3b69-p106">What is your organization’s plan for Microsoft Teams onboarding across the organization?  (Pilot or Open)</span></span></li></ul>         |
|![](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="f3b69-131">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="f3b69-131">Next Steps</span></span>         |<ul><li><span data-ttu-id="f3b69-132">Si realiza la adopción a través de Piloto, decida si desea hacerlo a través de licencias o comunicación dirigida.</span><span class="sxs-lookup"><span data-stu-id="f3b69-132">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="f3b69-133">Según cuál sea su decisión, realice los pasos para asegurarse de que solo los usuarios piloto puedan acceder a Microsoft Teams (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="f3b69-133">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="f3b69-134">Documente qué usuarios tendrán (o no tendrán) acceso a Microsoft Teams a continuación.</span><span class="sxs-lookup"><span data-stu-id="f3b69-134">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |
