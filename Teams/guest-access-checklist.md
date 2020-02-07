---
title: Lista de comprobación para el acceso de invitado de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de comprobación para ayudarle a configurar el acceso de invitado en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833260"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="d4d31-103">Lista de comprobación para el acceso de invitado de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4d31-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="d4d31-104">Use esta lista de comprobación para que le resulte más fácil activar y configurar el acceso de invitado en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4d31-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="d4d31-105">Debe ser administrador global o administrador de Teams para poder realizar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="d4d31-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4d31-106">Es posible que tenga que esperar hasta 24 horas para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="d4d31-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="d4d31-107">Vea este vídeo breve (5:31 minutos) para obtener información sobre cómo activar el acceso de invitados en Microsoft 365, incluidos los equipos.</span><span class="sxs-lookup"><span data-stu-id="d4d31-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="d4d31-108">Paso 1: activar el acceso de invitados en el nivel de toda la organización de los equipos</span><span class="sxs-lookup"><span data-stu-id="d4d31-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="d4d31-109">Para activar el acceso de invitados, vaya al **centro de administración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="d4d31-110">En el centro de administración de Teams, seleccione**acceso de invitado a** **toda** > la organización.</span><span class="sxs-lookup"><span data-stu-id="d4d31-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="d4d31-111">Establezca la opción **permitir acceso de invitado en Microsoft Teams** **.**</span><span class="sxs-lookup"><span data-stu-id="d4d31-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="d4d31-113">En esta misma página, Active o desactive las opciones de **llamada**, **reunión**y **Mensajería** de los invitados.</span><span class="sxs-lookup"><span data-stu-id="d4d31-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="d4d31-114">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d4d31-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="d4d31-115">Si está usando la configuración predeterminada en Azure Active Directory, SharePoint Online y grupos de Office 365, es posible que haya terminado de configurar el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="d4d31-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="d4d31-116">En este caso, puede omitir el resto de los pasos.</span><span class="sxs-lookup"><span data-stu-id="d4d31-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="d4d31-117">Si no está seguro, o si está usando una configuración personalizada para los grupos de AAD, SharePoint Online u Office 365, continúe con el resto de los pasos de esta lista de comprobación.</span><span class="sxs-lookup"><span data-stu-id="d4d31-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="d4d31-118">Paso 2: configurar las opciones de empresa a empresa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d4d31-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="d4d31-119">Estas son las opciones de configuración de Azure AD que admiten el acceso de invitado en Teams.</span><span class="sxs-lookup"><span data-stu-id="d4d31-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="d4d31-120">Una vez configurada esta configuración, podrá [Agregar](add-guests.md) y [administrar invitados](manage-guests.md) en Teams.</span><span class="sxs-lookup"><span data-stu-id="d4d31-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="d4d31-121">Inicie sesión en el [portal de Azure](https://portal.azure.com) como administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d4d31-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="d4d31-122">Seleccione**configuración de usuario**de**usuarios** > de **Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="d4d31-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="d4d31-123">En **usuarios externos**, seleccione **administrar la configuración de colaboración externa**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d4d31-124">La **configuración de colaboración externa** también está disponible en la página relaciones de la **organización** .</span><span class="sxs-lookup"><span data-stu-id="d4d31-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="d4d31-125">En Azure Active Directory, en **administrar**, vaya a > **configuración**de **relaciones organizativas**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="d4d31-126">En la página **configuración de colaboración externa** , elija las directivas que quiera habilitar.</span><span class="sxs-lookup"><span data-stu-id="d4d31-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="d4d31-127">**Los permisos de los usuarios invitados son limitados**: esta Directiva determina los permisos para los invitados de su directorio.</span><span class="sxs-lookup"><span data-stu-id="d4d31-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="d4d31-128">Seleccione **sí** para bloquear a los invitados de determinadas tareas de directorio, como la enumeración de usuarios, grupos u otros recursos de directorio.</span><span class="sxs-lookup"><span data-stu-id="d4d31-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="d4d31-129">Seleccione **no** para proporcionar a los invitados el mismo acceso a los datos de directorio que los usuarios habituales de su directorio.</span><span class="sxs-lookup"><span data-stu-id="d4d31-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="d4d31-130">**Los administradores y usuarios del rol invitado invitar pueden invitar**: para permitir que los administradores y los usuarios del rol "invitado invitar" puedan invitar a invitados, establezca esta directiva en **sí**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="d4d31-131">**Los miembros pueden invitar**: para permitir que los miembros de su directorio que no sean administradores inviten a otros usuarios, establezca esta directiva en **Sí** (recomendado).</span><span class="sxs-lookup"><span data-stu-id="d4d31-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="d4d31-132">Si prefiere que solo los administradores puedan agregar invitados, puede establecer esta directiva en **No**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="d4d31-133">Tenga en cuenta que, al establecer **No**, se limitará la experiencia de invitado para los propietarios de equipos que no sean administradores. Solo podrán agregar invitados a los equipos que el administrador ya haya agregado en AAD.</span><span class="sxs-lookup"><span data-stu-id="d4d31-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="d4d31-134">Los **invitados pueden invitar**: para permitir que los invitados inviten a otros invitados, establezca esta directiva en **sí**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="d4d31-135">Actualmente, Teams no permite el rol de invitador de usuarios invitados, por lo que, aunque configure **Los miembros pueden invitar** como **Sí**, los invitados no pueden invitar a otros invitados en Teams.</span><span class="sxs-lookup"><span data-stu-id="d4d31-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="d4d31-136">**Habilitar el código de acceso de un solo uso de correo electrónico para invitados (vista previa)**: para obtener más información sobre la característica de código de acceso de un solo uso, consulte [autenticación de código de acceso de un solo uso de correo electrónico (vista previa)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)</span><span class="sxs-lookup"><span data-stu-id="d4d31-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="d4d31-137">**Restricciones de colaboración**: para obtener más información sobre cómo permitir o bloquear invitaciones a dominios específicos, consulte [permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="d4d31-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="d4d31-138">Para obtener las restricciones de colaboración, consulte [Habilitar la colaboración externa B2B y administrar quién puede invitar a invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="d4d31-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="d4d31-139">Para obtener más información acerca de cómo controlar quién puede invitar a invitados, consulte [Delegar invitaciones para la colaboración de Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="d4d31-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="d4d31-140">Paso 3: configurar grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="d4d31-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="d4d31-141">En el centro de administración de Microsoft 365, **vaya a** > configuración**configuración**, haga clic en **servicios**y, a continuación, seleccione **grupos de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![Captura de pantalla que muestra la configuración de grupos de Office 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="d4d31-143">Asegúrese de que la casilla permitir que los **miembros del grupo fuera de la organización tengan activada la casilla contenido del grupo de acceso** .</span><span class="sxs-lookup"><span data-stu-id="d4d31-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="d4d31-144">Si esta opción no está seleccionada, los invitados no podrán acceder a ningún contenido de grupo.</span><span class="sxs-lookup"><span data-stu-id="d4d31-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Captura de pantalla que muestra la configuración de grupos de Office 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="d4d31-146">Asegúrese de que la casilla permitir que los **propietarios del grupo agreguen personas fuera de la organización a los grupos** estén activadas.</span><span class="sxs-lookup"><span data-stu-id="d4d31-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="d4d31-147">Si esta opción no está seleccionada, los propietarios del equipo no podrán agregar invitados nuevos.</span><span class="sxs-lookup"><span data-stu-id="d4d31-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="d4d31-148">Como mínimo, esta configuración debe estar activada para que sea compatible con el acceso de invitados.</span><span class="sxs-lookup"><span data-stu-id="d4d31-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="d4d31-149">Para obtener instrucciones detalladas sobre cómo configurar estas opciones, consulte [administrar el acceso de invitados en office 365 grupos](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en los grupos de Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="d4d31-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="d4d31-150">Paso 4: configurar el uso compartido en Office 365</span><span class="sxs-lookup"><span data-stu-id="d4d31-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="d4d31-151">Asegúrese de que los usuarios pueden agregar invitados.</span><span class="sxs-lookup"><span data-stu-id="d4d31-151">Make sure that users can add guests.</span></span> <span data-ttu-id="d4d31-152">Aquí le mostramos cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="d4d31-152">Here's how:</span></span>

1. <span data-ttu-id="d4d31-153">En el centro de administración de Microsoft 365, **vaya a** > configuración**Settings**, haga clic en **seguridad & privacidad**y, después, seleccione **uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de configuración de servicios](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="d4d31-155">Active la casilla **permitir que los usuarios agreguen nuevos invitados a la organización** y, a continuación, haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de uso compartido](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="d4d31-157">Esta opción es equivalente a la opción los **miembros pueden invitar** en **configuración** > de usuario**usuarios externos** en Azure ad.</span><span class="sxs-lookup"><span data-stu-id="d4d31-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="d4d31-158">Paso 5: comprobar la configuración de uso compartido en SharePoint</span><span class="sxs-lookup"><span data-stu-id="d4d31-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="d4d31-159">Inicie sesión en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4d31-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="d4d31-160">En **centros de administración**, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="d4d31-161">En el nuevo centro de administración de SharePoint, en **sitios**, seleccione **sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Sitios activos en el centro de administración de SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="d4d31-163">Seleccione el sitio y, a continuación, haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="d4d31-164">Asegúrese de que la opción está establecida en **cualquiera** o en **invitados nuevos o existentes**.</span><span class="sxs-lookup"><span data-stu-id="d4d31-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![Captura de pantalla que muestra un ejemplo de alternancia de configuración de SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="d4d31-166">Paso 6: configurar permisos de usuario invitados</span><span class="sxs-lookup"><span data-stu-id="d4d31-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="d4d31-167">En la aplicación de Teams, en el nivel de equipo individual, configure los permisos de invitado que controlan si los invitados pueden crear, actualizar o eliminar canales.</span><span class="sxs-lookup"><span data-stu-id="d4d31-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="d4d31-168">Los administradores de equipos y los propietarios de equipo pueden configurar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="d4d31-168">Teams admins as well as team owners can configure these settings.</span></span>

![Captura de pantalla que muestra un ejemplo de alternancia de configuración de un equipo o un canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="d4d31-170">Para obtener más información sobre el acceso de invitados, consulte [acceso de invitados en Teams](guest-access.md) y [activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="d4d31-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d4d31-171">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="d4d31-171">Troubleshooting</span></span>

<span data-ttu-id="d4d31-172">Si tiene problemas para configurar el acceso de invitados o agregar invitados en Teams, use estos recursos para ayudarle:</span><span class="sxs-lookup"><span data-stu-id="d4d31-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="d4d31-173">Solución de problemas con el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4d31-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="d4d31-174">Solución de problemas de equipos</span><span class="sxs-lookup"><span data-stu-id="d4d31-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
