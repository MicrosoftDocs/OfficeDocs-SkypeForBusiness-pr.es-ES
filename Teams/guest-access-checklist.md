---
title: Lista de comprobación para el acceso de invitado de Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/22/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de comprobación para ayudar a configurar el acceso de invitado en invitado de los equipos de Microsoft Access.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 404754c373d46b9b6e5578107415d61bbb87f97e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463471"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="51048-103">Lista de comprobación de acceso de invitado a los equipos</span><span class="sxs-lookup"><span data-stu-id="51048-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="51048-104">Use esta lista de comprobación que le ayudarán a habilitar y configurar la característica de acceso de invitado en Microsoft Teams según las preferencias de la organización.</span><span class="sxs-lookup"><span data-stu-id="51048-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="51048-105">Comprender las limitaciones de los invitados</span><span class="sxs-lookup"><span data-stu-id="51048-105">Understand the limitations for guests</span></span>

<span data-ttu-id="51048-106">La experiencia de invitado tiene limitaciones por diseño.</span><span class="sxs-lookup"><span data-stu-id="51048-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="51048-107">Asegúrese de que comprende la experiencia de invitado por lo que no intente corregir algo que no es un problema.</span><span class="sxs-lookup"><span data-stu-id="51048-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="51048-108">Por ejemplo, aquí es una lista de algunas de las funciones que no está disponible para un invitado en Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="51048-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="51048-109">OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="51048-109">OneDrive for Business</span></span>
- <span data-ttu-id="51048-110">Búsqueda de personas fuera de los equipos</span><span class="sxs-lookup"><span data-stu-id="51048-110">People search outside of Teams</span></span>
- <span data-ttu-id="51048-111">Calendario, las reuniones programadas o detalles de la reunión</span><span class="sxs-lookup"><span data-stu-id="51048-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="51048-112">RTC</span><span class="sxs-lookup"><span data-stu-id="51048-112">PSTN</span></span>
- <span data-ttu-id="51048-113">Gráfico de organización</span><span class="sxs-lookup"><span data-stu-id="51048-113">Organization chart</span></span>
- <span data-ttu-id="51048-114">Crear o revisar un equipo</span><span class="sxs-lookup"><span data-stu-id="51048-114">Create or revise a team</span></span>
- <span data-ttu-id="51048-115">Buscar un equipo</span><span class="sxs-lookup"><span data-stu-id="51048-115">Browse for a team</span></span>
- <span data-ttu-id="51048-116">Cargar archivos a una conversación entre dos persona</span><span class="sxs-lookup"><span data-stu-id="51048-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="51048-117">Para obtener más información, vea [¿Qué es la experiencia de invitado como](guest-experience.md) y [acceso de invitado en grupos de Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="51048-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="51048-118">Acceso de invitado frente a acceso externo (federación de)</span><span class="sxs-lookup"><span data-stu-id="51048-118">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="51048-119">Si los invitados están viendo errores de licencia</span><span class="sxs-lookup"><span data-stu-id="51048-119">If your guests are seeing license errors</span></span>

<span data-ttu-id="51048-120">Acceso como invitado en Microsoft Teams usa Azure Active Directory empresarial para el negocio (B2B) y su modelo de licencia.</span><span class="sxs-lookup"><span data-stu-id="51048-120">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="51048-121">Si está viendo errores de licencias, asegúrese de leer la Guía de licencias de B2B para comprender los requisitos de licencia que su organización tiene para que los usuarios puedan invitar a personas a la organización.</span><span class="sxs-lookup"><span data-stu-id="51048-121">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="51048-122">Recuerde los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="51048-122">A few things to remember:</span></span>

- <span data-ttu-id="51048-123">Para cada una de pago licencia de Azure AD que asignar a un usuario, los usuarios pueden invitar a un máximo de cinco usuarios invitados en la concesión de usuario externo.</span><span class="sxs-lookup"><span data-stu-id="51048-123">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="51048-124">Los invitados tienen los usuarios fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="51048-124">Guests are users outside your organization.</span></span> <span data-ttu-id="51048-125">No se puede agregar los empleados, contratistas in situ, los agentes en el sitio y así sucesivamente como invitados.</span><span class="sxs-lookup"><span data-stu-id="51048-125">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="51048-126">El mismo se aplica a sus filiales.</span><span class="sxs-lookup"><span data-stu-id="51048-126">The same applies to your affiliates.</span></span>
- <span data-ttu-id="51048-127">Las licencias de invitado se cuentan contra la organización invitar a.</span><span class="sxs-lookup"><span data-stu-id="51048-127">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="51048-128">Tenga en cuenta esto al calcular el número de licencias que necesita.</span><span class="sxs-lookup"><span data-stu-id="51048-128">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="51048-129">Las licencias se cuentan contra su organización si los usuarios invitados proceden de otro inquilino de Office 365 o usan sus direcciones de correo electrónico personal.</span><span class="sxs-lookup"><span data-stu-id="51048-129">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="51048-130">□ Paso 1: configurar las opciones en Azure AD para empresas</span><span class="sxs-lookup"><span data-stu-id="51048-130">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="51048-131">Inicie sesión en https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="51048-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="51048-132">En el panel izquierdo, haga clic en **Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="51048-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="51048-133">En **Administrar**, haga clic en **Configuración del usuario**.</span><span class="sxs-lookup"><span data-stu-id="51048-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="51048-134">**Los usuarios externos**, haga clic en **configuración de colaboración externa para administrar**.</span><span class="sxs-lookup"><span data-stu-id="51048-134">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="51048-135">En la página **configuración de colaboración externa** Asegúrese de que **pueden invitar los miembros** está establecida en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="51048-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="51048-136">Captura de pantalla muestra un ejemplo de un control de alternancia AAD configuración.</span><span class="sxs-lookup"><span data-stu-id="51048-136">Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="51048-137">Para admitir a invitados, **pueden invitar los miembros** se debe establecer en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="51048-137">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="51048-138">Si establece **pueden invitar los miembros** en **No** y, a continuación, habilitar el acceso de invitado en grupos de Office 365 y Microsoft Teams, los administradores pueden controlar las invitaciones de invitado a su directorio.</span><span class="sxs-lookup"><span data-stu-id="51048-138">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="51048-139">Después de que los invitados se encuentran en el directorio, puede agregarse a los equipos de los miembros sin permisos de administrador que son propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="51048-139">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="51048-140">Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="51048-140">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="51048-141">□ Paso 2: configurar grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="51048-141">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="51048-142">En el centro de administración de Microsoft 365, vaya a **configuración de** > **& Services Add-ins** > **Grupos de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="51048-142">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="51048-143">Asegúrese de **Permitir que los miembros del grupo fuera el contenido de grupo de acceso de la organización** está establecido en **On**.</span><span class="sxs-lookup"><span data-stu-id="51048-143">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="51048-144">Si esta opción está desactivada, los invitados no puedan tener acceso a cualquier contenido de grupo.</span><span class="sxs-lookup"><span data-stu-id="51048-144">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="51048-145">Asegúrese de **que permitir a los propietarios de grupo agregar personas fuera de la organización a grupos** se establece en **On**.</span><span class="sxs-lookup"><span data-stu-id="51048-145">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="51048-146">Si esta opción está desactivada, los propietarios de equipo no puedan agregar a nuevos invitados.</span><span class="sxs-lookup"><span data-stu-id="51048-146">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="51048-147">Como mínimo, este valor debe ser sesión en compatibilidad con acceso como invitado.</span><span class="sxs-lookup"><span data-stu-id="51048-147">At a minimum, this setting must be On to support guest access.</span></span>

     ![Captura de pantalla muestra la alterna de grupos de Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="51048-149">Para obtener instrucciones detalladas acerca de cómo configurar estas opciones, vea la sección "Office 365 grupos" en [autorizar el acceso de invitado en los equipos de Microsoft](Teams-dependencies.md)y [Administrar acceso como invitado en grupos de Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) .</span><span class="sxs-lookup"><span data-stu-id="51048-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="51048-150">□ Paso 3: habilitar el acceso de invitado en el nivel de inquilino</span><span class="sxs-lookup"><span data-stu-id="51048-150">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="51048-151">Como mínimo, debe activar el acceso de invitado para Microsoft Teams en el **Centro de administración de equipos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="51048-151">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="51048-152">En el centro de administración de equipos, seleccione **configuración de toda la organización** > **acceso de invitado**.</span><span class="sxs-lookup"><span data-stu-id="51048-152">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="51048-153">Configurar el conmutador de **Permitir el acceso de invitado en los equipos de Microsoft** **activado**.</span><span class="sxs-lookup"><span data-stu-id="51048-153">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Captura de pantalla muestra un ejemplo de un control de alternancia de la configuración de los equipos](media/set-up-guests-image1.png)

3. <span data-ttu-id="51048-155">En esta misma página, configure las demás opciones de invitado que necesita.</span><span class="sxs-lookup"><span data-stu-id="51048-155">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="51048-156">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51048-156">Click **Save**.</span></span>

<span data-ttu-id="51048-157">Para obtener instrucciones detalladas, vea [Activar o desactivar el acceso de invitado a los equipos de Microsoft](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="51048-157">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="51048-158">□ Paso 4: configurar el uso compartido en Office 365</span><span class="sxs-lookup"><span data-stu-id="51048-158">□  Step 4: Configure Sharing in Office 365</span></span> 

<span data-ttu-id="51048-159">Asegúrese de que los usuarios pueden agregar a invitados.</span><span class="sxs-lookup"><span data-stu-id="51048-159">Make sure that users can add guests.</span></span> <span data-ttu-id="51048-160">Aquí es cómo:</span><span class="sxs-lookup"><span data-stu-id="51048-160">Here's how:</span></span>

1. <span data-ttu-id="51048-161">En el centro de administración de Microsoft 365, vaya a **configuración de** > **privacy & de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="51048-161">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Captura de pantalla muestra un ejemplo de una configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="51048-163">En **el uso compartido**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51048-163">In **Sharing**, select **Edit**.</span></span>

     ![Captura de pantalla muestra un ejemplo de alternancia de una configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="51048-165">**Permitir a los usuarios agregar a nuevos invitados a esta organización** se establece en **On**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51048-165">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Captura de pantalla muestra un ejemplo de alternancia de una configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="51048-167">Esta configuración es equivalente a la configuración **pueden invitar los miembros** en **Configuración del usuario** > **a los usuarios externos** en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="51048-167">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="51048-168">□ Paso 5: comprobar la configuración de uso compartido en SharePoint</span><span class="sxs-lookup"><span data-stu-id="51048-168">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="51048-169">Inicie sesión en el Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="51048-169">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="51048-170">Haga clic en **Centro de administración**y, a continuación, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="51048-170">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="51048-171">En el centro de administración de SharePoint, seleccione **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="51048-171">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="51048-172">Asegúrese de que la opción para **no permitir el uso compartido de fuera de su organización** *no* está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="51048-172">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Captura de pantalla muestra un ejemplo de alternancia de una configuración de Online Sparepoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="51048-174">□ Paso 6: habilitar la configuración específica para canales</span><span class="sxs-lookup"><span data-stu-id="51048-174">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="51048-175">En la aplicación de los equipos, en el nivel de equipo individual, configurar permisos de invitado para que los invitados pueden crear, actualizar y eliminar canales.</span><span class="sxs-lookup"><span data-stu-id="51048-175">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="51048-176">Además de los administradores, los propietarios de equipo pueden configurar esta opción.</span><span class="sxs-lookup"><span data-stu-id="51048-176">In addition to admins,  team owners can configure this setting.</span></span>

![Captura de pantalla muestra un ejemplo de un control de alternancia de configuración del equipo/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="51048-178">Para obtener más información, vídeos de procedimientos, vea [acceso como invitado en los equipos de Microsoft](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="51048-178">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="51048-179">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="51048-179">Troubleshooting</span></span>

<span data-ttu-id="51048-180">Si tiene problemas con la adición de invitados en Microsoft Teams, consulte la [Guía de solución de problemas de acceso de invitado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="51048-180">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


