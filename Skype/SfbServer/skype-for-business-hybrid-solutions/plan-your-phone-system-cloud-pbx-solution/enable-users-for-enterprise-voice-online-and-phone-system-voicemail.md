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
description: Obtenga información sobre cómo habilitar los servicios de voz del sistema telefónico para sus usuarios de Skype empresarial.
ms.openlocfilehash: ed5e571976a032facc70b2e602d4b0ea7fd01afc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359186"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="8acd4-103">Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz</span><span class="sxs-lookup"><span data-stu-id="8acd4-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="8acd4-104">Skype empresarial online se retirará el 31 de julio de 2021 después del cual el servicio ya no será accesible.</span><span class="sxs-lookup"><span data-stu-id="8acd4-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="8acd4-105">Además, la conectividad con RTC entre su entorno local, ya sea a través de Skype empresarial Server o Cloud Connector Edition y Skype empresarial online, ya no será compatible.</span><span class="sxs-lookup"><span data-stu-id="8acd4-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="8acd4-106">Obtenga información sobre cómo conectar su red de telefonía local a Microsoft Teams con [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="8acd4-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="8acd4-107">Obtenga información sobre cómo habilitar los servicios de voz del sistema telefónico para sus usuarios de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="8acd4-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="8acd4-108">El último paso de la implementación del sistema telefónico con la conectividad RTC local es habilitar a los usuarios para el sistema telefónico y el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="8acd4-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="8acd4-109">Para habilitar estas funciones, debe ser un usuario con el rol de administrador global y poder ejecutar PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="8acd4-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="8acd4-110">Debe seguir los pasos de este tema para todas las cuentas de usuario que todavía no tienen habilitada la telefonía IP empresarial para Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="8acd4-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="8acd4-111">Habilitar los servicios de voz del sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="8acd4-111">Enable Phone System voice services</span></span>

<span data-ttu-id="8acd4-112">Para habilitar a un usuario para la voz y el correo de voz del sistema telefónico, deberá realizar algunos pasos iniciales, como comprobar si el conector de Skype empresarial online se ha implementado en los servidores y habilitar a los usuarios para el correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="8acd4-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="8acd4-113">Para habilitar a los usuarios para la voz y el correo de voz del sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="8acd4-113">To enable your users for Phone System voice and voicemail</span></span>

1. <span data-ttu-id="8acd4-114">Antes de empezar, compruebe que el conector de Skype empresarial online (módulo Windows PowerShell) esté implementado en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8acd4-114">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="8acd4-115">Si no lo está, puede descargarlo desde [el centro de descarga](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="8acd4-115">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="8acd4-116">Puede encontrar más información sobre el uso de este módulo en [configurar el equipo para la administración de Skype empresarial online](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8acd4-116">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="8acd4-117">Inicie Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="8acd4-117">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="8acd4-118">Escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8acd4-118">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="8acd4-119">Escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8acd4-119">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="8acd4-120">Después de presionar entrar, verá el cuadro de diálogo credenciales de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8acd4-120">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="8acd4-121">Escriba su nombre de usuario y contraseña de administrador de inquilinos y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8acd4-121">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="8acd4-122">En la ventana de PowerShell, escriba lo siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="8acd4-122">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="8acd4-123">Para importar la sesión, escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8acd4-123">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="8acd4-124">Al ejecutar PowerShell en un servidor de Skype empresarial, los cmdlets de Skype empresarial local ya están cargados cuando abre PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8acd4-124">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="8acd4-125">Debe especificar el parámetro-AllowClobber para permitir que los cmdlets en línea sobrescriban los cmdlets locales con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="8acd4-125">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="8acd4-126">Use el cmdlet Set-CsUser para asignar las propiedades $EnterpriseVoiceEnabled y $HostedVoiceMail a su usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8acd4-126">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="8acd4-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8acd4-127">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="8acd4-128">También puede especificar un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombre de usuario), y nombre para mostrar en Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="8acd4-128">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="8acd4-129">Actualizar el URI de línea y el plan de marcado para los usuarios habilitados para el sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="8acd4-129">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="8acd4-130">En esta sección se describe cómo actualizar el URI de línea y el plan de marcado para los usuarios habilitados para sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="8acd4-130">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="8acd4-131">Para actualizar el URI de línea</span><span class="sxs-lookup"><span data-stu-id="8acd4-131">To update the Line URI</span></span>

1. <span data-ttu-id="8acd4-132">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8acd4-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8acd4-133">Use el menú Inicio o el acceso directo del escritorio para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8acd4-133">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8acd4-134">También puede abrir una ventana del explorador y, a continuación, escribir la URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8acd4-134">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="8acd4-135">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8acd4-135">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="8acd4-136">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8acd4-136">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="8acd4-137">En la tabla, haga clic en la cuenta de usuario de Skype empresarial cuyo URI de línea desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="8acd4-137">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="8acd4-138">Haga clic en **URI de línea**y escriba un número de teléfono único y normalizado (por ejemplo, Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="8acd4-138">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="8acd4-139">A continuación, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8acd4-139">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="8acd4-140">Actualizar el plan de marcado con cmdlets locales de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8acd4-140">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8acd4-141">Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8acd4-141">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="8acd4-142">Puede ejecutar este cmdlet desde Skype empresarial Server 2015 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8acd4-142">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="8acd4-143">Para asignar un plan de marcado por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="8acd4-143">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="8acd4-144">Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para asignar el plan de marcado por usuario RedmondDialPlan al usuario Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="8acd4-144">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="8acd4-145">Para asignar un plan de marcado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="8acd4-145">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="8acd4-146">El comando siguiente asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="8acd4-146">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="8acd4-147">Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="8acd4-147">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="8acd4-148">Puede usar planes de marcado globales o de usuario para usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="8acd4-148">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="8acd4-149">Los planes de marcado de sitio no se pueden usar porque solo se aplican a los usuarios que están hospedados de forma local y que están asignados a un sitio local.</span><span class="sxs-lookup"><span data-stu-id="8acd4-149">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="8acd4-150">Para cancelar la asignación de un plan de marcado por usuario</span><span class="sxs-lookup"><span data-stu-id="8acd4-150">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="8acd4-151">Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para desasignar cualquier plan de marcado por usuario asignado previamente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8acd4-151">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="8acd4-152">Una vez sin asignar el plan de marcado por usuario, Ken Myer se administrará automáticamente mediante el plan de marcado global o el plan de marcado de ámbito de servicio asignado a su registrador o puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="8acd4-152">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="8acd4-153">Un plan de marcado de ámbito de servicio tiene prioridad sobre el plan de marcado global:</span><span class="sxs-lookup"><span data-stu-id="8acd4-153">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="8acd4-154">Actualizar las directivas de enrutamiento de voz mediante los cmdlets locales de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8acd4-154">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8acd4-155">En esta sección se describe cómo actualizar las directivas de enrutamiento de voz para los usuarios habilitados para sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="8acd4-155">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="8acd4-156">Los usuarios del sistema telefónico deben tener asignada una directiva de enrutamiento de voz para que las llamadas se enruten correctamente.</span><span class="sxs-lookup"><span data-stu-id="8acd4-156">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="8acd4-157">Esto difiere de los usuarios de voz de empresa locales que requieren que se les asigne una directiva de voz para permitir que las llamadas se enruten correctamente.</span><span class="sxs-lookup"><span data-stu-id="8acd4-157">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="8acd4-158">La Directiva de enrutamiento de voz debe contener usos de RTC que definen las llamadas y rutas autorizadas para los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="8acd4-158">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="8acd4-159">Puede copiar estos usos de RTC de las directivas de voz existentes a las nuevas directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="8acd4-159">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="8acd4-160">Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8acd4-160">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8acd4-161">A todos los usuarios del sistema telefónico se les asigna la misma directiva de voz en línea llamada Businessvoice, que define las características de llamada permitidas; por ejemplo, permitir llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="8acd4-161">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="8acd4-162">Para asignar una directiva de enrutamiento de voz por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="8acd4-162">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="8acd4-163">Use el cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para asignar la Directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy al usuario Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="8acd4-163">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="8acd4-164">Para asignar una directiva de enrutamiento de voz por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="8acd4-164">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="8acd4-165">El comando siguiente asigna la Directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="8acd4-165">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="8acd4-166">Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8acd4-166">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="8acd4-167">Puede usar directivas de enrutamiento de voz globales o de usuario para los usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="8acd4-167">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="8acd4-168">No se pueden usar las directivas de enrutamiento de voz del sitio, ya que solo se aplican a los usuarios hospedados de forma local y que están asignados a un sitio local.</span><span class="sxs-lookup"><span data-stu-id="8acd4-168">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="8acd4-169">Para quitar la asignación de una directiva de enrutamiento de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="8acd4-169">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="8acd4-170">Use Grant-CsVoiceRoutingPolicy para desasignar cualquier directiva de enrutamiento de voz por usuario asignada previamente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8acd4-170">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="8acd4-171">Una vez no asignada la Directiva de enrutamiento de voz por usuario, Ken Myer se administrará automáticamente mediante la Directiva de enrutamiento de voz global.</span><span class="sxs-lookup"><span data-stu-id="8acd4-171">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="8acd4-172">Para obtener más información, consulte [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8acd4-172">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

