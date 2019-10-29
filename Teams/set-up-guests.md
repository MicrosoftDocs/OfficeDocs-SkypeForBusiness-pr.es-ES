---
title: Active o desactive el acceso de invitado a Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Active o desactive el acceso de invitado en Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20971fd985d4512e8a9bf00db23092f1a6e44702
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753355"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="b9b4f-103">Active o desactive el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9b4f-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="b9b4f-104">De forma predeterminada, el acceso de invitado está desactivado.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-104">By default, guest access is turned off.</span></span> <span data-ttu-id="b9b4f-105">Como administrador de Office 365, debe activar el acceso de invitados para equipos antes de que los propietarios del equipo o administrador puedan agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-105">As the Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="b9b4f-106">Para activar el acceso de invitados, use la [lista de comprobación de acceso de invitados](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="b9b4f-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="b9b4f-107">Después de activar el acceso de invitado, se tarda 2-24 horas para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-107">After you turn on guest access, it takes 2-24 hours for the changes to take effect.</span></span> <span data-ttu-id="b9b4f-108">Si un usuario ve el mensaje "Póngase en contacto con el administrador" cuando intenta agregar un invitado a su equipo, es posible que el acceso de invitado no se haya activado o que la configuración aún no sea efectiva.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9b4f-109">Activar el acceso de invitados depende de la configuración de Azure Active Directory, Office 365, SharePoint Online y Teams.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-109">Turning on guest access depends on settings in Azure Active Directory, Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="b9b4f-110">Para obtener más información, consulte [autorizar el acceso de invitados en Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="b9b4f-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="b9b4f-111">Configurar el acceso de invitado en el centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="b9b4f-111">Configure guest access in the Teams admin center</span></span>

1.  <span data-ttu-id="b9b4f-112">Inicie sesión en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="b9b4f-113">Seleccione **Configuración de toda la organización** > **Acceso de invitado**.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="b9b4f-114">Establezca **permitir acceso de invitado en Microsoft Teams** en **activado**.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="b9b4f-115">Opción Permitir el acceso de invitado en Microsoft Teams activada</span><span class="sxs-lookup"><span data-stu-id="b9b4f-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="b9b4f-116">En **llamadas**, **reuniones**y **Mensajería**, seleccione **activado** o **desactivado** para cada función, en función de lo que desee permitir a los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

    - <span data-ttu-id="b9b4f-117">**Realizar llamadas privadas**: cambie esta opción a **Activado** para permitir que los invitados realicen llamadas entre compañeros.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="b9b4f-118">**Permitir vídeo IP**: cambie esta opción a **Activado** para permitir que los invitados usen vídeo en sus llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="b9b4f-119">**Modo de pantalla compartida**: esta configuración controla la disponibilidad de la pantalla compartida para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="b9b4f-120">Establezca esta opción como **Desactivado** para eliminar la posibilidad de que los invitados compartan sus pantallas en Teams.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="b9b4f-121">Establezca esta opción como **Solicitud única** para permitir el uso compartido de aplicaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="b9b4f-122">Establezca esta opción como **Pantalla completa** para permitir el uso de pantalla completa compartida.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="b9b4f-123">**Permitir Reunirse ahora**: establezca esta opción como **Activado** para permitir que los invitados usen la característica Reunirse ahora en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="b9b4f-124">**Editar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados editen los mensajes que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="b9b4f-125">**Los invitados pueden eliminar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados eliminen los mensajes que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="b9b4f-126">**Chat**: establezca esta opción como **Activado** para permitir a los invitados usar el chat en Teams.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="b9b4f-127">**Usar Giphy en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen Giphy en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="b9b4f-128">Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="b9b4f-129">A cada Giphy se le asigna una clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="b9b4f-130">**Clasificación de contenido Giphy**: seleccione una clasificación de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="b9b4f-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="b9b4f-131">**Permitir todo el contenido**: los invitados podrán insertar todos los Giphy en chats, independientemente de la clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="b9b4f-132">**Moderado**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="b9b4f-133">**Estricto**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma estricta.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="b9b4f-134">**Use memes en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen Memes en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="b9b4f-135">**Usar adhesivos en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen adhesivos en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="b9b4f-136">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="b9b4f-137">Usar PowerShell para activar o desactivar el acceso de invitados</span><span class="sxs-lookup"><span data-stu-id="b9b4f-137">Use PowerShell to turn guest access on or off</span></span>
<span data-ttu-id="b9b4f-138">Leer [use PowerShell para activar o desactivar el acceso de invitados](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="b9b4f-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span></span>


## <a name="video-adding-guests-in-teams"></a><span data-ttu-id="b9b4f-139">Vídeo: agregar invitados en Teams</span><span class="sxs-lookup"><span data-stu-id="b9b4f-139">Video: Adding guests in Teams</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="b9b4f-140">Agregar invitados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9b4f-140">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="b9b4f-141">Acceso externo (Federación) frente a acceso de invitados</span><span class="sxs-lookup"><span data-stu-id="b9b4f-141">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]