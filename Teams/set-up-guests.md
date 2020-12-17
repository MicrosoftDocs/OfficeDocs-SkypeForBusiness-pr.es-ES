---
title: Active o desactive el acceso de invitado a Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Obtenga más información sobre cómo habilitar o deshabilitar el acceso de invitado en Microsoft Teams como administrador de Office 365.
ms.openlocfilehash: 0920e9d8b8184f7f7ca83a71f0bd97d3a4d78470
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031196"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="6e92c-103">Active o desactive el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e92c-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="6e92c-104">Por defecto, el acceso de invitados está desactivado.</span><span class="sxs-lookup"><span data-stu-id="6e92c-104">By default, guest access is turned off.</span></span> <span data-ttu-id="6e92c-105">Debe habilitar el acceso de invitado para Teams antes de que los administradores o los propietarios del equipo puedan agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="6e92c-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="6e92c-106">Después de habilitar el acceso de invitado, puede que se necesiten algunas horas para que los cambios se apliquen por completo.</span><span class="sxs-lookup"><span data-stu-id="6e92c-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="6e92c-107">Si un usuario ve el mensaje "Póngase en contacto con su administrador" cuando intenta agregar un invitado a su equipo, es muy probable que el acceso de invitado no esté habilitado o que la configuración no haya entrado aún en vigor.</span><span class="sxs-lookup"><span data-stu-id="6e92c-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e92c-108">El habilitar el acceso de invitado depende de las características de Azure Active Directory, Microsoft 365, SharePoint y Teams.</span><span class="sxs-lookup"><span data-stu-id="6e92c-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="6e92c-109">Para obtener más información, consulte [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="6e92c-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="6e92c-110">Configurar el acceso de invitado en el centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="6e92c-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="6e92c-111">Inicie sesión en el [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6e92c-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="6e92c-112">Seleccione **Configuración de toda la organización** > **Acceso de invitado**.</span><span class="sxs-lookup"><span data-stu-id="6e92c-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="6e92c-113">Establezca cambiar **Permitir el acceso de invitado en Microsoft Teams** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="6e92c-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="6e92c-114">Opción Permitir el acceso de invitado activada</span><span class="sxs-lookup"><span data-stu-id="6e92c-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="6e92c-115">En **Llamadas**, **Reunión** y **Mensajería** seleccione **Activado** o **Desactivado** según se requiera, según las funciones que quiera permitir para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="6e92c-115">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="6e92c-116">**Realizar llamadas privadas**: cambie esta opción a **Activado** para permitir que los invitados realicen llamadas entre compañeros.</span><span class="sxs-lookup"><span data-stu-id="6e92c-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="6e92c-117">**Permitir vídeo IP**: cambie esta opción a **Activado** para permitir que los invitados usen vídeo en sus llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="6e92c-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="6e92c-118">**Modo de pantalla compartida**: esta configuración controla la disponibilidad de la pantalla compartida para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="6e92c-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="6e92c-119">Establezca esta opción como **Desactivado** para eliminar la posibilidad de que los invitados compartan sus pantallas en Teams.</span><span class="sxs-lookup"><span data-stu-id="6e92c-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="6e92c-120">Establezca esta opción como **Solicitud única** para permitir el uso compartido de aplicaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="6e92c-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="6e92c-121">Establezca esta opción como **Pantalla completa** para permitir el uso de pantalla completa compartida.</span><span class="sxs-lookup"><span data-stu-id="6e92c-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="6e92c-122">**Permitir Reunirse ahora**: establezca esta opción como **Activado** para permitir que los invitados usen la característica Reunirse ahora en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6e92c-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="6e92c-123">**Editar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados editen los mensajes que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6e92c-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="6e92c-124">**Los invitados pueden eliminar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados eliminen los mensajes que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6e92c-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="6e92c-125">**Chat**: establezca esta opción como **Activado** para permitir a los invitados usar el chat en Teams.</span><span class="sxs-lookup"><span data-stu-id="6e92c-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="6e92c-126">**Usar Giphy en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen Giphy en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="6e92c-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="6e92c-127">Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="6e92c-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="6e92c-128">A cada Giphy se le asigna una clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="6e92c-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="6e92c-129">**Clasificación de contenido Giphy**: seleccione una clasificación de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="6e92c-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="6e92c-130">**Permitir todo el contenido**: los invitados podrán insertar todos los Giphy en chats, independientemente de la clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="6e92c-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="6e92c-131">**Moderado**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.</span><span class="sxs-lookup"><span data-stu-id="6e92c-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="6e92c-132">**Estricto**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma estricta.</span><span class="sxs-lookup"><span data-stu-id="6e92c-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="6e92c-133">**Use memes en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen Memes en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="6e92c-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="6e92c-134">**Usar adhesivos en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen adhesivos en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="6e92c-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![Configuración de permisos de invitado en Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="6e92c-136">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e92c-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="6e92c-137">Acceso externo (federación) frente a acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="6e92c-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="6e92c-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e92c-138">See also</span></span>

[<span data-ttu-id="6e92c-139">Configurar la colaboración moderna con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e92c-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="6e92c-140">Bloquear el acceso de usuarios invitados a un equipo específico</span><span class="sxs-lookup"><span data-stu-id="6e92c-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="6e92c-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e92c-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
