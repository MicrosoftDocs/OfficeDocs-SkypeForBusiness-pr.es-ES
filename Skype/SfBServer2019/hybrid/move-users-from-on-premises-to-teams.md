---
title: Mover usuarios de local a los equipos
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo migrar la configuración de usuario y mover los usuarios a los equipos.'
ms.openlocfilehash: 78f0c49fa2179b4a0aa95a993476c21fb679f489
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2018
ms.locfileid: "25436568"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="5b9db-103">Mover usuarios de local a los equipos</span><span class="sxs-lookup"><span data-stu-id="5b9db-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="5b9db-104">Con Skype para Business Server 2019, puede migrar los usuarios locales a los equipos, tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5b9db-104">With Skype for Business Server 2019, you can migrate your on-premises users to Teams as described in this article.</span></span>

<span data-ttu-id="5b9db-105">Tenga en cuenta que después de mover los usuarios a los equipos:</span><span class="sxs-lookup"><span data-stu-id="5b9db-105">Be aware that after moving your users to Teams:</span></span> 
 
- <span data-ttu-id="5b9db-106">Sus reuniones se migran a Skype para profesionales en línea, y sus contactos se migran a los equipos.</span><span class="sxs-lookup"><span data-stu-id="5b9db-106">Their meetings are migrated to Skype for Business Online, and their contacts are migrated to Teams.</span></span> 
- <span data-ttu-id="5b9db-107">Puede unirse a reuniones de Skype a través de la Skype para el cliente enriquecido de negocio (no le pide a los usuarios para cada hora de inicio de sesión) o a través de la aplicación de las reuniones de Skype (requiere una descarga única e inicio de sesión).</span><span class="sxs-lookup"><span data-stu-id="5b9db-107">They can join Skype meetings through the Skype for Business rich client (users are not prompted for sign-in each time) or through the Skype Meetings App (requires a one-time download and sign-in).</span></span> <span data-ttu-id="5b9db-108">Cuando un usuario hace clic en un Skype para el vínculo de la reunión de negocio dentro de los equipos, se iniciará la reunión en la aplicación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5b9db-108">When a user clicks on a Skype for Business meeting link within Teams, the meeting will launch in the appropriate app.</span></span>

- <span data-ttu-id="5b9db-109">En el móvil, los usuarios podrán unirse a Skype existente para reuniones de negocio mediante la aplicación nativa sólo.</span><span class="sxs-lookup"><span data-stu-id="5b9db-109">On Mobile, your users will be able to join existing Skype for Business meetings using the native app only.</span></span>

> [!NOTE]
> <span data-ttu-id="5b9db-110">Después de que un usuario se mueve a modo de TeamsOnly, el usuario está hospedado en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="5b9db-110">After a user is moved to TeamsOnly mode, the user is homed in Skype for Business Online.</span></span>

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a><span data-ttu-id="5b9db-111">Requisitos previos para mover usuarios locales a los equipos</span><span class="sxs-lookup"><span data-stu-id="5b9db-111">Prerequisites for moving on-premises users to Teams</span></span> 

<span data-ttu-id="5b9db-112">En esta sección se describe los requisitos previos para mover los usuarios locales a los equipos.</span><span class="sxs-lookup"><span data-stu-id="5b9db-112">This section describes the prerequisites for moving your on-premises users to Teams.</span></span> <span data-ttu-id="5b9db-113">Debe:</span><span class="sxs-lookup"><span data-stu-id="5b9db-113">You must:</span></span>
- <span data-ttu-id="5b9db-114">[Configurar conectividad híbrida](#set-up-hybrid-connectivity) (si no lo ha hecho ya)</span><span class="sxs-lookup"><span data-stu-id="5b9db-114">[Set up hybrid connectivity](#set-up-hybrid-connectivity) (if you have not already done so)</span></span>
- <span data-ttu-id="5b9db-115">[Notifique a los usuarios de la mover a los equipos](#notify-your-users-of-the-move-to-teams) (opcional)</span><span class="sxs-lookup"><span data-stu-id="5b9db-115">[Notify your users of the move to Teams](#notify-your-users-of-the-move-to-teams) (optional)</span></span>
- [<span data-ttu-id="5b9db-116">Asegúrese de que los usuarios tienen una licencia válida</span><span class="sxs-lookup"><span data-stu-id="5b9db-116">Ensure that your users have a valid license</span></span>](#make-sure-your-users-have-a-valid-license)
- [<span data-ttu-id="5b9db-117">Debe tener en cuenta los requisitos de configuración de voz</span><span class="sxs-lookup"><span data-stu-id="5b9db-117">Be aware of voice configuration requirements</span></span>](#voice-configuration-requirements)
- <span data-ttu-id="5b9db-118">[Asignar una directiva de actualización de los equipos](#assign-a-teams-upgrade-policy) (opcional)</span><span class="sxs-lookup"><span data-stu-id="5b9db-118">[Assign a Teams Upgrade policy](#assign-a-teams-upgrade-policy) (optional)</span></span>

## <a name="set-up-hybrid-connectivity"></a><span data-ttu-id="5b9db-119">Configurar conectividad híbrida</span><span class="sxs-lookup"><span data-stu-id="5b9db-119">Set up hybrid connectivity</span></span>
<span data-ttu-id="5b9db-120">Antes de migrar los usuarios, si aún no lo ha hecho, debe asegurarse de que ha configurado la conectividad híbrida entre su Skype para entorno local de Business Server y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="5b9db-120">Before you migrate your users, if you have not already done so, you must ensure that you have configured hybrid connectivity between your Skype for Business Server on-premises environment and Skype for Business Online.</span></span> <span data-ttu-id="5b9db-121">Conectividad híbrida requiere la sincronización de Active Directory, configuración de federación y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="5b9db-121">Hybrid connectivity requires Active Directory synchronization, configuring federation, and so on.</span></span> <span data-ttu-id="5b9db-122">Para obtener más información, vea [Planear la conectividad híbrida](plan-hybrid-connectivity.md) y [conectividad de la configuración híbrida](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="5b9db-122">For more information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

## <a name="notify-your-users-of-the-move-to-teams"></a><span data-ttu-id="5b9db-123">Notifique a los usuarios de la mover a los equipos</span><span class="sxs-lookup"><span data-stu-id="5b9db-123">Notify your users of the move to Teams</span></span> 
<span data-ttu-id="5b9db-124">Esto es un paso opcional, pero que se deben tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="5b9db-124">This is an optional step, but one that you should consider.</span></span> <span data-ttu-id="5b9db-125">Para notificar a los usuarios de la actualización de los equipos pendiente, puede usar los cmdlets de TeamsUpgradePolicy y TeamsUpgradeConfiguration local.</span><span class="sxs-lookup"><span data-stu-id="5b9db-125">To notify users of the pending Teams upgrade, you can use the on-premises TeamsUpgradePolicy and TeamsUpgradeConfiguration cmdlets.</span></span> <span data-ttu-id="5b9db-126">También puede configurar la descarga automática silenciosa de los equipos en segundo plano antes de la actualización (solo para clientes de Win32).</span><span class="sxs-lookup"><span data-stu-id="5b9db-126">You can also configure silent auto-download of Teams in the background prior to upgrade (Win32 clients only).</span></span> 

<span data-ttu-id="5b9db-127">Por ejemplo, para notificar a los usuarios que se van a actualizar a los equipos, use el cmdlet de TeamsUpgradePolicy local con el parámetro - NotifySbUser.</span><span class="sxs-lookup"><span data-stu-id="5b9db-127">For example, to notify users that they are being upgraded to Teams, use the on-premises TeamsUpgradePolicy cmdlet with the -NotifySbUser parameter.</span></span> <span data-ttu-id="5b9db-128">Puede establecer la directiva en un nivel global, de sitio, grupo o usuario.</span><span class="sxs-lookup"><span data-stu-id="5b9db-128">You can set the policy on a global, site, pool, or user level.</span></span> <span data-ttu-id="5b9db-129">El comando siguiente, se crea y concede una directiva de nivel de usuario:</span><span class="sxs-lookup"><span data-stu-id="5b9db-129">The following command creates and grants a user-level policy:</span></span>
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

<span data-ttu-id="5b9db-130">Puede comprobar esta directiva mediante el cmdlet Get-csTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="5b9db-130">You can check this policy by using the Get-csTeamsUpgradePolicy cmdlet.</span></span>

<span data-ttu-id="5b9db-131">Los usuarios verán una notificación de la inminente mover a los equipos.</span><span class="sxs-lookup"><span data-stu-id="5b9db-131">Your users will see a notification of the impending move to Teams.</span></span> <span data-ttu-id="5b9db-132">Se produce la notificación en Win32, Mac, Mobile y clientes Web (con la versión correcta).</span><span class="sxs-lookup"><span data-stu-id="5b9db-132">The notification occurs on Win32, Mac, Mobile, and Web Clients (with the right version).</span></span>

<span data-ttu-id="5b9db-133">Puede especificar la descarga automática de los equipos (para los clientes de Win32) para los usuarios que se está actualizando mediante el cmdlet de TeamsUpgradeConfiguration de local con el parámetro DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="5b9db-133">You can specify automatic download of Teams (for Win32 clients) for users being upgraded by using the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="5b9db-134">Establecer esta directiva en el nivel de inquilino, y que se pueden aplicar en un sitio global y del nivel de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="5b9db-134">You set this policy at the tenant level, and it can be applied on a global, site, and pool level.</span></span> <span data-ttu-id="5b9db-135">Por ejemplo, el comando siguiente establece la directiva en el nivel de sitio:</span><span class="sxs-lookup"><span data-stu-id="5b9db-135">For example, the following command sets the policy at the site level:</span></span>

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

<span data-ttu-id="5b9db-136">De forma predeterminada, el valor de DownloadTeams es True, pero también se debe establecer NotifySfbUser en True para habilitar los equipos para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="5b9db-136">By default, the value of DownloadTeams is True, but you must also set NotifySfbUser to True to enable Teams for a given user.</span></span> 

## <a name="make-sure-your-users-have-a-valid-license"></a><span data-ttu-id="5b9db-137">Asegúrese de que los usuarios tienen una licencia válida</span><span class="sxs-lookup"><span data-stu-id="5b9db-137">Make sure your users have a valid license</span></span>  
<span data-ttu-id="5b9db-138">Antes de la migración, el usuario local se debe proporcionar una licencia válida, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="5b9db-138">Before migration, the on-premises user must be given a valid license, as follows:</span></span>

-   <span data-ttu-id="5b9db-139">Usuario debe tener una licencia de los equipos.</span><span class="sxs-lookup"><span data-stu-id="5b9db-139">User must have a Teams license.</span></span>
-   <span data-ttu-id="5b9db-140">Si el usuario está configurado para usar local Enterprise Voice, deben tener una licencia de voz en línea al mover.</span><span class="sxs-lookup"><span data-stu-id="5b9db-140">If the user is configured to use on-premises Enterprise Voice, they must have an online voice license when moving.</span></span> 
-   <span data-ttu-id="5b9db-141">Si el usuario está configurado para conferencias de acceso telefónico local, deben tener una licencia para el sistema telefónico (nube PBX).</span><span class="sxs-lookup"><span data-stu-id="5b9db-141">If the user is configured for on-premises dial-in conferencing, they must have a license for Phone System (Cloud PBX).</span></span>

## <a name="voice-configuration-requirements"></a><span data-ttu-id="5b9db-142">Requisitos de configuración de voz</span><span class="sxs-lookup"><span data-stu-id="5b9db-142">Voice configuration requirements</span></span>

<span data-ttu-id="5b9db-143">Si los usuarios local tienen voz local, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="5b9db-143">If your on-premises users have on-premises voice, you have two options:</span></span>

-  <span data-ttu-id="5b9db-144">**Migrar los usuarios con funciones de telefonía.**</span><span class="sxs-lookup"><span data-stu-id="5b9db-144">**Migrate users with telephony capabilities.**</span></span> <span data-ttu-id="5b9db-145">Los usuarios pueden realizar y recibir llamadas con el cliente de los equipos.</span><span class="sxs-lookup"><span data-stu-id="5b9db-145">Users can make and receive calls using the Teams client.</span></span>  <span data-ttu-id="5b9db-146">Puede elegir llamar a planeación de Microsoft o enrutamiento directo para conectarse a los servicios de telefonía para los equipos.</span><span class="sxs-lookup"><span data-stu-id="5b9db-146">You can choose either Microsoft Calling Plan or Direct Routing to connect the telephony services to Teams.</span></span>  

    -  <span data-ttu-id="5b9db-147">Llamar a planeación de Microsoft proporciona una solución de voz totalmente la en nube.</span><span class="sxs-lookup"><span data-stu-id="5b9db-147">Microsoft Calling Plan provides an all-in-the-cloud voice solution.</span></span> <span data-ttu-id="5b9db-148">Para obtener más información acerca de una llamada a planeación de Microsoft, consulte (vínculo próximamente).</span><span class="sxs-lookup"><span data-stu-id="5b9db-148">For more information about Microsoft Calling Plan, see (link coming soon).</span></span> 
    -  <span data-ttu-id="5b9db-149">Enrutamiento directo le permite usar prácticamente cualquier tronco RTC y se puede configurar la interoperabilidad entre equipos de telefonía que pertenecen al cliente y el sistema de teléfono de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b9db-149">Direct Routing lets you use virtually any PSTN trunk,  and you can configure interoperability between customer-owned telephony equipment and Microsoft Phone System.</span></span>  <span data-ttu-id="5b9db-150">Para obtener más información, vea [Planear el enrutamiento directo](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) y [Configurar el enrutamiento directo](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="5b9db-150">For more information, see [Plan Direct Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) and [Configure Direct Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).</span></span>

-  <span data-ttu-id="5b9db-151">**Migrar los usuarios sin funciones de telefonía.**</span><span class="sxs-lookup"><span data-stu-id="5b9db-151">**Migrate users without telephony capabilities.**</span></span> <span data-ttu-id="5b9db-152">Si migra a los usuarios sin mantener funciones de telefonía, asegúrese de que los usuarios tienen licencias adecuadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="5b9db-152">If you migrate users without preserving  telephony capabilities, make sure users have appropriate licenses in the cloud.</span></span> 

## <a name="assign-a-teams-upgrade-policy"></a><span data-ttu-id="5b9db-153">Asignar una directiva de actualización de los equipos</span><span class="sxs-lookup"><span data-stu-id="5b9db-153">Assign a Teams Upgrade policy</span></span>  
<span data-ttu-id="5b9db-154">Puede usar herramientas en línea para administrar las directivas de usuario, por ejemplo, para controlar el enrutamiento de los mensajes entrantes y las llamadas.</span><span class="sxs-lookup"><span data-stu-id="5b9db-154">You can use online tools to manage user policies, such as to control routing of incoming messages and calls.</span></span> <span data-ttu-id="5b9db-155">Para obtener más información, vea (vínculo próximamente).</span><span class="sxs-lookup"><span data-stu-id="5b9db-155">For more information, see (link coming soon).</span></span>

## <a name="move-on-premises-users-to-teams"></a><span data-ttu-id="5b9db-156">Mover usuarios locales a los equipos</span><span class="sxs-lookup"><span data-stu-id="5b9db-156">Move on-premises users to Teams</span></span>

<span data-ttu-id="5b9db-157">Puede mover los usuarios locales a los equipos mediante el uso de los cmdlets de PowerShell o mediante el Skype para el Panel de Control de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b9db-157">You can move your on-premises users to Teams by using PowerShell cmdlets or by using the Skype for Business Server 2019 Control Panel.</span></span>

### <a name="move-users-by-using-powershell"></a><span data-ttu-id="5b9db-158">Mover usuarios mediante el uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b9db-158">Move users by using PowerShell</span></span>
<span data-ttu-id="5b9db-159">Para mover los usuarios a los equipos mediante el uso de PowerShell, debe usar el cmdlet Move-CsUser con el parámetro moveToTeams como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="5b9db-159">To move your users to Teams by using PowerShell, you’ll use the Move-CsUser cmdlet with the moveToTeams parameter as follows:</span></span>

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

<span data-ttu-id="5b9db-160">($cred = get-credenciales.</span><span class="sxs-lookup"><span data-stu-id="5b9db-160">($cred = get-Credentials.</span></span> <span data-ttu-id="5b9db-161">Debe proporcionar credenciales de administrador de Office 365.)</span><span class="sxs-lookup"><span data-stu-id="5b9db-161">You must provide Office 365 admin credentials.)</span></span>

> [!NOTE]
> <span data-ttu-id="5b9db-162">Este comando establece la TeamsInteropPolicy a los equipos y la TeamsUpgradePolicy al modo de TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="5b9db-162">This command sets the TeamsInteropPolicy to Teams and sets the TeamsUpgradePolicy to TeamsOnly mode.</span></span> 
 
<span data-ttu-id="5b9db-163">Una vez realizada correctamente la mover a los equipos, Skype del usuario para Business client mostrará el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b9db-163">After the move to Teams is successful, the user’s Skype for Business client will display the following message:</span></span> 

![Se ha completado correctamente la migración a los mensajes de los equipos](../media/teams-upgrade-complete-message.png)

<span data-ttu-id="5b9db-165">Tenga en cuenta que Skype para la empresa ya no estará disponible para el usuario excepto al unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="5b9db-165">Note that Skype for Business will no longer be available to the user except to join a meeting.</span></span> 

<span data-ttu-id="5b9db-166">En algunos casos poco frecuentes, al mover los usuarios a los equipos, es posible que desee invalidar la conferencia de acceso telefónico y la funcionalidad de voz en nube.</span><span class="sxs-lookup"><span data-stu-id="5b9db-166">In rare cases, when moving your users to Teams, you might want to override dial-in conferencing and cloud voice functionality.</span></span> <span data-ttu-id="5b9db-167">Puede hacerlo mediante el uso de los siguientes parámetros con el comando Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="5b9db-167">You can do this by using the following parameters with the Move-CsUser command:</span></span>
- <span data-ttu-id="5b9db-168">**BypassAudioConferencingCheck:** Si un usuario tiene telefónico habilitado para local, el usuario también debe tener una licencia de AudioConf asignada en Office 365 antes de migrar.</span><span class="sxs-lookup"><span data-stu-id="5b9db-168">**BypassAudioConferencingCheck:** If a user has dial-in conferencing enabled for on-premises, the user must also have an AudioConf license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="5b9db-169">Una vez que se migran a la nube, el usuario se aprovisionará para conferencias de audio en la nube.</span><span class="sxs-lookup"><span data-stu-id="5b9db-169">Once migrated to the cloud, the user will be provisioned for audio conferencing in the cloud.</span></span> <span data-ttu-id="5b9db-170">Si, por alguna razón, desea mover a un usuario a la nube, pero no use la funcionalidad de conferencia de audio, se puede invalidar mediante la especificación de este parámetro.</span><span class="sxs-lookup"><span data-stu-id="5b9db-170">If, for some reason, you want to move a user to the cloud, but not use the audio conferencing functionality, you can override it by specifying this parameter.</span></span>
- <span data-ttu-id="5b9db-171">**ByPassEnterpriseVoice:** Si un usuario tiene Enterprise Voice habilitado para local, el usuario debe tener una licencia de Enterprise Voice asignada en Office 365 antes de migrar.</span><span class="sxs-lookup"><span data-stu-id="5b9db-171">**ByPassEnterpriseVoice:** If a user has Enterprise Voice enabled for on-premises, the user must have an Enterprise Voice license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="5b9db-172">Después de la migración a la nube, el usuario se aprovisionará para voz en la nube.</span><span class="sxs-lookup"><span data-stu-id="5b9db-172">After migration to the cloud, the user will be provisioned for voice in the cloud.</span></span> <span data-ttu-id="5b9db-173">Si, por alguna razón, desea mover a un usuario a la nube, pero no usar la funcionalidad de voz de la nube, se puede invalidar la voz de la nube mediante la especificación de este parámetro.</span><span class="sxs-lookup"><span data-stu-id="5b9db-173">If, for some reason, you want to move a user to the cloud but not use cloud voice functionality, you can override cloud voice by specifying this parameter.</span></span>
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="5b9db-174">Mover usuarios mediante el Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="5b9db-174">Move users by using the Skype for Business Server Control Panel</span></span> 

<span data-ttu-id="5b9db-175">Para mover los usuarios a los equipos mediante el Skype para el Panel de Control:</span><span class="sxs-lookup"><span data-stu-id="5b9db-175">To move users to Teams by using the Skype for Business Control Panel:</span></span>

1. <span data-ttu-id="5b9db-176">Abra el Skype para el Panel de Control e inicie sesión su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b9db-176">Open the Skype for Business Control Panel and sign in to your Office 365 account.</span></span>

2. <span data-ttu-id="5b9db-177">Seleccione **los usuarios** en el panel de navegación izquierdo y seleccione los usuarios a migrar.</span><span class="sxs-lookup"><span data-stu-id="5b9db-177">Select **Users** in the left navigation, and select the users to migrate.</span></span> 
     
3. <span data-ttu-id="5b9db-178">En el menú **acción** , elija **mover usuarios seleccionados a los equipos**.</span><span class="sxs-lookup"><span data-stu-id="5b9db-178">On the **Action** menu, choose **Move selected users to Teams**.</span></span> 

    ![Al hacer clic en siguiente para confirmar la migración](../media/migration-confirmation.png)
    
4. <span data-ttu-id="5b9db-180">Haga clic en **siguiente** para confirmar la migración.</span><span class="sxs-lookup"><span data-stu-id="5b9db-180">Click **Next** to confirm your migration.</span></span> 

<span data-ttu-id="5b9db-181">Después de que el usuario se mueva a los equipos, verá las confirmaciones similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b9db-181">After the user is moved to Teams, you will see  confirmations like the following:</span></span>

<span data-ttu-id="5b9db-182">![Mover la confirmación de los usuarios](../media/move-user-confirmation.png)
</span><span class="sxs-lookup"><span data-stu-id="5b9db-182">![Move users confirmation](../media/move-user-confirmation.png)
</span></span><br/><br/>
<span data-ttu-id="5b9db-183">![Mensaje que se han movido a los usuarios](../media/users-moved-successfully.png)</span><span class="sxs-lookup"><span data-stu-id="5b9db-183">![Message that users have been moved](../media/users-moved-successfully.png)</span></span>

<span data-ttu-id="5b9db-184">Si el movimiento no se realizó correctamente, verá un mensaje similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b9db-184">If the move was not successful, you will see a message like the following:</span></span>

![Mensajes que no se pudo mover el usuario](../media/users-not-moved.png)
