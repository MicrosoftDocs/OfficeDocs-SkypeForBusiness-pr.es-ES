---
title: Lista de comprobación de acceso de invitado de los equipos de Microsoft
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Utilice esta lista de comprobación para configurar el acceso de invitado en invitado de los equipos de Microsoft Access.
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53800ddf452fd6596abe3e4404c79352483e946
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2018
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="a7770-103">Lista de comprobación de acceso de invitado a los equipos</span><span class="sxs-lookup"><span data-stu-id="a7770-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="a7770-104">Utilice esta lista de comprobación para habilitar y configurar la característica de acceso de invitado en Microsoft Teams según las preferencias de la organización.</span><span class="sxs-lookup"><span data-stu-id="a7770-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="a7770-105">Acceso como invitado □ habilitar en el nivel de inquilinos</span><span class="sxs-lookup"><span data-stu-id="a7770-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="a7770-106">Como mínimo, debe activar Microsoft Teams para todos los usuarios del tipo de licencia **invitado**.</span><span class="sxs-lookup"><span data-stu-id="a7770-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="a7770-107">Para obtener instrucciones detalladas, consulte [Activar o desactivar acceso de invitado a equipos de Microsoft](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="a7770-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![Captura de pantalla muestra un ejemplo de un control de alternancia de la configuración de equipos](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="a7770-109">□ Habilitar configuración específica de los canales</span><span class="sxs-lookup"><span data-stu-id="a7770-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="a7770-110">En la aplicación de los equipos, en el nivel de equipo individual, configurar permisos de invitado para que los invitados pueden crear, actualizar y eliminar canales.</span><span class="sxs-lookup"><span data-stu-id="a7770-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="a7770-111">Además de administradores, propietarios de equipo pueden configurar esta opción.</span><span class="sxs-lookup"><span data-stu-id="a7770-111">In addition to admins,  team owners can configure this setting.</span></span>

![Captura de pantalla muestra un ejemplo de un control de alternancia de la configuración del equipo/canal](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="a7770-113">Para obtener más información, vídeos de procedimientos, consulte [acceso como invitado en los equipos de Microsoft](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="a7770-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="a7770-114">□ Configure el uso compartido en Office 365</span><span class="sxs-lookup"><span data-stu-id="a7770-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="a7770-115">□ Asegúrese de que los usuarios pueden agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="a7770-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="a7770-116">Le mostramos cómo:</span><span class="sxs-lookup"><span data-stu-id="a7770-116">Here's how:</span></span>

1. <span data-ttu-id="a7770-117">En el centro de administración de Office 365, vaya a **configuración de** > **de seguridad y privacidad**.</span><span class="sxs-lookup"><span data-stu-id="a7770-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="a7770-118">![Captura de pantalla muestra un ejemplo de una configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="a7770-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="a7770-119">En **Compartir**, seleccione **Editar**. ![Captura de pantalla muestra un ejemplo de un botón de edición de la configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="a7770-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="a7770-120">**Permitir a los usuarios agregar a nuevos invitados a esta organización** se establece en **On**y, a continuación, haga clic en **Guardar**. ![Captura de pantalla muestra un ejemplo de una alternancia de la configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="a7770-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="a7770-121">Este valor es equivalente a la configuración en configuración de usuario **pueden invitar miembros** > usuarios externos en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a7770-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="a7770-122">□ Configurar grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="a7770-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="a7770-123">En el centro de administración de Office 365, vaya a **configuración de** > **Servicios & Add-ins** > **Grupos de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="a7770-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="a7770-124">Asegúrese de que **Permitir que los miembros del grupo fuera del contenido del grupo de acceso de organización** se establece en **On**.</span><span class="sxs-lookup"><span data-stu-id="a7770-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="a7770-125">Si esta opción está desactivada, los invitados no pueden tener acceso a cualquier contenido de grupo.</span><span class="sxs-lookup"><span data-stu-id="a7770-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="a7770-126">Asegúrese de que **permiten agregar personas ajenas a la organización a grupos propietarios del grupo** se establece en **On**.</span><span class="sxs-lookup"><span data-stu-id="a7770-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="a7770-127">Si esta opción está desactivada, los propietarios del equipo no pueden agregar a nuevos invitados.</span><span class="sxs-lookup"><span data-stu-id="a7770-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="a7770-128">(Sin embargo, si un administrador había agregado un usuario invitado a Azure AD, a continuación, el propietario del equipo sería puede agregar ese usuario al equipo.) Como mínimo, este valor debe ser "on" admitir el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="a7770-128">(However, if an admin had added a guest user to Azure AD, then the Team owner would be able to add that user to the Team.) At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="a7770-129">Para obtener instrucciones detalladas acerca de cómo configurar estas opciones, consulte la sección "Office 365 grupos" de [autorizar el acceso de invitado en los equipos de Microsoft](Teams-dependencies.md) y [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://go.microsoft.com/fwlink/?linkid=869658).</span><span class="sxs-lookup"><span data-stu-id="a7770-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="a7770-130">Establecer la configuración del □ en AD Azure business-to-business (B2B)</span><span class="sxs-lookup"><span data-stu-id="a7770-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="a7770-131">Iniciar sesión en https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="a7770-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="a7770-132">En el panel izquierdo, haga clic en **Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="a7770-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="a7770-133">En **Administrar**, haga clic en **configuración de usuario**.</span><span class="sxs-lookup"><span data-stu-id="a7770-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="a7770-134">**Los usuarios externos**, asegúrese de que **pueden invitar los miembros** está establecida en **Sí**. ![Captura de pantalla muestra un ejemplo de una alternancia de DAA configuración.</span><span class="sxs-lookup"><span data-stu-id="a7770-134">In **External users**, make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="a7770-135">► Como mínimo para admitir a invitados, **pueden invitar miembros** debe establecerse en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a7770-135">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> <span data-ttu-id="a7770-136">Si establece **pueden invitar miembros** a **No** y habilitar el acceso de invitado en Office 365 grupos y Teams de Microsoft, administradores pueden controlar las invitaciones de invitado a su directorio.</span><span class="sxs-lookup"><span data-stu-id="a7770-136">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="a7770-137">Después de que los invitados están en el directorio, pueden agregarse a los equipos miembros no administrador (propietarios de equipo).</span><span class="sxs-lookup"><span data-stu-id="a7770-137">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="a7770-138">Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="a7770-138">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="a7770-139">Configuración de uso compartido de Verify □ en SharePoint</span><span class="sxs-lookup"><span data-stu-id="a7770-139">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="a7770-140">Inicie sesión en el Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7770-140">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="a7770-141">Haga clic en **Admin center**y, a continuación, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a7770-141">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="a7770-142">En el centro de administración de SharePoint, seleccione **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="a7770-142">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="a7770-143">Asegúrese de que la opción *no* está seleccionada para **no permitir compartir fuera de su organización** . ![Captura de pantalla muestra un ejemplo de una alternancia de configuración en línea Sparepoint.</span><span class="sxs-lookup"><span data-stu-id="a7770-143">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="a7770-144">Tipos y licencias □ comprobar cuenta</span><span class="sxs-lookup"><span data-stu-id="a7770-144">□ Verify account licenses and types</span></span>

- <span data-ttu-id="a7770-145">**Cuenta con licencia para equipos**: para una cuenta de "Invitado" sus raíces en una cuenta de usuario real en algunos otros clientes de Office 365, esa cuenta de usuario real debe tener una licencia para los equipos de "Invitado".</span><span class="sxs-lookup"><span data-stu-id="a7770-145">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="a7770-146">**Cuenta debe ser Office 365 escuela o trabajar la cuenta, o cuenta MSA**: actualmente, los usuarios que tengan una dirección de correo electrónico correspondiente a un Active Directory de Azure, Office 365 trabajo o escuela cuenta o una cuenta de Microsoft (MSA) pueden agregarse como usuario invitado.</span><span class="sxs-lookup"><span data-stu-id="a7770-146">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="a7770-147">Entorno de configurar □</span><span class="sxs-lookup"><span data-stu-id="a7770-147">□ Configure environment</span></span>


<span data-ttu-id="a7770-148">Los invitados deben utilizar la autenticación con varios factores (AMF) si lo requiere el inquilino alojamiento.</span><span class="sxs-lookup"><span data-stu-id="a7770-148">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="a7770-149">Para obtener más detalles, vea [modelos de identidad y la autenticación de equipos de Microsoft](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a7770-149">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="a7770-150">Limitaciones de entender □ para invitados</span><span class="sxs-lookup"><span data-stu-id="a7770-150">□ Understand limitations for guests</span></span>

<span data-ttu-id="a7770-151">La experiencia de invitado tiene limitaciones por diseño.</span><span class="sxs-lookup"><span data-stu-id="a7770-151">The guest experience has limitations by design.</span></span> <span data-ttu-id="a7770-152">Asegúrese de que entender la experiencia del invitado para no intentar arreglar algo que no sea un problema.</span><span class="sxs-lookup"><span data-stu-id="a7770-152">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="a7770-153">Por ejemplo, presentamos una lista de algunas de las funciones que no está disponible para un invitado en Teams de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="a7770-153">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="a7770-154">OneDrive para el negocio</span><span class="sxs-lookup"><span data-stu-id="a7770-154">OneDrive for Business</span></span>
- <span data-ttu-id="a7770-155">Búsqueda de personas fuera de los equipos</span><span class="sxs-lookup"><span data-stu-id="a7770-155">People search outside of Teams</span></span>
- <span data-ttu-id="a7770-156">Calendario, reuniones programadas o detalles de la reunión</span><span class="sxs-lookup"><span data-stu-id="a7770-156">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="a7770-157">RTC</span><span class="sxs-lookup"><span data-stu-id="a7770-157">PSTN</span></span>
- <span data-ttu-id="a7770-158">Organigrama</span><span class="sxs-lookup"><span data-stu-id="a7770-158">Organization chart</span></span>
- <span data-ttu-id="a7770-159">Crear o revisar un equipo</span><span class="sxs-lookup"><span data-stu-id="a7770-159">Create or revise a team</span></span>
- <span data-ttu-id="a7770-160">Buscar un equipo</span><span class="sxs-lookup"><span data-stu-id="a7770-160">Browse for a team</span></span>
- <span data-ttu-id="a7770-161">Cargar archivos en un chat de persona a persona</span><span class="sxs-lookup"><span data-stu-id="a7770-161">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="a7770-162">Para obtener más información, vea [cómo es la experiencia del invitado](guest-experience.md) y el [acceso como invitado en los grupos de Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="a7770-162">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="a7770-163">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="a7770-163">Troubleshooting</span></span>

<span data-ttu-id="a7770-164">Si tiene problemas con la adición de invitados en Teams de Microsoft, consulte la [Guía de solución de problemas de acceso de invitado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="a7770-164">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


