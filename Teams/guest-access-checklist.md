---
title: Lista de comprobación para el acceso de invitado de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de comprobación para ayudarle a configurar el acceso de invitado en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09a6ec1f60ca4bfc39dbeb5ba1829330c3413560
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925361"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="36997-103">Lista de comprobación de acceso de invitados de Teams</span><span class="sxs-lookup"><span data-stu-id="36997-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="36997-104">Use esta lista de comprobación para habilitar y configurar la característica de acceso de invitado en Microsoft Teams de acuerdo con las preferencias de su organización.</span><span class="sxs-lookup"><span data-stu-id="36997-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="36997-105">Para las restricciones de colaboración [, vea Habilitar la colaboración externa B2B y administrar quién puede invitar a invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="36997-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="36997-106">Comprender las limitaciones de los invitados</span><span class="sxs-lookup"><span data-stu-id="36997-106">Understand the limitations for guests</span></span>

<span data-ttu-id="36997-107">La experiencia de invitado tiene limitaciones por diseño.</span><span class="sxs-lookup"><span data-stu-id="36997-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="36997-108">Asegúrese de comprender la experiencia de invitado para no intentar corregir algo que no es un problema.</span><span class="sxs-lookup"><span data-stu-id="36997-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="36997-109">Por ejemplo, aquí tiene una lista de algunas de las funciones que no están disponibles para un invitado en Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="36997-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="36997-110">OneDrive para la empresa</span><span class="sxs-lookup"><span data-stu-id="36997-110">OneDrive for Business</span></span>
- <span data-ttu-id="36997-111">Búsqueda de personas fuera de Teams</span><span class="sxs-lookup"><span data-stu-id="36997-111">People search outside of Teams</span></span>
- <span data-ttu-id="36997-112">Calendario, reuniones programadas o detalles de la reunión</span><span class="sxs-lookup"><span data-stu-id="36997-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="36997-113">RTC</span><span class="sxs-lookup"><span data-stu-id="36997-113">PSTN</span></span>
- <span data-ttu-id="36997-114">Organigrama</span><span class="sxs-lookup"><span data-stu-id="36997-114">Organization chart</span></span>
- <span data-ttu-id="36997-115">Crear o revisar un equipo</span><span class="sxs-lookup"><span data-stu-id="36997-115">Create or revise a team</span></span>
- <span data-ttu-id="36997-116">Buscar un equipo</span><span class="sxs-lookup"><span data-stu-id="36997-116">Browse for a team</span></span>
- <span data-ttu-id="36997-117">Cargar archivos a una conversación entre usuarios</span><span class="sxs-lookup"><span data-stu-id="36997-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="36997-118">Los invitados pueden buscar y buscar usuarios (fuera de su equipo) si saben que el identificador de correo electrónico del usuario es completo.</span><span class="sxs-lookup"><span data-stu-id="36997-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="36997-119">Para evitar esto, los administradores de TI pueden usar patrones como la [búsqueda de directorios de ámbito](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) , que tienen la capacidad de restringir los invitados a su propia gal virtual.</span><span class="sxs-lookup"><span data-stu-id="36997-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="36997-120">Para obtener más información, consulte [cuál es la experiencia de invitado](guest-experience.md) y [acceso de invitados en los grupos de Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="36997-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="36997-121">Diferencias entre el acceso de invitados y el acceso externo (federación)</span><span class="sxs-lookup"><span data-stu-id="36997-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="36997-122">Actualmente, Microsoft Teams no es compatible con el rol invitado.</span><span class="sxs-lookup"><span data-stu-id="36997-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="36997-123">Como mínimo, el botón de alternancia "los miembros pueden invitar" debe establecerse en "sí" para que el acceso de invitados funcione en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36997-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="36997-124">Si establece "los miembros pueden invitar" a "no" y, después, habilita el acceso de invitado en Office 365 grupos y Microsoft Teams, los administradores pueden controlar invitaciones de invitados a su directorio.</span><span class="sxs-lookup"><span data-stu-id="36997-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="36997-125">Una vez que los invitados estén en el directorio, los miembros que no sean administradores podrán agregarlos a teams que sean propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="36997-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="36997-126">Si los invitados experimentan errores de licencia</span><span class="sxs-lookup"><span data-stu-id="36997-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="36997-127">El acceso de invitados en Microsoft Teams usa Azure Active Directory (Azure AD) empresarial para empresas (B2B) y su modelo de licencias.</span><span class="sxs-lookup"><span data-stu-id="36997-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="36997-128">Si ve errores de licencias, asegúrese de leer las instrucciones de licencias [B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para conocer los requisitos de licencia de la organización para que los usuarios puedan invitar a invitados a su organización.</span><span class="sxs-lookup"><span data-stu-id="36997-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="36997-129">Recuerde lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="36997-129">A few things to remember:</span></span>

- <span data-ttu-id="36997-130">Los invitados son usuarios externos a su organización.</span><span class="sxs-lookup"><span data-stu-id="36997-130">Guests are users outside your organization.</span></span> <span data-ttu-id="36997-131">Los empleados, los contratistas en el sitio, los agentes en el sitio, etc. no se pueden agregar como invitados.</span><span class="sxs-lookup"><span data-stu-id="36997-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="36997-132">Lo mismo se aplica a tus afiliados.</span><span class="sxs-lookup"><span data-stu-id="36997-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="36997-133">Las licencias de invitados se cuentan en relación con la organización que invita.</span><span class="sxs-lookup"><span data-stu-id="36997-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="36997-134">Considere esto cuando calcule el número de licencias que necesita.</span><span class="sxs-lookup"><span data-stu-id="36997-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="36997-135">Las licencias se cuentan en relación con su organización si los invitados invitados provienen de otro inquilino de Office 365 o si usan sus direcciones de correo electrónico personales.</span><span class="sxs-lookup"><span data-stu-id="36997-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="36997-136">□ Paso 1: configurar las opciones de Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="36997-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="36997-137">Inicie sesión en el [portal de Azure](https://portal.azure.com) como administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="36997-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="36997-138">Seleccione**configuración de usuario**de**usuarios** > de **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="36997-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="36997-139">En **usuarios externos**, seleccione **administrar la configuración de colaboración externa**.</span><span class="sxs-lookup"><span data-stu-id="36997-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="36997-140">La **configuración de colaboración externa** también está disponible en la página relaciones de la **organización** .</span><span class="sxs-lookup"><span data-stu-id="36997-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="36997-141">En Azure Active Directory, en **administrar**, vaya a**configuración**de **relaciones** > organizativas.</span><span class="sxs-lookup"><span data-stu-id="36997-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="36997-142">En la página **configuración de colaboración externa** , elija las directivas que quiera habilitar.</span><span class="sxs-lookup"><span data-stu-id="36997-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="36997-143">**Los permisos de los usuarios invitados son limitados**: esta Directiva determina los permisos para los invitados de su directorio.</span><span class="sxs-lookup"><span data-stu-id="36997-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="36997-144">Seleccione **sí** para bloquear a los invitados de determinadas tareas de directorio, como la enumeración de usuarios, grupos u otros recursos de directorio.</span><span class="sxs-lookup"><span data-stu-id="36997-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="36997-145">Seleccione **no** para proporcionar a los invitados el mismo acceso a los datos de directorio que los usuarios habituales de su directorio.</span><span class="sxs-lookup"><span data-stu-id="36997-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="36997-146">**Los administradores y usuarios del rol invitado invitar pueden invitar**: para permitir que los administradores y los usuarios del rol "invitado invitar" puedan invitar a invitados, establezca esta directiva en **sí**.</span><span class="sxs-lookup"><span data-stu-id="36997-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="36997-147">**Los miembros pueden invitar**: para que los miembros que no sean administradores de su directorio puedan invitar a invitados, establezca esta directiva en **sí**.</span><span class="sxs-lookup"><span data-stu-id="36997-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="36997-148">Si establece que **los miembros puedan invitar** a **no** y, a continuación, habilitar el acceso de invitado en Office 365 grupos y Microsoft Teams, los administradores pueden controlar invitaciones invitadas a su directorio.</span><span class="sxs-lookup"><span data-stu-id="36997-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="36997-149">Una vez que los invitados estén en el directorio, los miembros que no sean administradores podrán agregarlos a teams que sean propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="36997-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="36997-150">Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="36997-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="36997-151">Los **invitados pueden invitar**: para permitir que los invitados inviten a otros invitados, establezca esta directiva en **sí**.</span><span class="sxs-lookup"><span data-stu-id="36997-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="36997-152">**Habilitar el código de acceso de un solo uso de correo electrónico para invitados (vista previa)**: para obtener más información sobre la característica de código de acceso de un solo uso, consulte [autenticación de código de acceso de un solo uso de correo electrónico (vista previa)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)</span><span class="sxs-lookup"><span data-stu-id="36997-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="36997-153">**Restricciones de colaboración**: para obtener más información sobre cómo permitir o bloquear invitaciones a dominios específicos, consulte [permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](allow-deny-list.md).</span><span class="sxs-lookup"><span data-stu-id="36997-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](allow-deny-list.md).</span></span>

## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="36997-154">□ Paso 2: configurar grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="36997-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="36997-155">En el centro de administración de Microsoft 365, vaya a **configuración** > **servicios & complementos** > **Office 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="36997-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="36997-156">Asegúrese de **permitir que los miembros del grupo ajenos a la organización tengan el contenido del grupo** **activado**.</span><span class="sxs-lookup"><span data-stu-id="36997-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="36997-157">Si esta opción está desactivada, los invitados no podrán acceder a ningún contenido de grupo.</span><span class="sxs-lookup"><span data-stu-id="36997-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="36997-158">Asegúrese de **permitir que los propietarios del grupo agreguen personas fuera de la organización a groups** se establece en **activado**.</span><span class="sxs-lookup"><span data-stu-id="36997-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="36997-159">Si esta opción está desactivada, los propietarios del equipo no podrán agregar invitados nuevos.</span><span class="sxs-lookup"><span data-stu-id="36997-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="36997-160">Como mínimo, esta configuración debe estar activada para que sea compatible con el acceso de invitados.</span><span class="sxs-lookup"><span data-stu-id="36997-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![Captura de pantalla que muestra los alternancias de grupos de Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="36997-162">Para obtener instrucciones detalladas sobre cómo configurar estas opciones, consulte [administrar el acceso de invitados en office 365 grupos](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en los grupos de Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="36997-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="36997-163">□ Paso 3: habilitar el acceso de invitado en el nivel de inquilino</span><span class="sxs-lookup"><span data-stu-id="36997-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="36997-164">Como mínimo, debe activar el acceso de invitado para Microsoft Teams en el **centro de administración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="36997-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="36997-165">En el centro de administración de Teams, seleccione**acceso de invitado a** **toda** > la organización.</span><span class="sxs-lookup"><span data-stu-id="36997-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="36997-166">Establezca la opción **permitir acceso de invitado en Microsoft Teams** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="36997-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="36997-168">En esta misma página, configure cualquier otra configuración de invitados que necesite.</span><span class="sxs-lookup"><span data-stu-id="36997-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="36997-169">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="36997-169">Click **Save**.</span></span>

<span data-ttu-id="36997-170">Para obtener instrucciones detalladas, consulte [activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="36997-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="36997-171">□ Paso 4: configurar el uso compartido en Office 365</span><span class="sxs-lookup"><span data-stu-id="36997-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="36997-172">Asegúrese de que los usuarios pueden agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="36997-172">Make sure that users can add guests.</span></span> <span data-ttu-id="36997-173">Aquí le mostramos cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="36997-173">Here's how:</span></span>

1. <span data-ttu-id="36997-174">En el centro de administración de Microsoft 365, vaya a **configuración** > **seguridad & privacidad**.</span><span class="sxs-lookup"><span data-stu-id="36997-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="36997-176">En **compartir**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="36997-176">In **Sharing**, select **Edit**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="36997-178">Establezca **permitir a los usuarios agregar nuevos invitados a la organización** **en activado**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="36997-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="36997-180">Esta opción es equivalente a la opción los **miembros pueden invitar** en **configuración** > de usuario**usuarios externos** en Azure ad.</span><span class="sxs-lookup"><span data-stu-id="36997-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="36997-181">□ Paso 5: comprobar la configuración de uso compartido en SharePoint</span><span class="sxs-lookup"><span data-stu-id="36997-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="36997-182">Inicie sesión en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="36997-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="36997-183">Haga clic en **centro de administración**y, después, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="36997-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="36997-184">En el centro de administración de SharePoint, seleccione **uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="36997-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="36997-185">Asegúrese de que la opción para **no permitir el uso compartido fuera de su organización** *no* está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="36997-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Captura de pantalla que muestra un ejemplo de un botón de alternancia de configuración de SparePoint online.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="36997-187">□ Paso 6: habilitar la configuración específica de los canales</span><span class="sxs-lookup"><span data-stu-id="36997-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="36997-188">En la aplicación de Teams, en el nivel de equipo individual, configure los permisos de invitado para que los invitados puedan crear, actualizar y eliminar canales.</span><span class="sxs-lookup"><span data-stu-id="36997-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="36997-189">Además de los administradores, los propietarios del equipo pueden configurar esta opción.</span><span class="sxs-lookup"><span data-stu-id="36997-189">In addition to admins,  team owners can configure this setting.</span></span>

![Captura de pantalla que muestra un ejemplo de alternancia de configuración de un equipo o un canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="36997-191">Para obtener más información, incluyendo vídeos de procedimientos, consulte [acceso de invitado en Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="36997-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="36997-192">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="36997-192">Troubleshooting</span></span>

<span data-ttu-id="36997-193">Si tiene problemas al agregar invitados en Microsoft Teams, consulte la [Guía de solución de problemas de acceso de invitados](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="36997-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


