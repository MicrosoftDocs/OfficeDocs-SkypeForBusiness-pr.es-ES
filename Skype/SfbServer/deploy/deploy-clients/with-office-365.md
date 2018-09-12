---
title: Implementar Sistemas de salas de Skype v2 con Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Office 365.
ms.openlocfilehash: 9140ea2f1d88b8d56ecfee1b41d7bf5c9b571dbb
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "23938018"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="80d66-103">Implementar Sistemas de salas de Skype v2 con Office 365 </span><span class="sxs-lookup"><span data-stu-id="80d66-103">Deploy Skype Room Systems v2 with Office 365</span></span>
 
<span data-ttu-id="80d66-104">Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Office 365, donde Skype para empresas y Exchange estén en línea.</span><span class="sxs-lookup"><span data-stu-id="80d66-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span> 

<span data-ttu-id="80d66-105">La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="80d66-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="80d66-106">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudarle a convertirlas en cuentas de usuario de v2 de Skype salón sistemas compatibles.</span><span class="sxs-lookup"><span data-stu-id="80d66-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="80d66-107">Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="80d66-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="80d66-108">Implementar Sistemas de salas de Skype v2 con Office 365 </span><span class="sxs-lookup"><span data-stu-id="80d66-108">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="80d66-109">Antes de implementar sistemas de salón de Skype v2 con Office 365, asegúrese de que cumplen los requisitos.</span><span class="sxs-lookup"><span data-stu-id="80d66-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="80d66-110">Para obtener más información, vea [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80d66-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="80d66-111">Para habilitar Skype para la empresa, debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80d66-111">To enable Skype for Business, you must have the following:</span></span>
  
- <span data-ttu-id="80d66-112">Skype para profesionales Online (Plan 2 o un plan de empresa) o superior en su plan de Office 365.</span><span class="sxs-lookup"><span data-stu-id="80d66-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="80d66-113">El plan debe permitir que las capacidades de conferencia de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="80d66-113">The plan needs to allow dial-in conferencing capabilities.</span></span>
    
- <span data-ttu-id="80d66-114">Si necesita capacidades de marcado de una reunión, necesitará una conferencia de audio y la licencia del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="80d66-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="80d66-115">Si necesita las capacidades de acceso telefónico de salida de una reunión, necesitará un nacionales o nacional e internacional de llamada Plan.</span><span class="sxs-lookup"><span data-stu-id="80d66-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="80d66-116">Los usuarios de inquilinos deben tener los buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="80d66-116">Your tenant users must have Exchange mailboxes.</span></span>
    
- <span data-ttu-id="80d66-117">Su cuenta de Skype salón sistemas v2 requieren en como mínimo un Skype para licencia empresarial Online (Plan 2), pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80d66-117">Your Skype Room Systems v2 account does require at a minumum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span>

<span data-ttu-id="80d66-118">Para obtener información detallada en Skype para planes de negocios de en línea, vea la [Skype para la descripción de servicio en línea de negocio](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="80d66-118">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="80d66-119">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="80d66-119">Add a device account</span></span>

1. <span data-ttu-id="80d66-120">Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange.</span><span class="sxs-lookup"><span data-stu-id="80d66-120">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="80d66-121">Asegúrese de tener los permisos adecuados establecidos para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="80d66-121">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="80d66-122">Estos son algunos ejemplos de cmdlets que puede utilizar y modificar en su entorno.</span><span class="sxs-lookup"><span data-stu-id="80d66-122">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="80d66-123">Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="80d66-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="80d66-124">Esto le permitirá la cuenta autenticar a los sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="80d66-124">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
  <span data-ttu-id="80d66-125">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="80d66-125">If you are changing an existing resource mailbox:</span></span>
    
```
Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

  <span data-ttu-id="80d66-126">Si está creando un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="80d66-126">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="80d66-p107">Para mejorar la experiencia de la reunión, es necesario configurar diversas propiedades de Exchange en la cuenta del dispositivo. Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="80d66-p107">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="80d66-129">Tendrá que conectarse a Azure Active Directory para aplicar algunas de las configuraciones de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="80d66-129">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="80d66-130">Para conectarse a Azure AD, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="80d66-130">To connect to Azure AD, run the following cmdlet:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="80d66-131">	Si no desea que expire la contraseña, ejecute el cmdlet Set-MsolUser con la opción PasswordNeverExpires como sigue:  </span><span class="sxs-lookup"><span data-stu-id="80d66-131">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="80d66-132">También puede configurar un número de teléfono para la sala de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="80d66-132">You can also set a phone number for the room as follows:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="80d66-133">La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Skype para la empresa no funcionará.</span><span class="sxs-lookup"><span data-stu-id="80d66-133">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="80d66-134">Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="80d66-134">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="80d66-135">Puede usar Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="80d66-135">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
    
   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="80d66-p110">A continuación, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="80d66-p110">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="80d66-138">A continuación, deberá habilitar la cuenta del dispositivo con Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="80d66-138">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="80d66-139">Asegúrese de que su entorno cumple los requisitos definidos en [los requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80d66-139">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
    
   <span data-ttu-id="80d66-140">Iniciar una sesión remota de Windows PowerShell de manera (asegúrese de instalar Skype para componentes de PowerShell en línea de negocio):</span><span class="sxs-lookup"><span data-stu-id="80d66-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="80d66-141">A continuación, habilitar su cuenta de Skype salón sistemas v2 de Skype para Business Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="80d66-141">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="80d66-142">Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="80d66-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="80d66-143">No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="80d66-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="80d66-144">El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="80d66-144">The command above will prevent errors in account setup due to this situation.</span></span> 
  
<span data-ttu-id="80d66-145">Una vez haya completado los pasos anteriores para habilitar su cuenta de v2 de sistemas de salón de Skype en Skype para profesionales en línea, debe asignar una licencia a dispositivos de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="80d66-145">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="80d66-146">Uso del portal administrativo de Office 365, asignar puede ser un Skype para profesionales Online (Plan 2) o un Skype para licencia empresarial Online (Plan 3) para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="80d66-146">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>
  
### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="80d66-147">Asignar una licencia a su cuenta</span><span class="sxs-lookup"><span data-stu-id="80d66-147">Assign a license to your account</span></span>

1. <span data-ttu-id="80d66-148">Inicio de sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="80d66-148">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="80d66-149">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="80d66-149">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="80d66-150">Seleccione la cuenta de v2 de sistemas de salón de Skype y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.</span><span class="sxs-lookup"><span data-stu-id="80d66-150">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>
    
4. <span data-ttu-id="80d66-151">Haga clic en la opción **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="80d66-151">Click on the **Licenses** option.</span></span>
    
5. <span data-ttu-id="80d66-152">En la sección **asignación de licencias** , es necesario seleccionar Skype para profesionales Online (Plan 2) o Skype para profesionales Online (Plan 3), en función de la concesión de licencias y que haya decidido en cuanto a la necesidad de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="80d66-152">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="80d66-153">Debe utilizar una licencia de planeación 3 si desea usar en la nube PBX en sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="80d66-153">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="80d66-154">Para la conectividad de voz, como mínimo necesitará PBX en la nube.</span><span class="sxs-lookup"><span data-stu-id="80d66-154">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="80d66-155">Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC.</span><span class="sxs-lookup"><span data-stu-id="80d66-155">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span>
    
6. <span data-ttu-id="80d66-156">Haga clic en **Guardar** para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="80d66-156">Click **Save** to complete the task.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="80d66-157">Ejemplo: Cuenta de sala del programa de instalación de Exchange Online y Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="80d66-157">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> <span data-ttu-id="80d66-p115">De esta manera, se agregan CloudPBX y PSTNCallingDomesticAndInternational. Además, deberá usar la interfaz de administración para asignar un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="80d66-p115">This adds CloudPBX and PSTNCallingDomesticAndInternational. Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 
  
## <a name="validate"></a><span data-ttu-id="80d66-160">Validar</span><span class="sxs-lookup"><span data-stu-id="80d66-160">Validate</span></span>

<span data-ttu-id="80d66-161">Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en la cuenta que creó.</span><span class="sxs-lookup"><span data-stu-id="80d66-161">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>


## <a name="see-also"></a><span data-ttu-id="80d66-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="80d66-162">See also</span></span>

[<span data-ttu-id="80d66-163">Configurar cuentas para sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="80d66-163">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="80d66-164">Plan para Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="80d66-164">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="80d66-165">Implementar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="80d66-165">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="80d66-166">Configurar una consola de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="80d66-166">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="80d66-167">Administrar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="80d66-167">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[<span data-ttu-id="80d66-168">Licencias de v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="80d66-168">Skype Room Systems v2 Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)