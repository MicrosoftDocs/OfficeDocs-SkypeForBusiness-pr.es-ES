---
title: Implementar Salas de Microsoft Teams con Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Exchange Online.
ms.openlocfilehash: 9368a21d581b87bc71606ba4c7ccb035c3254cde
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827878"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="71691-103">Implementar Salas de Microsoft Teams con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="71691-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="71691-104">Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Exchange Online y Skype empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="71691-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="71691-105">Si su organización tiene una combinación de servicios, con algunos locales hospedados y alojados en línea, la configuración dependerá de dónde se hospede cada servicio.</span><span class="sxs-lookup"><span data-stu-id="71691-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="71691-106">En este tema se tratan las implementaciones híbridas de las salas de Microsoft Teams con Exchange hospedado en línea.</span><span class="sxs-lookup"><span data-stu-id="71691-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="71691-107">Puesto que existen tantas variantes diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas.</span><span class="sxs-lookup"><span data-stu-id="71691-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="71691-108">El siguiente proceso funciona para muchas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="71691-108">The following process will work for many configurations.</span></span> <span data-ttu-id="71691-109">Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para obtener el mismo resultado final que se explica aquí, así como para otras opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="71691-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="71691-110">La forma más sencilla de configurar cuentas de usuario es configurarlas con Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="71691-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="71691-111">Microsoft proporciona [SkypeRoomProvisioningScript. PS1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario compatibles con salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71691-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="71691-112">Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que usará el dispositivo de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71691-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="71691-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71691-113">Requirements</span></span>

<span data-ttu-id="71691-114">Antes de implementar salas de Microsoft Teams con Exchange Online, asegúrese de que cumple con los requisitos.</span><span class="sxs-lookup"><span data-stu-id="71691-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="71691-115">Para obtener más información, consulte [requisitos de salas de Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71691-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="71691-116">Para implementar salas de Microsoft Teams con Exchange Online, siga los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="71691-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="71691-117">Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="71691-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="71691-118">El [módulo Azure Active Directory para cmdlets de Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) de esta sección (por ejemplo, Set-MsolUser) se ha probado en la configuración de cuentas para dispositivos de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71691-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="71691-119">Sin embargo, es posible que otros cmdlets funcionen, pero que no hayan sido probados en este escenario específico.</span><span class="sxs-lookup"><span data-stu-id="71691-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="71691-120">Si implementó los servicios de Federación de Active Directory (AD FS), es posible que tenga que convertir la cuenta de usuario a un usuario administrado antes de seguir estos pasos y, después, volver a convertir el usuario en un usuario federado después de completar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="71691-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="71691-121">Crear una cuenta y configurar las propiedades de Exchange</span><span class="sxs-lookup"><span data-stu-id="71691-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="71691-122">Inicie una sesión remota de Windows PowerShell en un equipo PC y conéctese a Exchange online de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="71691-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="71691-123">Después de establecer una sesión, cree un nuevo buzón de correo y lo habilite como RoomMailboxAccount, o cambie la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="71691-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="71691-124">Esto permitirá que la cuenta se autentique en las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71691-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="71691-125">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="71691-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="71691-126">Si va a crear un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="71691-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="71691-127">Para mejorar la experiencia de la reunión, tendrá que configurar las propiedades de Exchange en la cuenta de usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="71691-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="71691-128">Agregar una cuenta de correo electrónico para su cuenta de dominio local</span><span class="sxs-lookup"><span data-stu-id="71691-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="71691-129">En la herramienta **ad de usuarios y equipos de Active** Directory, haga clic con el botón secundario en el contenedor o la unidad organizativa en el que se crearán las cuentas de las salas de Microsoft Teams, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.</span><span class="sxs-lookup"><span data-stu-id="71691-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="71691-130">Escriba el nombre para mostrar (-Identity) del cmdlet anterior (Set-Mailbox o New-Mailbox) en el cuadro **nombre completo** y el alias en el cuadro **nombre de inicio de sesión de usuario** .</span><span class="sxs-lookup"><span data-stu-id="71691-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="71691-131">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="71691-131">Click **Next**.</span></span>
3. <span data-ttu-id="71691-p108">Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.</span><span class="sxs-lookup"><span data-stu-id="71691-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71691-135">La selección de la **contraseña nunca expira** es un requisito de Skype empresarial Server en las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71691-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="71691-136">Es posible que las reglas de dominio prohíban las contraseñas que no expiran.</span><span class="sxs-lookup"><span data-stu-id="71691-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="71691-137">Si es así, tendrá que crear una excepción para cada cuenta de usuario de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71691-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="71691-138">Haga clic en **Finalizar** para crear la cuenta.</span><span class="sxs-lookup"><span data-stu-id="71691-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="71691-139">Una vez que haya creado la cuenta, ejecute una sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="71691-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="71691-140">Esto se puede llevar a cabo con [set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71691-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="71691-141">Cuando haya finalizado, vaya a la página usuarios y compruebe que las dos cuentas creadas en los pasos anteriores se hayan fusionado.</span><span class="sxs-lookup"><span data-stu-id="71691-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="71691-142">Asignar una licencia de Office 365</span><span class="sxs-lookup"><span data-stu-id="71691-142">Assign an Office 365 license</span></span>

1. <span data-ttu-id="71691-143">En primer lugar, conéctese a Azure AD para aplicar la configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="71691-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="71691-144">Puede ejecutar este cmdlet para conectarse.</span><span class="sxs-lookup"><span data-stu-id="71691-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="71691-145">Para obtener más información sobre Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="71691-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="71691-146">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.</span><span class="sxs-lookup"><span data-stu-id="71691-146">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="71691-147">La cuenta de usuario debe tener una licencia válida de Office 365 para garantizar que Exchange y Skype empresarial Server funcionen.</span><span class="sxs-lookup"><span data-stu-id="71691-147">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="71691-148">Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de usuario, lo cual determina qué SKU de licencia están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="71691-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="71691-149">Realizará la tarea en un paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="71691-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="71691-150">A continuación, use`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="71691-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="71691-151">para recuperar una lista de las SKU disponibles para su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="71691-151">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="71691-152">Una vez que haya finalizado la lista de las SKU, puede Agregar una licencia con el`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="71691-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="71691-153">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="71691-153">cmdlet.</span></span> <span data-ttu-id="71691-154">En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="71691-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="71691-155">Habilitar la cuenta de usuario con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="71691-155">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="71691-156">Cree una sesión remota de Windows PowerShell desde un equipo informático de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="71691-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="71691-157">Para habilitar la cuenta de Microsoft Teams Rooms para Skype empresarial Server, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="71691-157">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="71691-158">Si no está seguro de qué valor usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario existente de Skype empresarial Server mediante este comando</span><span class="sxs-lookup"><span data-stu-id="71691-158">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="71691-159">Asignar una licencia de Skype empresarial Server a su cuenta de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71691-159">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="71691-160">Inicie sesión como administrador de inquilinos, abra el portal administrativo de Office 365 y haga clic en la aplicación de administrador.</span><span class="sxs-lookup"><span data-stu-id="71691-160">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="71691-161">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="71691-161">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="71691-162">Haga clic en la cuenta salas de Microsoft Teams y, a continuación, haga clic en el icono de lápiz para editar la información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="71691-162">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="71691-163">Haga clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="71691-163">Click **Licenses**.</span></span>
5. <span data-ttu-id="71691-164">En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="71691-164">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="71691-165">Tendrá que usar una licencia de Plan 3 Si quiere usar la telefonía IP empresarial en salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71691-165">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="71691-166">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="71691-166">Click **Save**.</span></span>

<span data-ttu-id="71691-167">Para la validación, debe poder usar cualquier cliente de Skype empresarial para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="71691-167">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="71691-168">Si actualmente usa las SKU de E1, E3, E4 o E5 con Skype empresarial plan 2 con conferencias de audio o con el sistema telefónico de Office 365 y un plan de llamadas, estos seguirán funcionando.</span><span class="sxs-lookup"><span data-stu-id="71691-168">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Office 365 Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="71691-169">Sin embargo, debe considerar la posibilidad de cambiar a un modelo de licencias más sencillo, como se describe en [Teams, actualización de licencias de sala de reuniones](rooms-licensing.md), después de que venzan las licencias actuales.</span><span class="sxs-lookup"><span data-stu-id="71691-169">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71691-170">Si está usando Skype empresarial plan 2, solo puede usar las salas de Microsoft Teams en modo de solo Skype empresarial, lo que significa que todas sus reuniones serán reuniones de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="71691-170">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="71691-171">Para habilitar las reuniones de Microsoft Teams en su sala de reuniones, le recomendamos que compre la licencia sala de reuniones.</span><span class="sxs-lookup"><span data-stu-id="71691-171">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71691-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="71691-172">See also</span></span>

[<span data-ttu-id="71691-173">Configurar cuentas para salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71691-173">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="71691-174">Plan para salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71691-174">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="71691-175">Implementar salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71691-175">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="71691-176">Configurar una consola de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71691-176">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="71691-177">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71691-177">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
