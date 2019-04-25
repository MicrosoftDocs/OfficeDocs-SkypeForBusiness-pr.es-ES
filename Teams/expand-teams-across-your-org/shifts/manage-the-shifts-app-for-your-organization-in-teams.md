---
title: Administrar la aplicación Turnos para su organización en Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo configurar y administrar la aplicación de turnos en los equipos Firstline a los trabajadores de la organización.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9927da9aea89eeb4d5b1b71eac2818c5deb52925
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245943"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="0ca82-103">Administrar la aplicación Turnos para su organización en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ca82-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ca82-104">Eficaces se deben retirarse el 1 de octubre de 2019, Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="0ca82-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="0ca82-105">Capacidades de StaffHub que estamos creando en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ca82-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="0ca82-106">En la actualidad, los equipos incluye la aplicación de turnos para la administración de programación y funciones adicionales se lleve a cabo a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="0ca82-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="0ca82-107">StaffHub dejará de funcionar para todos los usuarios en el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="0ca82-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="0ca82-108">Cualquier persona que intenta abrir StaffHub se mostrará un mensaje que les dirige a descargar los equipos.</span><span class="sxs-lookup"><span data-stu-id="0ca82-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="0ca82-109">Para obtener más información, vea [Microsoft StaffHub retirarse](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="0ca82-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="0ca82-110">Información general de turnos</span><span class="sxs-lookup"><span data-stu-id="0ca82-110">Overview of Shifts</span></span>
<span data-ttu-id="0ca82-111">La aplicación de turnos en Microsoft Teams mantiene los trabajadores Firstline conectados y sincronizados. Se basa móvil en primer lugar para la administración de tiempo rápida y eficaz y comunicación para los equipos.</span><span class="sxs-lookup"><span data-stu-id="0ca82-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="0ca82-112">Turnos permite a los trabajadores de la Firstline y sus directores utilizar sus dispositivos móviles para administrar las programaciones y mantenerse en contacto.</span><span class="sxs-lookup"><span data-stu-id="0ca82-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="0ca82-113">Los administradores creación, actualización y administración programaciones MAYÚS para los equipos.</span><span class="sxs-lookup"><span data-stu-id="0ca82-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="0ca82-114">Pueden enviar mensajes a una persona ("hay un desbordamiento en el plano inferior") o todo el equipo ("el GM regional llega en 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="0ca82-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="0ca82-115">También pueden enviar documentos de directivas, boletines de noticias y vídeos.</span><span class="sxs-lookup"><span data-stu-id="0ca82-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="0ca82-116">Los empleados ver sus próximas turnos, pueden ver quién más está programado para el día, solicitar a intercambiar u ofrecen un turno y tiempo de la solicitud desactivado.</span><span class="sxs-lookup"><span data-stu-id="0ca82-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="0ca82-117">Es importante saber que turnos actualmente no es compatible con los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="0ca82-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="0ca82-118">Esto significa que los invitados en un equipo no puede agregarse a o usar programaciones MAYÚS cuando está activado el acceso como invitado en los equipos.</span><span class="sxs-lookup"><span data-stu-id="0ca82-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="0ca82-119">Disponibilidad de turnos</span><span class="sxs-lookup"><span data-stu-id="0ca82-119">Availability of Shifts</span></span>

<span data-ttu-id="0ca82-120">Turnos está disponible en todas las suscripciones a Office 365 que incluyen equipos con un par de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0ca82-120">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="0ca82-121">Las excepciones son equipos gratuitos y nos gubernamentales en la nube Comunidad (GCC).</span><span class="sxs-lookup"><span data-stu-id="0ca82-121">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="0ca82-122">Turnos no está disponible en Office 365 gobierno de Estados Unidos o las ofertas de libre de los equipos.</span><span class="sxs-lookup"><span data-stu-id="0ca82-122">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="0ca82-123">Para obtener más información acerca de las licencias para los equipos, incluida una lista de suscripciones a Office 365 que incluye los equipos, vea [licencias de Office 365 para los equipos](../../Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0ca82-123">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](../../Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="0ca82-124">Ubicación de los datos de turnos</span><span class="sxs-lookup"><span data-stu-id="0ca82-124">Location of Shifts data</span></span>

<span data-ttu-id="0ca82-125">Datos de turnos actualmente se almacenan en Azure en centros de datos en Norteamérica, Europa occidental y Asia Pacífico.</span><span class="sxs-lookup"><span data-stu-id="0ca82-125">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="0ca82-126">Para obtener más información acerca de dónde se almacenan los datos, vea [¿dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="0ca82-126">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="0ca82-127">Configurar los turnos</span><span class="sxs-lookup"><span data-stu-id="0ca82-127">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="0ca82-128">Habilitar o deshabilitar turnos de su organización</span><span class="sxs-lookup"><span data-stu-id="0ca82-128">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="0ca82-129">Turnos está habilitado de forma predeterminada para todos los usuarios de los equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="0ca82-129">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="0ca82-130">Puede activar o desactivar en la aplicación para su organización en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ca82-130">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="0ca82-131">Inicie sesión en el centro de administración de Microsoft 365 con su cuenta de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ca82-131">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="0ca82-132">Vaya a **configuración** > **complementos & de servicios** > **Equipos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0ca82-132">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="0ca82-133">En **configuración de todo el inquilino**, seleccione **aplicaciones**y, a continuación, en **Aplicaciones de valor predeterminado**, desactive o Active la casilla de verificación **turnos** para activar o desactivar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0ca82-133">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="0ca82-134">![Captura de pantalla de la sección de aplicaciones predeterminado] (../../media/firstline-worker-enable-disable-shifts.png "Captura de pantalla de la sección de aplicaciones predeterminado en el centro de administración de Microsoft 365, que muestra la lista de aplicaciones, como las aplicaciones de turnos")</span><span class="sxs-lookup"><span data-stu-id="0ca82-134">![Screen shot of the Default Apps section](../../media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstline-worker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="0ca82-135">Usan la directiva del programa de instalación de aplicación Firstline trabajo a turnos de pin a los equipos</span><span class="sxs-lookup"><span data-stu-id="0ca82-135">Use the Firstline Worker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="0ca82-136">Las directivas de aplicación del programa de instalación le permiten personalizar equipos para resaltar las aplicaciones que son más importantes para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="0ca82-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="0ca82-137">Las aplicaciones que se establezca en una directiva se anclan a la barra de la aplicación&mdash;la barra en el lado del cliente de escritorio de los equipos y en la parte inferior de los clientes móviles de equipos&mdash;donde los usuarios pueden rápida y fácilmente tener acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="0ca82-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="0ca82-138">Los equipos incluye una directiva del programa de instalación de aplicación Firstline trabajador integrada que se puede asignar a los trabajadores de Firstline en su organización.</span><span class="sxs-lookup"><span data-stu-id="0ca82-138">Teams includes a built-in Firstline Worker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="0ca82-139">De forma predeterminada, la directiva incluye las aplicaciones de actividad, turnos, Chat y llamadas.</span><span class="sxs-lookup"><span data-stu-id="0ca82-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="0ca82-140">Para ver la directiva de trabajador de Firstline, en la izquierda del centro de administración de Microsoft Teams, vaya a la **aplicación de los equipos** > **las directivas de aplicación del programa de instalación**.</span><span class="sxs-lookup"><span data-stu-id="0ca82-140">To view the Firstline Worker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="0ca82-141">![Captura de pantalla de la directiva de Firstline trabajador de la aplicación del programa de instalación en el centro de administración de equipos de Microsoft] (../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la directiva de Firstline trabajador de la aplicación del programa de instalación en el centro de administración de equipos de Microsoft")</span><span class="sxs-lookup"><span data-stu-id="0ca82-141">![Screen shot of the Firstline Worker app setup policy in the Microsoft Teams admin center](../../media/firstline-worker-app-setup-policy.png "Screen shot of the Firstline Worker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstline-worker-policy-to-individual-users"></a><span data-ttu-id="0ca82-142">Asigne la directiva Firstline trabajador a usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="0ca82-142">Assign the Firstline Worker policy to individual users</span></span>

1. <span data-ttu-id="0ca82-143">En la izquierda el centro de administración de Microsoft Teams, vaya a **los usuarios**y, a continuación, haga clic en el usuario.</span><span class="sxs-lookup"><span data-stu-id="0ca82-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="0ca82-144">Junto a **las directivas asignadas**, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0ca82-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="0ca82-145">En **el programa de instalación de los equipos de aplicación de directiva**, seleccione **FirstlineWorker**y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ca82-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstline-worker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="0ca82-146">Asignar el proceso de trabajo de Firstline directiva de aplicación del programa de instalación para los usuarios de un grupo</span><span class="sxs-lookup"><span data-stu-id="0ca82-146">Assign the Firstline Worker app setup policy to users in a group</span></span>

<span data-ttu-id="0ca82-147">Puede asignar el proceso de trabajo de Firstline directiva de aplicación del programa de instalación para los usuarios de un grupo, como un grupo de seguridad, conectándose a Azure Active Directory PowerShell para el módulo de gráfico y la Skype para el módulo de PowerShell de negocio.</span><span class="sxs-lookup"><span data-stu-id="0ca82-147">You can assign the Firstline Worker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="0ca82-148">Para obtener más información acerca del uso de PowerShell para administrar los equipos, vea [Información general de los equipos de PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0ca82-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="0ca82-149">En este ejemplo, asignamos el proceso de trabajo de Firstline directiva de aplicación del programa de instalación a todos los usuarios de Contoso Firstline del grupo.</span><span class="sxs-lookup"><span data-stu-id="0ca82-149">In this example, we assign the Firstline Worker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="0ca82-150">Asegúrese de que primero se conecta a Azure Active Directory PowerShell para el módulo de gráfico y Skype para el módulo de PowerShell de negocio siguiendo los pasos descritos en [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="0ca82-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="0ca82-151">Obtener la GroupObjectId de un grupo en particular.</span><span class="sxs-lookup"><span data-stu-id="0ca82-151">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="0ca82-152">Obtener a los miembros del grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="0ca82-152">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="0ca82-153">Asignar a todos los usuarios en el grupo a la directiva de FirstlineWorker aplicación del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="0ca82-153">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="0ca82-154">Según la cantidad de los miembros del grupo, este comando puede tardar varios minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="0ca82-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ca82-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0ca82-155">Related topics</span></span>
- [<span data-ttu-id="0ca82-156">Ayuda para los trabajadores de Firstline se desplaza</span><span class="sxs-lookup"><span data-stu-id="0ca82-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
