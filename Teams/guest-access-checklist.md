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
ms.openlocfilehash: d38b0adf1a342c4398d2779e2f0b5ec3aa310144
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372009"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="c04ae-103">Lista de control de acceso de invitados de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c04ae-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="c04ae-104">Use esta lista para ayudarse a activar y configurar el acceso de invitados en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c04ae-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="c04ae-105">Es necesario ser un Administrador global o un Administrador de Teams para hacer estos cambios.</span><span class="sxs-lookup"><span data-stu-id="c04ae-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c04ae-106">Es posible que tenga que esperar unas horas para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="c04ae-106">You may have to wait a few hours for your changes to take effect.</span></span>

<span data-ttu-id="c04ae-107">Mire este corto vídeo (5:31 minutos) para ver cómo activar el acceso de invitados a través de Microsoft 365, incluyendo Teams.</span><span class="sxs-lookup"><span data-stu-id="c04ae-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="c04ae-108">Paso 1: activar el acceso de invitados a nivel de toda la organización de Teams</span><span class="sxs-lookup"><span data-stu-id="c04ae-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="c04ae-109">Para realizar estos cambios, debe ser administrador del servicio de Teams.</span><span class="sxs-lookup"><span data-stu-id="c04ae-109">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="c04ae-110">Consulte [usar los roles de administrador de Teams para administrar los equipos](https://docs.microsoft.com/microsoftteams/using-admin-roles) para obtener información sobre cómo obtener roles y permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="c04ae-110">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="c04ae-111">En el centro de administración de Teams, seleccione **configuración de Toda la organización** > \*\* Acceso de invitado\*\*.</span><span class="sxs-lookup"><span data-stu-id="c04ae-111">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="c04ae-112">Establezca cambiar**Permitir el acceso de invitado en Microsoft Teams** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-112">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![La captura de pantalla muestra un ejemplo de un conmutador de configuración de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="c04ae-114">En esta misma página, active o desactive **Llamada**, **Reunión**, y **Configuración** de mensajería para invitados.</span><span class="sxs-lookup"><span data-stu-id="c04ae-114">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="c04ae-115">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="c04ae-115">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="c04ae-116">Si está usando la configuración predeterminada en Azure Active Directory, SharePoint Online y Microsoft 365 Groups, es posible que haya terminado de configurar el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="c04ae-116">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="c04ae-117">En este caso, puede saltarse el resto de los pasos.</span><span class="sxs-lookup"><span data-stu-id="c04ae-117">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="c04ae-118">Si no está seguro, o si está usando una configuración personalizada para los grupos de AAD, SharePoint Online o Microsoft 365, continúe con el resto de los pasos de esta lista de comprobación.</span><span class="sxs-lookup"><span data-stu-id="c04ae-118">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="c04ae-119">Paso 2: configurar las opciones de empresa a empresa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="c04ae-119">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="c04ae-120">Estos son los ajustes de Azure AD que permiten el acceso de invitados en Teams.</span><span class="sxs-lookup"><span data-stu-id="c04ae-120">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="c04ae-121">Una vez que estos ajustes estén configurados, estará habilitado para[agregar](add-guests.md) y [administrar invitados](manage-guests.md) en Teams.</span><span class="sxs-lookup"><span data-stu-id="c04ae-121">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="c04ae-122">Inicie sesión en [Azure Portal](https://portal.azure.com) como administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="c04ae-122">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="c04ae-123">Seleccione **Azure Active Directory** > **Usuarios** > **Configuración de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-123">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="c04ae-124">En **Usuarios externos**, seleccione **Administrar configuración de colaboración externa**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-124">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c04ae-125">Los **Ajustes de colaboración externa** también están disponibles en la página **Relaciones con la organización**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-125">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="c04ae-126">En el Azure Active Directory, en **Administrar**, vaya a **Configuración de relaciones** > \*\* organizacionales\*\*.</span><span class="sxs-lookup"><span data-stu-id="c04ae-126">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="c04ae-127">En la página de **Configuración de la colaboración externa**, elija las directivas que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="c04ae-127">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="c04ae-128">**Los permisos de los usuarios invitados están limitados**: esta directiva determina los permisos de los invitados en su directorio.</span><span class="sxs-lookup"><span data-stu-id="c04ae-128">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="c04ae-129">Seleccione **Sí** para bloquear invitados de ciertas tareas del directorio, como enumerar usuarios, grupos u otros recursos del directorio.</span><span class="sxs-lookup"><span data-stu-id="c04ae-129">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="c04ae-130">Seleccione **No** para dar a los invitados el mismo acceso a los datos del directorio que a los usuarios habituales de su directorio.</span><span class="sxs-lookup"><span data-stu-id="c04ae-130">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="c04ae-131">**Los administradores y usuarios en el rol de invitado pueden invitar**: para permitir a los administradores y usuarios en el papel de "Invitador de huéspedes" invitar a los huéspedes, establecer esta directiva a **Si**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-131">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="c04ae-132">**Los miembros pueden invitar**: para permitir que los miembros de su directorio que no sean administradores inviten a otros usuarios, establezca esta directiva en **Sí** (recomendado).</span><span class="sxs-lookup"><span data-stu-id="c04ae-132">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="c04ae-133">Si prefiere que solo los administradores puedan agregar invitados, puede establecer esta directiva en **No**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-133">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="c04ae-134">Tenga en cuenta que, al establecer **No**, se limitará la experiencia de invitado para los propietarios de equipos que no sean administradores. Solo podrán agregar invitados a los equipos que el administrador ya haya agregado en AAD.</span><span class="sxs-lookup"><span data-stu-id="c04ae-134">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="c04ae-135">**Los invitados pueden invitar**: para permitir que los invitados inviten a otros invitados, configure esta directiva a **Sí**. </span><span class="sxs-lookup"><span data-stu-id="c04ae-135">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="c04ae-136">Actualmente, Teams no permite el rol de invitador de usuarios invitados, por lo que, aunque configure **Los miembros pueden invitar** como **Sí**, los invitados no pueden invitar a otros invitados en Teams.</span><span class="sxs-lookup"><span data-stu-id="c04ae-136">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="c04ae-137">**Habilitar la contraseña de correo electrónico de un solo uso para invitados (Vista previa)**: Para obtener más información sobre la función de contraseña de un solo uso, consulte [Autenticación de la contraseña de correo electrónico de un solo uso (vista previa)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="c04ae-137">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="c04ae-138">**Restricciones a la colaboración**: Para obtener más información sobre cómo permitir o bloquear invitaciones a dominios específicos, consulte[Permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="c04ae-138">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="c04ae-139">Para las restricciones de colaboración, consulte [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="c04ae-139">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

    <span data-ttu-id="c04ae-140">Para más información sobre el control de quién puede invitar a los invitados, consulte [Invitaciones de delegados para la colaboración B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="c04ae-140">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="c04ae-141">Paso 3: configurar grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c04ae-141">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="c04ae-142">En el centro de administración de Microsoft 365, vaya a **configuración**de la  >  **organización**configuración de la organización, haga clic en **servicios**y, a continuación, seleccione **grupos de Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-142">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![Captura de pantalla que muestra la configuración de grupos de Microsoft 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="c04ae-144">Asegúrese de que la casilla de verificación **Dejar que los miembros del grupo fuera de la organización accedan al contenido del grupo** esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c04ae-144">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="c04ae-145">Si no se selecciona esta opción, los invitados no podrán acceder a ningún contenido del grupo.</span><span class="sxs-lookup"><span data-stu-id="c04ae-145">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Captura de pantalla que muestra la configuración de grupos de Microsoft 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="c04ae-147">Asegúrese de que la casilla de verificación **Dejar que los propietarios de los grupos añadan personas ajenas a la organización a los grupos** esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c04ae-147">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="c04ae-148">Si no se selecciona esta opción, los propietarios de los equipos no podrán añadir nuevos invitados.</span><span class="sxs-lookup"><span data-stu-id="c04ae-148">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="c04ae-149">Como mínimo, esta configuración debe estar activada para permitir el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="c04ae-149">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="c04ae-150">Para obtener instrucciones detalladas sobre cómo configurar estas opciones, vea [administrar el acceso de invitado en microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) y [controlar el acceso de invitados en grupos de Microsoft 365](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span><span class="sxs-lookup"><span data-stu-id="c04ae-150">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-microsoft-365"></a><span data-ttu-id="c04ae-151">Paso 4: configurar el uso compartido en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c04ae-151">Step 4: Configure sharing in Microsoft 365</span></span>

<span data-ttu-id="c04ae-152">Asegúrate de que los usuarios puedan añadir invitados.</span><span class="sxs-lookup"><span data-stu-id="c04ae-152">Make sure that users can add guests.</span></span> <span data-ttu-id="c04ae-153">A continuación se describe cómo:</span><span class="sxs-lookup"><span data-stu-id="c04ae-153">Here's how:</span></span>

1. <span data-ttu-id="c04ae-154">En el centro de administración de Microsoft 365, vaya a **configuración de**  >  **configuración**de la organización, haga clic en **seguridad & privacidad**y, después, seleccione **compartir**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-154">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![La captura de pantalla muestra un ejemplo de configuración de servicios](media/guest-access-checklist-security-privacy-settings.png)

2. <span data-ttu-id="c04ae-156">Seleccione la casilla **Permitir que los usuarios agreguen nuevos invitados a esta organización**, y luego haga clic en **Guardar los cambios**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-156">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![La captura de pantalla muestra un ejemplo de un cambio de configuración del uso compartido](media/guest-access-checklist-sharing-setting.png)

    > [!NOTE]
    > <span data-ttu-id="c04ae-158">Esta configuración es equivalente a la configuración de los **Miembros pueden invitar** en **Configuración de usuario** > **Usuarios externos** en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c04ae-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="c04ae-159">Paso 5: Verificar la configuración de compartir en SharePoint</span><span class="sxs-lookup"><span data-stu-id="c04ae-159">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="c04ae-160">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c04ae-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="c04ae-161">En **Centros de administración**, **seleccione SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-161">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="c04ae-162">En el nuevo Centro de administración de SharePoint, en **Sitios**, seleccione **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-162">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Sitios activos en el Centro de administración de SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="c04ae-164">Seleccione el sitio, y luego haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-164">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="c04ae-165">Asegúrese de que la opción se establece en **Cualquiera** o en **Huéspedes nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="c04ae-165">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![La captura de pantalla muestra un ejemplo de un cambio de configuración de SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="c04ae-167">Paso 6: establecer los permisos de usuario invitado</span><span class="sxs-lookup"><span data-stu-id="c04ae-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="c04ae-168">En la aplicación Teams, a nivel de equipo individual, configure los permisos de los invitados que controlan si los invitados pueden crear, actualizar o borrar canales.</span><span class="sxs-lookup"><span data-stu-id="c04ae-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="c04ae-169">Tanto los administradores de los equipos como los propietarios de los mismos pueden configurar estos ajustes.</span><span class="sxs-lookup"><span data-stu-id="c04ae-169">Teams admins as well as team owners can configure these settings.</span></span>

![La captura de pantalla muestra un ejemplo de una configuración de equipo/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="c04ae-171">Para obtener más información sobre el acceso de invitados, consulte [Acceso de invitados en Teams](guest-access.md) y [Activar o desactivar el acceso de invitados a Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="c04ae-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c04ae-172">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="c04ae-172">Troubleshooting</span></span>

<span data-ttu-id="c04ae-173">Si tiene problemas para configurar el acceso de invitados o para añadir invitados en Teams, utilice estos recursos para ayudarle:</span><span class="sxs-lookup"><span data-stu-id="c04ae-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="c04ae-174">Solucionar problemas con el acceso de invitados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c04ae-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="c04ae-175">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="c04ae-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
