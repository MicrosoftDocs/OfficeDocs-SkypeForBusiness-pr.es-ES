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
ms.openlocfilehash: c82172eb4d0c9fe50832d45ce2146c89d7e6d7d8
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884524"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="8e854-103">Active o desactive el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8e854-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="8e854-104">Hasta **febrero de 2021,** el acceso de invitado está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8e854-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="8e854-105">Debe habilitar el acceso de invitado para Teams antes de que los administradores o los propietarios del equipo puedan agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="8e854-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="8e854-106">Después de activar el acceso de invitado, es posible que los cambios tarden unas horas en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="8e854-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="8e854-107">Si los usuarios  ven el mensaje Póngase en contacto con el administrador cuando intenten agregar un invitado a su equipo, es probable que no se haya activado el acceso de invitado o que la configuración aún no sea efectiva.</span><span class="sxs-lookup"><span data-stu-id="8e854-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> <span data-ttu-id="8e854-108">Después de febrero de **2021,** el acceso de invitado en Microsoft Teams estará activado de forma predeterminada para los nuevos clientes & clientes existentes que no hayan configurado esta configuración.</span><span class="sxs-lookup"><span data-stu-id="8e854-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="8e854-109">Cuando se implemente este cambio, si aún no ha configurado la capacidad de acceso de invitado en Microsoft Teams, esa capacidad se habilitará en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="8e854-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="8e854-110">Si desea que el acceso de invitado permanezca deshabilitado para su organización, tendrá que confirmar que la configuración de acceso de invitado está establecida en **Desactivado** en lugar de **Servicio predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="8e854-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e854-111">El habilitar el acceso de invitado depende de las características de Azure Active Directory, Microsoft 365, SharePoint y Teams.</span><span class="sxs-lookup"><span data-stu-id="8e854-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="8e854-112">Para obtener más información, consulte [Colaborar con invitados en un equipo](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="8e854-112">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="8e854-113">Configurar el acceso de invitado en el centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="8e854-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="8e854-114">Inicie sesión en el [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8e854-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="8e854-115">Seleccione **Configuración de toda la organización** > **Acceso de invitado**.</span><span class="sxs-lookup"><span data-stu-id="8e854-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="8e854-116">Establezca cambiar **Permitir el acceso de invitado en Microsoft Teams** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="8e854-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="8e854-117">Opción Permitir el acceso de invitado activada</span><span class="sxs-lookup"><span data-stu-id="8e854-117">Allow guest access switch set to On</span></span> ](media/guest-access-setting.png)

4. <span data-ttu-id="8e854-118">En **Llamadas**, **Reunión** y **Mensajería** seleccione **Activado** o **Desactivado** según se requiera, según las funciones que quiera permitir para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="8e854-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="8e854-119">**Realizar llamadas privadas**: cambie esta opción a **Activado** para permitir que los invitados realicen llamadas entre compañeros.</span><span class="sxs-lookup"><span data-stu-id="8e854-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="8e854-120">**Permitir vídeo IP**: cambie esta opción a **Activado** para permitir que los invitados usen vídeo en sus llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="8e854-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="8e854-121">**Modo de pantalla compartida**: esta configuración controla la disponibilidad de la pantalla compartida para los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="8e854-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="8e854-122">Establezca esta opción como **Desactivado** para eliminar la posibilidad de que los invitados compartan sus pantallas en Teams.</span><span class="sxs-lookup"><span data-stu-id="8e854-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="8e854-123">Establezca esta opción como **Solicitud única** para permitir el uso compartido de aplicaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="8e854-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="8e854-124">Establezca esta opción como **Pantalla completa** para permitir el uso de pantalla completa compartida.</span><span class="sxs-lookup"><span data-stu-id="8e854-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="8e854-125">**Permitir Reunirse ahora**: establezca esta opción como **Activado** para permitir que los invitados usen la característica Reunirse ahora en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8e854-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="8e854-126">**Editar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados editen los mensajes que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8e854-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="8e854-127">**Los invitados pueden eliminar mensajes enviados**: establezca esta opción como **Activado** para permitir que los invitados eliminen los mensajes que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8e854-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="8e854-128">**Chat**: establezca esta opción como **Activado** para permitir a los invitados usar el chat en Teams.</span><span class="sxs-lookup"><span data-stu-id="8e854-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="8e854-129">**Usar Giphy en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen Giphy en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="8e854-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="8e854-130">Giphy es una base de datos en línea y un motor de búsqueda que permite a los usuarios buscar y compartir archivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="8e854-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="8e854-131">A cada Giphy se le asigna una clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="8e854-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="8e854-132">**Clasificación de contenido Giphy**: seleccione una clasificación de la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="8e854-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="8e854-133">**Permitir todo el contenido**: los invitados podrán insertar todos los Giphy en chats, independientemente de la clasificación de contenido.</span><span class="sxs-lookup"><span data-stu-id="8e854-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="8e854-134">**Moderado**: los invitados pueden insertar imágenes Giphy en los chats, pero el contenido para adultos estará restringido de forma moderada.</span><span class="sxs-lookup"><span data-stu-id="8e854-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="8e854-135">**Estricto:** los invitados pueden insertar Giphys en chats, pero no podrán insertar contenido para adultos.</span><span class="sxs-lookup"><span data-stu-id="8e854-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="8e854-136">**Use memes en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen Memes en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="8e854-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="8e854-137">**Usar adhesivos en conversaciones**: establezca esta opción como **Activado** para permitir que los invitados usen adhesivos en conversaciones.</span><span class="sxs-lookup"><span data-stu-id="8e854-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Configuración de permisos de invitado en Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="8e854-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8e854-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="8e854-140">Acceso externo (federación) frente a acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="8e854-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="8e854-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e854-141">See also</span></span>

[<span data-ttu-id="8e854-142">Configurar la colaboración moderna con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8e854-142">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="8e854-143">Bloquear el acceso de usuarios invitados a un equipo específico</span><span class="sxs-lookup"><span data-stu-id="8e854-143">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="8e854-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="8e854-144">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
