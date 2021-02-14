---
title: Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Obtenga información sobre cómo habilitar los servicios de voz del Sistema telefónico para los usuarios de Skype Empresarial.
ms.openlocfilehash: 76fbc20b11c0ec91685479d768b88abf71b65d21
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625116"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="bd8c4-103">Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz</span><span class="sxs-lookup"><span data-stu-id="bd8c4-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="bd8c4-104">Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual el servicio ya no será accesible.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="bd8c4-105">Además, ya no se admite la conectividad rtc entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="bd8c4-106">Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="bd8c4-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="bd8c4-107">Obtenga información sobre cómo habilitar los servicios de voz del Sistema telefónico para los usuarios de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="bd8c4-108">El último paso para implementar el sistema telefónico con conectividad RTC local es habilitar a los usuarios para el sistema telefónico y el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="bd8c4-109">Para habilitar estas funcionalidades, debe ser un usuario con el rol de administrador global y poder ejecutar PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="bd8c4-110">Debe seguir los pasos de este tema para todas las cuentas de usuario que aún no Telefonía IP empresarial habilitadas para Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="bd8c4-111">Habilitar los servicios de voz del sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bd8c4-111">Enable Phone System voice services</span></span>

<span data-ttu-id="bd8c4-112">Para habilitar a un usuario para voz del sistema telefónico y correo de voz, deberá realizar algunos pasos iniciales, como comprobar si skype empresarial Online Connector está implementado en los servidores y habilitar a los usuarios para correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="bd8c4-113">Para habilitar a los usuarios para voz y correo de voz del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bd8c4-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="bd8c4-114">El conector de Skype Empresarial Online forma parte actualmente del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="bd8c4-115">Si usa la versión pública de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)de Teams más reciente, no necesita instalar el conector de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="bd8c4-116">Antes de empezar, compruebe que el módulo de PowerShell de Teams está instalado en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="bd8c4-117">Si no es así, instale con las instrucciones de instalación del módulo [de PowerShell de Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="bd8c4-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="bd8c4-118">Inicie Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="bd8c4-119">Escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-119">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. <span data-ttu-id="bd8c4-120">Escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-120">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="bd8c4-121">Después de presionar Entrar, debería ver el cuadro de diálogo Windows PowerShell credencial.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-121">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="bd8c4-122">Escriba el nombre de usuario y la contraseña del administrador de inquilinos y haga clic **en Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="bd8c4-122">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="bd8c4-123">En la ventana de PowerShell, escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-123">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="bd8c4-124">Para importar la sesión, escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-124">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="bd8c4-125">Al ejecutar PowerShell en un Skype Empresarial Server, los cmdlets locales de Skype Empresarial ya se cargan al abrir PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-125">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="bd8c4-126">Debe especificar el parámetro -AllowClobber para permitir que los cmdlets en línea sobrescriban los cmdlets locales con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-126">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="bd8c4-127">Use el cmdlet Set-CsUser para asignar las propiedades $EnterpriseVoiceEnabled y $HostedVoiceMail a su usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-127">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="bd8c4-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-128">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="bd8c4-129">También puede especificar un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio #A0) y nombre para mostrar en Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="bd8c4-129">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="bd8c4-130">Actualizar el URI de línea y el plan de marcado para los usuarios habilitados para el sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bd8c4-130">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="bd8c4-131">En esta sección se describe cómo actualizar el URI de línea y el plan de marcado para los usuarios habilitados para sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-131">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="bd8c4-132">Para actualizar el URI de línea</span><span class="sxs-lookup"><span data-stu-id="bd8c4-132">To update the Line URI</span></span>

1. <span data-ttu-id="bd8c4-133">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bd8c4-134">Use el menú Inicio o el acceso directo de escritorio para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-134">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd8c4-135">También puede abrir una ventana del explorador y, a continuación, escribir la dirección URL del administrador para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-135">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="bd8c4-136">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-136">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="bd8c4-137">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-137">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="bd8c4-138">En la tabla, haga clic en la cuenta de usuario de Skype Empresarial que desea cambiar el URI de línea.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-138">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="bd8c4-139">Haga **clic en URI** de línea y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="bd8c4-139">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="bd8c4-140">A continuación, haga clic **en Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-140">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="bd8c4-141">Actualizar el plan de marcado con cmdlets de Windows PowerShell locales</span><span class="sxs-lookup"><span data-stu-id="bd8c4-141">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="bd8c4-142">Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet [Grant-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bd8c4-142">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="bd8c4-143">Puede ejecutar este cmdlet desde Skype Empresarial Server 2015 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-143">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="bd8c4-144">Para asignar un plan de marcado por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="bd8c4-144">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="bd8c4-145">Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para asignar el plan de marcado por usuario RedmondDialPlan al usuario Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-145">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="bd8c4-146">Para asignar un plan de marcado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="bd8c4-146">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="bd8c4-147">El siguiente comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-147">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="bd8c4-148">Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser:](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bd8c4-148">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="bd8c4-149">Puede usar planes de marcado global o de usuario para usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-149">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="bd8c4-150">Los planes de marcado de sitio no se pueden usar, ya que solo se aplican a los usuarios hospedados localmente y que están asignados a un sitio local.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-150">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="bd8c4-151">Para desasignación de un plan de marcado por usuario</span><span class="sxs-lookup"><span data-stu-id="bd8c4-151">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="bd8c4-152">Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para desasignación de cualquier plan de marcado por usuario previamente asignado a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-152">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="bd8c4-153">Una vez que se haya desasignado el plan de marcado por usuario, Ken Myer se administrará automáticamente mediante el plan de marcado global o el plan de marcado de ámbito de servicio asignado a su registrador o puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-153">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="bd8c4-154">Un plan de marcado de ámbito de servicio tiene prioridad sobre el plan de marcado global:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-154">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="bd8c4-155">Actualizar las directivas de enrutamiento de voz con cmdlets de Windows PowerShell locales</span><span class="sxs-lookup"><span data-stu-id="bd8c4-155">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="bd8c4-156">En esta sección se describe cómo actualizar las directivas de enrutamiento de voz para los usuarios habilitados para sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-156">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="bd8c4-157">Los usuarios del sistema telefónico deben tener asignada una directiva de enrutamiento de voz para que las llamadas se enruten correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-157">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="bd8c4-158">Esto difiere de los usuarios locales de business voice que requieren que se les asigne una directiva de voz para permitir que las llamadas se enruten correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-158">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="bd8c4-159">La directiva de enrutamiento de voz debe contener usos de RTC que definan las llamadas y rutas autorizadas para los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-159">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="bd8c4-160">Puede copiar estos usos de RTC de las directivas de voz existentes a las nuevas directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-160">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="bd8c4-161">Para obtener más información, [vea New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bd8c4-161">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd8c4-162">A todos los usuarios del Sistema telefónico se les asigna la misma directiva de voz en línea denominada BusinessVoice que define las características de llamada permitidas; por ejemplo, Permitir llamada simultánea.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-162">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="bd8c4-163">Para asignar una directiva de enrutamiento de voz por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="bd8c4-163">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="bd8c4-164">Use el cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para asignar la directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy al usuario Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="bd8c4-164">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="bd8c4-165">Para asignar una directiva de enrutamiento de voz por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="bd8c4-165">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="bd8c4-166">El siguiente comando asigna la directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-166">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="bd8c4-167">Para obtener más información sobre el parámetro LdapFilter usado en este comando, vea [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bd8c4-167">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="bd8c4-168">Puede usar directivas de enrutamiento de voz global o de usuario para usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-168">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="bd8c4-169">Las directivas de enrutamiento de voz de sitio no se pueden usar, ya que solo se aplican a los usuarios hospedados localmente y que están asignados a un sitio local.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-169">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="bd8c4-170">Para desasignar una directiva de enrutamiento de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="bd8c4-170">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="bd8c4-171">Use el Grant-CsVoiceRoutingPolicy para desasignar cualquier directiva de enrutamiento de voz por usuario previamente asignada a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-171">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="bd8c4-172">Una vez desasignada la directiva de enrutamiento de voz por usuario, Ken Myer se administrará automáticamente mediante la directiva de enrutamiento de voz global.</span><span class="sxs-lookup"><span data-stu-id="bd8c4-172">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="bd8c4-173">Para obtener más información, [vea Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bd8c4-173">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

