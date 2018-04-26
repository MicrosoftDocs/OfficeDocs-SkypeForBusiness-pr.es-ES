---
title: Implementar Sistemas de salas de Skype v2 con Exchange local (híbrida)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 en un entorno híbrido con Exchange en las instalaciones.
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a><span data-ttu-id="dcbbd-103">Implementar Sistemas de salas de Skype v2 con Exchange local (híbrida)</span><span class="sxs-lookup"><span data-stu-id="dcbbd-103">Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)</span></span>
 
<span data-ttu-id="dcbbd-104">Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 en un entorno híbrido con Exchange en las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises.</span></span>
  
<span data-ttu-id="dcbbd-105">Si su organización tiene una mezcla de servicios, con algunas alojadas en locales y algunos se alojan en línea, su configuración dependerá donde se hospeda cada servicio.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="dcbbd-106">Este tema trata las implementaciones híbrido para sistemas de salas de Skype v2 con Exchange alojado en locales.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="dcbbd-107">Porque hay muchas diversas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="dcbbd-108">El siguiente proceso de trabajo para muchas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-108">The following process will work for many configurations.</span></span> <span data-ttu-id="dcbbd-109">Si el proceso no es adecuado para la instalación, se recomienda utilizar Windows PowerShell para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="dcbbd-110">A continuación, debe utilizar la secuencia de comandos de Windows PowerShell para comprobar la configuración de sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="dcbbd-111">(Consulte la secuencia de comandos de comprobación de la cuenta.)</span><span class="sxs-lookup"><span data-stu-id="dcbbd-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="dcbbd-112">Implementar Sistemas de salas de Skype v2 con Exchange local</span><span class="sxs-lookup"><span data-stu-id="dcbbd-112">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="dcbbd-113">Antes de implementar sistemas de salas de Skype v2 con Exchange en las instalaciones, asegúrese de que cumple los requisitos.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="dcbbd-114">Para obtener más información, vea [requisitos de los sistemas de salas de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcbbd-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="dcbbd-115">Si está implementando sistemas de salas de Skype v2 con Exchange en las instalaciones, se va a utilizar herramientas administrativas de Active Directory para agregar una dirección de correo electrónico de su cuenta de dominio local.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="dcbbd-116">Esta cuenta se sincronizará con Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="dcbbd-117">Tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-117">You will need to:</span></span>
  
- <span data-ttu-id="dcbbd-118">Crear una cuenta y sincronizarla con Active Directory</span><span class="sxs-lookup"><span data-stu-id="dcbbd-118">Create an account and synchronize the account with Active Directory.</span></span>
    
- <span data-ttu-id="dcbbd-119">Habilitar el buzón de correo remoto y establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="dcbbd-119">Enable the remote mailbox and set properties.</span></span>
    
- <span data-ttu-id="dcbbd-120">Asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-120">Assign an Office 365 license.</span></span>
    
- <span data-ttu-id="dcbbd-121">Habilitar la cuenta del dispositivo con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="dcbbd-122">Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>
    
  - <span data-ttu-id="dcbbd-123">Debe tener Skype para los negocios en línea (Plan 2) o superior en su plan de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="dcbbd-124">El plan debe admitir la funcionalidad de conferencias.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-124">The plan needs to support conferencing capability.</span></span>
    
  - <span data-ttu-id="dcbbd-125">Si necesita Telefonía IP empresarial (telefonía PSTN) mediante proveedores de servicios de telefonía para sistemas de salas de Skype v2 necesita Skype para los negocios en línea (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="dcbbd-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
  - <span data-ttu-id="dcbbd-126">Los usuarios de inquilinos deben tener buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-126">Your tenant users must have Exchange mailboxes.</span></span>
    
  - <span data-ttu-id="dcbbd-127">Tu cuenta de Skype sala sistemas v2 requieren un Skype para los negocios en línea (Plan 2) o Skype para licencia de negocios en línea (Plan 3), pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
- <span data-ttu-id="dcbbd-128">Asignar un Skype para licencia Business Server a tu cuenta de Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="dcbbd-129">Crear una cuenta y sincronizarla con Active Directory</span><span class="sxs-lookup"><span data-stu-id="dcbbd-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="dcbbd-130">En la herramienta **y equipos AD de usuarios de Active Directory** , haga clic en la carpeta o la unidad organizativa que sus sistemas de sala de Skype se crearán cuentas de v2, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>
    
2. <span data-ttu-id="dcbbd-p106">Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-p106">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
    
3. <span data-ttu-id="dcbbd-p107">Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dcbbd-136">Seleccione la **contraseña nunca caduca** es un requisito para Skype para Business Server en sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="dcbbd-137">Es posible que las reglas de dominio prohíban las contraseñas que no expiran.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="dcbbd-138">Si es así, debe crear una excepción para cada cuenta de dispositivo v2 de sistemas de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="dcbbd-139">Tras crear la cuenta, ejecute una sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="dcbbd-140">Cuando es completa, vaya a la página de usuarios en el centro de administración de Office 365 y compruebe que la cuenta que creó en los pasos anteriores ha combinado en línea.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="dcbbd-141">Habilitar el buzón de correo remoto y establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="dcbbd-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="dcbbd-142">Habilitar el buzón remoto, abra el shell de administración de Exchange local con permisos de administrador y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-142">Enable the remote mailbox by opening your on-premises Exchange management shell with administrator permissions and run the following command:</span></span>
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. <span data-ttu-id="dcbbd-143">Iniciar una sesión remota de Windows PowerShell y conectarse a Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span></span> <span data-ttu-id="dcbbd-144">De los inquilinos de Office 365, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-144">From your Office 365 tenant, run the following commands:</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. <span data-ttu-id="dcbbd-145">Para mejorar la experiencia de la reunión, debe establecer las propiedades de Exchange en la cuenta del dispositivo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-145">To improve the meeting experience, you'll need to set the Exchange properties on the device account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    <span data-ttu-id="dcbbd-146">Para obtener más información acerca de las propiedades que debe establecer, vea Propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-146">For more information about which properties you need to set, see Exchange properties.</span></span>
    
4. <span data-ttu-id="dcbbd-147">Tendrá que conectarse a Azure AD para aplicar algunas de las configuraciones de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-147">You will need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="dcbbd-148">Puede ejecutar este comando para conectarse:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-148">You can run this command to connect:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a><span data-ttu-id="dcbbd-149">Asignar una licencia de Office 365</span><span class="sxs-lookup"><span data-stu-id="dcbbd-149">Assign an Office 365 license</span></span>

1. <span data-ttu-id="dcbbd-150">La cuenta del dispositivo debe tener una licencia válida de Office 365 para asegurarse de que Exchange y Skype para Business Server funcionarán.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="dcbbd-151">Si dispone de la licencia, debe asignar una ubicación de uso a la cuenta del dispositivo, esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-151">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="dcbbd-152">A continuación, utilice MsolAccountSku de Get para recuperar una lista de SKU disponibles para los clientes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-152">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="dcbbd-p113">Una vez que tenga la lista de las SKU, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="dcbbd-p113">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="dcbbd-155">Habilitar la cuenta del dispositivo con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="dcbbd-155">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="dcbbd-156">Cree una sesión remota de Windows PowerShell desde un PC de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="dcbbd-157">Para habilitar tu cuenta de Skype sala sistemas v2 para Skype para Business Server, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="dcbbd-158">Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un Skype existente para usuario Business Server usando este comando</span><span class="sxs-lookup"><span data-stu-id="dcbbd-158">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="dcbbd-159">Asignar una licencia de Skype Empresarial a su cuenta de Sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-159">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="dcbbd-160">Inicie sesión como un administrador de inquilinos, abrir el Portal de administración de Office 365 y haga clic en Administrador de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-160">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="dcbbd-161">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-161">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="dcbbd-162">Haga clic en la cuenta de Skype sala sistemas v2 y, a continuación, haga clic en el icono de lápiz para editar la información de cuenta.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-162">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="dcbbd-163">Haga clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-163">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="dcbbd-164">En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-164">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="dcbbd-165">Tendrá que utilizar una licencia de Plan 3 si desea utilizar la Telefonía IP empresarial en su v2 sistemas de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-165">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="dcbbd-166">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-166">Click **Save**.</span></span>
    
<span data-ttu-id="dcbbd-167">Para la validación, puede utilizar cualquier Skype para Business client para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-167">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dcbbd-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcbbd-168">See also</span></span>

#### 

[<span data-ttu-id="dcbbd-169">Plan para la sala de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="dcbbd-169">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="dcbbd-170">Implementar sala de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="dcbbd-170">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="dcbbd-171">Configurar una consola de sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="dcbbd-171">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="dcbbd-172">Administrar espacio de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="dcbbd-172">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

