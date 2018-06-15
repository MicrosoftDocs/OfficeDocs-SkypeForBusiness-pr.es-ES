---
title: Implementar Sistemas de salas de Skype v2 con Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Exchange Online.
ms.openlocfilehash: dad47f56d96da0f84383b2638684c65554e5a8f9
ms.sourcegitcommit: 4e9f4e2297cea3372a97f4ea178eb75ba6f8753f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2018
ms.locfileid: "19887894"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="f3991-103">Implementar Sistemas de salas de Skype v2 con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f3991-103">Deploy Skype Room Systems v2 with Exchange Online</span></span> 
 
<span data-ttu-id="f3991-104">Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Exchange Online y Skype para Business Server local.</span><span class="sxs-lookup"><span data-stu-id="f3991-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="f3991-105">Si su organización tiene una mezcla de servicios, con algunas hospedado en local y algunas alojado en línea, a continuación, la configuración depende de donde se hospeda cada servicio.</span><span class="sxs-lookup"><span data-stu-id="f3991-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="f3991-106">Este tema tratan las implementaciones híbridas en sistemas de salón de Skype v2 con Exchange alojado en línea.</span><span class="sxs-lookup"><span data-stu-id="f3991-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="f3991-107">Debido a que hay muchas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos.</span><span class="sxs-lookup"><span data-stu-id="f3991-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="f3991-108">El siguiente proceso funcionará para muchas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="f3991-108">The following process will work for many configurations.</span></span> <span data-ttu-id="f3991-109">Si el proceso no es adecuado para el programa de instalación, se recomienda que use Windows PowerShell para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="f3991-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> 

<span data-ttu-id="f3991-110">La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="f3991-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="f3991-111">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudarle a convertirlas en cuentas de usuario de v2 de Skype salón sistemas compatibles.</span><span class="sxs-lookup"><span data-stu-id="f3991-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="f3991-112">Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="f3991-112">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="f3991-113">Implementar Sistemas de salas de Skype v2 con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f3991-113">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="f3991-114">Antes de implementar sistemas de salón de Skype v2 con Exchange Online, debe asegurarse de que cumplen los requisitos.</span><span class="sxs-lookup"><span data-stu-id="f3991-114">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="f3991-115">Para obtener más información, vea [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3991-115">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="f3991-116">Para implementar sistemas de salón de Skype v2 con Exchange Online, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f3991-116">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="f3991-117">Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="f3991-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="f3991-118">Crear una cuenta y configurar las propiedades de Exchange</span><span class="sxs-lookup"><span data-stu-id="f3991-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="f3991-119">Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange Online, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="f3991-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="f3991-120">Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="f3991-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="f3991-121">Esto le permitirá la cuenta autenticar en sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f3991-121">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="f3991-122">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="f3991-122">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="f3991-123">Si está creando un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="f3991-123">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="f3991-124">Para mejorar la experiencia de reunión, debe establecer las propiedades de Exchange en la cuenta de usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f3991-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. <span data-ttu-id="f3991-p106">Debe conectarse a Azure AD para aplicar algunas de las configuraciones de la cuenta. Puede ejecutar este cmdlet para conectarse.</span><span class="sxs-lookup"><span data-stu-id="f3991-p106">You need to connect to Azure AD to apply some account settings. You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="f3991-127">Agregar una cuenta de correo electrónico para su cuenta de dominio local</span><span class="sxs-lookup"><span data-stu-id="f3991-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="f3991-128">Herramienta de **usuarios de Active Directory y AD de equipos** , haga clic en la carpeta o unidad organizativa que los sistemas de salón de Skype se crearán cuentas de v2 en, haga clic en **nuevo**y haga clic en **usuario**.</span><span class="sxs-lookup"><span data-stu-id="f3991-128">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and the click **User**.</span></span>
    
2. <span data-ttu-id="f3991-p107">Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f3991-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>


3. <span data-ttu-id="f3991-p108">Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.</span><span class="sxs-lookup"><span data-stu-id="f3991-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3991-134">Selección de **la contraseña nunca caduca** es un requisito para Skype para Business Server 2015 en sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f3991-134">Selecting **Password never expires** is a requirement for Skype for Business Server 2015 on Skype Room Systems v2.</span></span> <span data-ttu-id="f3991-135">Es posible que las reglas de dominio prohíban las contraseñas que no expiran.</span><span class="sxs-lookup"><span data-stu-id="f3991-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="f3991-136">Si es así, debe crear una excepción para cada cuenta de usuario de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="f3991-136">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
4. <span data-ttu-id="f3991-137">Haga clic en **Finalizar** para crear la cuenta.</span><span class="sxs-lookup"><span data-stu-id="f3991-137">Click **Finish** to create the account.</span></span>
    
5. <span data-ttu-id="f3991-p110">Tras crear la cuenta, ejecute una sincronización de directorios. Cuando finalice, vaya a la página de usuarios y compruebe que las dos cuentas que ha creado en los pasos anteriores se han fusionado.</span><span class="sxs-lookup"><span data-stu-id="f3991-p110">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="f3991-140">Asignar una licencia de Office 365</span><span class="sxs-lookup"><span data-stu-id="f3991-140">Assign an Office 365 license</span></span>

1. <span data-ttu-id="f3991-141">La cuenta de usuario debe tener una licencia válida de Office 365 para asegurarse de que funcionará Exchange y Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f3991-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server 2015 will work.</span></span> <span data-ttu-id="f3991-142">Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de usuario: Esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="f3991-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="f3991-143">A continuación, use Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3991-143">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="f3991-p112">Una vez que tenga la lista de las SKU, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="f3991-p112">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a><span data-ttu-id="f3991-146">Habilitar la cuenta de usuario con Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="f3991-146">Enable the user account with Skype for Business Server 2015</span></span>

1. <span data-ttu-id="f3991-147">Crear una sesión remota de Windows PowerShell desde un PC de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f3991-147">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="f3991-148">Para habilitar su cuenta de Skype salón sistemas v2 de Skype para Business Server 2015, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="f3991-148">To enable your Skype Room Systems v2 account for Skype for Business Server 2015, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="f3991-149">Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en el entorno, puede obtener el valor de una existente Skype para usuario Business Server 2015 con este comando</span><span class="sxs-lookup"><span data-stu-id="f3991-149">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server 2015 user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="f3991-150">Asignar una licencia de Skype Empresarial Server 2015 a su cuenta de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="f3991-150">Assign a Skype for Business Server 2015 license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="f3991-151">Inicie sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="f3991-151">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="f3991-152">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="f3991-152">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="f3991-153">Haga clic en la cuenta de Skype salón sistemas v2 y, a continuación, haga clic en el icono de lápiz para editar la información de cuenta.</span><span class="sxs-lookup"><span data-stu-id="f3991-153">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="f3991-154">Haga clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="f3991-154">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="f3991-155">En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f3991-155">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="f3991-156">Debe utilizar una licencia de planeación 3 si desea usar Enterprise Voice en su v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="f3991-156">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="f3991-157">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f3991-157">Click **Save**.</span></span>
    
<span data-ttu-id="f3991-158">Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="f3991-158">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f3991-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3991-159">See also</span></span>

[<span data-ttu-id="f3991-160">Configurar cuentas para sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="f3991-160">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="f3991-161">Planeación de la sala de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="f3991-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="f3991-162">Implementación de salón de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="f3991-162">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="f3991-163">Configurar una consola de v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="f3991-163">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="f3991-164">Administración de salón de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="f3991-164">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

