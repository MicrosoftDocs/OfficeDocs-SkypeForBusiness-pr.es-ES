---
title: Mover los equipos de StaffHub a Turnos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo mover los equipos de Microsoft StaffHub y programar datos a turnos en Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 885872b62d15091faf8b14609aed69b274c1ae74
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914589"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="8c66b-103">Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c66b-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c66b-104">Eficaces se deben retirarse el 1 de octubre de 2019, Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8c66b-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="8c66b-105">Capacidades de StaffHub que estamos creando en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c66b-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="8c66b-106">En la actualidad, los equipos incluye la aplicación de turnos para la administración de programación y funciones adicionales se lleve a cabo a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="8c66b-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="8c66b-107">StaffHub dejará de funcionar para todos los usuarios en el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="8c66b-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="8c66b-108">Cualquier persona que intenta abrir StaffHub se mostrará un mensaje que les dirige a descargar los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="8c66b-109">Para obtener más información, vea [Microsoft StaffHub retirarse](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="8c66b-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="8c66b-110">Aún no se ha emitido la funcionalidad descrita en este artículo.</span><span class="sxs-lookup"><span data-stu-id="8c66b-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="8c66b-111">Se ha anunciado y estará disponible próximamente, hacia el final de abril de 2019.</span><span class="sxs-lookup"><span data-stu-id="8c66b-111">It's been announced, and is coming soon, towards the end of April 2019.</span></span> <span data-ttu-id="8c66b-112">Si usted es un administrador, puede saber cuándo estará disponible en el centro de mensajes (en el [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="8c66b-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="8c66b-113">La aplicación de turnos en los equipos proporciona un método sencillo para administración de programaciones y el flujo constante de MAYÚS permutaciones y cancelaciones que se producen en un diario.</span><span class="sxs-lookup"><span data-stu-id="8c66b-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="8c66b-114">Los miembros del equipo pueden tener acceso a su programación y MAYÚS información directamente en la aplicación y a través de sus dispositivos para establecer sus preferencias, administrar sus programaciones y tiempo de la solicitud desactivado.</span><span class="sxs-lookup"><span data-stu-id="8c66b-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="8c66b-115">En este artículo le guiará a través del procedimiento para mover los equipos de su organización StaffHub y programar datos a turnos en los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="8c66b-116">Independientemente de si una empresa pequeña con uno o dos equipos de StaffHub o una empresa grande con cientos de equipos StaffHub, aquí encontrará la orientación de administración que necesita para ayudar a hacer la transición a los equipos se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c66b-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="8c66b-117">Debe ser un administrador global para llevar a cabo los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="8c66b-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="8c66b-118">Si aún no lo ha hecho, eche un vistazo a través de la [retirada de StaffHub preguntas más frecuentes](microsoft-staffhub-to-be-retired.md) para obtener respuestas a cualquier pregunta que tenga.</span><span class="sxs-lookup"><span data-stu-id="8c66b-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="8c66b-119">Lo que necesita saber sobre el movimiento para los equipos</span><span class="sxs-lookup"><span data-stu-id="8c66b-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="8c66b-120">Cuándo se deben mover a los equipos</span><span class="sxs-lookup"><span data-stu-id="8c66b-120">When to move to Teams</span></span>

<span data-ttu-id="8c66b-121">Eficaces se deben retirarse el 1 de octubre de 2019, StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8c66b-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="8c66b-122">Le animamos a empezar a usar los equipos de hoy en día y empezar a realizar la transición de los equipos y usuarios de StaffHub de su organización.</span><span class="sxs-lookup"><span data-stu-id="8c66b-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="8c66b-123">Con la administración de programación que se va a la característica usan con más frecuencia en StaffHub, se recomienda que usar la aplicación de turnos en los equipos en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8c66b-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="8c66b-124">¿Qué se mueve a los equipos</span><span class="sxs-lookup"><span data-stu-id="8c66b-124">What is moved to Teams</span></span>

<span data-ttu-id="8c66b-125">Detalles del usuario, la información de programación y datos de chat y de archivo son la transición a los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="8c66b-126">Esto incluye los miembros del equipo, las programaciones de equipo y chats y los archivos de los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="8c66b-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="8c66b-127">Cada equipo StaffHub necesita un grupo de 365 Office correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8c66b-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="8c66b-128">Si un equipo StaffHub no tiene un grupo de Office 365 asociados con ella, uno se crea automáticamente para que admitir la transición.</span><span class="sxs-lookup"><span data-stu-id="8c66b-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="8c66b-129">Teniendo en cuenta la diferencia en el equipo y la asignación de nombres de grupo entre los equipos y StaffHub, es posible que vea un nombre de equipo diferente en los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="8c66b-130">Como hacer la transición de los equipos de StaffHub a los equipos, los usuarios ya no tendrán acceso a sus programaciones en StaffHub y se redirigen a turnos en los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="8c66b-131">Se recomienda que comunicarse este cambio en toda la organización para minimizar las interrupciones y para animar a los usuarios a adoptar y explorar los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span>

## <a name="prepare"></a><span data-ttu-id="8c66b-132">Preparar</span><span class="sxs-lookup"><span data-stu-id="8c66b-132">Prepare</span></span>

<span data-ttu-id="8c66b-133">Aquí es cómo prepararse para mover a los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-133">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="8c66b-134">Asignar licencias de Teams</span><span class="sxs-lookup"><span data-stu-id="8c66b-134">Assign Teams licenses</span></span>

<span data-ttu-id="8c66b-135">Cada usuario debe tener una licencia de Microsoft 365 u Office 365 activada desde [un plan de elegible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y se debe asignar una licencia de los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-135">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="8c66b-136">Asignación de una licencia de los equipos a los usuarios les proporciona acceso a los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-136">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="8c66b-137">Administrar las licencias de los equipos en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c66b-137">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8c66b-138">Para obtener más información, vea [administrar el acceso de usuarios a los equipos](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8c66b-138">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8c66b-139">Si la organización usa Skype para la empresa y no está listo para mover todos los usuarios a los equipos, puede habilitar los equipos para su Firstline a los trabajadores que, a continuación, puede ejecutar los equipos junto con Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="8c66b-139">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="8c66b-140">En este modo de coexistencia, llamado *Islas*, cada aplicación cliente funciona como una solución independiente.</span><span class="sxs-lookup"><span data-stu-id="8c66b-140">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="8c66b-141">Para obtener más información, vea [Descripción de los equipos y Skype para la interoperabilidad y coexistencia de negocio](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="8c66b-141">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="8c66b-142">Aprovisionamiento de cuentas para los usuarios de StaffHub que no tienen una identidad en Azure AD</span><span class="sxs-lookup"><span data-stu-id="8c66b-142">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="8c66b-143">Cada administrador y miembro del equipo deben tener una identidad en Azure Active Directory (AD Azure).</span><span class="sxs-lookup"><span data-stu-id="8c66b-143">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="8c66b-144">Si un usuario ya no tiene una identidad en Azure AD, aprovisionar una cuenta para ellos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-144">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="8c66b-145">Le mostramos cómo.</span><span class="sxs-lookup"><span data-stu-id="8c66b-145">Here's how.</span></span>

- <span data-ttu-id="8c66b-146">Los administradores y propietarios de equipo StaffHub pueden convertir una cuenta ficticia o inactiva y vincularlo a una cuenta proporcionada en StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8c66b-146">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="8c66b-147">Los administradores pueden ejecutar el [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) y cmdlets de [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para quitar una cuenta que no sean aprovisionado de un equipo de StaffHub y agregue la cuenta de back-usando el UPN.</span><span class="sxs-lookup"><span data-stu-id="8c66b-147">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="8c66b-148">Instalar el módulo de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="8c66b-148">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="8c66b-149">Si no lo ha hecho ya, [instale el módulo de StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="8c66b-149">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="8c66b-150">Cuando se mueve un equipo de StaffHub, la solicitud de movimiento comprueba los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-150">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="8c66b-151">Aquí es motivos de por qué puede producir un error de una solicitud de movimiento:</span><span class="sxs-lookup"><span data-stu-id="8c66b-151">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="8c66b-152">El usuario ha iniciado sesión no es un administrador global</span><span class="sxs-lookup"><span data-stu-id="8c66b-152">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="8c66b-153">Los equipos se deshabilita para todos los usuarios en el inquilino</span><span class="sxs-lookup"><span data-stu-id="8c66b-153">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="8c66b-154">Creación de grupos de Office 365 está deshabilitada en el inquilino</span><span class="sxs-lookup"><span data-stu-id="8c66b-154">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="8c66b-155">La teamId StaffHub no es válido o no tiene ningún miembro</span><span class="sxs-lookup"><span data-stu-id="8c66b-155">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="8c66b-156">El equipo de StaffHub incluye a miembros que no están vinculados a una cuenta de Azure AD</span><span class="sxs-lookup"><span data-stu-id="8c66b-156">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="8c66b-157">Ejecutar una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="8c66b-157">Run a pilot</span></span>

<span data-ttu-id="8c66b-158">Se recomienda que inicie moviendo dos o tres equipos de StaffHub para un grupo seleccionado de los primeros usuarios.</span><span class="sxs-lookup"><span data-stu-id="8c66b-158">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="8c66b-159">Ejecutar a una prueba piloto le ayuda a refinar el plan de transición y asegúrese de que está listo para mover los equipos de StaffHub de todos los de su organización a los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-159">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="8c66b-160">Se identifican los Campeones que pueden ayudar a estimular la adopción en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="8c66b-160">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="8c66b-161">Si usted es una empresa pequeña que no necesita un enfoque por fases, los pasos descritos en esta sección pueden ser todo lo que necesita para realizar el cambio de StaffHub a los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-161">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="8c66b-162">Identificar los equipos pilotos</span><span class="sxs-lookup"><span data-stu-id="8c66b-162">Identify pilot teams</span></span>

<span data-ttu-id="8c66b-163">Llegar a identificar dos o tres equipos pilotos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-163">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="8c66b-164">Todos los miembros del equipo deben confirmar al uso de turnos en los equipos a administrar sus programaciones y comunicarse y colaborar con cada una de las demás.</span><span class="sxs-lookup"><span data-stu-id="8c66b-164">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="8c66b-165">Identificar a campeones de equipo</span><span class="sxs-lookup"><span data-stu-id="8c66b-165">Identify team champions</span></span>

<span data-ttu-id="8c66b-166">Identificar a campeones entre los equipos pilotos y dar de alta para ayudar a dé a conocer turnos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-166">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="8c66b-167">Campeones de equipo son entusiastas sobre lo que hacen, uso compartido de sus propios conocimientos para ofrecer soporte técnico y orientación a los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="8c66b-167">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="8c66b-168">Campeones de equipo pueden ser propietarios de equipo o los administradores.</span><span class="sxs-lookup"><span data-stu-id="8c66b-168">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="8c66b-169">Deben asegurarse de campeones de equipo los integrantes del grupo están configurar por dedique tiempo para todos los usuarios para [obtener a los clientes de los equipos](../../get-clients.md), inicie sesión en los equipos y desproteger sus programaciones por turnos e inicio charlar con cada una de las demás.</span><span class="sxs-lookup"><span data-stu-id="8c66b-169">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="8c66b-170">Los usuarios que ya están familiarizados con StaffHub será y en funcionamiento rápidamente por turnos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-170">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="8c66b-171">También puede indicarles que [Ayudarán a turnos](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener más ayuda.</span><span class="sxs-lookup"><span data-stu-id="8c66b-171">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="8c66b-172">Mover un equipo de StaffHub (próximamente)</span><span class="sxs-lookup"><span data-stu-id="8c66b-172">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="8c66b-173">Siga estos pasos para mover un equipo de StaffHub a la vez.</span><span class="sxs-lookup"><span data-stu-id="8c66b-173">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="8c66b-174">Se recomienda este enfoque para los equipos de prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="8c66b-174">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="8c66b-175">Más adelante, cuando esté listo para mover los equipos de StaffHub de todos los de su organización, consulte [mover sus equipos StaffHub](#move-your-staffhub-teams-coming-soon) para obtener instrucciones acerca de cómo mover varios equipos a la vez.</span><span class="sxs-lookup"><span data-stu-id="8c66b-175">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="8c66b-176">Ejecute el siguiente procedimiento para mover un equipo StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8c66b-176">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="8c66b-177">Este es un ejemplo de la respuesta que se obtiene al enviar una solicitud para mover un equipo de StaffHub a los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-177">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="8c66b-178">Para comprobar el estado de una solicitud de movimiento, ejecute lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8c66b-178">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="8c66b-179">Este es un ejemplo de la respuesta que se obtiene cuando un movimiento está en curso.</span><span class="sxs-lookup"><span data-stu-id="8c66b-179">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="8c66b-180">Realizar la transición desde StaffHub a los equipos</span><span class="sxs-lookup"><span data-stu-id="8c66b-180">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="8c66b-181">Mejorar el conocimiento</span><span class="sxs-lookup"><span data-stu-id="8c66b-181">Raise awareness</span></span>

<span data-ttu-id="8c66b-182">Cuando esté listo para ir más allá de sus equipos pilotos y mover los equipos de su organización StaffHub a los equipos, es importante comunicarse en primer lugar el cambio a través de la organización.</span><span class="sxs-lookup"><span data-stu-id="8c66b-182">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="8c66b-183">Propagar la palabra acerca de turnos y la transición a los equipos para mejorar el conocimiento, generar diversión y adopción de unidad.</span><span class="sxs-lookup"><span data-stu-id="8c66b-183">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="8c66b-184">Mover los equipos de StaffHub (próximamente)</span><span class="sxs-lookup"><span data-stu-id="8c66b-184">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="8c66b-185">Siga estos pasos para mover los equipos de StaffHub de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="8c66b-185">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="8c66b-186">Puede elegir mover los equipos de StaffHub de todos los de su organización o mover determinados equipos StaffHub.</span><span class="sxs-lookup"><span data-stu-id="8c66b-186">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="8c66b-187">Si desea mover que los equipos StaffHub uno a la vez, consulte [mover un equipo StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="8c66b-187">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="8c66b-188">Mover todos los equipos de StaffHub (próximamente)</span><span class="sxs-lookup"><span data-stu-id="8c66b-188">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="8c66b-189">Ejecute el siguiente procedimiento para obtener una lista de todos los equipos de StaffHub en su organización.</span><span class="sxs-lookup"><span data-stu-id="8c66b-189">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="8c66b-190">A continuación, ejecute el siguiente procedimiento para mover todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-190">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="8c66b-191">Este es un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="8c66b-191">Here's an example of the response.</span></span>

<span data-ttu-id="8c66b-192">Para cualquier equipo que ya se ha movido a los equipos o ya existe en los equipos, jobId será "null" como un trabajo no es necesario que se debe enviar para mover ese equipo.</span><span class="sxs-lookup"><span data-stu-id="8c66b-192">For any team that already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="8c66b-193">Mover determinados equipos StaffHub (próximamente)</span><span class="sxs-lookup"><span data-stu-id="8c66b-193">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="8c66b-194">Ejecute el siguiente procedimiento para obtener una lista de todos los StaffHub equipo identificadores en su organización.</span><span class="sxs-lookup"><span data-stu-id="8c66b-194">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="8c66b-195">En los resultados devueltos por la `Get-StaffHubteamsForTenant` cmdlet ejecutó anteriormente, seleccione los identificadores de equipo que desea mover y, a continuación, agregarlas a un archivo de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="8c66b-195">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="8c66b-196">Este es un ejemplo de cómo se debe aplicar el formato de archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="8c66b-196">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="8c66b-197">Id.</span><span class="sxs-lookup"><span data-stu-id="8c66b-197">Id</span></span>  |
|---------|
|<span data-ttu-id="8c66b-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="8c66b-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="8c66b-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="8c66b-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="8c66b-200">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="8c66b-200">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="8c66b-201">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="8c66b-201">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="8c66b-202">Después de crear el archivo CSV, ejecute el siguiente procedimiento para mover los equipos que especificó en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="8c66b-202">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="8c66b-203">Confirme que los equipos de StaffHub se han movido a los equipos (próximamente)</span><span class="sxs-lookup"><span data-stu-id="8c66b-203">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="8c66b-204">Ejecute el siguiente procedimiento para obtener una lista de todos los equipos de turnos en su organización.</span><span class="sxs-lookup"><span data-stu-id="8c66b-204">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

#### 

## <a name="monitor-teams-usage"></a><span data-ttu-id="8c66b-205">Supervisar el uso de los equipos</span><span class="sxs-lookup"><span data-stu-id="8c66b-205">Monitor Teams usage</span></span>

<span data-ttu-id="8c66b-206">Informes de uso le ayudarán a comprender los patrones de uso mejor y proporcionan una perspectiva sobre dónde asignar prioridades a los esfuerzos de aprendizaje y la comunicación en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="8c66b-206">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="8c66b-207">Dado que turnos es una aplicación en los equipos, puede ver el uso a través de informes de los equipos.</span><span class="sxs-lookup"><span data-stu-id="8c66b-207">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="8c66b-208">Para obtener más información, vea [creación de informes de los equipos en el centro de administración de equipos de Microsoft](../../teams-analytics-and-reports/teams-reporting-reference.md) e [informes de actividad de los equipos en el centro de administración de Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="8c66b-208">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c66b-209">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8c66b-209">Related topics</span></span>
- [<span data-ttu-id="8c66b-210">Se retirará Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="8c66b-210">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="8c66b-211">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c66b-211">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="8c66b-212">Referencia de StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c66b-212">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
