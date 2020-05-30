---
title: Administrar la aplicación de turnos para su organización
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
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
ms.openlocfilehash: c2ca24f2176547f83efb6bdce591ac71d516dca9
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416890"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="181f9-103">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="181f9-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="181f9-104">A partir del 30 de junio de 2020, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="181f9-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="181f9-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="181f9-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="181f9-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="181f9-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="181f9-107">StaffHub dejará de funcionar para todos los usuarios el 30 de junio de 2020.</span><span class="sxs-lookup"><span data-stu-id="181f9-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="181f9-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="181f9-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="181f9-109">Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="181f9-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="181f9-110">Descripción general de los turnos</span><span class="sxs-lookup"><span data-stu-id="181f9-110">Overview of Shifts</span></span>

<span data-ttu-id="181f9-111">La aplicación turnos en Microsoft Teams mantiene a los trabajadores de los Firstline conectados y sincronizados. En primer lugar, se ha creado un teléfono móvil para una administración y comunicación rápidas y eficaces de los equipos.</span><span class="sxs-lookup"><span data-stu-id="181f9-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="181f9-112">Turnos permite que los trabajadores de los Firstline y sus gerentes usen sus dispositivos móviles para administrar las programaciones y mantenerse en contacto.</span><span class="sxs-lookup"><span data-stu-id="181f9-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="181f9-113">Los administradores crean, actualizan y administran programaciones de turnos para Teams.</span><span class="sxs-lookup"><span data-stu-id="181f9-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="181f9-114">Pueden enviar mensajes a una persona ("hay un derrame en el piso") o todo el equipo ("el GM regional está llegando en 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="181f9-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="181f9-115">También pueden enviar documentos de directivas, boletines de noticias y videos.</span><span class="sxs-lookup"><span data-stu-id="181f9-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="181f9-116">Los empleados ven sus próximos turnos, pueden ver quién más está programado para el día, solicitar intercambiar o ofrecer un turno, y solicitar un tiempo.</span><span class="sxs-lookup"><span data-stu-id="181f9-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="181f9-117">Es importante saber que los turnos actualmente no admiten usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="181f9-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="181f9-118">Esto significa que los invitados de un equipo no se pueden agregar o usar programaciones de turno cuando el acceso de invitados está activado en Teams.</span><span class="sxs-lookup"><span data-stu-id="181f9-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="181f9-119">Disponibilidad de los turnos</span><span class="sxs-lookup"><span data-stu-id="181f9-119">Availability of Shifts</span></span>

<span data-ttu-id="181f9-120">Turnos está disponible en todas las SKU de Enterprise donde está disponible Teams.</span><span class="sxs-lookup"><span data-stu-id="181f9-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="181f9-121">Ubicación de los datos de turnos</span><span class="sxs-lookup"><span data-stu-id="181f9-121">Location of Shifts data</span></span>

<span data-ttu-id="181f9-122">Mayús los datos están almacenados actualmente en Azure en centros de datos en Norteamérica, Europa occidental y Asia Pacífico.</span><span class="sxs-lookup"><span data-stu-id="181f9-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="181f9-123">Para obtener más información sobre dónde se almacenan los datos, vea ¿ [dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="181f9-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="181f9-124">Configurar turnos</span><span class="sxs-lookup"><span data-stu-id="181f9-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="181f9-125">Habilitar o deshabilitar turnos en su organización</span><span class="sxs-lookup"><span data-stu-id="181f9-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="181f9-126">Turnos está habilitado de forma predeterminada para todos los usuarios de los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="181f9-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="181f9-127">Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](../../manage-apps.md) del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="181f9-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="181f9-128">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps** .</span><span class="sxs-lookup"><span data-stu-id="181f9-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="181f9-129">En la lista de aplicaciones, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="181f9-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="181f9-130">Para desactivar los turnos de su organización, busque la aplicación turnos, selecciónela y haga clic en **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="181f9-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="181f9-131">Para activar los turnos de su organización, busque la aplicación turnos, selecciónela y, a continuación, haga clic en **permitir**.</span><span class="sxs-lookup"><span data-stu-id="181f9-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="181f9-132">Habilitar o deshabilitar turnos para usuarios específicos de su organización</span><span class="sxs-lookup"><span data-stu-id="181f9-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="181f9-133">Para permitir o bloquear a determinados usuarios de su organización el uso de turnos, asegúrese de que la opción turnos está activada para su organización en la página [Administrar aplicaciones](../../manage-apps.md) y, después, cree una directiva de permisos de aplicaciones personalizada y asígnela a esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="181f9-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="181f9-134">Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="181f9-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="181f9-135">Use la Directiva de configuración de la aplicación de FirstlineWorker para anclar turnos a teams</span><span class="sxs-lookup"><span data-stu-id="181f9-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="181f9-136">Las directivas de configuración de la aplicación le permiten personalizar Teams para resaltar las aplicaciones más importantes para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="181f9-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="181f9-137">Las aplicaciones establecidas en una directiva se anclan a la barra de la aplicación, que se &mdash; encuentra en el costado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams &mdash; donde los usuarios puedan acceder a ellas de forma rápida y fácil.</span><span class="sxs-lookup"><span data-stu-id="181f9-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="181f9-138">Teams incluye una directiva de configuración de aplicaciones de FirstlineWorker integrada que puede asignar a los trabajadores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="181f9-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="181f9-139">De forma predeterminada, la Directiva incluye las aplicaciones actividad, turnos, chat y llamadas.</span><span class="sxs-lookup"><span data-stu-id="181f9-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="181f9-140">Para ver la Directiva de FirstlineWorker, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de configuración de la aplicación de **aplicación de Teams**  >  **App setup policies**.</span><span class="sxs-lookup"><span data-stu-id="181f9-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="181f9-141">![Captura de pantalla de la Directiva de configuración de la aplicación de FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la Directiva de configuración de la aplicación de FirstlineWorker en el centro de administración de Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="181f9-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-users"></a><span data-ttu-id="181f9-142">Asignar la Directiva FirstlineWorker a los usuarios</span><span class="sxs-lookup"><span data-stu-id="181f9-142">Assign the FirstlineWorker policy to users</span></span>

<span data-ttu-id="181f9-143">Para asignar la Directiva de configuración de la aplicación de FirstlineWorker a un usuario:</span><span class="sxs-lookup"><span data-stu-id="181f9-143">To assign the FirstlineWorker app setup policy to one user:</span></span>

1. <span data-ttu-id="181f9-144">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="181f9-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="181f9-145">Para seleccionar el usuario, haga clic a la izquierda del nombre de usuario y, después, en **Editar configuración**.</span><span class="sxs-lookup"><span data-stu-id="181f9-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="181f9-146">En **Directiva de configuración**de la aplicación, seleccione **FirstlineWorker**y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="181f9-146">Under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>

<span data-ttu-id="181f9-147">Para asignar una directiva a varios usuarios a la vez:</span><span class="sxs-lookup"><span data-stu-id="181f9-147">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="181f9-148">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Usuarios**, después, busque los usuarios o filtre la vista para mostrar los usuarios que desee.</span><span class="sxs-lookup"><span data-stu-id="181f9-148">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="181f9-149">En la columna **&#x2713;** (marca de verificación), seleccione los usuarios.</span><span class="sxs-lookup"><span data-stu-id="181f9-149">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="181f9-150">Para seleccionar todos los usuarios, haga clic en &#x2713; (marca de verificación) situado en la parte superior de la tabla.</span><span class="sxs-lookup"><span data-stu-id="181f9-150">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="181f9-151">Haga clic en **Editar configuración**, en **Directiva de configuración**de la aplicación, seleccione **FirstlineWorker**y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="181f9-151">Click **Edit settings**, under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>  

<span data-ttu-id="181f9-152">También puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="181f9-152">Or, you can also do the following:</span></span>

1. <span data-ttu-id="181f9-153">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de configuración de las **aplicaciones de Teams**  >  **Setup policies**.</span><span class="sxs-lookup"><span data-stu-id="181f9-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="181f9-154">Seleccione la Directiva FirstlineWorker haciendo clic a la izquierda del nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="181f9-154">Select the FirstlineWorker policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="181f9-155">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="181f9-155">Select **Manage users**.</span></span>
4. <span data-ttu-id="181f9-156">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="181f9-156">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="181f9-157">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="181f9-157">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="181f9-158">Cuando termine de agregar usuarios, seleccione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="181f9-158">After you finish adding users, select **Apply**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="181f9-159">Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los miembros del usuario de un grupo</span><span class="sxs-lookup"><span data-stu-id="181f9-159">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="181f9-160">Puede asignar la Directiva de configuración de la aplicación de FirstlineWorker a los miembros de usuario de un grupo, como un grupo de seguridad, conectándose al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="181f9-160">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="181f9-161">Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="181f9-161">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="181f9-162">En este ejemplo, asignamos la Directiva de configuración de la aplicación FirstlineWorker a todos los miembros del usuario del grupo de equipo de Contoso los Firstline.</span><span class="sxs-lookup"><span data-stu-id="181f9-162">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="181f9-163">Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="181f9-163">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="181f9-164">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="181f9-164">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="181f9-165">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="181f9-165">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="181f9-166">Asigne la Directiva de configuración de la aplicación de FirstlineWorker a todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="181f9-166">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="181f9-167">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="181f9-167">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="181f9-168">Buscar eventos de turnos en el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="181f9-168">Search the audit log for Shifts events</span></span>

<span data-ttu-id="181f9-169">**(en la versión preliminar)**</span><span class="sxs-lookup"><span data-stu-id="181f9-169">**(in preview)**</span></span>

<span data-ttu-id="181f9-170">Puede buscar en el registro de auditoría para ver la actividad de los turnos en su organización.</span><span class="sxs-lookup"><span data-stu-id="181f9-170">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="181f9-171">Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de [las actividades de turnos](../../audit-log-events.md#shifts-in-teams-activities) registradas en el registro de auditoría, consulte [buscar eventos en el registro de auditoría de los equipos](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="181f9-171">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="181f9-172">Antes de poder buscar en el registro de auditoría, primero debe activar la auditoría en el [centro de cumplimiento de & de seguridad](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="181f9-172">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="181f9-173">Para obtener más información, vea [activar o desactivar la búsqueda de registros de auditoría](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="181f9-173">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="181f9-174">Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que activó la auditoría.</span><span class="sxs-lookup"><span data-stu-id="181f9-174">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="181f9-175">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="181f9-175">Related topics</span></span>

- [<span data-ttu-id="181f9-176">Desplaza la ayuda para los trabajadores de los Firstline</span><span class="sxs-lookup"><span data-stu-id="181f9-176">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="181f9-177">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="181f9-177">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
