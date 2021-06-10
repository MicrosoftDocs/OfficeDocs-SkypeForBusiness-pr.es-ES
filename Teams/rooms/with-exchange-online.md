---
title: Implementar Salas de Microsoft Teams con Exchange Online
ms.author: dstrome
author: dstrome
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
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Exchange Online y Skype Empresarial Server locales.
ms.openlocfilehash: 2f92f85ddf39c5e1a813492b3092eeeef9b77e4c
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796684"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="909e5-103">Implementar Salas de Microsoft Teams con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="909e5-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="909e5-104">Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Exchange Online y Skype Empresarial Server locales.</span><span class="sxs-lookup"><span data-stu-id="909e5-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="909e5-105">Si su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea, la configuración dependerá de dónde se hospeda cada servicio.</span><span class="sxs-lookup"><span data-stu-id="909e5-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="909e5-106">En este tema se tratan las implementaciones híbridas para Salas de Microsoft Teams con Exchange en línea.</span><span class="sxs-lookup"><span data-stu-id="909e5-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="909e5-107">Dado que hay muchas variaciones diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas.</span><span class="sxs-lookup"><span data-stu-id="909e5-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="909e5-108">El siguiente proceso funcionará para muchas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="909e5-108">The following process will work for many configurations.</span></span> <span data-ttu-id="909e5-109">Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para lograr el mismo resultado final que se documenta aquí y para otras opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="909e5-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="909e5-110">La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante el uso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="909e5-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="909e5-111">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario Salas de Microsoft Teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="909e5-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="909e5-112">Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que Salas de Microsoft Teams dispositivo usará.</span><span class="sxs-lookup"><span data-stu-id="909e5-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="909e5-113">Requirements</span><span class="sxs-lookup"><span data-stu-id="909e5-113">Requirements</span></span>

<span data-ttu-id="909e5-114">Antes de implementar Salas de Microsoft Teams con Exchange Online, asegúrese de que ha cumplido los requisitos.</span><span class="sxs-lookup"><span data-stu-id="909e5-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="909e5-115">Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="909e5-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="909e5-116">Para implementar Salas de Microsoft Teams con Exchange Online, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="909e5-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="909e5-117">Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="909e5-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="909e5-118">El Azure Active Directory de Windows PowerShell [cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) de esta sección (por ejemplo, Set-MsolUser) se ha probado al configurar cuentas para Salas de Microsoft Teams dispositivos.</span><span class="sxs-lookup"><span data-stu-id="909e5-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="909e5-119">Es posible que otros cmdlets funcionen, pero no se han probado en este escenario específico.</span><span class="sxs-lookup"><span data-stu-id="909e5-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="909e5-120">Si implementó servicios de federación de Active Directory (AD FS), es posible que tenga que convertir la cuenta de usuario en un usuario administrado antes de seguir estos pasos y, después, convertir el usuario de nuevo en un usuario federado después de completar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="909e5-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="909e5-121">Crear una cuenta y configurar las propiedades de Exchange</span><span class="sxs-lookup"><span data-stu-id="909e5-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="909e5-122">Inicie una sesión Windows PowerShell sesión remota en un equipo y conéctese a Exchange Online siguiente:</span><span class="sxs-lookup"><span data-stu-id="909e5-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="909e5-123">Después de establecer una sesión, creará un buzón nuevo y lo habilitará como RoomMailboxAccount, o bien cambiará la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="909e5-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="909e5-124">Esto permitirá que la cuenta se autentique en Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="909e5-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="909e5-125">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="909e5-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="909e5-126">Si va a crear un buzón de recursos nuevo:</span><span class="sxs-lookup"><span data-stu-id="909e5-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="909e5-127">Para mejorar la experiencia de la reunión, deberá establecer las Exchange en la cuenta de usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="909e5-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="909e5-128">Agregar una cuenta de correo electrónico para su cuenta de dominio local</span><span class="sxs-lookup"><span data-stu-id="909e5-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="909e5-129">En la herramienta Ad Usuarios y equipos de **Active Directory,** haga clic con el botón derecho en el contenedor o unidad organizativa en el que se crearán las cuentas de Salas de Microsoft Teams, haga clic en Nuevo y, a continuación, haga clic en **Usuario.**</span><span class="sxs-lookup"><span data-stu-id="909e5-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="909e5-130">Escriba el nombre para mostrar (- Identidad) del cmdlet anterior (Set-Mailbox o New-Mailbox) en el cuadro Nombre completo y el alias en el cuadro Nombre **de inicio de** sesión de usuario. </span><span class="sxs-lookup"><span data-stu-id="909e5-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="909e5-131">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="909e5-131">Click **Next**.</span></span>
3. <span data-ttu-id="909e5-p108">Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.</span><span class="sxs-lookup"><span data-stu-id="909e5-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="909e5-135">Seleccionar **Contraseña nunca expira es** un requisito para Skype Empresarial Server en Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="909e5-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="909e5-136">Es posible que las reglas de dominio prohíban las contraseñas que no expiran.</span><span class="sxs-lookup"><span data-stu-id="909e5-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="909e5-137">Si es así, deberá crear una excepción para cada cuenta Salas de Microsoft Teams usuario.</span><span class="sxs-lookup"><span data-stu-id="909e5-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="909e5-138">Haga clic en **Finalizar** para crear la cuenta.</span><span class="sxs-lookup"><span data-stu-id="909e5-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="909e5-139">Después de crear la cuenta, ejecute una sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="909e5-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="909e5-140">Esto se puede lograr mediante [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="909e5-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="909e5-141">Cuando se complete, vaya a la página de usuarios y compruebe que las dos cuentas creadas en los pasos anteriores se han combinado.</span><span class="sxs-lookup"><span data-stu-id="909e5-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="909e5-142">Asignar una Microsoft 365 o Office 365 licencia</span><span class="sxs-lookup"><span data-stu-id="909e5-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="909e5-143">En primer lugar, conéctese a Azure AD para aplicar algunas opciones de configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="909e5-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="909e5-144">Puede ejecutar este cmdlet para conectarse.</span><span class="sxs-lookup"><span data-stu-id="909e5-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="909e5-145">Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="909e5-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="909e5-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.</span><span class="sxs-lookup"><span data-stu-id="909e5-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="909e5-147">La cuenta de usuario debe tener una licencia Microsoft 365 o Office 365 para asegurarse de que Exchange y Skype Empresarial Server funcionarán.</span><span class="sxs-lookup"><span data-stu-id="909e5-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="909e5-148">Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de usuario, esto determina qué SKU de licencia están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="909e5-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="909e5-149">Hará la tarea en un paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="909e5-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="909e5-150">A continuación, use `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="909e5-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="909e5-151">para recuperar una lista de SKU disponibles para su Microsoft 365 o Office 365 organización.</span><span class="sxs-lookup"><span data-stu-id="909e5-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="909e5-152">Una vez que haya listado las SKU, puede agregar una licencia con el `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="909e5-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="909e5-153">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="909e5-153">cmdlet.</span></span> <span data-ttu-id="909e5-154">En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="909e5-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="909e5-155">Habilitar la cuenta de usuario con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="909e5-155">Enable the user account with Skype for Business Server</span></span>

> [!NOTE]
> <span data-ttu-id="909e5-156">Si está configurando Salas de Teams para unirse Microsoft Teams reuniones, no es necesario que realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="909e5-156">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="909e5-157">Los pasos siguientes solo son necesarios si desea habilitar la compatibilidad con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="909e5-157">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="909e5-158">Cree una sesión de Windows PowerShell remoto desde un equipo como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="909e5-158">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="909e5-159">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="909e5-159">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="909e5-160">Si usa la versión pública más [reciente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar el Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="909e5-160">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="909e5-161">Para habilitar su Salas de Microsoft Teams de Skype Empresarial Server, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="909e5-161">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="909e5-162">Si no está seguro de qué valor usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario Skype Empresarial Server existente con este comando</span><span class="sxs-lookup"><span data-stu-id="909e5-162">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="909e5-163">Asignar una Skype Empresarial Server a su Salas de Microsoft Teams cuenta</span><span class="sxs-lookup"><span data-stu-id="909e5-163">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

> [!NOTE]
> <span data-ttu-id="909e5-164">Si está configurando Salas de Teams para unirse Microsoft Teams reuniones, no es necesario que realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="909e5-164">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="909e5-165">Los pasos siguientes solo son necesarios si desea habilitar la compatibilidad con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="909e5-165">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="909e5-166">Inicie sesión como administrador de inquilinos, abra el Microsoft 365 de administración y haga clic en la aplicación Administrador.</span><span class="sxs-lookup"><span data-stu-id="909e5-166">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="909e5-167">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="909e5-167">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="909e5-168">Haga clic en Salas de Microsoft Teams cuenta y, a continuación, haga clic en el icono del lápiz para editar la información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="909e5-168">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="909e5-169">Haga clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="909e5-169">Click **Licenses**.</span></span>
5. <span data-ttu-id="909e5-170">En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="909e5-170">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="909e5-171">Tendrá que usar una licencia de Plan 3 si desea usar Telefonía IP empresarial en Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="909e5-171">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="909e5-172">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="909e5-172">Click **Save**.</span></span>

<span data-ttu-id="909e5-173">Para la validación, debería poder usar cualquier Skype Empresarial cliente para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="909e5-173">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="909e5-174">Si actualmente usa SKU de E1, E3, E4 o E Skype Empresarial 5 con un plan 2 con audioconferencias o con Sistema telefónico y un plan de llamadas, estos seguirán funcionando.</span><span class="sxs-lookup"><span data-stu-id="909e5-174">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="909e5-175">Sin embargo, debería considerar la posibilidad de cambiar a un modelo de licencias más sencillo, como se describe [en Teams Sala de reuniones actualización](rooms-licensing.md)de licencias, después de que expiren las licencias actuales.</span><span class="sxs-lookup"><span data-stu-id="909e5-175">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="909e5-176">Si usa Skype Empresarial Plan 2, solo puede usar el Salas de Microsoft Teams en el modo solo Skype Empresarial, lo que significa que todas las reuniones se Skype Empresarial reuniones.</span><span class="sxs-lookup"><span data-stu-id="909e5-176">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="909e5-177">Para habilitar la sala de reuniones Microsoft Teams reuniones, le recomendamos que compre la licencia Sala de reuniones reunión.</span><span class="sxs-lookup"><span data-stu-id="909e5-177">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="909e5-178">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="909e5-178">Related topics</span></span>

[<span data-ttu-id="909e5-179">Configurar cuentas para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="909e5-179">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="909e5-180">Plan para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="909e5-180">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="909e5-181">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="909e5-181">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="909e5-182">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="909e5-182">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="909e5-183">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="909e5-183">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
