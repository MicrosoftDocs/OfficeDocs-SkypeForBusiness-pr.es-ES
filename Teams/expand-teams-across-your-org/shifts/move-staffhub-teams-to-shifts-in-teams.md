---
title: Mover los equipos de StaffHub a Turnos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo mover los equipos de Microsoft StaffHub y programar datos para desplazarse por Microsoft Teams.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cef8c6fbfd5ed0b19d6762b7508b311413d11066
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233288"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="22d9e-103">Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22d9e-104">A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="22d9e-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="22d9e-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="22d9e-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="22d9e-107">StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="22d9e-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="22d9e-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="22d9e-109">Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.</span><span class="sxs-lookup"><span data-stu-id="22d9e-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="22d9e-110">La aplicación de turnos de Teams ofrece un enfoque simple para administrar las programaciones y el flujo constante de swaps y cancelaciones de turnos que se producen diariamente.</span><span class="sxs-lookup"><span data-stu-id="22d9e-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="22d9e-111">Los miembros del equipo pueden acceder a su programación y desplazar la información directamente en la aplicación y en todos sus dispositivos para establecer sus preferencias, administrar sus programaciones y solicitar tiempo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="22d9e-112">Este artículo le muestra cómo mover los equipos de StaffHub y programar datos para desplazarse por los equipos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="22d9e-113">Cubre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22d9e-113">It covers:</span></span>

- [<span data-ttu-id="22d9e-114">Lo que debe saber sobre el desplazamiento a teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="22d9e-115">Preparar</span><span class="sxs-lookup"><span data-stu-id="22d9e-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="22d9e-116">Realizar una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="22d9e-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="22d9e-117">Vaya más allá de la prueba piloto y mueva todos los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="22d9e-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="22d9e-118">Supervisar el uso de Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="22d9e-119">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="22d9e-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="22d9e-120">Tanto si es una pequeña empresa con uno o dos equipos de StaffHub como si es una empresa grande con cientos de equipos de StaffHub, aquí encontrará las instrucciones para administradores que necesita para que la transición a teams se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="22d9e-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="22d9e-121">Debe ser administrador global para poder realizar los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="22d9e-122">Si todavía no lo ha hecho, consulte las [preguntas más frecuentes sobre la jubilación de StaffHub](microsoft-staffhub-to-be-retired.md) para obtener respuestas a las preguntas que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="22d9e-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="22d9e-123">Lo que debe saber sobre el desplazamiento a teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="22d9e-124">Cuándo mover a teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-124">When to move to Teams</span></span>

<span data-ttu-id="22d9e-125">A partir del 1 de octubre de 2019, se retirará StaffHub.</span><span class="sxs-lookup"><span data-stu-id="22d9e-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="22d9e-126">Le recomendamos que comience a usar Teams hoy y empiece a cambiar la transición de los equipos y usuarios de su organización de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="22d9e-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="22d9e-127">Con la administración de programación como la característica que se usa con más frecuencia en StaffHub, le recomendamos que use la aplicación turnos en Teams en el futuro.</span><span class="sxs-lookup"><span data-stu-id="22d9e-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="22d9e-128">Qué se mueve a teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-128">What is moved to Teams</span></span>

<span data-ttu-id="22d9e-129">Al mover un equipo de StaffHub, los miembros del equipo, los detalles del usuario, las programaciones del equipo y los datos del chat se mueven a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="22d9e-130">Los archivos no se mueven al mover un equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="22d9e-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="22d9e-131">Si un equipo de StaffHub contiene archivos que también desea mover a Teams, mueva los archivos en un paso independiente.</span><span class="sxs-lookup"><span data-stu-id="22d9e-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="22d9e-132">Cada equipo de StaffHub necesita un grupo de Office 365 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="22d9e-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="22d9e-133">Si un equipo de StaffHub no tiene asociado un grupo de Office 365, se crea uno automáticamente para que admita la transición.</span><span class="sxs-lookup"><span data-stu-id="22d9e-133">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="22d9e-134">Dada la diferencia de nomenclatura de equipo y grupo entre Teams y StaffHub, es posible que vea un nombre de equipo diferente en Teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-134">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="22d9e-135">A medida que vaya migrando equipos de StaffHub a Teams, los usuarios ya no tendrán acceso a sus programaciones en StaffHub y se redirigirán a los equipos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-135">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="22d9e-136">Le recomendamos que comunique este cambio en toda la organización para minimizar las interrupciones y para animar a los usuarios a adoptar y explorar equipos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-136">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="22d9e-137">Si tiene Azure AD Premium, puede [ejecutar un informe](run-report-to-show-staffhub-usage.md) para obtener una lista de los usuarios de StaffHub de su organización que necesitan saber sobre este cambio.</span><span class="sxs-lookup"><span data-stu-id="22d9e-137">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="22d9e-138">No hay ninguna opción de deshacer después de mover un equipo de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-138">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="22d9e-139">Experiencia de usuario al mover un equipo</span><span class="sxs-lookup"><span data-stu-id="22d9e-139">User experience when you move a team</span></span>

<span data-ttu-id="22d9e-140">El tiempo de inactividad es mínimo (menos de un segundo, si lo hay) para los usuarios cuando su equipo cambia de StaffHub a turnos en Teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-140">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="22d9e-141">Los usuarios pueden seguir usando StaffHub hasta que se complete el cambio a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-141">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="22d9e-142">Cuando se haya completado el movimiento, los miembros del equipo verán un mensaje para informarles de que necesitan comenzar a usar turnos en Teams para acceder a su programación de equipo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-142">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="22d9e-143">Este es un ejemplo del mensaje que los usuarios ven después de que el equipo de StaffHub se mueva a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-143">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="22d9e-144">![Ejemplo del mensaje que los usuarios ven.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de staffhub a teams")</span><span class="sxs-lookup"><span data-stu-id="22d9e-144">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="22d9e-145">Preparar</span><span class="sxs-lookup"><span data-stu-id="22d9e-145">Prepare</span></span>

<span data-ttu-id="22d9e-146">Aquí le mostramos cómo prepararse para desplazarse a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-146">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="22d9e-147">Comprobar que se cumplen los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="22d9e-147">Check that prerequisites are met</span></span>

<span data-ttu-id="22d9e-148">Antes de mover un equipo de StaffHub a Teams, asegúrese de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22d9e-148">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="22d9e-149">El usuario que ha iniciado sesión es un administrador global.</span><span class="sxs-lookup"><span data-stu-id="22d9e-149">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="22d9e-150">Teams está habilitado para todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="22d9e-150">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="22d9e-151">La creación de grupos de Office 365 está habilitada en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="22d9e-151">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="22d9e-152">La teamId de StaffHub es válida.</span><span class="sxs-lookup"><span data-stu-id="22d9e-152">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="22d9e-153">El equipo de StaffHub contiene miembros.</span><span class="sxs-lookup"><span data-stu-id="22d9e-153">The StaffHub team contains members.</span></span>
- <span data-ttu-id="22d9e-154">Todos los miembros del equipo StaffHub están vinculados a una cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="22d9e-154">All StaffHub team members are linked to an Azure AD account.</span></span>

<span data-ttu-id="22d9e-155">Si no se cumplen estos requisitos previos, se producirá un error en la solicitud de movimiento.</span><span class="sxs-lookup"><span data-stu-id="22d9e-155">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="22d9e-156">Asignar licencias de Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-156">Assign Teams licenses</span></span>

<span data-ttu-id="22d9e-157">Cada usuario debe tener una licencia activa de Microsoft 365 o de Office 365 de [un plan apto](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y debe tener asignada una licencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-157">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="22d9e-158">Asignar una licencia de Teams a los usuarios les da acceso a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-158">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="22d9e-159">Administra las licencias de Teams en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22d9e-159">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="22d9e-160">Para obtener más información, vea [administrar el acceso de los usuarios a teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="22d9e-160">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="22d9e-161">Si su organización usa Skype empresarial y no está listo para mover a todos los usuarios a Teams, puede habilitar a Teams para sus trabajadores de los Firstline, que luego pueden ejecutar equipos junto con Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="22d9e-161">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="22d9e-162">En este modo de coexistencia, llamadas *islas*, cada aplicación cliente funciona como una solución independiente.</span><span class="sxs-lookup"><span data-stu-id="22d9e-162">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="22d9e-163">Para obtener más información, consulte [comprender Teams y la interoperabilidad y coexistencia de Skype empresarial](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="22d9e-163">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="22d9e-164">Instalar el módulo de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="22d9e-164">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="22d9e-165">Si todavía no lo ha hecho, [Instale el módulo de PowerShell de StaffHub](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="22d9e-165">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="22d9e-166">Vincular una cuenta de Azure AD a los miembros del equipo de StaffHub que no tengan una</span><span class="sxs-lookup"><span data-stu-id="22d9e-166">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="22d9e-167">Cada miembro del equipo de StaffHub debe estar vinculado a una cuenta de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="22d9e-167">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="22d9e-168">Los usuarios de la organización no estarán vinculados a una cuenta de Azure AD si se aplica alguno de los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="22d9e-168">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="22d9e-169">Un propietario de equipo agregó a un usuario que no tiene una cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="22d9e-169">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="22d9e-170">Un propietario del equipo ha invitado a un usuario a un equipo de StaffHub y ese usuario no aceptó la invitación.</span><span class="sxs-lookup"><span data-stu-id="22d9e-170">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="22d9e-171">Puedes vincular una cuenta de Azure AD para estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="22d9e-171">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="22d9e-172">Le mostramos cómo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-172">Here's how.</span></span>

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a><span data-ttu-id="22d9e-173">Obtener una lista de todos los usuarios de los equipos de StaffHub que tienen miembros del equipo que no están vinculados a una cuenta de Azure AD</span><span class="sxs-lookup"><span data-stu-id="22d9e-173">Get a list of all users on StaffHub teams that have team members that aren't linked to an Azure AD account</span></span>

<span data-ttu-id="22d9e-174">Ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22d9e-174">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a><span data-ttu-id="22d9e-175">Vincular la cuenta</span><span class="sxs-lookup"><span data-stu-id="22d9e-175">Link the account</span></span>

<span data-ttu-id="22d9e-176">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="22d9e-176">Do one of the following:</span></span>

- <span data-ttu-id="22d9e-177">Convertir y vincular la cuenta.</span><span class="sxs-lookup"><span data-stu-id="22d9e-177">Convert and link the account.</span></span>

  <span data-ttu-id="22d9e-178">Los propietarios y administradores del equipo de StaffHub pueden convertir una cuenta inactiva y vincularla a una cuenta de Azure AD de StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="22d9e-178">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="22d9e-179">Quite la cuenta desvinculada y, a continuación, vuelva a agregar la cuenta con el UPN.</span><span class="sxs-lookup"><span data-stu-id="22d9e-179">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="22d9e-180">Ejecute el cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) para quitar la cuenta no aprovisionada del equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="22d9e-180">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="22d9e-181">Ejecute el cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para volver a agregar la cuenta al equipo de StaffHub mediante el UPN.</span><span class="sxs-lookup"><span data-stu-id="22d9e-181">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="22d9e-182">Quite la cuenta de usuario sin vincular.</span><span class="sxs-lookup"><span data-stu-id="22d9e-182">Remove the unlinked user account.</span></span> <span data-ttu-id="22d9e-183">Use esta opción la cuenta de usuario ya no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="22d9e-183">Use this option the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="22d9e-184">Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los usuarios</span><span class="sxs-lookup"><span data-stu-id="22d9e-184">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="22d9e-185">Teams incluye una directiva de configuración de aplicaciones de FirstlineWorker integrada que puede usar para personalizar Teams y resaltar las aplicaciones más importantes para los trabajadores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="22d9e-185">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="22d9e-186">Cuando asigne esta directiva a los usuarios, las aplicaciones de la Directiva se anclarán a la barra de la aplicación de Teams para acceder a ellas de forma rápida y fácil.</span><span class="sxs-lookup"><span data-stu-id="22d9e-186">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="22d9e-187">Puede encontrar otras aplicaciones agregadas a teams en la barra de aplicaciones haciendo clic en **... Más aplicaciones** en el escritorio de Teams y en los clientes Web, y deshaciendo el dedo hacia arriba en el cliente móvil de Teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-187">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="22d9e-188">De forma predeterminada, la Directiva de configuración de la aplicación FirstlineWorker incluye las aplicaciones actividad, turnos, chat y llamadas.</span><span class="sxs-lookup"><span data-stu-id="22d9e-188">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="22d9e-189">Para conocer los pasos sobre cómo asignar la Directiva de configuración de la aplicación FirstlineWorker a los usuarios, consulte [usar la Directiva de configuración de la aplicación FirstlineWorker para anclar turnos a teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="22d9e-189">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="22d9e-190">Después de asignar una directiva, esta puede tardar hasta 24 horas en surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="22d9e-190">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="22d9e-191">Le recomendamos que complete este paso al menos una semana antes de mover los equipos y usuarios de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-191">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="22d9e-192">Cuando los usuarios estén en Teams, asegúrese de que pueden ver y acceder a la aplicación turnos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-192">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="22d9e-193">También puede crear directivas de configuración de aplicaciones personalizadas y editar la configuración en la Directiva configuración global de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22d9e-193">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="22d9e-194">Para obtener más información, consulte [Administrar directivas de configuración de aplicaciones en Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="22d9e-194">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="22d9e-195">Usuarios incorporados a teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-195">Onboard users to Teams</span></span>

<span data-ttu-id="22d9e-196">Como parte de la estrategia de incorporación, proporcione formación e instrucciones a los usuarios para que puedan familiarizarse con los equipos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-196">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="22d9e-197">Comparta los siguientes recursos con los usuarios para que sepan dónde obtener los clientes, la formación y el soporte técnico de Teams:</span><span class="sxs-lookup"><span data-stu-id="22d9e-197">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="22d9e-198">Cliente web de Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-198">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="22d9e-199">Vínculos de descarga del cliente de escritorio y móvil</span><span class="sxs-lookup"><span data-stu-id="22d9e-199">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="22d9e-200">Vídeos de aprendizaje de Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-200">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="22d9e-201">Documentación de Ayuda de Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-201">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="22d9e-202">Para obtener instrucciones sobre la implementación de equipos y sobre la adopción de equipos, consulte [Cómo](../../How-to-roll-out-teams.md) implementar Teams y [adoptar equipos](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="22d9e-202">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="22d9e-203">Realizar una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="22d9e-203">Conduct a pilot</span></span>

<span data-ttu-id="22d9e-204">Le recomendamos que empiece por mover dos o tres equipos de StaffHub para un grupo seleccionado de primeras personas.</span><span class="sxs-lookup"><span data-stu-id="22d9e-204">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="22d9e-205">La ejecución de un proyecto piloto le ayuda a afinar el plan de transición y a asegurarse de que está listo para mover todos los equipos de StaffHub de su organización a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-205">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="22d9e-206">También identifica a los campeones que pueden ayudar a impulsar la adopción en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="22d9e-206">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="22d9e-207">Si es una pequeña empresa que no necesita un enfoque por fases, es posible que los pasos de esta sección sean todo lo que necesita para cambiar de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-207">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="22d9e-208">Identificar equipos piloto</span><span class="sxs-lookup"><span data-stu-id="22d9e-208">Identify pilot teams</span></span>

<span data-ttu-id="22d9e-209">Póngase en contacto con usted para identificar dos o tres equipos piloto.</span><span class="sxs-lookup"><span data-stu-id="22d9e-209">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="22d9e-210">Todos los miembros del equipo deben confirmar el uso de turnos en Teams para administrar su programación y comunicarse y colaborar entre sí.</span><span class="sxs-lookup"><span data-stu-id="22d9e-210">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="22d9e-211">Identificar a los expertos en el equipo</span><span class="sxs-lookup"><span data-stu-id="22d9e-211">Identify team champions</span></span>

<span data-ttu-id="22d9e-212">Identifique a los campeones a través de equipos piloto y inscribalos para ayudar a repartir turnos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-212">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="22d9e-213">Los campeones del equipo son apasionados de lo que hacen, compartiendo su propio aprendizaje para ofrecer asistencia y orientación a los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-213">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="22d9e-214">Los expertos del equipo pueden ser administradores o propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-214">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="22d9e-215">Los expertos en equipo deben asegurarse de que los miembros del equipo se configuren dedicando tiempo para que todos puedan [obtener clientes](../../get-clients.md)de equipo, iniciar sesión en Teams y consultar sus programaciones en turnos y empezar a conversar entre sí.</span><span class="sxs-lookup"><span data-stu-id="22d9e-215">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="22d9e-216">Los usuarios que ya estén familiarizados con StaffHub se activarán y se ejecutarán rápidamente en turnos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-216">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="22d9e-217">También puede hacer que desplace la [ayuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener ayuda adicional.</span><span class="sxs-lookup"><span data-stu-id="22d9e-217">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="22d9e-218">Mover un equipo de StaffHub</span><span class="sxs-lookup"><span data-stu-id="22d9e-218">Move a StaffHub team</span></span>

<span data-ttu-id="22d9e-219">Siga estos pasos para mover un equipo de StaffHub a la vez.</span><span class="sxs-lookup"><span data-stu-id="22d9e-219">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="22d9e-220">Recomendamos este enfoque para los equipos de la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="22d9e-220">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="22d9e-221">Más adelante, cuando esté listo para mover todos los equipos de StaffHub de su organización, vea [mover los equipos de staffhub](#move-your-staffhub-teams) para conocer los pasos para mover varios equipos a la vez.</span><span class="sxs-lookup"><span data-stu-id="22d9e-221">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="22d9e-222">Ejecute lo siguiente para mover un equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="22d9e-222">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="22d9e-223">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22d9e-223">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="22d9e-224">Este es un ejemplo de la respuesta que obtiene al enviar una solicitud para mover un equipo de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-224">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="22d9e-225">Para comprobar el estado de una solicitud de movimiento, ejecute lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="22d9e-225">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="22d9e-226">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22d9e-226">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="22d9e-227">Este es un ejemplo de la respuesta que obtiene cuando hay un movimiento en curso.</span><span class="sxs-lookup"><span data-stu-id="22d9e-227">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="22d9e-228">Mover archivos de un equipo de StaffHub a teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-228">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="22d9e-229">Este paso solo se aplica si el equipo de StaffHub que movió a teams tiene archivos que también desea mover a teams.</span><span class="sxs-lookup"><span data-stu-id="22d9e-229">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="22d9e-230">Puede mover archivos directamente en SharePoint Online o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22d9e-230">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="22d9e-231">En SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="22d9e-231">In SharePoint Online</span></span>

<span data-ttu-id="22d9e-232">Vea [Cómo mover archivos en SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="22d9e-232">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="22d9e-233">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="22d9e-233">Using PowerShell</span></span>

<span data-ttu-id="22d9e-234">Descargue e instale el [Shell de administración de SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), si todavía no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="22d9e-234">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="22d9e-235">Contiene los cmdlets que necesita para mover los archivos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-235">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="22d9e-236">Use el cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para conectarse al sitio de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="22d9e-236">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="22d9e-237">Para cada archivo que desee mover de StaffHub a Teams, use el cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover el archivo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-237">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="22d9e-238">Para mover varios archivos, recorra los archivos y ejecute el segundo comando en el bucle.</span><span class="sxs-lookup"><span data-stu-id="22d9e-238">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="22d9e-239">No es necesario que repitas el primer comando si la sesión sigue activa.</span><span class="sxs-lookup"><span data-stu-id="22d9e-239">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="22d9e-240">Vaya más allá de la prueba piloto y mueva todos los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="22d9e-240">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="22d9e-241">Aumentar el conocimiento</span><span class="sxs-lookup"><span data-stu-id="22d9e-241">Raise awareness</span></span>

<span data-ttu-id="22d9e-242">Cuando esté listo para ir más allá de los equipos piloto y mover los equipos de StaffHub de su organización a Teams, es importante comunicar primero el cambio en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="22d9e-242">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="22d9e-243">Represente la palabra acerca de los turnos y la transición a Teams para aumentar la conciencia, generar entusiasmo y adopción de unidades.</span><span class="sxs-lookup"><span data-stu-id="22d9e-243">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="22d9e-244">Mover los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="22d9e-244">Move your StaffHub teams</span></span>

<span data-ttu-id="22d9e-245">Siga estos pasos para mover equipos de StaffHub de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="22d9e-245">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="22d9e-246">Puede elegir mover todos los equipos de StaffHub de su organización o mover determinados equipos de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="22d9e-246">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="22d9e-247">Si quiere mover los equipos de StaffHub de uno en uno, vea [mover un equipo de staffhub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="22d9e-247">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="22d9e-248">Mover todos los equipos de StaffHub</span><span class="sxs-lookup"><span data-stu-id="22d9e-248">Move all StaffHub teams</span></span>

<span data-ttu-id="22d9e-249">Ejecute lo siguiente para obtener una lista de todos los equipos de StaffHub de su organización.</span><span class="sxs-lookup"><span data-stu-id="22d9e-249">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="22d9e-250">A continuación, ejecute lo siguiente para mover todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-250">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="22d9e-251">Este es un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="22d9e-251">Here's an example of the response.</span></span>

<span data-ttu-id="22d9e-252">En el caso de cualquier equipo que ya se haya movido a teams o que ya exista en Teams, jobId tendrá el valor "null", ya que no es necesario enviar el trabajo para mover ese equipo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-252">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="22d9e-253">Mover equipos de StaffHub específicos</span><span class="sxs-lookup"><span data-stu-id="22d9e-253">Move specific StaffHub teams</span></span>

<span data-ttu-id="22d9e-254">Ejecute el siguiente procedimiento para obtener una lista de todos los identificadores de equipo de StaffHub en su organización.</span><span class="sxs-lookup"><span data-stu-id="22d9e-254">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="22d9e-255">En los resultados devueltos `Get-StaffHubteamsForTenant` por el cmdlet que ejecutó anteriormente, seleccione los identificadores de equipo que desea mover y agréguelos a un archivo de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="22d9e-255">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="22d9e-256">Este es un ejemplo de cómo se debe dar formato al archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="22d9e-256">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="22d9e-257">Identificar</span><span class="sxs-lookup"><span data-stu-id="22d9e-257">Id</span></span>  |
|---------|
|<span data-ttu-id="22d9e-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="22d9e-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="22d9e-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="22d9e-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="22d9e-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="22d9e-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="22d9e-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="22d9e-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="22d9e-262">Después de crear el archivo CSV, ejecute lo siguiente para mover los equipos especificados en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="22d9e-262">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="22d9e-263">Confirmar que los equipos de StaffHub se movieron a teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-263">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="22d9e-264">Ejecute lo siguiente para obtener una lista de todos los equipos de los turnos de su organización.</span><span class="sxs-lookup"><span data-stu-id="22d9e-264">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="22d9e-265">Mover archivos de los equipos de StaffHub a teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-265">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="22d9e-266">Si los equipos de StaffHub que movió contiene archivos que también desea mover a Teams, vea [mover archivos de un equipo de staffhub a teams](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="22d9e-266">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="22d9e-267">Supervisar el uso de Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-267">Monitor Teams usage</span></span>

<span data-ttu-id="22d9e-268">Los informes de uso pueden ayudarlo a comprender mejor los patrones de uso y le proporcionan información sobre cómo priorizar los esfuerzos de aprendizaje y comunicación en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="22d9e-268">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="22d9e-269">Puede ejecutar informes que muestran el uso general de los equipos, los tipos de actividades que los usuarios realizan en Teams, cómo se conectan los usuarios a teams y mucho más.</span><span class="sxs-lookup"><span data-stu-id="22d9e-269">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="22d9e-270">Para obtener más información, vea informes [de equipos en el centro de administración de Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) y [informes de actividades de Teams en el centro de administración de Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="22d9e-270">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="22d9e-271">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="22d9e-271">Troubleshooting</span></span>

<span data-ttu-id="22d9e-272">**Al intentar mover archivos de StaffHub a Teams, recibe el mensaje de error "Permiso denegado".**</span><span class="sxs-lookup"><span data-stu-id="22d9e-272">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="22d9e-273">Esto puede ocurrir si está intentando mover archivos en un grupo privado de Office 365 del que no es miembro.</span><span class="sxs-lookup"><span data-stu-id="22d9e-273">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="22d9e-274">Si este es el caso, use el cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para agregarse al equipo de StaffHub y, a continuación, mueva los archivos.</span><span class="sxs-lookup"><span data-stu-id="22d9e-274">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="22d9e-275">Después de mover los archivos, use el cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) para quitarse del equipo.</span><span class="sxs-lookup"><span data-stu-id="22d9e-275">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="22d9e-276">**Al intentar mover archivos de StaffHub a Teams, recibe un error que indica que no existe la carpeta general.**</span><span class="sxs-lookup"><span data-stu-id="22d9e-276">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="22d9e-277">Ejecute el siguiente comando para agregar la carpeta general a SharePoint y, a continuación, vuelva a intentarlo:</span><span class="sxs-lookup"><span data-stu-id="22d9e-277">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="22d9e-278">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="22d9e-278">Related topics</span></span>
- [<span data-ttu-id="22d9e-279">Cómo implementar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-279">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="22d9e-280">Se retirará Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="22d9e-280">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="22d9e-281">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22d9e-281">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="22d9e-282">Referencia de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="22d9e-282">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
