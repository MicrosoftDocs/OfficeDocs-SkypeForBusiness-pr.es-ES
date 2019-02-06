---
title: Administrar la configuración de reuniones en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: Obtenga información sobre cómo administrar la configuración para las reuniones de los equipos que los usuarios programar en la organización.
ms.openlocfilehash: e4eba5f585f7621add95101d06194bebead507e2
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754420"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="a091b-103">Administrar la configuración de reuniones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a091b-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="a091b-104">Como administrador, usa la configuración de las reuniones de los equipos para controlar si los usuarios anónimos pueden participar en las reuniones de los equipos, personalizar las invitaciones a reuniones y si desea habilitar la calidad de servicio (QoS), definir puertos para el tráfico en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="a091b-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set ports for real-time traffic.</span></span> <span data-ttu-id="a091b-105">Esta configuración aplica a todas las reuniones de los equipos que programación a los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="a091b-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="a091b-106">Administrar estas opciones de configuración de **reuniones** > **configuración de reunión** en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a091b-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span> 

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="a091b-107">Permitir a los usuarios anónimos unirse a reuniones</span><span class="sxs-lookup"><span data-stu-id="a091b-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="a091b-108">Unión anónima, cualquier usuario puede unirse a la reunión como un usuario anónimo haciendo clic en el vínculo en la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="a091b-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> 

<span data-ttu-id="a091b-109">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="a091b-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="a091b-110">En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="a091b-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="a091b-111">En **los participantes**, activar **los usuarios anónimos pueden unirse a una reunión**.</span><span class="sxs-lookup"><span data-stu-id="a091b-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span> 

    <span data-ttu-id="a091b-112">![reunión-configuración-participants.png] (media/meeting-settings-participants.png "Captura de pantalla de configuración de los participantes de las reuniones de los equipos en el centro de administración de equipos de Microsoft")</span><span class="sxs-lookup"><span data-stu-id="a091b-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="a091b-113">Si no desea que los usuarios anónimos a participar en reuniones programadas por los usuarios de su organización, desactive esta opción.</span><span class="sxs-lookup"><span data-stu-id="a091b-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span> 

## <a name="customize-meeting-invitations"></a><span data-ttu-id="a091b-114">Personalizar invitaciones a reuniones</span><span class="sxs-lookup"><span data-stu-id="a091b-114">Customize meeting invitations</span></span>

<span data-ttu-id="a091b-115">Puede personalizar las invitaciones a reuniones de los equipos para satisfacer las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="a091b-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="a091b-116">Puede agregar el logotipo de su organización e incluye información útil, como vínculos a su sitio Web de soporte técnico y renuncia de responsabilidad legal y un pie de página de sólo texto.</span><span class="sxs-lookup"><span data-stu-id="a091b-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span> 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="a091b-117">Sugerencias para la creación de un logotipo para las invitaciones a reuniones</span><span class="sxs-lookup"><span data-stu-id="a091b-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="a091b-118">Crear una imagen que es no más de 188 píxeles de ancho por 30 píxeles de alto (es bastante pequeña).</span><span class="sxs-lookup"><span data-stu-id="a091b-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span> 
2. <span data-ttu-id="a091b-119">Guarde la imagen en formato JPG.</span><span class="sxs-lookup"><span data-stu-id="a091b-119">Save the image in JPG format.</span></span> 
3. <span data-ttu-id="a091b-120">Almacenar la imagen en una ubicación central que todas las personas de su organización pueden tener acceso, como un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="a091b-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span> 

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="a091b-121">Personalizar las invitaciones de reunión</span><span class="sxs-lookup"><span data-stu-id="a091b-121">Customize your meeting invitations</span></span>

<span data-ttu-id="a091b-122">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="a091b-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a091b-123">En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="a091b-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="a091b-124">En la **invitación por correo electrónico**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a091b-124">Under **Email invitation**, do the following:</span></span> 

    <span data-ttu-id="a091b-125">![reunión-configuración-invitation.png] (media/meeting-settings-invitation.png "Captura de pantalla de la reunión configuración de invitación que se puede personalizar para las reuniones de los equipos")</span><span class="sxs-lookup"><span data-stu-id="a091b-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span> 

    - <span data-ttu-id="a091b-126">**Dirección URL del logotipo** Escriba la dirección URL donde está almacenado el logotipo.</span><span class="sxs-lookup"><span data-stu-id="a091b-126">**Logo URL** Enter the URL where your logo is stored.</span></span> 
    - <span data-ttu-id="a091b-127">**Dirección URL legal** Si su organización tiene un sitio Web legal que desea que las personas para ir a si tiene alguna duda legal, escriba la dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="a091b-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span> 
    - <span data-ttu-id="a091b-128">**Dirección URL de ayuda** Si su organización tiene un sitio Web de soporte técnico que desea que las personas para ir a si se ejecutan en problemas, escriba la dirección URL aquí.</span><span class="sxs-lookup"><span data-stu-id="a091b-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="a091b-129">**Pie de página** Escriba el texto que desea incluir como un pie de página.</span><span class="sxs-lookup"><span data-stu-id="a091b-129">**Footer** Enter text that you want to include as a footer.</span></span> 
3. <span data-ttu-id="a091b-130">Tiempo de espera una hora o lo propagar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a091b-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="a091b-131">A continuación, programar una reunión de los equipos para ver qué aspecto tiene la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="a091b-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="a091b-132">Establecer cómo desea controlar el tráfico de medios en tiempo real para las reuniones de los equipos</span><span class="sxs-lookup"><span data-stu-id="a091b-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>
<span data-ttu-id="a091b-133">Si se usa la calidad de servicio (QoS) para dar prioridad al tráfico de red, puede habilitar QoS marcadores y puede establecer los intervalos de puertos para cada tipo de tráfico de medios.</span><span class="sxs-lookup"><span data-stu-id="a091b-133">If you're using Quality of Service (QoS) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> 

 <span data-ttu-id="a091b-134">![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="a091b-134">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a091b-135">En el panel de navegación izquierdo, vaya a **las reuniones** > **configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="a091b-135">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="a091b-136">En la **red**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a091b-136">Under **Network**, do the following:</span></span>

    <span data-ttu-id="a091b-137">![reunión-configuración-network.png] (media/meeting-settings-network.png "Captura de pantalla de la configuración de red para las reuniones de los equipos en el centro de administración de equipos de Microsoft")</span><span class="sxs-lookup"><span data-stu-id="a091b-137">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="a091b-138">Para habilitar QoS marcadores, activar **marcadores de insertar calidad de servicio (QoS) para el tráfico de medios en tiempo real**.</span><span class="sxs-lookup"><span data-stu-id="a091b-138">To enable QoS markers, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span>
    - <span data-ttu-id="a091b-139">Para especificar intervalos de puertos, junto al **Seleccionar un rango de puerto para cada tipo de tráfico de medios en tiempo real**, seleccione **especificar intervalos de puertos**y, a continuación, escriba los puertos inicial y final de audio, vídeo y uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a091b-139">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> 
    
        <span data-ttu-id="a091b-140">Si selecciona **utilizar automáticamente los puertos disponibles**, disponibles puertos entre 1024 y 65535 se usan.</span><span class="sxs-lookup"><span data-stu-id="a091b-140">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="a091b-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a091b-141">Related topics</span></span>
- [<span data-ttu-id="a091b-142">Calidad de servicio (QoS) en los equipos</span><span class="sxs-lookup"><span data-stu-id="a091b-142">Quality of Service (QoS) in Teams</span></span>](qos-in-teams.md)

