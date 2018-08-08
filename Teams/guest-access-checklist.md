---
title: Lista de comprobación de acceso de invitado de los equipos de Microsoft
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Use esta lista de comprobación para ayudar a configurar el acceso de invitado en invitado de los equipos de Microsoft Access.
localization_priority: Priority
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9eec0425f7060597fc0d6a669a9b76821f141421
ms.sourcegitcommit: 0fa147c33b1d7b5790af8d93339700ab62939430
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2018
ms.locfileid: "19744274"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="1f451-103">Lista de comprobación de acceso de invitado a los equipos</span><span class="sxs-lookup"><span data-stu-id="1f451-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="1f451-104">Use esta lista de comprobación que le ayudarán a habilitar y configurar la característica de acceso de invitado en Microsoft Teams según las preferencias de la organización.</span><span class="sxs-lookup"><span data-stu-id="1f451-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="1f451-105">Acceso como invitado □ habilitar en el nivel de inquilino</span><span class="sxs-lookup"><span data-stu-id="1f451-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="1f451-106">Como mínimo, debe activar Microsoft Teams para todos los usuarios del tipo de licencia **invitado**.</span><span class="sxs-lookup"><span data-stu-id="1f451-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="1f451-107">Para obtener instrucciones detalladas, vea [Activar o desactivar el acceso de invitado a los equipos de Microsoft](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="1f451-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![Captura de pantalla muestra un ejemplo de un control de alternancia de la configuración de los equipos](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="1f451-109">□ Habilitar opciones específicas de canales</span><span class="sxs-lookup"><span data-stu-id="1f451-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="1f451-110">En la aplicación de los equipos, en el nivel de equipo individual, configurar permisos de invitado para que los invitados pueden crear, actualizar y eliminar canales.</span><span class="sxs-lookup"><span data-stu-id="1f451-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="1f451-111">Además de los administradores, los propietarios de equipo pueden configurar esta opción.</span><span class="sxs-lookup"><span data-stu-id="1f451-111">In addition to admins,  team owners can configure this setting.</span></span>

![Captura de pantalla muestra un ejemplo de un control de alternancia de configuración del equipo/canal](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="1f451-113">Para obtener más información, vídeos de procedimientos, vea [acceso como invitado en los equipos de Microsoft](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="1f451-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="1f451-114">□ Configurar el uso compartido en Office 365</span><span class="sxs-lookup"><span data-stu-id="1f451-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="1f451-115">□ Asegúrese de que los usuarios pueden agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="1f451-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="1f451-116">Aquí es cómo:</span><span class="sxs-lookup"><span data-stu-id="1f451-116">Here's how:</span></span>

1. <span data-ttu-id="1f451-117">En el centro de administración de Office 365, vaya a **configuración de** > **de seguridad y privacidad**.</span><span class="sxs-lookup"><span data-stu-id="1f451-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="1f451-118">![Captura de pantalla muestra un ejemplo de una configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="1f451-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="1f451-119">En **el uso compartido**, seleccione **Editar**. ![Captura de pantalla muestra un ejemplo de un botón de edición de la configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="1f451-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="1f451-120">**Permitir a los usuarios agregar a nuevos invitados a esta organización** se establece en **On**y, a continuación, haga clic en **Guardar**. ![Captura de pantalla muestra un ejemplo de alternancia de una configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="1f451-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="1f451-121">Esta configuración es equivalente a la configuración **pueden invitar los miembros** en configuración del usuario > usuarios externos en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1f451-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="1f451-122">□ Configurar grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="1f451-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="1f451-123">En el centro de administración de Office 365, vaya a **configuración de** > **Services & Add-ins** > **Grupos de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="1f451-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="1f451-124">Asegúrese de **Permitir que los miembros del grupo fuera el contenido de grupo de acceso de la organización** está establecido en **On**.</span><span class="sxs-lookup"><span data-stu-id="1f451-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="1f451-125">Si esta opción está desactivada, los invitados no puedan tener acceso a cualquier contenido de grupo.</span><span class="sxs-lookup"><span data-stu-id="1f451-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="1f451-126">Asegúrese de **que permitir a los propietarios de grupo agregar personas fuera de la organización a grupos** se establece en **On**.</span><span class="sxs-lookup"><span data-stu-id="1f451-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="1f451-127">Si esta opción está desactivada, los propietarios de equipo no puedan agregar a nuevos invitados.</span><span class="sxs-lookup"><span data-stu-id="1f451-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="1f451-128">Como mínimo, este valor debe ser "en" admitir el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="1f451-128">At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="1f451-129">Para obtener instrucciones detalladas acerca de cómo configurar estas opciones, vea la sección "Grupos de Office 365" en [autorizar el acceso de invitado en los equipos de Microsoft](Teams-dependencies.md) y [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=869658).</span><span class="sxs-lookup"><span data-stu-id="1f451-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="1f451-130">Establecer la configuración del □ en Azure AD business-to-business (B2B)</span><span class="sxs-lookup"><span data-stu-id="1f451-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="1f451-131">Inicie sesión en https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="1f451-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="1f451-132">En el panel izquierdo, haga clic en **Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="1f451-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="1f451-133">En **Administrar**, haga clic en **Configuración del usuario**.</span><span class="sxs-lookup"><span data-stu-id="1f451-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="1f451-134">En **los usuarios externos**, haga clic en **Administrar externo configuración de colaboración**</span><span class="sxs-lookup"><span data-stu-id="1f451-134">Under **External users**, click **Manage External collaboration settings**</span></span>
5. <span data-ttu-id="1f451-135">En la página **configuración de colaboración externa** Asegúrese de que **pueden invitar los miembros** está establecida en **Sí**. ![Captura de pantalla muestra un ejemplo de un control de alternancia AAD configuración.</span><span class="sxs-lookup"><span data-stu-id="1f451-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="1f451-136">► Como mínimo para admitir a los invitados, **pueden invitar los miembros** se debe establecer en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1f451-136">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> <span data-ttu-id="1f451-137">Si establece **pueden invitar los miembros** en **No** y habilitar el acceso de invitado en grupos de Office 365 y Microsoft Teams, los administradores pueden controlar las invitaciones de invitado a su directorio.</span><span class="sxs-lookup"><span data-stu-id="1f451-137">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="1f451-138">Después de que los invitados se encuentran en el directorio, puede agregarse a los equipos de los miembros sin permisos de administrador (propietarios de equipo).</span><span class="sxs-lookup"><span data-stu-id="1f451-138">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="1f451-139">Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="1f451-139">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="1f451-140">Configuración de uso compartido de Verify □ en SharePoint</span><span class="sxs-lookup"><span data-stu-id="1f451-140">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="1f451-141">Inicie sesión en el Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f451-141">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="1f451-142">Haga clic en **Centro de administración**y, a continuación, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1f451-142">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="1f451-143">En el centro de administración de SharePoint, seleccione **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="1f451-143">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="1f451-144">Asegúrese de que la opción para **no permitir el uso compartido de fuera de su organización** *no* está seleccionado. ![Captura de pantalla muestra un ejemplo de alternancia de una configuración de Online Sparepoint.</span><span class="sxs-lookup"><span data-stu-id="1f451-144">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="1f451-145">Tipos y licencias □ Verify cuenta</span><span class="sxs-lookup"><span data-stu-id="1f451-145">□ Verify account licenses and types</span></span>

- <span data-ttu-id="1f451-146">**Cuenta con licencia para equipos**: para una cuenta de "Invitado" con raíz en una cuenta de usuario real en algunos otro inquilino de Office 365, debe tener licencia para los equipos de esa cuenta de usuario real para "Invitado".</span><span class="sxs-lookup"><span data-stu-id="1f451-146">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="1f451-147">**Cuenta debe ser school de Office 365 o trabajar cuenta, o cuenta MSA**: actualmente, se pueden agregar los usuarios que tienen una dirección de correo electrónico correspondiente a un Azure Active Directory, del trabajo de Office 365 o cuenta de escuela o una cuenta de Microsoft (MSA) como un usuario invitado.</span><span class="sxs-lookup"><span data-stu-id="1f451-147">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="1f451-148">Entorno de Configure □</span><span class="sxs-lookup"><span data-stu-id="1f451-148">□ Configure environment</span></span>


<span data-ttu-id="1f451-149">Los invitados son necesarios para usar la autenticación multifactor (MFA) si así lo requiere el inquilino de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1f451-149">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="1f451-150">Para obtener más información, vea [modelos de identidad y la autenticación en los equipos de Microsoft](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1f451-150">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="1f451-151">Limitaciones de □ comprenda el funcionamiento de los invitados</span><span class="sxs-lookup"><span data-stu-id="1f451-151">□ Understand limitations for guests</span></span>

<span data-ttu-id="1f451-152">La experiencia de invitado tiene limitaciones por diseño.</span><span class="sxs-lookup"><span data-stu-id="1f451-152">The guest experience has limitations by design.</span></span> <span data-ttu-id="1f451-153">Asegúrese de que comprende la experiencia de invitado por lo que no intente corregir algo que no es un problema.</span><span class="sxs-lookup"><span data-stu-id="1f451-153">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="1f451-154">Por ejemplo, aquí es una lista de algunas de las funciones que no está disponible para un invitado en Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="1f451-154">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="1f451-155">OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="1f451-155">OneDrive for Business</span></span>
- <span data-ttu-id="1f451-156">Búsqueda de personas fuera de los equipos</span><span class="sxs-lookup"><span data-stu-id="1f451-156">People search outside of Teams</span></span>
- <span data-ttu-id="1f451-157">Calendario, las reuniones programadas o detalles de la reunión</span><span class="sxs-lookup"><span data-stu-id="1f451-157">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="1f451-158">RTC</span><span class="sxs-lookup"><span data-stu-id="1f451-158">PSTN</span></span>
- <span data-ttu-id="1f451-159">Gráfico de organización</span><span class="sxs-lookup"><span data-stu-id="1f451-159">Organization chart</span></span>
- <span data-ttu-id="1f451-160">Crear o revisar un equipo</span><span class="sxs-lookup"><span data-stu-id="1f451-160">Create or revise a team</span></span>
- <span data-ttu-id="1f451-161">Buscar un equipo</span><span class="sxs-lookup"><span data-stu-id="1f451-161">Browse for a team</span></span>
- <span data-ttu-id="1f451-162">Cargar archivos a una conversación entre dos persona</span><span class="sxs-lookup"><span data-stu-id="1f451-162">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="1f451-163">Para obtener más información, vea [¿Qué es la experiencia de invitado como](guest-experience.md) y [acceso de invitado en grupos de Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="1f451-163">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="1f451-164">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1f451-164">Troubleshooting</span></span>

<span data-ttu-id="1f451-165">Si tiene problemas con la adición de invitados en Microsoft Teams, consulte la [Guía de solución de problemas de acceso de invitado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="1f451-165">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


