---
title: Administrar la aplicación Turnos para su organización en Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar y administrar la aplicación de turnos en Teams para trabajadores de los Firstline de su organización.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f773cc2ee3aa8a1e98d139f55067c9205355611
ms.sourcegitcommit: c6ecea3205d509609a655db2348c04f655319df8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171644"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="aaf51-103">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aaf51-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aaf51-104">A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="aaf51-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="aaf51-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aaf51-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="aaf51-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="aaf51-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="aaf51-107">StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="aaf51-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="aaf51-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="aaf51-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="aaf51-109">Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.</span><span class="sxs-lookup"><span data-stu-id="aaf51-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="aaf51-110">Descripción general de los turnos</span><span class="sxs-lookup"><span data-stu-id="aaf51-110">Overview of Shifts</span></span>
<span data-ttu-id="aaf51-111">La aplicación turnos en Microsoft Teams mantiene a los trabajadores de los Firstline conectados y sincronizados. En primer lugar, se ha creado un teléfono móvil para una administración y comunicación rápidas y eficaces de los equipos.</span><span class="sxs-lookup"><span data-stu-id="aaf51-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="aaf51-112">Turnos permite que los trabajadores de los Firstline y sus gerentes usen sus dispositivos móviles para administrar las programaciones y mantenerse en contacto.</span><span class="sxs-lookup"><span data-stu-id="aaf51-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="aaf51-113">Los administradores crean, actualizan y administran programaciones de turnos para Teams.</span><span class="sxs-lookup"><span data-stu-id="aaf51-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="aaf51-114">Pueden enviar mensajes a una persona ("hay un derrame en el piso") o todo el equipo ("el GM regional está llegando en 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="aaf51-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="aaf51-115">También pueden enviar documentos de directivas, boletines de noticias y videos.</span><span class="sxs-lookup"><span data-stu-id="aaf51-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="aaf51-116">Los empleados ven sus próximos turnos, pueden ver quién más está programado para el día, solicitar intercambiar o ofrecer un turno, y solicitar un tiempo.</span><span class="sxs-lookup"><span data-stu-id="aaf51-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="aaf51-117">Es importante saber que los turnos actualmente no admiten usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="aaf51-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="aaf51-118">Esto significa que los invitados de un equipo no se pueden agregar o usar programaciones de turno cuando el acceso de invitados está activado en Teams.</span><span class="sxs-lookup"><span data-stu-id="aaf51-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="aaf51-119">Disponibilidad de los turnos</span><span class="sxs-lookup"><span data-stu-id="aaf51-119">Availability of Shifts</span></span>

<span data-ttu-id="aaf51-120">Turnos está disponible en todas las suscripciones de Office 365 que incluyen equipos, con un par de excepciones.</span><span class="sxs-lookup"><span data-stu-id="aaf51-120">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="aaf51-121">Las excepciones son la comunidad de la nube de Estados Unidos (GCC) y Teams gratis.</span><span class="sxs-lookup"><span data-stu-id="aaf51-121">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="aaf51-122">Los turnos no están disponibles en las ofertas gratuitas de Office 365 Estados Unidos o los equipos.</span><span class="sxs-lookup"><span data-stu-id="aaf51-122">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="aaf51-123">Para obtener más información sobre las licencias de Teams, incluida una lista de suscripciones de Office 365 que incluye equipos, consulte [Office 365 Licensing for Teams](../../Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="aaf51-123">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](../../Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="aaf51-124">Ubicación de los datos de turnos</span><span class="sxs-lookup"><span data-stu-id="aaf51-124">Location of Shifts data</span></span>

<span data-ttu-id="aaf51-125">Mayús los datos están almacenados actualmente en Azure en centros de datos en Norteamérica, Europa occidental y Asia Pacífico.</span><span class="sxs-lookup"><span data-stu-id="aaf51-125">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="aaf51-126">Para obtener más información sobre dónde se almacenan los datos, vea ¿ [dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="aaf51-126">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="aaf51-127">Configurar turnos</span><span class="sxs-lookup"><span data-stu-id="aaf51-127">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="aaf51-128">Habilitar o deshabilitar turnos en su organización</span><span class="sxs-lookup"><span data-stu-id="aaf51-128">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="aaf51-129">Turnos está habilitado de forma predeterminada para todos los usuarios de los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="aaf51-129">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="aaf51-130">Puede desactivar o activar la organización de toda la organización mediante la configuración de toda la organización en directivas de permisos de aplicaciones en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aaf51-130">You can turn off or turn on the app org-wide by using org-wide settings in app permission policies in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="aaf51-131">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de permisos** de las **aplicaciones** > de Teams.</span><span class="sxs-lookup"><span data-stu-id="aaf51-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies** .</span></span>
2. <span data-ttu-id="aaf51-132">Haga clic en **configuración de toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="aaf51-132">Click **Org-wide settings**.</span></span>
3. <span data-ttu-id="aaf51-133">En el panel **configuración de toda la organización** , en **aplicaciones bloqueadas**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="aaf51-133">In the **Org-wide settings** panel, under **Blocked apps**, do one of the following:</span></span>

    - <span data-ttu-id="aaf51-134">Para desactivar los turnos de su organización, busque la aplicación turnos y haga clic en **Agregar** para agregarla a la lista de aplicaciones bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="aaf51-134">To turn off Shifts for your organization, search for the Shifts app, and click **Add** to add it to the blocked apps list.</span></span>
    - <span data-ttu-id="aaf51-135">Para activar los turnos de su organización, quite la aplicación turnos de la lista de aplicaciones bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="aaf51-135">To turn on Shifts for your organization, remove the Shifts app from the blocked apps list.</span></span>
4. <span data-ttu-id="aaf51-136">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="aaf51-136">Click **Save**.</span></span> 

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="aaf51-137">Habilitar o deshabilitar turnos para usuarios específicos de su organización</span><span class="sxs-lookup"><span data-stu-id="aaf51-137">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="aaf51-138">Para permitir o bloquear a determinados usuarios de su organización el uso de turnos, asegúrese de que la opción turnos está activada para su organización en la configuración de toda la organización y, a continuación, cree una directiva de permisos de aplicaciones personalizada y asígnela a esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="aaf51-138">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization in org-wide settings, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="aaf51-139">Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aaf51-139">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="aaf51-140">Use la Directiva de configuración de la aplicación de FirstlineWorker para anclar turnos a teams</span><span class="sxs-lookup"><span data-stu-id="aaf51-140">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="aaf51-141">Las directivas de configuración de la aplicación le permiten personalizar Teams para resaltar las aplicaciones más importantes para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="aaf51-141">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="aaf51-142">Las aplicaciones establecidas en una directiva se anclan a la barra&mdash;de la aplicación, que se encuentra en el costado del cliente de escritorio de Teams y en&mdash;la parte inferior de los clientes móviles de Teams donde los usuarios puedan acceder a ellas de forma rápida y fácil.</span><span class="sxs-lookup"><span data-stu-id="aaf51-142">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="aaf51-143">Teams incluye una directiva de configuración de aplicaciones de FirstlineWorker integrada que puede asignar a los trabajadores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="aaf51-143">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="aaf51-144">De forma predeterminada, la Directiva incluye las aplicaciones actividad, turnos, chat y llamadas.</span><span class="sxs-lookup"><span data-stu-id="aaf51-144">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="aaf51-145">Para ver la Directiva de FirstlineWorker, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de configuración**de la aplicación de **aplicación** > de Teams.</span><span class="sxs-lookup"><span data-stu-id="aaf51-145">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="aaf51-146">![Captura de pantalla de la Directiva de configuración de la aplicación FirstlineWorker] (../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la Directiva de configuración de la aplicación FirstlineWorker en el centro de administración de Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="aaf51-146">![Screen shot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screen shot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="aaf51-147">Asignar la Directiva FirstlineWorker a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="aaf51-147">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="aaf51-148">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="aaf51-148">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="aaf51-149">Junto a **directivas asignadas**, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aaf51-149">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="aaf51-150">En **Directiva de configuración**de la aplicación de Teams, seleccione **FirstlineWorker**y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aaf51-150">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="aaf51-151">Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="aaf51-151">Assign the FirstlineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="aaf51-152">Puede asignar la Directiva de configuración de la aplicación de FirstlineWorker a los usuarios de un grupo, como un grupo de seguridad, conectándose al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="aaf51-152">You can assign the FirstlineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="aaf51-153">Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aaf51-153">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="aaf51-154">En este ejemplo, asignamos la Directiva de configuración de la aplicación FirstlineWorker a todos los usuarios del grupo de equipo de Contoso los Firstline.</span><span class="sxs-lookup"><span data-stu-id="aaf51-154">In this example, we assign the FirstlineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="aaf51-155">Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="aaf51-155">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="aaf51-156">Obtén la GroupObjectId del grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="aaf51-156">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="aaf51-157">Obtener los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="aaf51-157">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="aaf51-158">Asigne todos los usuarios del grupo a la Directiva de configuración de la aplicación de FirstlineWorker.</span><span class="sxs-lookup"><span data-stu-id="aaf51-158">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="aaf51-159">Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="aaf51-159">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aaf51-160">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aaf51-160">Related topics</span></span>
- [<span data-ttu-id="aaf51-161">Desplaza la ayuda para los trabajadores de los Firstline</span><span class="sxs-lookup"><span data-stu-id="aaf51-161">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
