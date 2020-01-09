---
title: Mover los equipos de StaffHub a Turnos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo mover los equipos de Microsoft StaffHub y programar datos para desplazarse por Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a14c7cbca85be266347cd6777ea1108cc63d065
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992847"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="34e90-103">Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34e90-104">A partir del 31 de diciembre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="34e90-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="34e90-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="34e90-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="34e90-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="34e90-107">StaffHub dejará de funcionar para todos los usuarios el 31 de diciembre de 2019.</span><span class="sxs-lookup"><span data-stu-id="34e90-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="34e90-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="34e90-109">Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="34e90-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="34e90-110">La aplicación de turnos de Teams ofrece un enfoque simple para administrar las programaciones y el flujo constante de swaps y cancelaciones de turnos que se producen diariamente.</span><span class="sxs-lookup"><span data-stu-id="34e90-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="34e90-111">Los miembros del equipo pueden acceder a su programación y desplazar la información directamente en la aplicación y en todos sus dispositivos para establecer sus preferencias, administrar sus programaciones y solicitar tiempo.</span><span class="sxs-lookup"><span data-stu-id="34e90-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="34e90-112">Este artículo le muestra cómo mover los equipos de StaffHub y programar datos para desplazarse por los equipos.</span><span class="sxs-lookup"><span data-stu-id="34e90-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="34e90-113">Cubre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34e90-113">It covers:</span></span>

- [<span data-ttu-id="34e90-114">Lo que debe saber sobre el desplazamiento a teams</span><span class="sxs-lookup"><span data-stu-id="34e90-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="34e90-115">Preparar</span><span class="sxs-lookup"><span data-stu-id="34e90-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="34e90-116">Realizar una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="34e90-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="34e90-117">Vaya más allá de la prueba piloto y mueva todos los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="34e90-118">Supervisar el uso de Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="34e90-119">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="34e90-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="34e90-120">Tanto si es una pequeña empresa con uno o dos equipos de StaffHub como si es una empresa grande con cientos de equipos de StaffHub, aquí encontrará las instrucciones para administradores que necesita para que la transición a teams se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="34e90-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="34e90-121">Debe ser administrador global para poder realizar los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="34e90-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="34e90-122">Si todavía no lo ha hecho, consulte las [preguntas más frecuentes sobre la jubilación de StaffHub](microsoft-staffhub-to-be-retired.md) para obtener respuestas a las preguntas que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="34e90-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="34e90-123">Lo que debe saber sobre el desplazamiento a teams</span><span class="sxs-lookup"><span data-stu-id="34e90-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="34e90-124">Cuándo mover a teams</span><span class="sxs-lookup"><span data-stu-id="34e90-124">When to move to Teams</span></span>

<span data-ttu-id="34e90-125">A partir del 31 de diciembre de 2019, StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="34e90-125">Effective December 31, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="34e90-126">Le recomendamos que comience a usar Teams hoy y empiece a cambiar la transición de los equipos y usuarios de su organización de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="34e90-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="34e90-127">Con la administración de programación como la característica que se usa con más frecuencia en StaffHub, le recomendamos que use la aplicación turnos en Teams en el futuro.</span><span class="sxs-lookup"><span data-stu-id="34e90-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="34e90-128">Qué se mueve a teams</span><span class="sxs-lookup"><span data-stu-id="34e90-128">What is moved to Teams</span></span>

<span data-ttu-id="34e90-129">Al mover un equipo de StaffHub, los miembros del equipo, los detalles del usuario, las programaciones del equipo y los datos del chat se mueven a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="34e90-130">Los archivos no se mueven al mover un equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="34e90-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="34e90-131">Si un equipo de StaffHub contiene archivos que también desea mover a Teams, mueva los archivos en un paso independiente.</span><span class="sxs-lookup"><span data-stu-id="34e90-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="34e90-132">Cada equipo de StaffHub necesita un grupo de Office 365 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="34e90-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="34e90-133">Si un equipo de StaffHub está asociado con un grupo de Office 365, la configuración de privacidad del grupo se conserva cuando se mueve el equipo.</span><span class="sxs-lookup"><span data-stu-id="34e90-133">If a StaffHub team is associated with an Office 365 Group, the privacy setting of the group is retained when you move the team.</span></span> <span data-ttu-id="34e90-134">Si un equipo de StaffHub no tiene un grupo de 365 de Office asociado, se crea automáticamente un grupo con la configuración de privacidad privada para que admita la transición.</span><span class="sxs-lookup"><span data-stu-id="34e90-134">If a StaffHub team doesn't have an Office 365 Group associated with it, a group with a privacy setting of Private is automatically created for you to support the transition.</span></span>  <span data-ttu-id="34e90-135">Dada la diferencia de nomenclatura de equipo y grupo entre Teams y StaffHub, es posible que vea un nombre de equipo diferente en Teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-135">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span> 

<span data-ttu-id="34e90-136">A medida que vaya migrando equipos de StaffHub a Teams, los usuarios ya no tendrán acceso a sus programaciones en StaffHub y se redirigirán a los equipos.</span><span class="sxs-lookup"><span data-stu-id="34e90-136">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="34e90-137">Le recomendamos que comunique este cambio en toda la organización para minimizar las interrupciones y para animar a los usuarios a adoptar y explorar equipos.</span><span class="sxs-lookup"><span data-stu-id="34e90-137">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="34e90-138">Si tiene Azure AD Premium, puede [ejecutar un informe](run-report-to-show-staffhub-usage.md) para obtener una lista de los usuarios de StaffHub de su organización que necesitan saber sobre este cambio.</span><span class="sxs-lookup"><span data-stu-id="34e90-138">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="34e90-139">No hay ninguna opción de deshacer después de mover un equipo de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-139">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="34e90-140">Experiencia de usuario al mover un equipo</span><span class="sxs-lookup"><span data-stu-id="34e90-140">User experience when you move a team</span></span>

<span data-ttu-id="34e90-141">El tiempo de inactividad es mínimo (menos de un segundo, si lo hay) para los usuarios cuando su equipo cambia de StaffHub a turnos en Teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-141">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="34e90-142">Los usuarios pueden seguir usando StaffHub hasta que se complete el cambio a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-142">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="34e90-143">Cuando se haya completado el movimiento, los miembros del equipo verán un mensaje para informarles de que necesitan comenzar a usar turnos en Teams para acceder a su programación de equipo.</span><span class="sxs-lookup"><span data-stu-id="34e90-143">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="34e90-144">Este es un ejemplo del mensaje que los usuarios ven después de que el equipo de StaffHub se mueva a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-144">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="34e90-145">![Ejemplo del mensaje que los usuarios ven.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de StaffHub a teams")</span><span class="sxs-lookup"><span data-stu-id="34e90-145">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="34e90-146">Preparar</span><span class="sxs-lookup"><span data-stu-id="34e90-146">Prepare</span></span>

<span data-ttu-id="34e90-147">Aquí le mostramos cómo prepararse para desplazarse a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-147">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="34e90-148">Comprobar que se cumplen los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="34e90-148">Check that prerequisites are met</span></span>

<span data-ttu-id="34e90-149">Antes de mover un equipo de StaffHub a Teams, asegúrese de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34e90-149">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="34e90-150">El usuario que ha iniciado sesión es un administrador global.</span><span class="sxs-lookup"><span data-stu-id="34e90-150">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="34e90-151">Teams está habilitado para todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="34e90-151">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="34e90-152">La creación de grupos de Office 365 está habilitada en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="34e90-152">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="34e90-153">La teamId de StaffHub es válida.</span><span class="sxs-lookup"><span data-stu-id="34e90-153">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="34e90-154">El equipo de StaffHub tiene al menos un propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="34e90-154">The StaffHub team has at least one team owner.</span></span>
- <span data-ttu-id="34e90-155">El equipo de StaffHub contiene miembros.</span><span class="sxs-lookup"><span data-stu-id="34e90-155">The StaffHub team contains members.</span></span>
- <span data-ttu-id="34e90-156">Todos los miembros del equipo StaffHub están vinculados a una cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="34e90-156">All StaffHub team members are linked to an Azure AD account.</span></span>
- <span data-ttu-id="34e90-157">Se asigna a todos los miembros del equipo StaffHub una licencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-157">All StaffHub team members are assigned a Teams license.</span></span>  

<span data-ttu-id="34e90-158">Si no se cumplen estos requisitos previos, se producirá un error en la solicitud de movimiento.</span><span class="sxs-lookup"><span data-stu-id="34e90-158">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="34e90-159">Asignar licencias de Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-159">Assign Teams licenses</span></span>

<span data-ttu-id="34e90-160">Cada usuario debe tener una licencia activa de Microsoft 365 o de Office 365 de [un plan apto](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y debe tener asignada una licencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-160">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="34e90-161">Asignar una licencia de Teams a los usuarios les da acceso a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-161">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="34e90-162">Administra las licencias de Teams en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34e90-162">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="34e90-163">Para obtener más información, vea [administrar el acceso de los usuarios a teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="34e90-163">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="34e90-164">Si su organización usa Skype empresarial y no está listo para mover a todos los usuarios a Teams, puede habilitar a Teams para sus trabajadores de los Firstline, que luego pueden ejecutar equipos junto con Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="34e90-164">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="34e90-165">En este modo de coexistencia, llamadas *islas*, cada aplicación cliente funciona como una solución independiente.</span><span class="sxs-lookup"><span data-stu-id="34e90-165">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="34e90-166">Para obtener más información, consulte [comprender Teams y la interoperabilidad y coexistencia de Skype empresarial](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="34e90-166">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="34e90-167">Instalar la versión preliminar del módulo de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-167">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="34e90-168">Si todavía no lo ha hecho, [Instale la versión preliminar del módulo de PowerShell de StaffHub](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="34e90-168">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="34e90-169">Debe tener instalada la versión preliminar del módulo para mover los equipos de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-169">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="34e90-170">Vincular una cuenta de Azure AD a los miembros del equipo de StaffHub que no tengan una</span><span class="sxs-lookup"><span data-stu-id="34e90-170">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="34e90-171">Cada miembro del equipo de StaffHub debe estar vinculado a una cuenta de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="34e90-171">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="34e90-172">Los usuarios de la organización no estarán vinculados a una cuenta de Azure AD si se aplica alguno de los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="34e90-172">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="34e90-173">Un propietario de equipo agregó a un usuario que no tiene una cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="34e90-173">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="34e90-174">Un propietario del equipo ha invitado a un usuario a un equipo de StaffHub y ese usuario no aceptó la invitación.</span><span class="sxs-lookup"><span data-stu-id="34e90-174">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="34e90-175">Estos usuarios tienen cuentas inactivas y muestran un estado de usuario desconocido, invitado o InviteRejected.</span><span class="sxs-lookup"><span data-stu-id="34e90-175">These users have inactive accounts and show a user state of Unknown, Invited, or InviteRejected.</span></span> <span data-ttu-id="34e90-176">Puedes vincular una cuenta de Azure AD para estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="34e90-176">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="34e90-177">A continuación, le mostramos cómo.</span><span class="sxs-lookup"><span data-stu-id="34e90-177">Here's how.</span></span>

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a><span data-ttu-id="34e90-178">Obtener una lista de todas las cuentas inactivas de los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-178">Get a list of all inactive accounts on StaffHub teams</span></span>

<span data-ttu-id="34e90-179">Ejecute la siguiente serie de comandos para obtener una lista de todas las cuentas inactivas de los equipos de StaffHub y exporte la lista a un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="34e90-179">Run the following series of commands to get a list of all inactive accounts on StaffHub teams and export the list to a CSV file.</span></span> <span data-ttu-id="34e90-180">Cada comando debe ejecutarse por separado.</span><span class="sxs-lookup"><span data-stu-id="34e90-180">Each command should be run separately.</span></span>

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a><span data-ttu-id="34e90-181">Vincular la cuenta</span><span class="sxs-lookup"><span data-stu-id="34e90-181">Link the account</span></span>

<span data-ttu-id="34e90-182">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34e90-182">Do one of the following:</span></span>

- <span data-ttu-id="34e90-183">Convertir y vincular la cuenta.</span><span class="sxs-lookup"><span data-stu-id="34e90-183">Convert and link the account.</span></span>

  <span data-ttu-id="34e90-184">Los propietarios y administradores del equipo de StaffHub pueden convertir una cuenta inactiva y vincularla a una cuenta de Azure AD de StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="34e90-184">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="34e90-185">Quite la cuenta desvinculada y, a continuación, vuelva a agregar la cuenta con el UPN.</span><span class="sxs-lookup"><span data-stu-id="34e90-185">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="34e90-186">Ejecute el cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) para quitar la cuenta no aprovisionada del equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="34e90-186">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="34e90-187">Ejecute el cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para volver a agregar la cuenta al equipo de StaffHub mediante el UPN.</span><span class="sxs-lookup"><span data-stu-id="34e90-187">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="34e90-188">Quitar la cuenta inactiva.</span><span class="sxs-lookup"><span data-stu-id="34e90-188">Remove the inactive account.</span></span> <span data-ttu-id="34e90-189">Use esta opción si la cuenta de usuario ya no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="34e90-189">Use this option if the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="34e90-190">Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los usuarios</span><span class="sxs-lookup"><span data-stu-id="34e90-190">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="34e90-191">Teams incluye una directiva de configuración de aplicaciones de FirstlineWorker integrada que puede usar para personalizar Teams y resaltar las aplicaciones más importantes para los trabajadores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="34e90-191">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="34e90-192">Cuando asigne esta directiva a los usuarios, las aplicaciones de la Directiva se anclarán a la barra de la aplicación de Teams para acceder a ellas de forma rápida y fácil.</span><span class="sxs-lookup"><span data-stu-id="34e90-192">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="34e90-193">Puede encontrar otras aplicaciones agregadas a teams en la barra de aplicaciones haciendo clic en **... Más aplicaciones** en el escritorio de Teams y en los clientes Web, y deshaciendo el dedo hacia arriba en el cliente móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-193">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="34e90-194">De forma predeterminada, la Directiva de configuración de la aplicación FirstlineWorker incluye las aplicaciones actividad, turnos, chat y llamadas.</span><span class="sxs-lookup"><span data-stu-id="34e90-194">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="34e90-195">Para conocer los pasos sobre cómo asignar la Directiva de configuración de la aplicación FirstlineWorker a los usuarios, consulte [usar la Directiva de configuración de la aplicación FirstlineWorker para anclar turnos a teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="34e90-195">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="34e90-196">Después de asignar una directiva, esta puede tardar hasta 24 horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="34e90-196">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="34e90-197">Le recomendamos que complete este paso al menos una semana antes de mover los equipos y usuarios de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-197">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="34e90-198">Cuando los usuarios estén en Teams, asegúrese de que pueden ver y acceder a la aplicación turnos.</span><span class="sxs-lookup"><span data-stu-id="34e90-198">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="34e90-199">También puede crear directivas de configuración de aplicaciones personalizadas y editar la configuración en la Directiva configuración global de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="34e90-199">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="34e90-200">Para obtener más información, consulte [Administrar directivas de configuración de aplicaciones en Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="34e90-200">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="34e90-201">Usuarios incorporados a teams</span><span class="sxs-lookup"><span data-stu-id="34e90-201">Onboard users to Teams</span></span>

<span data-ttu-id="34e90-202">Como parte de la estrategia de incorporación, proporcione formación e instrucciones a los usuarios para que puedan familiarizarse con los equipos.</span><span class="sxs-lookup"><span data-stu-id="34e90-202">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="34e90-203">Comparta los siguientes recursos con los usuarios para que sepan dónde obtener los clientes, la formación y el soporte técnico de Teams:</span><span class="sxs-lookup"><span data-stu-id="34e90-203">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="34e90-204">Cliente web de Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-204">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="34e90-205">Vínculos de descarga del cliente de escritorio y móvil</span><span class="sxs-lookup"><span data-stu-id="34e90-205">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="34e90-206">Vídeos de aprendizaje de Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-206">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="34e90-207">Documentación de Ayuda de Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-207">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="34e90-208">Para obtener instrucciones sobre la implementación de equipos y sobre la adopción de equipos, consulte [cómo implementar Teams](../../How-to-roll-out-teams.md) y [adoptar equipos](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="34e90-208">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="34e90-209">Realizar una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="34e90-209">Conduct a pilot</span></span>

<span data-ttu-id="34e90-210">Le recomendamos que empiece por mover dos o tres equipos de StaffHub para un grupo seleccionado de primeras personas.</span><span class="sxs-lookup"><span data-stu-id="34e90-210">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="34e90-211">La ejecución de un proyecto piloto le ayuda a afinar el plan de transición y a asegurarse de que está listo para mover todos los equipos de StaffHub de su organización a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-211">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="34e90-212">También identifica a los campeones que pueden ayudar a impulsar la adopción en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="34e90-212">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="34e90-213">Si es una pequeña empresa que no necesita un enfoque por fases, es posible que los pasos de esta sección sean todo lo que necesita para cambiar de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-213">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="34e90-214">Identificar equipos piloto</span><span class="sxs-lookup"><span data-stu-id="34e90-214">Identify pilot teams</span></span>

<span data-ttu-id="34e90-215">Póngase en contacto con usted para identificar dos o tres equipos piloto.</span><span class="sxs-lookup"><span data-stu-id="34e90-215">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="34e90-216">Todos los miembros del equipo deben confirmar el uso de turnos en Teams para administrar su programación y comunicarse y colaborar entre sí.</span><span class="sxs-lookup"><span data-stu-id="34e90-216">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="34e90-217">Identificar a los expertos en el equipo</span><span class="sxs-lookup"><span data-stu-id="34e90-217">Identify team champions</span></span>

<span data-ttu-id="34e90-218">Identifique a los campeones a través de equipos piloto y inscribalos para ayudar a repartir turnos.</span><span class="sxs-lookup"><span data-stu-id="34e90-218">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="34e90-219">Los campeones del equipo son apasionados de lo que hacen, compartiendo su propio aprendizaje para ofrecer asistencia y orientación a los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="34e90-219">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="34e90-220">Los expertos del equipo pueden ser administradores o propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="34e90-220">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="34e90-221">Los expertos en equipo deben asegurarse de que los miembros del equipo se configuren dedicando tiempo para que todos puedan [obtener clientes](../../get-clients.md)de equipo, iniciar sesión en Teams y consultar sus programaciones en turnos y empezar a conversar entre sí.</span><span class="sxs-lookup"><span data-stu-id="34e90-221">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="34e90-222">Los usuarios que ya estén familiarizados con StaffHub se activarán y se ejecutarán rápidamente en turnos.</span><span class="sxs-lookup"><span data-stu-id="34e90-222">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="34e90-223">También puede hacer que [desplace la ayuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener ayuda adicional.</span><span class="sxs-lookup"><span data-stu-id="34e90-223">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="34e90-224">Mover un equipo de StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-224">Move a StaffHub team</span></span>

<span data-ttu-id="34e90-225">Siga estos pasos para mover un equipo de StaffHub a la vez.</span><span class="sxs-lookup"><span data-stu-id="34e90-225">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="34e90-226">Recomendamos este enfoque para los equipos de la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="34e90-226">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="34e90-227">Más adelante, cuando esté listo para mover todos los equipos de StaffHub de su organización, vea [mover los equipos de staffhub](#move-your-staffhub-teams) para conocer los pasos para mover varios equipos a la vez.</span><span class="sxs-lookup"><span data-stu-id="34e90-227">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="34e90-228">Ejecute lo siguiente para mover un equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="34e90-228">Run the following to move a StaffHub team.</span></span>

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="34e90-229">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34e90-229">Example:</span></span>

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="34e90-230">Este es un ejemplo de la respuesta que obtiene al enviar una solicitud para mover un equipo de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-230">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```output
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="34e90-231">Para comprobar el estado de una solicitud de movimiento, ejecute lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="34e90-231">To check the status of a move request, run the following.</span></span>

```PowerShell
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="34e90-232">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34e90-232">Example:</span></span>

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="34e90-233">Este es un ejemplo de la respuesta que obtiene cuando hay un movimiento en curso.</span><span class="sxs-lookup"><span data-stu-id="34e90-233">Here's an example of the response you get when a move is in progress.</span></span>

```output
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="34e90-234">Mover archivos de un equipo de StaffHub a teams</span><span class="sxs-lookup"><span data-stu-id="34e90-234">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="34e90-235">Este paso solo se aplica si el equipo de StaffHub que movió a teams tiene archivos que también desea mover a teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-235">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="34e90-236">Puede mover archivos directamente en SharePoint Online o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34e90-236">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="34e90-237">En SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="34e90-237">In SharePoint Online</span></span>

<span data-ttu-id="34e90-238">Vea [Cómo mover archivos en SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="34e90-238">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="34e90-239">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="34e90-239">Using PowerShell</span></span>

<span data-ttu-id="34e90-240">Descargue e instale el [Shell de administración de SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), si todavía no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="34e90-240">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="34e90-241">Contiene los cmdlets que necesita para mover los archivos.</span><span class="sxs-lookup"><span data-stu-id="34e90-241">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="34e90-242">Use el cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para conectarse al sitio de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="34e90-242">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="34e90-243">Para cada archivo que desee mover de StaffHub a Teams, use el cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover el archivo.</span><span class="sxs-lookup"><span data-stu-id="34e90-243">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="34e90-244">Para mover varios archivos, recorra los archivos y ejecute el segundo comando en el bucle.</span><span class="sxs-lookup"><span data-stu-id="34e90-244">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="34e90-245">No es necesario que repitas el primer comando si la sesión sigue activa.</span><span class="sxs-lookup"><span data-stu-id="34e90-245">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="34e90-246">Vaya más allá de la prueba piloto y mueva todos los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-246">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="34e90-247">Aumentar el conocimiento</span><span class="sxs-lookup"><span data-stu-id="34e90-247">Raise awareness</span></span>

<span data-ttu-id="34e90-248">Cuando esté listo para ir más allá de los equipos piloto y mover los equipos de StaffHub de su organización a Teams, es importante comunicar primero el cambio en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="34e90-248">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="34e90-249">Represente la palabra acerca de los turnos y la transición a Teams para aumentar la conciencia, generar entusiasmo y adopción de unidades.</span><span class="sxs-lookup"><span data-stu-id="34e90-249">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="34e90-250">Mover los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-250">Move your StaffHub teams</span></span>

<span data-ttu-id="34e90-251">Siga estos pasos para mover equipos de StaffHub de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="34e90-251">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="34e90-252">Puede elegir mover todos los equipos de StaffHub de su organización o mover determinados equipos de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="34e90-252">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="34e90-253">Si quiere mover los equipos de StaffHub de uno en uno, vea [mover un equipo de staffhub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="34e90-253">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="34e90-254">Mover todos los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-254">Move all StaffHub teams</span></span>

<span data-ttu-id="34e90-255">Ejecute lo siguiente para obtener una lista de todos los equipos de StaffHub de su organización.</span><span class="sxs-lookup"><span data-stu-id="34e90-255">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="34e90-256">A continuación, ejecute lo siguiente para mover todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="34e90-256">Then, run the following to move all teams.</span></span>

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="34e90-257">Este es un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="34e90-257">Here's an example of the response.</span></span>

<span data-ttu-id="34e90-258">En el caso de cualquier equipo que ya se haya movido a teams o que ya exista en Teams, jobId tendrá el valor "null", ya que no es necesario enviar el trabajo para mover ese equipo.</span><span class="sxs-lookup"><span data-stu-id="34e90-258">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```output
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="34e90-259">Mover equipos de StaffHub específicos</span><span class="sxs-lookup"><span data-stu-id="34e90-259">Move specific StaffHub teams</span></span>

<span data-ttu-id="34e90-260">Ejecute el siguiente procedimiento para obtener una lista de todos los identificadores de equipo de StaffHub en su organización.</span><span class="sxs-lookup"><span data-stu-id="34e90-260">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="34e90-261">En los resultados devueltos `Get-StaffHubteamsForTenant` por el cmdlet que ejecutó anteriormente, seleccione los identificadores de equipo que desea mover y agréguelos a un archivo de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="34e90-261">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="34e90-262">Este es un ejemplo de cómo se debe dar formato al archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="34e90-262">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="34e90-263">Identificar</span><span class="sxs-lookup"><span data-stu-id="34e90-263">Id</span></span>  |
|---------|
|<span data-ttu-id="34e90-264">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="34e90-264">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="34e90-265">TEAM_81b1f191-3e19-45ce-AB32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="34e90-265">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="34e90-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="34e90-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="34e90-267">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="34e90-267">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="34e90-268">Después de crear el archivo CSV, ejecute lo siguiente para mover los equipos especificados en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="34e90-268">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="34e90-269">Confirmar que los equipos de StaffHub se movieron a teams</span><span class="sxs-lookup"><span data-stu-id="34e90-269">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="34e90-270">Ejecute lo siguiente para obtener una lista de todos los equipos de los turnos de su organización.</span><span class="sxs-lookup"><span data-stu-id="34e90-270">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="34e90-271">Mover archivos de los equipos de StaffHub a teams</span><span class="sxs-lookup"><span data-stu-id="34e90-271">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="34e90-272">Si los equipos de StaffHub que movió contiene archivos que también desea mover a Teams, vea [mover archivos de un equipo de staffhub a teams](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="34e90-272">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="34e90-273">Supervisar el uso de Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-273">Monitor Teams usage</span></span>

<span data-ttu-id="34e90-274">Los informes de uso pueden ayudarlo a comprender mejor los patrones de uso y le proporcionan información sobre cómo priorizar los esfuerzos de aprendizaje y comunicación en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="34e90-274">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="34e90-275">Puede ejecutar informes que muestran el uso general de los equipos, los tipos de actividades que los usuarios realizan en Teams, cómo se conectan los usuarios a teams y mucho más.</span><span class="sxs-lookup"><span data-stu-id="34e90-275">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="34e90-276">Para obtener más información, vea informes [de equipos en el centro de administración de Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) y [informes de actividades de Teams en el centro de administración de Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="34e90-276">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="34e90-277">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="34e90-277">Troubleshooting</span></span>

<span data-ttu-id="34e90-278">**Cómo obtener más información sobre errores**</span><span class="sxs-lookup"><span data-stu-id="34e90-278">**How to get more information about failure errors**</span></span>

<span data-ttu-id="34e90-279">Ejecute lo siguiente para obtener más información sobre los errores de "error" que se producen al intentar mover un equipo:</span><span class="sxs-lookup"><span data-stu-id="34e90-279">Run the following to get more information about "Failure" errors that occur when you try to move a team:</span></span>

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

<span data-ttu-id="34e90-280">Verá uno de los siguientes Estados devuelto: Succeed, Failure, Ingress, queued.</span><span class="sxs-lookup"><span data-stu-id="34e90-280">You'll see one of the following statuses returned: Success, Failure, InProgress, Queued.</span></span>

<span data-ttu-id="34e90-281">Si se devuelve "Failure", ejecute lo siguiente para obtener más información sobre el error:</span><span class="sxs-lookup"><span data-stu-id="34e90-281">If "Failure" is returned, run the following to get more information about the error:</span></span>

```PowerShell
$res.Result.Error.Innererror
```

<span data-ttu-id="34e90-282">**Al intentar mover un equipo de StaffHub, el estado se muestra como "error" y recibe un mensaje de error "no se pudo recuperar las categorías de SKU aplicables para el usuario"**</span><span class="sxs-lookup"><span data-stu-id="34e90-282">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Failed to retrieve applicable SKU categories for the user" error message**</span></span>

<span data-ttu-id="34e90-283">Esto puede ocurrir si uno o más miembros del equipo no tienen una licencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="34e90-283">This can occur if one or more team members don't have a Teams license.</span></span> <span data-ttu-id="34e90-284">Vaya a portal.office.com, busque el grupo y, a continuación, confirme que se asigna una licencia de Teams a los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="34e90-284">Go to portal.office.com, find the group, and then confirm that group members are assigned a Teams license.</span></span>

<span data-ttu-id="34e90-285">**Al intentar mover un equipo de StaffHub, el estado se muestra como "error" y recibe el mensaje de error "no se encontró el propietario del equipo"**</span><span class="sxs-lookup"><span data-stu-id="34e90-285">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Team owner not found" error message**</span></span>

<span data-ttu-id="34e90-286">Esto puede ocurrir si el grupo que está asociado al equipo de StaffHub no tiene un propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="34e90-286">This can occur if the group that's associated with the StaffHub team doesn't have a team owner.</span></span> <span data-ttu-id="34e90-287">Vaya a portal.office.com, busque el grupo y, a continuación, agregue uno o más propietarios al grupo.</span><span class="sxs-lookup"><span data-stu-id="34e90-287">Go to portal.office.com, find the group, and then add one or more owners to the group.</span></span>

<span data-ttu-id="34e90-288">**Al intentar mover archivos de StaffHub a Teams, recibe el mensaje de error "Permiso denegado".**</span><span class="sxs-lookup"><span data-stu-id="34e90-288">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="34e90-289">Esto puede ocurrir si está intentando mover archivos en un grupo privado de Office 365 del que no es miembro.</span><span class="sxs-lookup"><span data-stu-id="34e90-289">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="34e90-290">Si este es el caso, use el cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para agregarse al equipo de StaffHub y, a continuación, mueva los archivos.</span><span class="sxs-lookup"><span data-stu-id="34e90-290">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="34e90-291">Después de mover los archivos, use el cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) para quitarse del equipo.</span><span class="sxs-lookup"><span data-stu-id="34e90-291">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="34e90-292">**Al intentar mover archivos de StaffHub a Teams, recibe un error que indica que no existe la carpeta general.**</span><span class="sxs-lookup"><span data-stu-id="34e90-292">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="34e90-293">Ejecute el siguiente comando para agregar la carpeta general a SharePoint y, a continuación, vuelva a intentarlo:</span><span class="sxs-lookup"><span data-stu-id="34e90-293">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="34e90-294">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="34e90-294">Related topics</span></span>
- [<span data-ttu-id="34e90-295">Cómo implementar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-295">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="34e90-296">Se retirará Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-296">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="34e90-297">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34e90-297">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="34e90-298">Referencia de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="34e90-298">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
