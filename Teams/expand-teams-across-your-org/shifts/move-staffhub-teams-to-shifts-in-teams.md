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
description: Obtenga información sobre cómo mover los equipos de Microsoft StaffHub y programar datos para desplazarse por Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548297"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="1166e-103">Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1166e-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1166e-104">A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="1166e-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="1166e-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="1166e-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="1166e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="1166e-107">StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="1166e-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="1166e-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="1166e-109">Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.</span><span class="sxs-lookup"><span data-stu-id="1166e-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="1166e-110">La funcionalidad tratada en este artículo todavía no se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="1166e-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="1166e-111">Se ha anunciado y pronto estará disponible a principios del 2019 de junio.</span><span class="sxs-lookup"><span data-stu-id="1166e-111">It's been announced, and is coming soon, in early June 2019.</span></span> <span data-ttu-id="1166e-112">Si es un administrador, puede averiguar cuándo estará disponible en el centro de mensajes (en el centro de administración de [Microsoft 365](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="1166e-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="1166e-113">La aplicación de turnos de Teams ofrece un enfoque simple para administrar las programaciones y el flujo constante de swaps y cancelaciones de turnos que se producen diariamente.</span><span class="sxs-lookup"><span data-stu-id="1166e-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="1166e-114">Los miembros del equipo pueden acceder a su programación y desplazar la información directamente en la aplicación y en todos sus dispositivos para establecer sus preferencias, administrar sus programaciones y solicitar tiempo.</span><span class="sxs-lookup"><span data-stu-id="1166e-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="1166e-115">Este artículo le muestra cómo mover los equipos de StaffHub y programar datos para desplazarse por los equipos.</span><span class="sxs-lookup"><span data-stu-id="1166e-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="1166e-116">Tanto si es una pequeña empresa con uno o dos equipos de StaffHub como si es una empresa grande con cientos de equipos de StaffHub, aquí encontrará las instrucciones para administradores que necesita para que la transición a teams se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="1166e-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="1166e-117">Debe ser administrador global para poder realizar los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="1166e-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="1166e-118">Si todavía no lo ha hecho, consulte las [preguntas más frecuentes sobre la jubilación de StaffHub](microsoft-staffhub-to-be-retired.md) para obtener respuestas a las preguntas que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="1166e-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="1166e-119">Lo que debe saber sobre el desplazamiento a teams</span><span class="sxs-lookup"><span data-stu-id="1166e-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="1166e-120">Cuándo mover a teams</span><span class="sxs-lookup"><span data-stu-id="1166e-120">When to move to Teams</span></span>

<span data-ttu-id="1166e-121">A partir del 1 de octubre de 2019, se retirará StaffHub.</span><span class="sxs-lookup"><span data-stu-id="1166e-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="1166e-122">Le recomendamos que comience a usar Teams hoy y empiece a cambiar la transición de los equipos y usuarios de su organización de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="1166e-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="1166e-123">Con la administración de programación como la característica que se usa con más frecuencia en StaffHub, le recomendamos que use la aplicación turnos en Teams en el futuro.</span><span class="sxs-lookup"><span data-stu-id="1166e-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="1166e-124">Qué se mueve a teams</span><span class="sxs-lookup"><span data-stu-id="1166e-124">What is moved to Teams</span></span>

<span data-ttu-id="1166e-125">Los detalles del usuario, la información de programación y los datos de chat y de archivos están migrados a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="1166e-126">Esto incluye la pertenencia a grupos, las programaciones de equipo y los chats y archivos de los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="1166e-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="1166e-127">Cada equipo de StaffHub necesita un grupo de Office 365 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1166e-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="1166e-128">Si un equipo de StaffHub no tiene asociado un grupo de Office 365, se crea uno automáticamente para que admita la transición.</span><span class="sxs-lookup"><span data-stu-id="1166e-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="1166e-129">Dada la diferencia de nomenclatura de equipo y grupo entre Teams y StaffHub, es posible que vea un nombre de equipo diferente en Teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="1166e-130">A medida que vaya migrando equipos de StaffHub a Teams, los usuarios ya no tendrán acceso a sus programaciones en StaffHub y se redirigirán a los equipos.</span><span class="sxs-lookup"><span data-stu-id="1166e-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="1166e-131">Le recomendamos que comunique este cambio en toda la organización para minimizar las interrupciones y para animar a los usuarios a adoptar y explorar equipos.</span><span class="sxs-lookup"><span data-stu-id="1166e-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="1166e-132">Si tiene Azure AD Premium, puede [ejecutar un informe](run-report-to-show-staffhub-usage.md) para obtener una lista de los usuarios de StaffHub de su organización que necesitan saber sobre este cambio.</span><span class="sxs-lookup"><span data-stu-id="1166e-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="1166e-133">No hay ninguna opción de deshacer después de mover un equipo de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="1166e-134">Experiencia de usuario al mover un equipo</span><span class="sxs-lookup"><span data-stu-id="1166e-134">User experience when you move a team</span></span>

<span data-ttu-id="1166e-135">El tiempo de inactividad es mínimo (menos de un segundo, si lo hay) para los usuarios cuando su equipo cambia de StaffHub a turnos en Teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="1166e-136">Los usuarios pueden seguir usando StaffHub hasta que se complete el cambio a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="1166e-137">Cuando se haya completado el movimiento, los miembros del equipo verán un mensaje para informarles de que necesitan comenzar a usar turnos en Teams para acceder a su programación de equipo.</span><span class="sxs-lookup"><span data-stu-id="1166e-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="1166e-138">Este es un ejemplo del mensaje que los usuarios ven después de que el equipo de StaffHub se mueva a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-138">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="1166e-139">![Ejemplo del mensaje que los usuarios ven.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de staffhub a teams")</span><span class="sxs-lookup"><span data-stu-id="1166e-139">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="1166e-140">Preparar</span><span class="sxs-lookup"><span data-stu-id="1166e-140">Prepare</span></span>

<span data-ttu-id="1166e-141">Aquí le mostramos cómo prepararse para desplazarse a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="1166e-142">Asignar licencias de Teams</span><span class="sxs-lookup"><span data-stu-id="1166e-142">Assign Teams licenses</span></span>

<span data-ttu-id="1166e-143">Cada usuario debe tener una licencia activa de Microsoft 365 o de Office 365 de [un plan apto](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y debe tener asignada una licencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="1166e-144">Asignar una licencia de Teams a los usuarios les da acceso a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="1166e-145">Administra las licencias de Teams en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1166e-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1166e-146">Para obtener más información, vea [administrar el acceso de los usuarios a teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1166e-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1166e-147">Si su organización usa Skype empresarial y no está listo para mover a todos los usuarios a Teams, puede habilitar a Teams para sus trabajadores de los Firstline, que luego pueden ejecutar equipos junto con Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1166e-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="1166e-148">En este modo de coexistencia, llamadas *islas*, cada aplicación cliente funciona como una solución independiente.</span><span class="sxs-lookup"><span data-stu-id="1166e-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="1166e-149">Para obtener más información, consulte [comprender Teams y la interoperabilidad y coexistencia de Skype empresarial](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="1166e-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="1166e-150">Aprovisionar cuentas para los usuarios de StaffHub que no tienen una identidad en Azure AD</span><span class="sxs-lookup"><span data-stu-id="1166e-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="1166e-151">Cada administrador y cada miembro del equipo debe tener una identidad en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1166e-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="1166e-152">Si un usuario aún no tiene una identidad en Azure AD, aprovisione una cuenta.</span><span class="sxs-lookup"><span data-stu-id="1166e-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="1166e-153">Le mostramos cómo.</span><span class="sxs-lookup"><span data-stu-id="1166e-153">Here's how.</span></span>

- <span data-ttu-id="1166e-154">Los propietarios y administradores del equipo de StaffHub pueden convertir una cuenta ficticia o inactiva y vincularla a una cuenta aprovisionada de StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="1166e-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="1166e-155">Los administradores pueden ejecutar los cmdlets [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) y [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para quitar una cuenta no aprovisionada de un equipo de StaffHub y agregarla de nuevo con el UPN.</span><span class="sxs-lookup"><span data-stu-id="1166e-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="1166e-156">Instalar el módulo de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="1166e-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="1166e-157">Si todavía no lo ha hecho, [Instale el módulo de PowerShell de StaffHub](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="1166e-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="1166e-158">Al mover un equipo de StaffHub, la solicitud de movimiento comprueba los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="1166e-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="1166e-159">Estas son las razones por las que se puede producir un error en una solicitud de movimiento:</span><span class="sxs-lookup"><span data-stu-id="1166e-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="1166e-160">El usuario que ha iniciado sesión no es un administrador global</span><span class="sxs-lookup"><span data-stu-id="1166e-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="1166e-161">Teams está deshabilitado para todos los usuarios del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="1166e-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="1166e-162">La creación de grupos de Office 365 está deshabilitada en el inquilino</span><span class="sxs-lookup"><span data-stu-id="1166e-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="1166e-163">El teamId de StaffHub no es válido o no tiene miembros</span><span class="sxs-lookup"><span data-stu-id="1166e-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="1166e-164">El equipo de StaffHub incluye miembros que no están vinculados a una cuenta de Azure AD</span><span class="sxs-lookup"><span data-stu-id="1166e-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="1166e-165">Ejecutar una prueba piloto</span><span class="sxs-lookup"><span data-stu-id="1166e-165">Run a pilot</span></span>

<span data-ttu-id="1166e-166">Le recomendamos que empiece por mover dos o tres equipos de StaffHub para un grupo seleccionado de primeras personas.</span><span class="sxs-lookup"><span data-stu-id="1166e-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="1166e-167">La ejecución de un proyecto piloto le ayuda a afinar el plan de transición y a asegurarse de que está listo para mover todos los equipos de StaffHub de su organización a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="1166e-168">También identifica a los campeones que pueden ayudar a impulsar la adopción en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="1166e-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="1166e-169">Si es una pequeña empresa que no necesita un enfoque por fases, es posible que los pasos de esta sección sean todo lo que necesita para cambiar de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="1166e-170">Identificar equipos piloto</span><span class="sxs-lookup"><span data-stu-id="1166e-170">Identify pilot teams</span></span>

<span data-ttu-id="1166e-171">Póngase en contacto con usted para identificar dos o tres equipos piloto.</span><span class="sxs-lookup"><span data-stu-id="1166e-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="1166e-172">Todos los miembros del equipo deben confirmar el uso de turnos en Teams para administrar su programación y comunicarse y colaborar entre sí.</span><span class="sxs-lookup"><span data-stu-id="1166e-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="1166e-173">Identificar a los expertos en el equipo</span><span class="sxs-lookup"><span data-stu-id="1166e-173">Identify team champions</span></span>

<span data-ttu-id="1166e-174">Identifique a los campeones a través de equipos piloto y inscribalos para ayudar a repartir turnos.</span><span class="sxs-lookup"><span data-stu-id="1166e-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="1166e-175">Los campeones del equipo son apasionados de lo que hacen, compartiendo su propio aprendizaje para ofrecer asistencia y orientación a los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="1166e-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="1166e-176">Los expertos del equipo pueden ser administradores o propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="1166e-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="1166e-177">Los expertos en equipo deben asegurarse de que los miembros del equipo se configuren dedicando tiempo para que todos puedan [obtener clientes](../../get-clients.md)de equipo, iniciar sesión en Teams y consultar sus programaciones en turnos y empezar a conversar entre sí.</span><span class="sxs-lookup"><span data-stu-id="1166e-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="1166e-178">Los usuarios que ya estén familiarizados con StaffHub se activarán y se ejecutarán rápidamente en turnos.</span><span class="sxs-lookup"><span data-stu-id="1166e-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="1166e-179">También puede hacer que desplace la [ayuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener ayuda adicional.</span><span class="sxs-lookup"><span data-stu-id="1166e-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="1166e-180">Mover un equipo de StaffHub (próximamente)</span><span class="sxs-lookup"><span data-stu-id="1166e-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="1166e-181">Siga estos pasos para mover un equipo de StaffHub a la vez.</span><span class="sxs-lookup"><span data-stu-id="1166e-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="1166e-182">Recomendamos este enfoque para los equipos de la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="1166e-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="1166e-183">Más adelante, cuando esté listo para mover todos los equipos de StaffHub de su organización, vea [mover los equipos de staffhub](#move-your-staffhub-teams-coming-soon) para conocer los pasos para mover varios equipos a la vez.</span><span class="sxs-lookup"><span data-stu-id="1166e-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="1166e-184">Ejecute lo siguiente para mover un equipo de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="1166e-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="1166e-185">Este es un ejemplo de la respuesta que obtiene al enviar una solicitud para mover un equipo de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="1166e-186">Para comprobar el estado de una solicitud de movimiento, ejecute lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1166e-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="1166e-187">Este es un ejemplo de la respuesta que obtiene cuando hay un movimiento en curso.</span><span class="sxs-lookup"><span data-stu-id="1166e-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="1166e-188">Realizar la transición de StaffHub a teams</span><span class="sxs-lookup"><span data-stu-id="1166e-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="1166e-189">Aumentar el conocimiento</span><span class="sxs-lookup"><span data-stu-id="1166e-189">Raise awareness</span></span>

<span data-ttu-id="1166e-190">Cuando esté listo para ir más allá de los equipos piloto y mover los equipos de StaffHub de su organización a Teams, es importante comunicar primero el cambio en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="1166e-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="1166e-191">Represente la palabra acerca de los turnos y la transición a Teams para aumentar la conciencia, generar entusiasmo y adopción de unidades.</span><span class="sxs-lookup"><span data-stu-id="1166e-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="1166e-192">Mover los equipos de StaffHub (próximamente)</span><span class="sxs-lookup"><span data-stu-id="1166e-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="1166e-193">Siga estos pasos para mover equipos de StaffHub de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="1166e-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="1166e-194">Puede elegir mover todos los equipos de StaffHub de su organización o mover determinados equipos de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="1166e-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="1166e-195">Si quiere mover los equipos de StaffHub de uno en uno, vea [mover un equipo de staffhub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="1166e-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="1166e-196">Mover todos los equipos de StaffHub (próximamente)</span><span class="sxs-lookup"><span data-stu-id="1166e-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="1166e-197">Ejecute lo siguiente para obtener una lista de todos los equipos de StaffHub de su organización.</span><span class="sxs-lookup"><span data-stu-id="1166e-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="1166e-198">A continuación, ejecute lo siguiente para mover todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="1166e-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="1166e-199">Este es un ejemplo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="1166e-199">Here's an example of the response.</span></span>

<span data-ttu-id="1166e-200">En el caso de cualquier equipo que ya se haya movido a teams o que ya exista en Teams, jobId tendrá el valor "null", ya que no es necesario enviar el trabajo para mover ese equipo.</span><span class="sxs-lookup"><span data-stu-id="1166e-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="1166e-201">Mover equipos de StaffHub específicos (próximamente)</span><span class="sxs-lookup"><span data-stu-id="1166e-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="1166e-202">Ejecute el siguiente procedimiento para obtener una lista de todos los identificadores de equipo de StaffHub en su organización.</span><span class="sxs-lookup"><span data-stu-id="1166e-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="1166e-203">En los resultados devueltos `Get-StaffHubteamsForTenant` por el cmdlet que ejecutó anteriormente, seleccione los identificadores de equipo que desea mover y agréguelos a un archivo de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="1166e-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="1166e-204">Este es un ejemplo de cómo se debe dar formato al archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1166e-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="1166e-205">Identificar</span><span class="sxs-lookup"><span data-stu-id="1166e-205">Id</span></span>  |
|---------|
|<span data-ttu-id="1166e-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="1166e-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="1166e-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="1166e-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="1166e-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="1166e-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="1166e-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="1166e-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="1166e-210">Después de crear el archivo CSV, ejecute lo siguiente para mover los equipos especificados en el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1166e-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="1166e-211">Confirmar que los equipos de StaffHub se han movido a Teams (próximamente)</span><span class="sxs-lookup"><span data-stu-id="1166e-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="1166e-212">Ejecute lo siguiente para obtener una lista de todos los equipos de los turnos de su organización.</span><span class="sxs-lookup"><span data-stu-id="1166e-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="1166e-213">Supervisar el uso de Teams</span><span class="sxs-lookup"><span data-stu-id="1166e-213">Monitor Teams usage</span></span>

<span data-ttu-id="1166e-214">Los informes de uso pueden ayudarlo a comprender mejor los patrones de uso y le proporcionan información sobre cómo priorizar los esfuerzos de aprendizaje y comunicación en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="1166e-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="1166e-215">Como ShiftS es una aplicación en Teams, puede ver el uso mediante informes de Teams.</span><span class="sxs-lookup"><span data-stu-id="1166e-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="1166e-216">Para obtener más información, vea informes [de equipos en el centro de administración de Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) y [informes de actividades de Teams en el centro de administración de Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="1166e-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1166e-217">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1166e-217">Related topics</span></span>
- [<span data-ttu-id="1166e-218">Se retirará Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="1166e-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="1166e-219">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1166e-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="1166e-220">Referencia de PowerShell de StaffHub</span><span class="sxs-lookup"><span data-stu-id="1166e-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
