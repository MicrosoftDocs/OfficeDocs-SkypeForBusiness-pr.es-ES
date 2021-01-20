---
title: Administrar la aplicación Turnos para su organización
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenga información sobre cómo configurar y administrar la aplicación Turnos en Teams para trabajadores de primera línea de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909094"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="e4db3-103">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4db3-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4db3-104">A partir del 30 de junio de 2020, Se ha retirado Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="e4db3-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="e4db3-105">Estamos creando funciones de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4db3-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="e4db3-106">Hoy en día, Teams incluye la aplicación Turnos para la administración de programación y otras funcionalidades se irán lanzando a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="e4db3-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="e4db3-107">StaffHub dejó de funcionar para todos los usuarios el 30 de junio de 2020.</span><span class="sxs-lookup"><span data-stu-id="e4db3-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="e4db3-108">Cualquier persona que intente abrir StaffHub se mostrará un mensaje que le dirigirá a descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="e4db3-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="e4db3-109">Para obtener más información, [vea Microsoft StaffHub se ha retirado.](microsoft-staffhub-to-be-retired.md)</span><span class="sxs-lookup"><span data-stu-id="e4db3-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="e4db3-110">Información general sobre turnos</span><span class="sxs-lookup"><span data-stu-id="e4db3-110">Overview of Shifts</span></span>

<span data-ttu-id="e4db3-111">La aplicación Turnos de Microsoft Teams mantiene a los Trabajadores de Frontline Workers conectados y sincronizados. Se ha creado para dispositivos móviles, lo que ofrece una administración del tiempo y una comunicación rápida y eficaz para los equipos.</span><span class="sxs-lookup"><span data-stu-id="e4db3-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="e4db3-112">Turnos permite a los trabajadores de frontline workers y sus administradores usar sus dispositivos móviles para administrar programaciones y mantenerse en contacto.</span><span class="sxs-lookup"><span data-stu-id="e4db3-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="e4db3-113">Los administradores crean, actualizan y administran las programaciones de turnos de los equipos.</span><span class="sxs-lookup"><span data-stu-id="e4db3-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="e4db3-114">Pueden enviar mensajes a una persona ("se ha desbordado algo al suelo") o a todo el equipo ("el director general regional llegará en 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="e4db3-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="e4db3-115">También pueden enviar documentos de directiva, boletines de noticias y vídeos.</span><span class="sxs-lookup"><span data-stu-id="e4db3-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="e4db3-116">Los empleados ven sus próximos turnos, ven quién más está programado para el día, solicitan permutar u ofrecer un turno y solicitan un permiso.</span><span class="sxs-lookup"><span data-stu-id="e4db3-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="e4db3-117">Es importante saber que Turnos no admite actualmente usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="e4db3-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="e4db3-118">Esto significa que no se pueden agregar invitados en un equipo ni usar las programaciones de turnos cuando se ha activado el acceso de invitado en Teams.</span><span class="sxs-lookup"><span data-stu-id="e4db3-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="e4db3-119">Para obtener más información sobre las capacidades de Turnos en distintas plataformas, consulte [Características de Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="e4db3-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="e4db3-120">Disponibilidad de los turnos</span><span class="sxs-lookup"><span data-stu-id="e4db3-120">Availability of Shifts</span></span>

<span data-ttu-id="e4db3-121">Turnos está disponible en todas las SKU empresariales donde Teams está disponible.</span><span class="sxs-lookup"><span data-stu-id="e4db3-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="e4db3-122">Ubicación de los datos de Turnos</span><span class="sxs-lookup"><span data-stu-id="e4db3-122">Location of Shifts data</span></span>

<span data-ttu-id="e4db3-123">Los datos de Turnos se almacenan actualmente en Azure en los centros de datos de Norteamérica, Europa occidental y Asia Pacífico.</span><span class="sxs-lookup"><span data-stu-id="e4db3-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="e4db3-124">Para obtener más información sobre dónde se almacenan los datos, vea [¿Dónde están mis datos?](http://o365datacentermap.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="e4db3-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="e4db3-125">Configurar turnos</span><span class="sxs-lookup"><span data-stu-id="e4db3-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="e4db3-126">Habilitar o deshabilitar Turnos en su organización</span><span class="sxs-lookup"><span data-stu-id="e4db3-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="e4db3-127">Turnos está habilitado de forma predeterminada para todos los usuarios de Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="e4db3-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="e4db3-128">Puede desactivar o activar la aplicación en el [](../../manage-apps.md) nivel de la organización en la página Administrar aplicaciones del Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4db3-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="e4db3-129">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones de Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="e4db3-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="e4db3-130">En la lista de aplicaciones, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e4db3-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="e4db3-131">Para desactivar Turnos para su organización, busque la aplicación Turnos, selecciónelo y, a continuación, **seleccione Bloquear.**</span><span class="sxs-lookup"><span data-stu-id="e4db3-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="e4db3-132">Para activar Turnos para su organización, busque la aplicación Turnos, selecciónelo y, a continuación, **seleccione Permitir.**</span><span class="sxs-lookup"><span data-stu-id="e4db3-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="e4db3-133">Habilitar o deshabilitar Turnos para usuarios específicos de su organización</span><span class="sxs-lookup"><span data-stu-id="e4db3-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="e4db3-134">Para permitir o impedir que determinados usuarios de su organización utilicen Turnos, asegúrese de que Turnos está activado para su organización en la página Administrar aplicaciones y, a continuación, cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. [](../../manage-apps.md)</span><span class="sxs-lookup"><span data-stu-id="e4db3-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="e4db3-135">Para obtener más información, consulte [Administrar directivas de permisos de aplicaciones en Teams.](../../teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e4db3-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="e4db3-136">Usar la directiva de configuración de la aplicación FrontlineWorker para anclar Turnos a Teams</span><span class="sxs-lookup"><span data-stu-id="e4db3-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="e4db3-137">Las directivas de configuración de aplicaciones le permiten personalizar Teams para resaltar las aplicaciones más importantes para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="e4db3-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="e4db3-138">Las aplicaciones establecidas en una directiva se anclan en la barra de aplicaciones situada en el lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams, donde los usuarios pueden acceder a ellos de forma rápida y &mdash; &mdash; sencilla.</span><span class="sxs-lookup"><span data-stu-id="e4db3-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="e4db3-139">Teams incluye una directiva de configuración de la aplicación FrontlineWorker integrada que puede asignar a los trabajadores de frontline workers de su organización.</span><span class="sxs-lookup"><span data-stu-id="e4db3-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="e4db3-140">De forma predeterminada, la directiva incluye las aplicaciones Actividad, Turnos, Chat y Llamadas.</span><span class="sxs-lookup"><span data-stu-id="e4db3-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="e4db3-141">Para ver la directiva de FrontlineWorker, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las directivas de configuración de la  >  **aplicación Teams.**</span><span class="sxs-lookup"><span data-stu-id="e4db3-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="e4db3-142">![Captura de pantalla de la directiva de configuración de la aplicación FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la directiva de configuración de la aplicación FrontlineWorker en el Centro de administración de Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="e4db3-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="e4db3-143">Asignar la directiva de configuración de la aplicación FrontlineWorker a los usuarios</span><span class="sxs-lookup"><span data-stu-id="e4db3-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="e4db3-144">Buscar eventos de Turnos en el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="e4db3-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="e4db3-145">**(en la versión preliminar)**</span><span class="sxs-lookup"><span data-stu-id="e4db3-145">**(in preview)**</span></span>

<span data-ttu-id="e4db3-146">Puede buscar en el registro de auditoría para ver la actividad de Turnos en su organización.</span><span class="sxs-lookup"><span data-stu-id="e4db3-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="e4db3-147">Para obtener más información sobre cómo buscar en el registro de auditoría y para ver una lista de las actividades de [Turnos](../../audit-log-events.md#shifts-in-teams-activities) que se registran en el registro de auditoría, consulte Buscar eventos en el registro de auditoría [en Teams.](../../audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="e4db3-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="e4db3-148">Antes de poder buscar en el registro de auditoría, primero tiene que activar la auditoría en el Centro de seguridad y [& cumplimiento.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="e4db3-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="e4db3-149">Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)</span><span class="sxs-lookup"><span data-stu-id="e4db3-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="e4db3-150">Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que ha activado la auditoría.</span><span class="sxs-lookup"><span data-stu-id="e4db3-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4db3-151">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e4db3-151">Related topics</span></span>

- [<span data-ttu-id="e4db3-152">Ayuda de turnos para los trabajadores de primera línea</span><span class="sxs-lookup"><span data-stu-id="e4db3-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="e4db3-153">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="e4db3-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
