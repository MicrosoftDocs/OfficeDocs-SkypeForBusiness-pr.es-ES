---
title: Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz de Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Aprenda a habilitar el sistema telefónico en los servicios de voz de Office 365 para los usuarios de Skype empresarial.
ms.openlocfilehash: 902d2e1bad76c8275bfc8f4ce7ec7b4243b8572a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003470"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="c6c2b-103">Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz de Office 365</span><span class="sxs-lookup"><span data-stu-id="c6c2b-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="c6c2b-104">Aprenda a habilitar el sistema telefónico en los servicios de voz de Office 365 para los usuarios de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="c6c2b-105">El paso final de la implementación del sistema telefónico en Office 365 con la conectividad RTC local es habilitar a los usuarios para el sistema telefónico en Office 365 y el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="c6c2b-106">Para habilitar estas funciones, tiene que ser un usuario con el rol de administrador global de Office 365 y ser capaz de ejecutar PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="c6c2b-107">Solo tiene que seguir los pasos que se indican en este tema para las cuentas de usuario que no tengan habilitada la telefonía IP empresarial para Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="c6c2b-108">Habilitar el sistema telefónico en los servicios de voz de Office 365</span><span class="sxs-lookup"><span data-stu-id="c6c2b-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="c6c2b-109">Para habilitar un usuario para el sistema telefónico en Office 365 Voice y el buzón de voz, tendrá que realizar algunos pasos iniciales, como comprobar si el conector de Skype empresarial online está implementado en los servidores y habilitar a los usuarios para el buzón de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="c6c2b-110">Para habilitar a los usuarios para el sistema telefónico en Office 365 voz y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="c6c2b-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="c6c2b-111">Antes de empezar, compruebe que el conector de Skype empresarial online (módulo Windows PowerShell) está implementado en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="c6c2b-112">Si no lo está, puede descargarlo desde [el centro de descarga](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="c6c2b-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="c6c2b-113">Puede encontrar más información sobre cómo usar este módulo en [configuración del equipo para la administración de Skype empresarial online](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c6c2b-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="c6c2b-114">Inicie Windows PowerShell como un administrador.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="c6c2b-115">Escriba lo siguiente y presione Entrar:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-115">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="c6c2b-116">Escriba lo siguiente y presione Entrar:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-116">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="c6c2b-117">Después de presionar ENTRAR, verá el cuadro de diálogo Credenciales de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="c6c2b-118">Escriba el nombre de usuario y la contraseña del administrador del inquilino y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="c6c2b-119">En la ventana de la PowerShell, escriba lo siguiente y presione Entrar:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="c6c2b-120">Escriba el siguiente cmdlet para importar la sesión:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-120">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="c6c2b-121">Al ejecutar PowerShell en un servidor de Skype empresarial, los cmdlets de Skype empresarial locales ya se cargan al abrir PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="c6c2b-122">Debe especificar el parámetro-AllowClobber para permitir que los cmdlets en línea sobrescriban los cmdlets locales con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="c6c2b-123">Use el cmdlet Set-CsUser para asignar las propiedades $EnterpriseVoiceEnabled y $HostedVoiceMail a su usuario del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="c6c2b-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-124">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="c6c2b-125">También puede especificar un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombre de usuario), y nombre para mostrar en Active Directory ("Guillermo Rodarte").</span><span class="sxs-lookup"><span data-stu-id="c6c2b-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="c6c2b-126">Actualice el URI de línea y el plan de marcado de los usuarios habilitados para el sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="c6c2b-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="c6c2b-127">En esta sección se describe cómo actualizar el URI de línea y el plan de marcado para los usuarios habilitados para el sistema telefónico en Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="c6c2b-128">Para actualizar el URI de línea</span><span class="sxs-lookup"><span data-stu-id="c6c2b-128">To update the Line URI</span></span>

1. <span data-ttu-id="c6c2b-129">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c6c2b-130">Use el menú Inicio o un acceso directo en el escritorio para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c6c2b-131">También puede abrir una ventana del explorador y, después, escribir la URL del administrador para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="c6c2b-132">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c6c2b-133">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="c6c2b-134">En la tabla, haga clic en la cuenta de usuario de Skype Empresarial cuyo URI de línea quiera cambiar.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="c6c2b-p104">Haga clic en **URI de línea** y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). Después, haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-p104">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="c6c2b-137">Actualizar el plan de marcado con cmdlets locales de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6c2b-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c6c2b-138">Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c6c2b-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="c6c2b-139">Puede ejecutar este cmdlet desde Skype empresarial Server 2015 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="c6c2b-140">Para asignar un plan de marcado por usuario a un único usuario</span><span class="sxs-lookup"><span data-stu-id="c6c2b-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="c6c2b-141">Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para asignar el plan de marcado por usuario RedmondDialPlan al usuario Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="c6c2b-142">Para asignar un plan de marcado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="c6c2b-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="c6c2b-143">El siguiente comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajen en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="c6c2b-144">Para obtener más información sobre el parámetro LdapFilter que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c6c2b-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="c6c2b-p107">Puede utilizar planes de marcado globales o por usuario para los usuarios en línea. Los planes de marcado de sitio no se pueden usar ya que solo se aplican a los usuarios hospedados en una implementación local y se asignan a un sitio local.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-p107">You may use either Global or User dial plans for online users. Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="c6c2b-147">Para quitar la asignación de un plan de marcado por usuario</span><span class="sxs-lookup"><span data-stu-id="c6c2b-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="c6c2b-148">Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para cancelar la asignación de cualquier plan de marcado por usuario previamente asignado a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="c6c2b-149">Una vez que se ha cancelado la asignación del plan de marcado por usuario, el usuario Ken Myer se administrará automáticamente mediante el plan de marcado global o el plan de marcado de ámbito de servicio asignado a su registrador o a su puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="c6c2b-150">Los planes de marcado de ámbito de servicio tienen prioridad sobre el plan de marcado global:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="c6c2b-151">Actualizar las directivas de enrutamiento de voz con cmdlets locales de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6c2b-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c6c2b-152">En esta sección se describe cómo actualizar las directivas de enrutamiento de voz para los usuarios habilitados para el sistema telefónico en Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="c6c2b-153">Sistema telefónico en Office 365 los usuarios deben tener asignada una directiva de enrutamiento de voz para que las llamadas se enruten correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="c6c2b-154">Esto difiere de los usuarios de telefonía empresarial local que deben tener una directiva de voz asignada para permitir que las llamadas se enruten correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="c6c2b-155">La Directiva de enrutamiento de voz debe contener usos de RTC que definan las llamadas y rutas autorizadas para el sistema telefónico en los usuarios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="c6c2b-156">Puede copiar estos usos de RTC de las directivas de voz existentes a las nuevas directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="c6c2b-157">Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c6c2b-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6c2b-158">A todos los sistemas telefónicos de los usuarios de Office 365 se les asigna la misma directiva de voz en línea denominada BusinessVoice que define las características de llamadas permitidas. por ejemplo, permitir llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="c6c2b-159">Para asignar una directiva de enrutamiento de voz por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="c6c2b-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="c6c2b-160">Use el cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para asignar la Directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy al usuario Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="c6c2b-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="c6c2b-161">Para asignar una directiva de enrutamiento de voz por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="c6c2b-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="c6c2b-162">El siguiente comando permite asignar la directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="c6c2b-163">Para obtener más información sobre el parámetro LdapFilter que se usa en este comando, vea [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c6c2b-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="c6c2b-p111">Puede utilizar directivas de enrutamiento de voz globales o por usuario para usuarios en línea. Las directivas de enrutamiento de voz de sitio no se pueden usar, ya que solo se aplican a los usuarios hospedados en una implementación local y se asignan a un sitio local.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-p111">You may use either Global or User voice routing policies for online users. Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="c6c2b-166">Para desasignar una directiva de enrutamiento de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="c6c2b-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="c6c2b-167">Use la función Grant-CsVoiceRoutingPolicy para cancelar la asignación de cualquier directiva de enrutamiento de voz por usuario asignada previamente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="c6c2b-168">Después de cancelar la asignación de la directiva de enrutamiento de voz por usuario, el usuario Ken Myer se administrará automáticamente mediante la directiva de enrutamiento de voz global.</span><span class="sxs-lookup"><span data-stu-id="c6c2b-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="c6c2b-169">Para obtener más información, vea [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c6c2b-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

