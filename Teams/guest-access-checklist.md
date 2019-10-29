---
title: Lista de comprobación para el acceso de invitado de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de comprobación para ayudarle a configurar el acceso de invitado en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753325"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="79d29-103">Lista de comprobación para el acceso de invitado de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79d29-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="79d29-104">Use esta lista de comprobación para que le resulte más fácil activar y configurar el acceso de invitado en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79d29-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79d29-105">Es posible que tenga que esperar hasta 24 horas para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="79d29-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="79d29-106">Paso 1: activar el acceso de invitados en el nivel de toda la organización de los equipos</span><span class="sxs-lookup"><span data-stu-id="79d29-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="79d29-107">Para activar el acceso de invitados, vaya al **centro de administración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="79d29-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="79d29-108">En el centro de administración de Teams, seleccione**acceso de invitado a** **toda** > la organización.</span><span class="sxs-lookup"><span data-stu-id="79d29-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="79d29-109">Establezca la opción **permitir acceso de invitado en Microsoft Teams** **.**</span><span class="sxs-lookup"><span data-stu-id="79d29-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="79d29-111">En esta misma página, Active o desactive las opciones de **llamada**, **reunión**y **Mensajería** de los invitados.</span><span class="sxs-lookup"><span data-stu-id="79d29-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="79d29-112">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="79d29-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="79d29-113">Si está usando la configuración predeterminada en Azure Active Directory, SharePoint Online y grupos de Office 365, es posible que haya terminado de configurar el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="79d29-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="79d29-114">En este caso, puede omitir el resto de los pasos.</span><span class="sxs-lookup"><span data-stu-id="79d29-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="79d29-115">Si no está seguro, o si está usando una configuración personalizada para los grupos de AAD, SharePoint Online u Office 365, continúe con el resto de los pasos de esta lista de comprobación.</span><span class="sxs-lookup"><span data-stu-id="79d29-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="79d29-116">Paso 2: configurar las opciones de empresa a empresa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="79d29-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="79d29-117">Inicie sesión en el [portal de Azure](https://portal.azure.com) como administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="79d29-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="79d29-118">Seleccione**configuración de usuario**de**usuarios** > de **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="79d29-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="79d29-119">En **usuarios externos**, seleccione **administrar la configuración de colaboración externa**.</span><span class="sxs-lookup"><span data-stu-id="79d29-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="79d29-120">La **configuración de colaboración externa** también está disponible en la página relaciones de la **organización** .</span><span class="sxs-lookup"><span data-stu-id="79d29-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="79d29-121">En Azure Active Directory, en **administrar**, vaya a > **configuración**de **relaciones organizativas**.</span><span class="sxs-lookup"><span data-stu-id="79d29-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="79d29-122">En la página **configuración de colaboración externa** , elija las directivas que quiera habilitar.</span><span class="sxs-lookup"><span data-stu-id="79d29-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="79d29-123">**Los permisos de los usuarios invitados son limitados**: esta Directiva determina los permisos para los invitados de su directorio.</span><span class="sxs-lookup"><span data-stu-id="79d29-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="79d29-124">Seleccione **sí** para bloquear a los invitados de determinadas tareas de directorio, como la enumeración de usuarios, grupos u otros recursos de directorio.</span><span class="sxs-lookup"><span data-stu-id="79d29-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="79d29-125">Seleccione **no** para proporcionar a los invitados el mismo acceso a los datos de directorio que los usuarios habituales de su directorio.</span><span class="sxs-lookup"><span data-stu-id="79d29-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="79d29-126">**Los administradores y usuarios del rol invitado invitar pueden invitar**: para permitir que los administradores y los usuarios del rol "invitado invitar" puedan invitar a invitados, establezca esta directiva en **sí**.</span><span class="sxs-lookup"><span data-stu-id="79d29-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="79d29-127">**Los miembros pueden invitar**: para que los miembros que no sean administradores de su directorio puedan invitar a invitados, establezca esta directiva en **sí**.</span><span class="sxs-lookup"><span data-stu-id="79d29-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="79d29-128">Si establece que **los miembros puedan invitar** a **no** y, a continuación, habilitar el acceso de invitado en Office 365 grupos y Microsoft Teams, los administradores pueden controlar invitaciones invitadas a su directorio.</span><span class="sxs-lookup"><span data-stu-id="79d29-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="79d29-129">Una vez que los invitados estén en el directorio, los miembros que no sean administradores podrán agregarlos a teams que sean propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="79d29-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="79d29-130">Para obtener más información, consulte [Autorizar el acceso de invitado en Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="79d29-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="79d29-131">Para que el acceso de invitados funcione en todos los equipos, debe establecer que **los miembros puedan invitar** a **sí**.</span><span class="sxs-lookup"><span data-stu-id="79d29-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="79d29-132">Los **invitados pueden invitar**: para permitir que los invitados inviten a otros invitados, establezca esta directiva en **sí**.</span><span class="sxs-lookup"><span data-stu-id="79d29-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="79d29-133">Actualmente, Teams no es compatible con el rol invitado, por lo tanto, aunque establezca que los **invitados puedan invitar** a **sí**, los invitados no pueden invitar a otros invitados en Teams.</span><span class="sxs-lookup"><span data-stu-id="79d29-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="79d29-134">**Habilitar el código de acceso de un solo uso de correo electrónico para invitados (vista previa)**: para obtener más información sobre la característica de código de acceso de un solo uso, consulte [autenticación de código de acceso de un solo uso de correo electrónico (vista previa)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)</span><span class="sxs-lookup"><span data-stu-id="79d29-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="79d29-135">**Restricciones de colaboración**: para obtener más información sobre cómo permitir o bloquear invitaciones a dominios específicos, consulte [permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="79d29-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="79d29-136">Para obtener las restricciones de colaboración, consulte [Habilitar la colaboración externa B2B y administrar quién puede invitar a invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="79d29-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="79d29-137">Para obtener más información acerca de cómo controlar quién puede invitar a invitados, consulte [Delegar invitaciones para la colaboración de Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="79d29-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="79d29-138">Paso 3: configurar grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="79d29-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="79d29-139">En el centro de administración de Microsoft 365, vaya a **configuración** > **servicios & complementos** > **Office 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="79d29-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="79d29-140">Asegúrese de **permitir que los miembros del grupo ajenos a la organización tengan el contenido del grupo** **activado**.</span><span class="sxs-lookup"><span data-stu-id="79d29-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="79d29-141">Si esta opción está desactivada, los invitados no podrán acceder a ningún contenido de grupo.</span><span class="sxs-lookup"><span data-stu-id="79d29-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="79d29-142">Asegúrese de **permitir que los propietarios del grupo agreguen personas fuera de la organización a groups** se establece en **activado**.</span><span class="sxs-lookup"><span data-stu-id="79d29-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="79d29-143">Si esta opción está desactivada, los propietarios del equipo no podrán agregar invitados nuevos.</span><span class="sxs-lookup"><span data-stu-id="79d29-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="79d29-144">Como mínimo, esta configuración debe estar activada para que sea compatible con el acceso de invitados.</span><span class="sxs-lookup"><span data-stu-id="79d29-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![Captura de pantalla que muestra los alternancias de grupos de Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="79d29-146">Para obtener instrucciones detalladas sobre cómo configurar estas opciones, consulte [administrar el acceso de invitados en office 365 grupos](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en los grupos de Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="79d29-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="79d29-147">Paso 4: configurar el uso compartido en Office 365</span><span class="sxs-lookup"><span data-stu-id="79d29-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="79d29-148">Asegúrese de que los usuarios pueden agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="79d29-148">Make sure that users can add guests.</span></span> <span data-ttu-id="79d29-149">Aquí le mostramos cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="79d29-149">Here's how:</span></span>

1. <span data-ttu-id="79d29-150">En el centro de administración de Microsoft 365, vaya a **configuración** > **seguridad & privacidad**.</span><span class="sxs-lookup"><span data-stu-id="79d29-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de configuración de servicios](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="79d29-152">En **compartir**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79d29-152">In **Sharing**, select **Edit**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="79d29-154">Establezca **permitir a los usuarios agregar nuevos invitados a la organización** **en activado**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="79d29-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="79d29-156">Esta opción es equivalente a la opción los **miembros pueden invitar** en **configuración** > de usuario**usuarios externos** en Azure ad.</span><span class="sxs-lookup"><span data-stu-id="79d29-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="79d29-157">Paso 5: comprobar la configuración de uso compartido en SharePoint</span><span class="sxs-lookup"><span data-stu-id="79d29-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="79d29-158">Este es un poco de un rompecabezas.</span><span class="sxs-lookup"><span data-stu-id="79d29-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="79d29-159">El acceso de invitados en Teams no funciona si la opción **no permitir el uso compartido fuera de la organización** está seleccionada en el centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="79d29-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="79d29-160">Inicie sesión en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79d29-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="79d29-161">Haga clic en **centro de administración**y, después, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="79d29-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="79d29-162">En el centro de administración de SharePoint, seleccione **uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="79d29-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="79d29-163">Asegúrese de que la opción para **no permitir el uso compartido fuera de su organización** *no* está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="79d29-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Captura de pantalla que muestra un ejemplo de un botón de alternancia de configuración de SparePoint online.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="79d29-165">Paso 6: configurar permisos de usuario invitados</span><span class="sxs-lookup"><span data-stu-id="79d29-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="79d29-166">En la aplicación de Teams, en el nivel de equipo individual, configure los permisos de invitado que controlan si los invitados pueden crear, actualizar o eliminar canales.</span><span class="sxs-lookup"><span data-stu-id="79d29-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="79d29-167">Los administradores de equipos y los propietarios de equipo pueden configurar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="79d29-167">Teams admins as well as team owners can configure these settings.</span></span>

![Captura de pantalla que muestra un ejemplo de alternancia de configuración de un equipo o un canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="79d29-169">Para obtener más información sobre el acceso de invitados, consulte [acceso de invitados en Teams](guest-access.md) y [activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="79d29-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="79d29-170">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="79d29-170">Troubleshooting</span></span>

<span data-ttu-id="79d29-171">Si tiene problemas para configurar el acceso de invitados o agregar invitados en Teams, use estos recursos para ayudarle:</span><span class="sxs-lookup"><span data-stu-id="79d29-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="79d29-172">Solución de problemas con el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79d29-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="79d29-173">Solución de problemas de equipos</span><span class="sxs-lookup"><span data-stu-id="79d29-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



