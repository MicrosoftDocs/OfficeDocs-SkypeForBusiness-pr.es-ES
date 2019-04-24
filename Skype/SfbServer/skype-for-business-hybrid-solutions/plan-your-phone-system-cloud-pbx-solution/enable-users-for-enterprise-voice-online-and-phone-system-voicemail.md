---
title: Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz de Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
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
description: Obtenga información sobre cómo habilitar sistema telefónico en servicios de voz de Office 365 para su Skype para los usuarios empresariales.
ms.openlocfilehash: f7ba1c4e259d68ab423ec2bde8aee3604035d125
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234257"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="7b9c3-103">Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz de Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9c3-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="7b9c3-104">Obtenga información sobre cómo habilitar sistema telefónico en servicios de voz de Office 365 para su Skype para los usuarios empresariales.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="7b9c3-105">El último paso de implementación del sistema de teléfono en Office 365 con conectividad de RTC local es permitir a los usuarios para el sistema telefónico en Office 365 y correo de voz.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="7b9c3-106">Para habilitar estas funciones, tiene que ser un usuario con el rol de administrador global de Office 365 y ser capaz de ejecutar PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="7b9c3-107">Solo tiene que seguir los pasos que se indican en este tema para las cuentas de usuario que no tengan habilitada la telefonía IP empresarial para Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="7b9c3-108">Habilitar sistema telefónico en servicios de voz de Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9c3-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="7b9c3-109">Para habilitar a un usuario para el sistema telefónico en Office 365 voz y correo de voz, debe realizar algunos pasos iniciales, como la comprobación para ver si el Skype para Business Connector en línea se implementa en los servidores y permitir que los usuarios de correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="7b9c3-110">Para habilitar a los usuarios para el sistema telefónico en correo de voz y voz de Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9c3-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="7b9c3-111">Antes de comenzar, compruebe que la Skype para Business Connector en línea (módulo de Windows PowerShell) se implementa en los servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="7b9c3-112">Si no es así, se puede descargar desde [el centro de descarga](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="7b9c3-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="7b9c3-113">Puede encontrar más información acerca del uso de este módulo a la [configuración de su equipo para Skype para administración en línea de negocio](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b9c3-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="7b9c3-114">Inicie Windows PowerShell como un administrador.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="7b9c3-115">Escriba lo siguiente y presione Entrar:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-115">Type the following and press Enter:</span></span>
    
   ```
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="7b9c3-116">Escriba lo siguiente y presione Entrar:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-116">Type the following and press Enter:</span></span>
    
   ```
   $cred = Get-Credential
   ```

    <span data-ttu-id="7b9c3-117">Después de presionar ENTRAR, verá el cuadro de diálogo Credenciales de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="7b9c3-118">Escriba el nombre de usuario y la contraseña del administrador del inquilino y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="7b9c3-119">En la ventana de la PowerShell, escriba lo siguiente y presione Entrar:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="7b9c3-120">Escriba el siguiente cmdlet para importar la sesión:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-120">Import the session by typing the following cmdlet:</span></span>
    
   ```
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="7b9c3-121">Al ejecutar PowerShell en un Skype para Business Server, el local Skype para cmdlets empresarial ya están cargados cuando abra PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="7b9c3-122">Debe especificar el parámetro - AllowClobber para permitir que los cmdlets en línea sobrescribir los cmdlets local con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="7b9c3-123">Use el cmdlet Set-CsUser para asignar las propiedades $EnterpriseVoiceEnabled y $HostedVoiceMail a su usuario del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="7b9c3-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-124">For example:</span></span>
    
   ```
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="7b9c3-125">También puede especificar un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombre de usuario), y nombre para mostrar en Active Directory ("Guillermo Rodarte").</span><span class="sxs-lookup"><span data-stu-id="7b9c3-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="7b9c3-126">Actualizar el URI de línea y de marcado de plan para los usuarios habilitados para el sistema telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9c3-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="7b9c3-127">En esta sección se describe cómo actualizar el URI de línea y plan para los usuarios habilitados para el sistema telefónico en Office 365 de marcado.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="7b9c3-128">Para actualizar el URI de línea</span><span class="sxs-lookup"><span data-stu-id="7b9c3-128">To update the Line URI</span></span>

1. <span data-ttu-id="7b9c3-129">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7b9c3-130">Use el menú Inicio o un acceso directo en el escritorio para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7b9c3-131">También puede abrir una ventana del explorador y, después, escribir la URL del administrador para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="7b9c3-132">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7b9c3-133">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="7b9c3-134">En la tabla, haga clic en la cuenta de usuario de Skype Empresarial cuyo URI de línea quiera cambiar.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="7b9c3-p104">Haga clic en **URI de línea** y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). Después, haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-p104">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="7b9c3-137">Actualizar el plan de marcado con cmdlets locales de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b9c3-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7b9c3-138">Puede asignar por usuario en los planes de marcado con Windows PowerShell y el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7b9c3-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="7b9c3-139">Se puede ejecutar este cmdlet, ya sea desde el Skype para Business Server 2015 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="7b9c3-140">Para asignar un plan de marcado por usuario a un único usuario</span><span class="sxs-lookup"><span data-stu-id="7b9c3-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="7b9c3-141">Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para asignar el plan de marcado por usuario RedmondDialPlan al usuario Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="7b9c3-142">Para asignar un plan de marcado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="7b9c3-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="7b9c3-143">El siguiente comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajen en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="7b9c3-144">Para obtener más información en el parámetro LdapFilter que se usa en este comando, consulte la documentación para el cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="7b9c3-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="7b9c3-p107">Puede utilizar planes de marcado globales o por usuario para los usuarios en línea. Los planes de marcado de sitio no se pueden usar ya que solo se aplican a los usuarios hospedados en una implementación local y se asignan a un sitio local.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-p107">You may use either Global or User dial plans for online users. Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="7b9c3-147">Para quitar la asignación de un plan de marcado por usuario</span><span class="sxs-lookup"><span data-stu-id="7b9c3-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="7b9c3-148">Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para cancelar la asignación de cualquier plan de marcado por usuario previamente asignada a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="7b9c3-149">Una vez que se ha cancelado la asignación del plan de marcado por usuario, el usuario Ken Myer se administrará automáticamente mediante el plan de marcado global o el plan de marcado de ámbito de servicio asignado a su registrador o a su puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="7b9c3-150">Los planes de marcado de ámbito de servicio tienen prioridad sobre el plan de marcado global:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="7b9c3-151">Actualizar las directivas de enrutamiento de voz con cmdlets locales de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b9c3-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7b9c3-152">En esta sección se describe cómo actualizar las directivas de enrutamiento de voz para los usuarios habilitados para el sistema telefónico en Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="7b9c3-153">Sistema telefónico en Office 365 a los usuarios debe tener una directiva de enrutamiento de voz asignada a ellos para las llamadas enrutar correctamente.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="7b9c3-154">Esto difiere de los usuarios de telefonía empresarial local que deben tener una directiva de voz asignada para permitir que las llamadas se enruten correctamente.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="7b9c3-155">La directiva de enrutamiento de voz debe contener los usos de RTC que definen llamadas autorizadas y rutas para el sistema telefónico en usuarios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="7b9c3-156">Puede copiar estos usos de RTC de las directivas de voz existentes a las nuevas directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="7b9c3-157">Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7b9c3-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b9c3-158">Todos los sistema telefónico en Office 365 a los usuarios se asignan a la misma directiva de voz en línea denominado BusinessVoice que define las características de llamada permitidas; Por ejemplo, permitir que la llamada simultánea.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="7b9c3-159">Para asignar una directiva de enrutamiento de voz por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="7b9c3-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="7b9c3-160">Use el cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para asignar la directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy al usuario Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="7b9c3-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="7b9c3-161">Para asignar una directiva de enrutamiento de voz por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="7b9c3-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="7b9c3-162">El siguiente comando permite asignar la directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="7b9c3-163">Para obtener más información sobre el parámetro LdapFilter que se usa en este comando, vea [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7b9c3-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="7b9c3-p111">Puede utilizar directivas de enrutamiento de voz globales o por usuario para usuarios en línea. Las directivas de enrutamiento de voz de sitio no se pueden usar, ya que solo se aplican a los usuarios hospedados en una implementación local y se asignan a un sitio local.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-p111">You may use either Global or User voice routing policies for online users. Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="7b9c3-166">Para desasignar una directiva de enrutamiento de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="7b9c3-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="7b9c3-167">Use el Grant-CsVoiceRoutingPolicy para cancelar la asignación de cualquier directiva de enrutamiento de voz por usuario previamente asignada a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="7b9c3-168">Después de cancelar la asignación de la directiva de enrutamiento de voz por usuario, el usuario Ken Myer se administrará automáticamente mediante la directiva de enrutamiento de voz global.</span><span class="sxs-lookup"><span data-stu-id="7b9c3-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="7b9c3-169">Para obtener más información, vea [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7b9c3-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

