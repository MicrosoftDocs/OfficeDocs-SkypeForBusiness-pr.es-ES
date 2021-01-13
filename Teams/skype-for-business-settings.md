---
title: Administrar la configuración de Skype Empresarial en el Centro de administración de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de las características de Skype Empresarial en el Centro de administración de Microsoft Teams.
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834220"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="004ff-103">Administrar la configuración de Skype Empresarial en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="004ff-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="004ff-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="004ff-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="004ff-105">Como administrador, el Centro de administración de Microsoft Teams es donde administra las características de Skype Empresarial para los usuarios de Skype Empresarial de su organización.</span><span class="sxs-lookup"><span data-stu-id="004ff-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="004ff-106">Puede administrar la configuración [de](#manage-skype-for-business-settings-for-your-organization) su organización en la página **Skype** Empresarial y la configuración para usuarios [individuales](#manage-skype-for-business-settings-for-individual-users) en la pestaña **Skype** Empresarial de las páginas de detalles de usuario.</span><span class="sxs-lookup"><span data-stu-id="004ff-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="004ff-107">Solo verá la página **de Skype Empresarial** si el modo de coexistencia de su organización no se establece solo en **Teams.**</span><span class="sxs-lookup"><span data-stu-id="004ff-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="004ff-108">De forma similar, solo verá la pestaña **Skype** Empresarial de un usuario si el modo de coexistencia del usuario no es **Solo Teams.**</span><span class="sxs-lookup"><span data-stu-id="004ff-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="004ff-109">Para obtener más información sobre los modos de coexistencia, consulte [Comprender la](teams-and-skypeforbusiness-coexistence-and-interoperability.md) coexistencia e interoperabilidad de Teams y Skype Empresarial, y Establecer la configuración de [coexistencia y actualización.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="004ff-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="004ff-110">La configuración de Skype Empresarial estaba anteriormente en **el portal heredado** del Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="004ff-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="004ff-111">Con la retirada del portal heredado, migramos la configuración a estas nuevas ubicaciones en el Centro de administración de Teams para la administración de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="004ff-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="004ff-112">Debe tener asignado el rol de administrador de [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de Administrador global o de administrador de Skype Empresarial para poder administrar las características de Skype Empresarial en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="004ff-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="004ff-113">Administrar la configuración de Skype Empresarial para su organización</span><span class="sxs-lookup"><span data-stu-id="004ff-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="004ff-114">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a la configuración de Skype Empresarial **para**  >  **toda la organización.**</span><span class="sxs-lookup"><span data-stu-id="004ff-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="004ff-115">Desde aquí, puede configurar y administrar las notificaciones de Difusión de reunión de Skype, privacidad de presencia y dispositivos móviles para todos los usuarios de Skype Empresarial de su organización.</span><span class="sxs-lookup"><span data-stu-id="004ff-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="004ff-116">Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="004ff-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="004ff-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="004ff-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="004ff-118">Use las siguientes opciones para administrar la [Difusión de reunión de Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) en su organización.</span><span class="sxs-lookup"><span data-stu-id="004ff-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de pantalla de la configuración de Difusión de reunión de Skype en el centro de administración":::

- <span data-ttu-id="004ff-120">**Difusiones de reunión de Skype:** active esta opción para habilitar Difusión de reunión de Skype para su organización.</span><span class="sxs-lookup"><span data-stu-id="004ff-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="004ff-121">Después de habilitar esta característica, debe configurar la red para Difusión de reunión [de Skype.](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)</span><span class="sxs-lookup"><span data-stu-id="004ff-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="004ff-122">**Ver características de vista** previa: Active esta opción para obtener acceso anticipado a las nuevas características.</span><span class="sxs-lookup"><span data-stu-id="004ff-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="004ff-123">**Los organizadores pueden** programar reuniones anónimas: active esta opción si quiere permitir a los organizadores crear eventos de difusión que permitan a cualquier persona de fuera de su organización unirse sin tener que iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="004ff-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="004ff-124">**Grabar reuniones de Difusión de reunión de Skype:** active esta opción para permitir que los organizadores y presentadores graben reuniones.</span><span class="sxs-lookup"><span data-stu-id="004ff-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="004ff-125">Dirección URL del departamento de soporte técnico para los **asistentes:** escriba la dirección URL de soporte técnico de su organización que los asistentes a la reunión pueden usar si necesitan ayuda durante una reunión.</span><span class="sxs-lookup"><span data-stu-id="004ff-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="004ff-126">Notificaciones de presencia y de móvil</span><span class="sxs-lookup"><span data-stu-id="004ff-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="004ff-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="004ff-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="004ff-128">Use las siguientes opciones para administrar la privacidad de presencia de Skype Empresarial y las notificaciones móviles en su organización.</span><span class="sxs-lookup"><span data-stu-id="004ff-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de pantalla de la configuración de presencia en el centro de administración":::

#### <a name="presence"></a><span data-ttu-id="004ff-130">Presence</span><span class="sxs-lookup"><span data-stu-id="004ff-130">Presence</span></span>

<span data-ttu-id="004ff-131">De forma predeterminada, los usuarios de Skype Empresarial de su organización pueden ver el estado de presencia (como Disponible, Ocupado o No disponible) de otros usuarios de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="004ff-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="004ff-132">Elija una de las siguientes opciones para establecer quién puede ver la presencia de sus usuarios de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="004ff-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="004ff-133">**Mostrar automáticamente** la información de presencia: cualquier usuario de Skype Empresarial de su  organización  que no se haya agregado a la lista de bloqueados o externos del usuario puede ver su presencia.</span><span class="sxs-lookup"><span data-stu-id="004ff-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="004ff-134">**Mostrar la** información de presencia solo a los contactos de un usuario: cualquier usuario de  Skype  Empresarial que no se agrega a su lista De contactos externos o Bloqueados puede ver la presencia de ese usuario.</span><span class="sxs-lookup"><span data-stu-id="004ff-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="004ff-135">Los usuarios pueden invalidar esta configuración en Skype Empresarial en Opciones **de**  >  **herramientas de**  >  **configuración.**</span><span class="sxs-lookup"><span data-stu-id="004ff-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="004ff-136">Notificaciones móviles</span><span class="sxs-lookup"><span data-stu-id="004ff-136">Mobile notifications</span></span>

<span data-ttu-id="004ff-137">Puede establecer si los usuarios móviles de Skype Empresarial pueden recibir alertas sobre mensajes instantáneos entrantes y perdidos, mensajes de correo de voz y llamadas perdidas a través de un servicio de notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="004ff-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="004ff-138">Según los dispositivos móviles usados en su organización, puede usar el Servicio de notificaciones de inserción de **Microsoft,** el Servicio de notificaciones push **de Apple** o ambos.</span><span class="sxs-lookup"><span data-stu-id="004ff-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="004ff-139">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="004ff-139">Keep the following in mind:</span></span>

- <span data-ttu-id="004ff-140">Si desactiva las notificaciones de inserción, los usuarios recibirán todas las alertas la próxima vez que inicien Skype Empresarial en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="004ff-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="004ff-141">De forma predeterminada, las notificaciones push están activadas.</span><span class="sxs-lookup"><span data-stu-id="004ff-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="004ff-142">Los usuarios individuales pueden desactivarlas en Skype Empresarial en sus dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="004ff-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="004ff-143">Si desactiva las notificaciones de inserción, los usuarios no podrán volver a activarlas.</span><span class="sxs-lookup"><span data-stu-id="004ff-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="004ff-144">Microsoft usa otras empresas que proporcionan notificaciones móviles para Skype Empresarial en tiempo real para usuarios de Windows Phone, iPhone y iPad.</span><span class="sxs-lookup"><span data-stu-id="004ff-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="004ff-145">Consulte esta declaración [de privacidad.](https://go.microsoft.com/fwlink/p/?linkid=247732)</span><span class="sxs-lookup"><span data-stu-id="004ff-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="004ff-146">Administrar la configuración de Skype Empresarial para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="004ff-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="004ff-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="004ff-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="004ff-148">Para administrar la configuración de Skype Empresarial para usuarios individuales, en el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Usuarios,** haga clic en el nombre para mostrar del usuario para abrir la página de detalles del usuario y, a continuación, seleccione la pestaña de configuración de **Skype** Empresarial. Desde aquí, puede configurar las opciones de acceso externo y reunión para el usuario.</span><span class="sxs-lookup"><span data-stu-id="004ff-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de pantalla de la pestaña Skype Empresarial en la página de detalles del usuario":::

### <a name="external-access-settings"></a><span data-ttu-id="004ff-150">Configuración de acceso externo</span><span class="sxs-lookup"><span data-stu-id="004ff-150">External access settings</span></span>

<span data-ttu-id="004ff-151">Puede permitir o bloquear de forma selectiva si un usuario puede comunicarse con personas fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="004ff-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="004ff-152">**Usuarios externos de Skype** Empresarial: active esta opción si desea permitir que el usuario se comunique con usuarios de Skype Empresarial en dominios federados.</span><span class="sxs-lookup"><span data-stu-id="004ff-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="004ff-153">**Usuarios externos de Skype:** active esta opción si desea permitir que el usuario se comunique con otros usuarios de Skype.</span><span class="sxs-lookup"><span data-stu-id="004ff-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="004ff-154">Configuración de las reuniones</span><span class="sxs-lookup"><span data-stu-id="004ff-154">Meeting settings</span></span>

<span data-ttu-id="004ff-155">Puede configurar las siguientes opciones de reunión para el usuario.</span><span class="sxs-lookup"><span data-stu-id="004ff-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="004ff-156">**Vídeo &** audio: elija una de las siguientes opciones de configuración de audio y vídeo:</span><span class="sxs-lookup"><span data-stu-id="004ff-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="004ff-157">**Ninguna:** el usuario no puede usar audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="004ff-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="004ff-158">**Solo audio:** el usuario puede usar el audio, pero no el vídeo.</span><span class="sxs-lookup"><span data-stu-id="004ff-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="004ff-159">**Audio y vídeo:** el usuario puede usar audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="004ff-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="004ff-160">**Audio y vídeo (HD):** el usuario puede usar audio y vídeo de alta definición.</span><span class="sxs-lookup"><span data-stu-id="004ff-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="004ff-161">**Grabar conversaciones & reuniones:** active esta opción para permitir al usuario grabar conversaciones y reuniones.</span><span class="sxs-lookup"><span data-stu-id="004ff-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="004ff-162">**Cumplimiento:** active esta opción si se le exige legalmente que conserve la información almacenada de forma electrónica.</span><span class="sxs-lookup"><span data-stu-id="004ff-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span> 
