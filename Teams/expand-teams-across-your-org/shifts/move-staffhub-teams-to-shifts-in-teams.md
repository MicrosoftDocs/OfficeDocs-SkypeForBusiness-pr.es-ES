---
title: Mover los equipos de StaffHub a Turnos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo programar datos y mover los equipos de Microsoft StaffHub a Turnos en Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780812"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="8bdaf-103">Mover los equipos de Microsoft StaffHub a Turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-103">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bdaf-104">A partir del 1 de octubre de 2019, se retirará Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="8bdaf-105">Estamos creando las funciones de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="8bdaf-106">En la actualidad, Teams incluye la aplicación Turnos para la administración de la programación y, a lo largo del tiempo, se implementarán funciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="8bdaf-107">StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="8bdaf-108">A cualquier usuario que intente abrir StaffHub se mostrará un mensaje en el que se le indicará que descargue Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="8bdaf-109">Para obtener más información, vea [Se retirará Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="8bdaf-110">La aplicación Turnos de Teams ofrece un enfoque sencillo para administrar la programación y el flujo constante de las intercambios de turnos y de las cancelaciones que se producen diariamente.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="8bdaf-111">Los miembros del equipo pueden acceder a su programación, cambiar la información directamente en la aplicación y en todos sus dispositivos para establecer las preferencias, administrar la programación y solicitar tiempo libre.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="8bdaf-112">En este artículo se mostrará cómo programar datos y mover los equipos de StaffHub de la organización a Turnos en Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="8bdaf-113">Este tema abarca:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-113">It covers:</span></span>

- [<span data-ttu-id="8bdaf-114">Todo lo que debe saber sobre el movimiento a Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="8bdaf-115">Preparación</span><span class="sxs-lookup"><span data-stu-id="8bdaf-115">Prepare Schema</span></span>](#prepare)
- [<span data-ttu-id="8bdaf-116">Realizar una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="8bdaf-116">Conduct a user pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="8bdaf-117">Ir más allá de la prueba piloto y mover todos los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="8bdaf-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="8bdaf-118">Supervisar el uso de Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="8bdaf-119">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="8bdaf-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="8bdaf-120">Tanto si una empresa pequeña con uno o dos equipos de StaffHub como si es una gran empresa con cientos de equipos de StaffHub, aquí encontrará las instrucciones para administradores que necesita para que la transición a Teams se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="8bdaf-121">Debe ser un administrador global para realizar los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="8bdaf-122">Si aún no lo ha hecho, consulte las [Preguntas frecuentes sobre el retiro de StaffHub](microsoft-staffhub-to-be-retired.md) para obtener respuestas a las preguntas que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="8bdaf-123">Todo lo que debe saber sobre el movimiento a Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="8bdaf-124">Cuándo moverse a Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-124">When to move to Teams</span></span>

<span data-ttu-id="8bdaf-125">A partir del 1 de octubre de 2019, se retirará StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="8bdaf-126">Le recomendamos que empiece a usar Teams hoy y que empiece a realizar la transición de los equipos y usuarios de la organización desde StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="8bdaf-127">Como la administración de programación es la característica más usada de StaffHub, le recomendamos usar en el futuro la aplicación Turnos en Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="8bdaf-128">Qué se mueve a Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-128">What is moved to Teams</span></span>

<span data-ttu-id="8bdaf-129">Los detalles de los usuarios, la información de programación, el chat y los datos de los archivos pasan a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-129">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="8bdaf-130">Esto incluye la subscripción de equipo, la programación de equipo, los chats y los archivos de los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-130">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="8bdaf-131">Cada equipo de StaffHub necesita un correspondiente grupo de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-131">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="8bdaf-132">Si un equipo de StaffHub no tiene un grupo de Office 365 asociado, se crea uno automáticamente para dar soporte a la transición.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-132">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="8bdaf-133">Debido a la diferencia de nombres de equipo y grupo entre Teams y StaffHub, es posible que vea un nombre de equipo distinto en Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-133">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="8bdaf-134">Al realizar la transición de los equipos de StaffHub a Teams, los usuarios ya no tienen acceso a su programación en StaffHub y serán dirigidos a Turnos en Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-134">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="8bdaf-135">Le recomendamos que comunique este cambio en toda la organización para minimizar las interrupciones y animar a los usuarios a adoptar y explorar Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-135">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="8bdaf-136">Si tiene Azure AD Premium, puede [ejecutar un informe](run-report-to-show-staffhub-usage.md) para obtener una lista de los usuarios de StaffHub de la organización que necesitan saber sobre este cambio.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-136">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="8bdaf-137">No hay ninguna opción de reversión después de mover un equipo de StaffHub a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-137">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="8bdaf-138">Experiencia del usuario al mover un equipo</span><span class="sxs-lookup"><span data-stu-id="8bdaf-138">User experience when you move a team</span></span>

<span data-ttu-id="8bdaf-139">Al cambiar el equipo de StaffHub a Turnos en Teams, el tiempo de inactividad de los usuarios es mínimo (menos de un segundo, si lo hay).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-139">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="8bdaf-140">Los usuarios pueden seguir usando StaffHub hasta que se complete el movimiento a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-140">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="8bdaf-141">Cuando haya finalizado el movimiento, los miembros del equipo verán un mensaje que les informa de que necesitan empezar a usar Teams en Teams para tener acceso a su programación de equipo.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-141">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="8bdaf-142">Este es un ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de StaffHub a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-142">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="8bdaf-143">![Ejemplo del mensaje que verán los usuarios.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de StaffHub a Teams")</span><span class="sxs-lookup"><span data-stu-id="8bdaf-143">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="8bdaf-144">Preparación</span><span class="sxs-lookup"><span data-stu-id="8bdaf-144">Prepare Schema</span></span>

<span data-ttu-id="8bdaf-145">Aquí le mostramos cómo prepararse para el movimiento a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-145">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="8bdaf-146">Comprobar que se cumplen los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8bdaf-146">Ensure that deployment prerequisites are met</span></span>

<span data-ttu-id="8bdaf-147">Antes de mover un equipo de StaffHub a Teams, asegúrese de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-147">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="8bdaf-148">El usuario que ha iniciado sesión es un administrador global.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-148">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="8bdaf-149">Teams está habilitado para todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-149">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="8bdaf-150">La creación de Grupos de Office 365 está habilitada en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-150">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="8bdaf-151">El teamId de StaffHub es válido.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-151">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="8bdaf-152">El equipo de StaffHub contiene miembros.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-152">The StaffHub team contains members.</span></span> 
- <span data-ttu-id="8bdaf-153">Todos los miembros del equipo de StaffHub se vinculan a una cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-153">All StaffHub team members are linked to an Azure AD account.</span></span> 

<span data-ttu-id="8bdaf-154">Si no se cumplen estos requisitos previos, se producirá un error en la solicitud de movimiento.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-154">If these prerequisites aren't met, the move request will fail.</span></span> 

### <a name="assign-teams-licenses"></a><span data-ttu-id="8bdaf-155">Asignar licencias de Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-155">Assign Teams licenses</span></span>

<span data-ttu-id="8bdaf-156">Cada usuario debe tener una licencia de Office 365 o Microsoft 365 de [un plan válido](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y se le debe asignar una licencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-156">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="8bdaf-157">La asignación de una licencia de Teams a los usuarios les da acceso a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-157">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="8bdaf-158">Puede administrar las licencias de Teams en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-158">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8bdaf-159">Para obtener más información, vea [Administrar el acceso de los usuarios a Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-159">To learn more, see [Manage user access to Microsoft Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8bdaf-160">Si la organización usa Skype Empresarial y usted no está listo para mover todos los usuarios a Teams, puede habilitar Teams para los Firstline Workers que pueden ejecutarlo junto con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-160">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="8bdaf-161">En este modo de coexistencia, llamado *Aplicaciones aisladas*, todas las aplicaciones de cliente funcionan como soluciones independientes.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-161">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="8bdaf-162">Para obtener más información, vea [Entender la coexistencia y la interoperabilidad de Skype Empresarial y Teams](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-162">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="8bdaf-163">Instalar el módulo de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="8bdaf-163">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="8bdaf-164">Si aún no lo ha hecho, [instale el módulo de PowerShell de StaffHub](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-164">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="8bdaf-165">Aprovisionar cuentas para los usuarios de StaffHub que no tienen una identidad en Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bdaf-165">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="8bdaf-166">Todos los administradores y miembros del equipo deben tener una identidad en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-166">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="8bdaf-167">Si un usuario aún no tiene una identidad en Azure AD, proporcióneles una cuenta.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-167">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="8bdaf-168">A continuación, le mostramos cómo.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-168">Here's how.</span></span> 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a><span data-ttu-id="8bdaf-169">Obtener una lista de todos los usuarios de los equipos de StaffHub que tienen miembros del equipo que no están aprovisionados con una cuenta de Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bdaf-169">Get a list of all users on StaffHub teams that have team members that aren't provisioned with an Azure AD account</span></span>

<span data-ttu-id="8bdaf-170">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-170">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a><span data-ttu-id="8bdaf-171">Aprovisionar la cuenta</span><span class="sxs-lookup"><span data-stu-id="8bdaf-171">Provision the account</span></span>

<span data-ttu-id="8bdaf-172">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-172">Do one of the following:</span></span>

- <span data-ttu-id="8bdaf-173">Convierta y vincule la cuenta a una cuenta aprovisionada.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-173">Convert and link the account to a provisioned account.</span></span>

  <span data-ttu-id="8bdaf-174">Los propietarios y administradores del equipo de StaffHub pueden convertir una cuenta ficticia o inactiva y vincularla a una cuenta aprovisionada en StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-174">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="8bdaf-175">Quite la cuenta sin aprovisionar y, después, vuelva a agregar la cuenta con el UPN.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-175">Remove the non-provisioned account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="8bdaf-176">Ejecute el cmdlet [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para quitar la cuenta sin aprovisionar del equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-176">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="8bdaf-177">Ejecute el cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para volver a agregar la cuenta al equipo de StaffHub con el UPN.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-177">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span> 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="8bdaf-178">Asignar la directiva de configuración de la aplicación FirstlineWorker a los usuarios</span><span class="sxs-lookup"><span data-stu-id="8bdaf-178">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="8bdaf-179">Teams incluye una directiva integrada de configuración de la aplicación de FirstlineWorker que puede usar para personalizar Teams y resaltar las aplicaciones que son más importantes para los Firstline Workers de la organización.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-179">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="8bdaf-180">Cuando asigna esta directiva a los usuarios, las aplicaciones de la directiva se anclan a la barra de la aplicación de Teams para acceder de forma rápida y fácil.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-180">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="8bdaf-181">Se pueden encontrar otras aplicaciones agregadas a Teams en la barra de la aplicación haciendo clic en **... Más aplicaciones** en los clientes para equipos de escritorio y web, y desplazando hacia arriba en la aplicación móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-181">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="8bdaf-182">De forma predeterminada, la directiva de configuración de la aplicación FirstlineWorker incluye las aplicaciones Actividad, Turnos, Chat y Llamadas.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-182">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="8bdaf-183">Para conocer los pasos para asignar la directiva de configuración de la aplicación FirstlineWorker a los usuarios, vea [Usar la directiva de configuración de la aplicación FirstlineWorker para anclar Turnos a Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-183">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="8bdaf-184">Después de asignar una directiva, puede tardar hasta 24 horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-184">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="8bdaf-185">Le recomendamos que realice este paso por lo menos una semana antes de mover los equipos y usuarios de StaffHub a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-185">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="8bdaf-186">Cuando los usuarios se encuentren en Teams, compruebe que pueden ver y acceder a la aplicación Turnos.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-186">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="8bdaf-187">También puede crear directivas de configuración de aplicaciones personalizadas y editar la configuración en la directiva de configuración global de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-187">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="8bdaf-188">Para obtener más información, consulte [Administrar directivas de configuración de aplicaciones en Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-188">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="8bdaf-189">Incorporar usuarios a Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-189">Onboard users to Teams</span></span>

<span data-ttu-id="8bdaf-190">Como parte de la estrategia de incorporación, proporcione formación e instrucciones para ayudar a los usuarios a familiarizarse con Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-190">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="8bdaf-191">Comparta los siguientes recursos con los usuarios para que sepan dónde obtener clientes, formación y soporte técnico de Teams:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-191">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="8bdaf-192">Cliente web de Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-192">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="8bdaf-193">Vínculos de descarga del cliente de escritorio y móvil</span><span class="sxs-lookup"><span data-stu-id="8bdaf-193">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="8bdaf-194">Vídeos de aprendizaje de Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-194">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="8bdaf-195">Documentación de Ayuda de Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-195">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="8bdaf-196">Para obtener instrucciones sobre cómo implementar Teams y para impulsar su adopción, vea [Cómo implementar Teams](../../How-to-roll-out-teams.md) y [Adoptar Teams](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-196">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="8bdaf-197">Realizar una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="8bdaf-197">Conduct a user pilot</span></span>

<span data-ttu-id="8bdaf-198">Le recomendamos que comience moviendo dos o tres equipos de StaffHub para un grupo selecto de usuarios pioneros.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-198">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="8bdaf-199">La ejecución de una prueba piloto le ayuda a afinar su plan de transición y a asegurarse de que está preparado para mover todos los equipos de StaffHub de la organización a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-199">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="8bdaf-200">También identifica a los expertos que pueden ayudar a impulsar la adopción en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-200">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="8bdaf-201">Si es una empresa pequeña que no necesita un enfoque por fases, los pasos de esta sección pueden ser todo lo que necesita para realizar el cambio de StaffHub a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-201">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="8bdaf-202">Identificar equipos piloto</span><span class="sxs-lookup"><span data-stu-id="8bdaf-202">Identify pilot teams</span></span>

<span data-ttu-id="8bdaf-203">Póngase en contacto para identificar dos o tres equipos piloto.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-203">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="8bdaf-204">Todos los miembros del equipo deben confirmar el uso de Turnos en Teams para administrar su programación, comunicarse y colaborar entre sí.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-204">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="8bdaf-205">Identificar a los expertos del equipo</span><span class="sxs-lookup"><span data-stu-id="8bdaf-205">Identify team champions</span></span>

<span data-ttu-id="8bdaf-206">Identifique a los expertos en los equipos piloto e inscríbalos para que ayuden a dar información sobre Turnos. </span><span class="sxs-lookup"><span data-stu-id="8bdaf-206">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="8bdaf-207">Los expertos de equipo están muy apasionados por lo que hacen, compartiendo sus propios conocimientos para ofrecer soporte técnico e instrucciones a los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-207">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="8bdaf-208">Los expertos del equipo pueden ser propietarios o administradores del equipo.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-208">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="8bdaf-209">Los expertos del equipo deben asegurarse de que los miembros del equipo están preparados, dedicando tiempo para todos para que puedan [obtener clientes de Teams](../../get-clients.md), iniciar sesión en Teams, consultar su programación en Turnos y empezar el chat entre sí.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-209">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="8bdaf-210">Los usuarios que ya conocen StaffHub se pondrán en marcha rápidamente en Turnos.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-210">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="8bdaf-211">También puede aconsejarles [Ayuda de Turnos](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener ayuda adicional.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-211">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="8bdaf-212">Mover un equipo de StaffHub</span><span class="sxs-lookup"><span data-stu-id="8bdaf-212">Move a StaffHub team</span></span>

<span data-ttu-id="8bdaf-213">Siga estos pasos para mover un equipo de StaffHub a la vez.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-213">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="8bdaf-214">Se recomienda este enfoque para los equipos piloto.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-214">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="8bdaf-215">Más adelante, cuando esté listo para mover todos los equipos de StaffHub de la organización, vea [Mover los equipos de StaffHub](#move-your-staffhub-teams) para conocer los pasos para mover varios equipos a la vez.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-215">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="8bdaf-216">Ejecute lo siguiente para mover un equipo de StaffHub:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-216">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="8bdaf-217">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-217">Example</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="8bdaf-218">Este es un ejemplo de la respuesta que obtiene al enviar una solicitud para mover un equipo de StaffHub a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-218">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="8bdaf-219">Para comprobar el estado de una solicitud de movimiento, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-219">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="8bdaf-220">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-220">Example</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="8bdaf-221">Este es un ejemplo de la respuesta que obtiene cuando un movimiento está en curso.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-221">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="8bdaf-222">Mover archivos de un equipo de StaffHub a Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-222">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="8bdaf-223">Este paso solo se aplica si el equipo de StaffHub que ha movido a Teams tiene archivos que también quiere mover a Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-223">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="8bdaf-224">Puede mover archivos directamente en SharePoint Online o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-224">You can move files directly in SharePoint Online or by using PowerShell.</span></span> 

#### <a name="in-sharepoint-online"></a><span data-ttu-id="8bdaf-225">En SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8bdaf-225">In SharePoint Online</span></span>

<span data-ttu-id="8bdaf-226">Vea [Cómo mover archivos en SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-226">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="8bdaf-227">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bdaf-227">Using Windows PowerShell</span></span>

<span data-ttu-id="8bdaf-228">Descargue e instale el [Shell de SharePoint Online Management](https://www.microsoft.com/download/details.aspx?id=35588), si aún no lo ha hecho. </span><span class="sxs-lookup"><span data-stu-id="8bdaf-228">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="8bdaf-229">Este contiene los cmdlets que necesita para mover los archivos.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-229">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="8bdaf-230">Use el cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para conectarse al sitio de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-230">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="8bdaf-231">Para cada archivo que quiera mover de StaffHub a Teams, use el cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover el archivo.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-231">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="8bdaf-232">Para mover varios archivos, ejecute un bucle en los archivos y ejecute el segundo comando del bucle.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-232">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="8bdaf-233">No es necesario repetir el primer comando si la sesión permanece activa.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-233">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="8bdaf-234">Ir más allá de la prueba piloto y mover todos los equipos de StaffHub </span><span class="sxs-lookup"><span data-stu-id="8bdaf-234">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="8bdaf-235">Crear conciencia </span><span class="sxs-lookup"><span data-stu-id="8bdaf-235">Raise awareness</span></span>

<span data-ttu-id="8bdaf-236">Cuando esté listo para ir más allá de los equipos piloto y mover los equipos de StaffHub de la organización a Teams, es importante que primero comunique el cambio a toda la organización.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-236">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="8bdaf-237">Informa a los usuarios sobre Turnos y la transición a Teams para crear conciencia, generar entusiasmo e impulsar la adopción.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-237">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="8bdaf-238">Mover los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="8bdaf-238">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

<span data-ttu-id="8bdaf-239">Siga estos pasos para mover los equipos de StaffHub de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-239">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="8bdaf-240">Puede elegir mover todos los equipos de StaffHub de la organización o mover equipos de StaffHub específicos.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-240">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="8bdaf-241">Si quiere mover los equipos de StaffHub uno a la vez, vea [Mover un equipo de StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-241">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="8bdaf-242">Mover todos los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="8bdaf-242">Move all StaffHub teams</span></span>

<span data-ttu-id="8bdaf-243">Ejecute lo siguiente para obtener una lista de todos los equipos de StaffHub dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-243">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="8bdaf-244">Después, ejecute lo siguiente para mover todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-244">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="8bdaf-245">Este es un ejemplo de la respuesta:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-245">Here's an example of the response.</span></span>

<span data-ttu-id="8bdaf-246">Para cualquier equipo que ya se haya movido a Teams o que ya exista en Teams, jobId tendrá el valor "null", ya que no es necesario enviar un trabajo para mover ese equipo.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-246">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="8bdaf-247">Mover equipos de StaffHub específicos</span><span class="sxs-lookup"><span data-stu-id="8bdaf-247">Move specific StaffHub teams</span></span>

<span data-ttu-id="8bdaf-248">Ejecute lo siguiente para obtener una lista de todos los Id. de equipo de StaffHub de la organización.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-248">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="8bdaf-249">En los resultados devueltos por el cmdlet `Get-StaffHubteamsForTenant` anteriormente ejecutado, seleccione los id. de los equipos que quiera mover y, después, agréguelos a un archivo de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-249">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="8bdaf-250">Aquí tiene un ejemplo de cómo se debe dar formato al archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-250">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="8bdaf-251">Id</span><span class="sxs-lookup"><span data-stu-id="8bdaf-251">ID</span></span>  |
|---------|
|<span data-ttu-id="8bdaf-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="8bdaf-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="8bdaf-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="8bdaf-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="8bdaf-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="8bdaf-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="8bdaf-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="8bdaf-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="8bdaf-256">Después de crear el archivo CSV, ejecute lo siguiente para mover los equipos especificados en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-256">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="8bdaf-257">Confirmar que los equipos de StaffHub se movieron a Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-257">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="8bdaf-258">Ejecute lo siguiente para obtener una lista de todos los equipos de Turnos de la organización.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-258">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="8bdaf-259">Mover archivos de los equipos de StaffHub a Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-259">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="8bdaf-260">Si los equipos de StaffHub que movió contienen archivos que también quiere mover a Teams, vea [Mover archivos de un equipo de StaffHub a Teams.](#move-files-from-a-staffhub-team-to-teams)</span><span class="sxs-lookup"><span data-stu-id="8bdaf-260">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="8bdaf-261">Supervisar el uso de Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-261">Monitor Teams usage</span></span>

<span data-ttu-id="8bdaf-262">Los informes de uso pueden ayudarle a comprender mejor los patrones de uso y obtener información sobre cómo priorizar los esfuerzos de aprendizaje y comunicación en la organización.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-262">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span> <span data-ttu-id="8bdaf-263">Como Turnos es una aplicación de Teams, puede ver el uso a través de informes de Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-263">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="8bdaf-264">Para obtener más información, vea [Informes de Teams en el Centro de administración de Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e [Informes de actividad de Teams en el Centro de administración de Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="8bdaf-264">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8bdaf-265">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="8bdaf-265">Troubleshooting</span></span> 

<span data-ttu-id="8bdaf-266">**Cuando intenta mover archivos de StaffHub a Teams, recibe el mensaje de error "Permiso denegado".**</span><span class="sxs-lookup"><span data-stu-id="8bdaf-266">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="8bdaf-267">Esto puede ocurrir si está intentando mover archivos a un grupo privado de Office 365 del que no es miembro.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-267">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="8bdaf-268">Si ocurre esto, use el cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para agregarse al equipo de StaffHub y, después, mueva los archivos.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-268">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="8bdaf-269">Después de mover los archivos, use el [cmdlet Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) para quitarse del equipo.</span><span class="sxs-lookup"><span data-stu-id="8bdaf-269">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="8bdaf-270">**Cuando intenta mover archivos de StaffHub a Teams, obtiene un error que indica que la carpeta general no existe.**</span><span class="sxs-lookup"><span data-stu-id="8bdaf-270">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="8bdaf-271">Ejecute el comando siguiente para agregar la carpeta general a SharePoint y, después, vuelva a intentarlo:</span><span class="sxs-lookup"><span data-stu-id="8bdaf-271">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="8bdaf-272">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8bdaf-272">Related topics</span></span>
- [<span data-ttu-id="8bdaf-273">Cómo implementar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-273">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="8bdaf-274">Se retirará Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="8bdaf-274">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="8bdaf-275">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bdaf-275">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="8bdaf-276">Referencia de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="8bdaf-276">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
