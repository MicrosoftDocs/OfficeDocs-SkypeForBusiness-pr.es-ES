---
title: Administrar la aplicación de turnos para su organización
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar y administrar la aplicación de turnos en Teams para trabajadores de los Firstline de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ecc64c105bb9171942dfac912ccea4f2fa1442aa
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938359"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="b673a-103">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b673a-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b673a-104">A partir del 30 de junio de 2020, se ha retirado a Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b673a-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="b673a-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b673a-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b673a-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="b673a-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b673a-107">StaffHub ha dejado de funcionar para todos los usuarios el 30 de junio de 2020.</span><span class="sxs-lookup"><span data-stu-id="b673a-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="b673a-108">Cualquier persona que intente abrir StaffHub verá un mensaje que le indica que debe descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="b673a-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="b673a-109">Para obtener más información, vea se ha [retirado Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="b673a-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="b673a-110">Descripción general de los turnos</span><span class="sxs-lookup"><span data-stu-id="b673a-110">Overview of Shifts</span></span>

<span data-ttu-id="b673a-111">La aplicación turnos en Microsoft Teams mantiene a los trabajadores de los Firstline conectados y sincronizados. En primer lugar, se ha creado un teléfono móvil para una administración y comunicación rápidas y eficaces de los equipos.</span><span class="sxs-lookup"><span data-stu-id="b673a-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="b673a-112">Turnos permite que los trabajadores de los Firstline y sus gerentes usen sus dispositivos móviles para administrar las programaciones y mantenerse en contacto.</span><span class="sxs-lookup"><span data-stu-id="b673a-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="b673a-113">Los administradores crean, actualizan y administran programaciones de turnos para Teams.</span><span class="sxs-lookup"><span data-stu-id="b673a-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="b673a-114">Pueden enviar mensajes a una persona ("hay un derrame en el piso") o todo el equipo ("el GM regional está llegando en 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="b673a-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="b673a-115">También pueden enviar documentos de directivas, boletines de noticias y videos.</span><span class="sxs-lookup"><span data-stu-id="b673a-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="b673a-116">Los empleados ven sus próximos turnos, pueden ver quién más está programado para el día, solicitar intercambiar o ofrecer un turno, y solicitar un tiempo.</span><span class="sxs-lookup"><span data-stu-id="b673a-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="b673a-117">Es importante saber que los turnos actualmente no admiten usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="b673a-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="b673a-118">Esto significa que los invitados de un equipo no se pueden agregar o usar programaciones de turno cuando el acceso de invitados está activado en Teams.</span><span class="sxs-lookup"><span data-stu-id="b673a-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="b673a-119">Disponibilidad de los turnos</span><span class="sxs-lookup"><span data-stu-id="b673a-119">Availability of Shifts</span></span>

<span data-ttu-id="b673a-120">Turnos está disponible en todas las SKU de Enterprise donde está disponible Teams.</span><span class="sxs-lookup"><span data-stu-id="b673a-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="b673a-121">Ubicación de los datos de turnos</span><span class="sxs-lookup"><span data-stu-id="b673a-121">Location of Shifts data</span></span>

<span data-ttu-id="b673a-122">Mayús los datos están almacenados actualmente en Azure en centros de datos en Norteamérica, Europa occidental y Asia Pacífico.</span><span class="sxs-lookup"><span data-stu-id="b673a-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="b673a-123">Para obtener más información sobre dónde se almacenan los datos, vea ¿ [dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="b673a-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="b673a-124">Configurar turnos</span><span class="sxs-lookup"><span data-stu-id="b673a-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="b673a-125">Habilitar o deshabilitar turnos en su organización</span><span class="sxs-lookup"><span data-stu-id="b673a-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="b673a-126">Turnos está habilitado de forma predeterminada para todos los usuarios de los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="b673a-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="b673a-127">Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](../../manage-apps.md) del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b673a-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b673a-128">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps** .</span><span class="sxs-lookup"><span data-stu-id="b673a-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="b673a-129">En la lista de aplicaciones, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b673a-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="b673a-130">Para desactivar los turnos de su organización, busque la aplicación turnos, selecciónela y haga clic en **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="b673a-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="b673a-131">Para activar los turnos de su organización, busque la aplicación turnos, selecciónela y, a continuación, haga clic en **permitir**.</span><span class="sxs-lookup"><span data-stu-id="b673a-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="b673a-132">Habilitar o deshabilitar turnos para usuarios específicos de su organización</span><span class="sxs-lookup"><span data-stu-id="b673a-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="b673a-133">Para permitir o bloquear a determinados usuarios de su organización el uso de turnos, asegúrese de que la opción turnos está activada para su organización en la página [Administrar aplicaciones](../../manage-apps.md) y, después, cree una directiva de permisos de aplicaciones personalizada y asígnela a esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="b673a-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="b673a-134">Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b673a-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="b673a-135">Use la Directiva de configuración de la aplicación de FirstlineWorker para anclar turnos a teams</span><span class="sxs-lookup"><span data-stu-id="b673a-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="b673a-136">Las directivas de configuración de la aplicación le permiten personalizar Teams para resaltar las aplicaciones más importantes para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="b673a-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="b673a-137">Las aplicaciones establecidas en una directiva se anclan a la barra de la aplicación, que se &mdash; encuentra en el costado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams &mdash; donde los usuarios puedan acceder a ellas de forma rápida y fácil.</span><span class="sxs-lookup"><span data-stu-id="b673a-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="b673a-138">Teams incluye una directiva de configuración de aplicaciones de FirstlineWorker integrada que puede asignar a los trabajadores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="b673a-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="b673a-139">De forma predeterminada, la Directiva incluye las aplicaciones actividad, turnos, chat y llamadas.</span><span class="sxs-lookup"><span data-stu-id="b673a-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="b673a-140">Para ver la Directiva de FirstlineWorker, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de configuración de la aplicación de **aplicación de Teams**  >  **App setup policies**.</span><span class="sxs-lookup"><span data-stu-id="b673a-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="b673a-141">![Captura de pantalla de la Directiva de configuración de la aplicación de FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la Directiva de configuración de la aplicación de FirstlineWorker en el centro de administración de Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="b673a-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="b673a-142">Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los usuarios</span><span class="sxs-lookup"><span data-stu-id="b673a-142">Assign the FirstlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="b673a-143">Buscar eventos de turnos en el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="b673a-143">Search the audit log for Shifts events</span></span>

<span data-ttu-id="b673a-144">**(en la versión preliminar)**</span><span class="sxs-lookup"><span data-stu-id="b673a-144">**(in preview)**</span></span>

<span data-ttu-id="b673a-145">Puede buscar en el registro de auditoría para ver la actividad de los turnos en su organización.</span><span class="sxs-lookup"><span data-stu-id="b673a-145">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="b673a-146">Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de [las actividades de turnos](../../audit-log-events.md#shifts-in-teams-activities) registradas en el registro de auditoría, consulte [buscar eventos en el registro de auditoría de los equipos](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="b673a-146">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="b673a-147">Antes de poder buscar en el registro de auditoría, primero debe activar la auditoría en el [centro de cumplimiento de & de seguridad](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="b673a-147">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="b673a-148">Para obtener más información, vea [activar o desactivar la búsqueda de registros de auditoría](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="b673a-148">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="b673a-149">Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que activó la auditoría.</span><span class="sxs-lookup"><span data-stu-id="b673a-149">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b673a-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b673a-150">Related topics</span></span>

- [<span data-ttu-id="b673a-151">Desplaza la ayuda para los trabajadores de los Firstline</span><span class="sxs-lookup"><span data-stu-id="b673a-151">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="b673a-152">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="b673a-152">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
