---
title: Lista de control de acceso de invitados de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Obtenga más información sobre cómo activar y configurar el acceso de invitado en Microsoft Teams como administrador global o de Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9d91731792dd049f76d781c4a0be08e92d09e0bb
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326607"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="64738-103">Lista de control de acceso de invitados de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64738-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="64738-104">Use esta lista para ayudarse a activar y configurar el acceso de invitados en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64738-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="64738-105">Es necesario ser un Administrador global o un Administrador de Teams para hacer estos cambios.</span><span class="sxs-lookup"><span data-stu-id="64738-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64738-106">Es posible que tenga que esperar unas horas para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="64738-106">You may have to wait a few hours for your changes to take effect.</span></span> 

<span data-ttu-id="64738-107">Mire este corto vídeo (5:31 minutos) para ver cómo activar el acceso de invitados a través de Microsoft 365, incluyendo Teams.</span><span class="sxs-lookup"><span data-stu-id="64738-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="64738-108">Paso 1: activar el acceso de invitados a nivel de toda la organización de Teams</span><span class="sxs-lookup"><span data-stu-id="64738-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="64738-109">Para activar el acceso de invitados, vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="64738-109">To turn on guest access, go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

1. <span data-ttu-id="64738-110">En el centro de administración de Teams, seleccione **configuración de Toda la organización** > \*\* Acceso de invitado\*\*.</span><span class="sxs-lookup"><span data-stu-id="64738-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="64738-111">Establezca cambiar**Permitir el acceso de invitado en Microsoft Teams** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="64738-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![La captura de pantalla muestra un ejemplo de un conmutador de configuración de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="64738-113">En esta misma página, active o desactive **Llamada**, **Reunión**, y **Configuración** de mensajería para invitados.</span><span class="sxs-lookup"><span data-stu-id="64738-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="64738-114">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="64738-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="64738-115">Si está usando la configuración predeterminada en Azure Active Directory, SharePoint Online y Microsoft 365 Groups, es posible que haya terminado de configurar el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="64738-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="64738-116">En este caso, puede saltarse el resto de los pasos.</span><span class="sxs-lookup"><span data-stu-id="64738-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="64738-117">Si no está seguro, o si está usando una configuración personalizada para los grupos de AAD, SharePoint Online o Microsoft 365, continúe con el resto de los pasos de esta lista de comprobación.</span><span class="sxs-lookup"><span data-stu-id="64738-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="64738-118">Paso 2: configurar las opciones de empresa a empresa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="64738-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="64738-119">Estos son los ajustes de Azure AD que permiten el acceso de invitados en Teams.</span><span class="sxs-lookup"><span data-stu-id="64738-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="64738-120">Una vez que estos ajustes estén configurados, estará habilitado para[agregar](add-guests.md) y [administrar invitados](manage-guests.md) en Teams.</span><span class="sxs-lookup"><span data-stu-id="64738-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="64738-121">Inicie sesión en [Azure Portal](https://portal.azure.com) como administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="64738-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="64738-122">Seleccione **Azure Active Directory** > **Usuarios** > **Configuración de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="64738-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="64738-123">En **Usuarios externos**, seleccione **Administrar configuración de colaboración externa**.</span><span class="sxs-lookup"><span data-stu-id="64738-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="64738-124">Los **Ajustes de colaboración externa** también están disponibles en la página **Relaciones con la organización**.</span><span class="sxs-lookup"><span data-stu-id="64738-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="64738-125">En el Azure Active Directory, en **Administrar**, vaya a **Configuración de relaciones** > \*\* organizacionales\*\*.</span><span class="sxs-lookup"><span data-stu-id="64738-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="64738-126">En la página de **Configuración de la colaboración externa**, elija las directivas que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="64738-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="64738-127">**Los permisos de los usuarios invitados están limitados**: esta directiva determina los permisos de los invitados en su directorio.</span><span class="sxs-lookup"><span data-stu-id="64738-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="64738-128">Seleccione **Sí** para bloquear invitados de ciertas tareas del directorio, como enumerar usuarios, grupos u otros recursos del directorio.</span><span class="sxs-lookup"><span data-stu-id="64738-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="64738-129">Seleccione **No** para dar a los invitados el mismo acceso a los datos del directorio que a los usuarios habituales de su directorio.</span><span class="sxs-lookup"><span data-stu-id="64738-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="64738-130">**Los administradores y usuarios en el rol de invitado pueden invitar**: para permitir a los administradores y usuarios en el papel de "Invitador de huéspedes" invitar a los huéspedes, establecer esta directiva a **Si**.</span><span class="sxs-lookup"><span data-stu-id="64738-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="64738-131">**Los miembros pueden invitar**: para permitir que los miembros de su directorio que no sean administradores inviten a otros usuarios, establezca esta directiva en **Sí** (recomendado).</span><span class="sxs-lookup"><span data-stu-id="64738-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="64738-132">Si prefiere que solo los administradores puedan agregar invitados, puede establecer esta directiva en **No**.</span><span class="sxs-lookup"><span data-stu-id="64738-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="64738-133">Tenga en cuenta que, al establecer **No**, se limitará la experiencia de invitado para los propietarios de equipos que no sean administradores. Solo podrán agregar invitados a los equipos que el administrador ya haya agregado en AAD.</span><span class="sxs-lookup"><span data-stu-id="64738-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="64738-134">**Los invitados pueden invitar**: para permitir que los invitados inviten a otros invitados, configure esta directiva a **Sí**. </span><span class="sxs-lookup"><span data-stu-id="64738-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="64738-135">Actualmente, Teams no permite el rol de invitador de usuarios invitados, por lo que, aunque configure **Los miembros pueden invitar** como **Sí**, los invitados no pueden invitar a otros invitados en Teams.</span><span class="sxs-lookup"><span data-stu-id="64738-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="64738-136">**Habilitar la contraseña de correo electrónico de un solo uso para invitados (Vista previa)**: Para obtener más información sobre la función de contraseña de un solo uso, consulte [Autenticación de la contraseña de correo electrónico de un solo uso (vista previa)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="64738-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="64738-137">**Restricciones a la colaboración**: Para obtener más información sobre cómo permitir o bloquear invitaciones a dominios específicos, consulte[Permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="64738-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="64738-138">Para las restricciones de colaboración, consulte [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="64738-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="64738-139">Para más información sobre el control de quién puede invitar a los invitados, consulte [Invitaciones de delegados para la colaboración B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="64738-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="64738-140">Paso 3: configurar grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="64738-140">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="64738-141">En el centro de administración de Microsoft 365, **vaya a configuración**  >  **configuración**, haga clic en **servicios**y, a continuación, seleccione **grupos de Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="64738-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![Captura de pantalla que muestra la configuración de grupos de Microsoft 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="64738-143">Asegúrese de que la casilla de verificación **Dejar que los miembros del grupo fuera de la organización accedan al contenido del grupo** esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="64738-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="64738-144">Si no se selecciona esta opción, los invitados no podrán acceder a ningún contenido del grupo.</span><span class="sxs-lookup"><span data-stu-id="64738-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Captura de pantalla que muestra la configuración de grupos de Microsoft 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="64738-146">Asegúrese de que la casilla de verificación **Dejar que los propietarios de los grupos añadan personas ajenas a la organización a los grupos** esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="64738-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="64738-147">Si no se selecciona esta opción, los propietarios de los equipos no podrán añadir nuevos invitados.</span><span class="sxs-lookup"><span data-stu-id="64738-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="64738-148">Como mínimo, esta configuración debe estar activada para permitir el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="64738-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="64738-149">Para obtener instrucciones detalladas sobre cómo configurar estas opciones, vea [administrar el acceso de invitado en microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en grupos de Microsoft 365](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span><span class="sxs-lookup"><span data-stu-id="64738-149">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="64738-150">Paso 4: Configurar el uso compartido en Office 365</span><span class="sxs-lookup"><span data-stu-id="64738-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="64738-151">Asegúrate de que los usuarios puedan añadir invitados.</span><span class="sxs-lookup"><span data-stu-id="64738-151">Make sure that users can add guests.</span></span> <span data-ttu-id="64738-152">A continuación se describe cómo:</span><span class="sxs-lookup"><span data-stu-id="64738-152">Here's how:</span></span>

1. <span data-ttu-id="64738-153">En el Centro de administración de Microsoft 365, diríjase a **Configuraciones** > **Configuraciones**, haga clic en**Seguridad y privacidad**, y luego seleccione **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="64738-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![La captura de pantalla muestra un ejemplo de configuración de servicios](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="64738-155">Seleccione la casilla **Permitir que los usuarios agreguen nuevos invitados a esta organización**, y luego haga clic en **Guardar los cambios**.</span><span class="sxs-lookup"><span data-stu-id="64738-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![La captura de pantalla muestra un ejemplo de un cambio de configuración del uso compartido](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="64738-157">Esta configuración es equivalente a la configuración de los **Miembros pueden invitar** en **Configuración de usuario** > **Usuarios externos** en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="64738-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="64738-158">Paso 5: Verificar la configuración de compartir en SharePoint</span><span class="sxs-lookup"><span data-stu-id="64738-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="64738-159">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="64738-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="64738-160">En **Centros de administración**, **seleccione SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="64738-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="64738-161">En el nuevo Centro de administración de SharePoint, en **Sitios**, seleccione **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="64738-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Sitios activos en el Centro de administración de SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="64738-163">Seleccione el sitio, y luego haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="64738-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="64738-164">Asegúrese de que la opción se establece en **Cualquiera** o en **Huéspedes nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="64738-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![La captura de pantalla muestra un ejemplo de un cambio de configuración de SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="64738-166">Paso 6: establecer los permisos de usuario invitado</span><span class="sxs-lookup"><span data-stu-id="64738-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="64738-167">En la aplicación Teams, a nivel de equipo individual, configure los permisos de los invitados que controlan si los invitados pueden crear, actualizar o borrar canales.</span><span class="sxs-lookup"><span data-stu-id="64738-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="64738-168">Tanto los administradores de los equipos como los propietarios de los mismos pueden configurar estos ajustes.</span><span class="sxs-lookup"><span data-stu-id="64738-168">Teams admins as well as team owners can configure these settings.</span></span>

![La captura de pantalla muestra un ejemplo de una configuración de equipo/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="64738-170">Para obtener más información sobre el acceso de invitados, consulte [Acceso de invitados en Teams](guest-access.md) y [Activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="64738-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="64738-171">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="64738-171">Troubleshooting</span></span>

<span data-ttu-id="64738-172">Si tiene problemas para configurar el acceso de invitados o para añadir invitados en Teams, utilice estos recursos para ayudarle:</span><span class="sxs-lookup"><span data-stu-id="64738-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="64738-173">Solucionar problemas con el acceso de invitados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64738-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="64738-174">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="64738-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
