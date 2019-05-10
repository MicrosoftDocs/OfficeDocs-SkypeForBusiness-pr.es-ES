---
title: Implementar Salas de Microsoft Teams con Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos con Office 365.
ms.openlocfilehash: 05b6bc05200bd6664fc597b937d2a45fba1c9e2b
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835258"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="70aaf-103">Implementar Salas de Microsoft Teams con Office 365</span><span class="sxs-lookup"><span data-stu-id="70aaf-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="70aaf-104">Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos con Office 365, donde Microsoft Teams o Skype para empresas y Exchange estén en línea.</span><span class="sxs-lookup"><span data-stu-id="70aaf-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="70aaf-105">La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="70aaf-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="70aaf-106">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudar a convertirlas en cuentas de usuario compatibles con salones de los equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70aaf-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="70aaf-107">Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70aaf-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="70aaf-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70aaf-108">Requirements</span></span>

<span data-ttu-id="70aaf-109">Antes de implementar Microsoft salones de los equipos con Office 365, asegúrese de que cumplen los requisitos.</span><span class="sxs-lookup"><span data-stu-id="70aaf-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="70aaf-110">Para obtener más información, vea [requisitos de salas de equipos de Microsoft](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70aaf-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="70aaf-111">Para habilitar Skype para la empresa, debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70aaf-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="70aaf-112">Skype para profesionales Online (Plan 2 o un plan de empresa) o superior en su plan de Office 365.</span><span class="sxs-lookup"><span data-stu-id="70aaf-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="70aaf-113">El plan debe permitir que las capacidades de conferencia de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="70aaf-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="70aaf-114">Si necesita capacidades de marcado de una reunión, necesitará una conferencia de audio y la licencia del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="70aaf-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="70aaf-115">Si necesita las capacidades de acceso telefónico de salida de una reunión, necesitará un nacionales o nacional e internacional de llamada Plan.</span><span class="sxs-lookup"><span data-stu-id="70aaf-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="70aaf-116">Los usuarios de inquilinos deben tener los buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="70aaf-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="70aaf-117">Su cuenta de salas de equipos de Microsoft requieren como mínimo un Skype para licencia empresarial Online (Plan 2), pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70aaf-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="70aaf-118">Para obtener información detallada, vea [licencias de salas de equipos de Microsoft](skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="70aaf-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="70aaf-119">Para obtener información detallada en Skype para planes de negocios de en línea, vea la [Skype para la descripción de servicio en línea de negocio](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="70aaf-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="70aaf-120">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="70aaf-120">Add a device account</span></span>

1. <span data-ttu-id="70aaf-121">Conectarse a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70aaf-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="70aaf-122">Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="70aaf-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="70aaf-123">En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="70aaf-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="70aaf-124">De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que necesitará para agregar una cuenta al crear o modificar un buzón de sala que le permite autenticar con sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="70aaf-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="70aaf-125">Para crear un nuevo buzón de sala, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="70aaf-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="70aaf-126">En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="70aaf-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="70aaf-127">Nombre: Proyecto-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="70aaf-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="70aaf-128">Alias: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="70aaf-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="70aaf-129">Cuenta: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="70aaf-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="70aaf-130">Contraseña de la cuenta: P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="70aaf-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="70aaf-131">Para modificar un buzón de sala existente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="70aaf-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="70aaf-132">En este ejemplo se habilita la cuenta para el buzón de sala existente que tiene el valor de alias ProjectRigel02 y se establece la contraseña en 9898P@$$W0rd.</span><span class="sxs-lookup"><span data-stu-id="70aaf-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="70aaf-133">Tenga en cuenta que la cuenta será ProjectRigel02@contoso.onmicrosoft.com debido al valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="70aaf-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="70aaf-134">Para obtener información de parámetro y detallada sobre la sintaxis, vea [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="70aaf-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="70aaf-135">En Exchange Online PowerShell, configure las opciones siguientes en el buzón de sala para mejorar la experiencia de reunión:</span><span class="sxs-lookup"><span data-stu-id="70aaf-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="70aaf-136">AutomateProcessing: AutoAccept (los organizadores de reuniones reciben la decisión de reserva de sala directamente sin intervención humana: libre = acepte; ocupado = rechazar.)</span><span class="sxs-lookup"><span data-stu-id="70aaf-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="70aaf-137">AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).</span><span class="sxs-lookup"><span data-stu-id="70aaf-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="70aaf-138">DeleteComments: $false (mantener el texto del cuerpo del mensaje de convocatorias de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="70aaf-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="70aaf-139">DeleteSubject: $false (conservar el asunto de convocatorias de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="70aaf-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="70aaf-140">RemovePrivateProperty: $false (garantiza la marca privada que se envió el organizador de la reunión original permanece tal como se especifica de solicitudes).</span><span class="sxs-lookup"><span data-stu-id="70aaf-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="70aaf-141">AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).</span><span class="sxs-lookup"><span data-stu-id="70aaf-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="70aaf-142">AdditionalResponse: "ésta es una sala de reuniones de Skype!"</span><span class="sxs-lookup"><span data-stu-id="70aaf-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="70aaf-143">(El texto adicional para agregar a la convocatoria de reunión).</span><span class="sxs-lookup"><span data-stu-id="70aaf-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="70aaf-144">En este ejemplo se configura estas opciones de configuración en el buzón de sala denominado Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="70aaf-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="70aaf-145">Para obtener información de parámetro y detallada sobre la sintaxis, vea [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="70aaf-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="70aaf-146">Conectarse a MS Online PowerShell para realizar la configuración de Active Directory mediante la ejecución de la `Connect-MsolService -Credential $cred` cmdlet de powershell.</span><span class="sxs-lookup"><span data-stu-id="70aaf-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="70aaf-147">Para obtener información detallada acerca de Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="70aaf-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="70aaf-148">No se admite [de Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="70aaf-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="70aaf-149">Si no desea que la contraseña a punto de caducar, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="70aaf-149">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="70aaf-150">En este ejemplo se establece la contraseña de la cuenta ProjectRigel01@contoso.onmicrosoft.com para que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="70aaf-150">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="70aaf-151">También puede establecer un número de teléfono de la cuenta, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="70aaf-151">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="70aaf-152">La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Microsoft Teams o Skype para la empresa no funcionará.</span><span class="sxs-lookup"><span data-stu-id="70aaf-152">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="70aaf-153">Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="70aaf-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="70aaf-154">Puede usar`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="70aaf-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="70aaf-155">para recuperar una lista de SKU disponibles para el inquilino de Office 365 de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="70aaf-155">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="70aaf-156">A continuación, puede agregar una licencia mediante la`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="70aaf-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="70aaf-157">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70aaf-157">cmdlet.</span></span> <span data-ttu-id="70aaf-158">En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="70aaf-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="70aaf-159">Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="70aaf-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="70aaf-160">A continuación, deberá habilitar la cuenta del dispositivo con Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="70aaf-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="70aaf-161">Asegúrese de que su entorno cumple los requisitos definidos en [los requisitos de salas de equipos de Microsoft](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70aaf-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="70aaf-162">Iniciar una [sesión de Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de remota como se muestra a continuación (asegúrese de [instalar Skype para componentes de PowerShell en línea de negocio](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="70aaf-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="70aaf-163">A continuación, habilitar la cuenta de salones de los equipos de Microsoft para Skype para Business Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="70aaf-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="70aaf-164">Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="70aaf-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="70aaf-165">No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="70aaf-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="70aaf-166">El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="70aaf-166">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="70aaf-167">Una vez haya completado los pasos anteriores para habilitar la cuenta de salas de equipos de Microsoft en Microsoft Teams o Skype para profesionales en línea, debe asignar una licencia a dispositivo de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70aaf-167">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="70aaf-168">Uso del portal administrativo de Office 365, asignar puede ser un Skype para profesionales Online (Plan 2) o un Skype para licencia empresarial Online (Plan 3) para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="70aaf-168">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="70aaf-169">Asignar una licencia a su cuenta</span><span class="sxs-lookup"><span data-stu-id="70aaf-169">Assign a license to your account</span></span>

1. <span data-ttu-id="70aaf-170">Inicio de sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="70aaf-170">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="70aaf-171">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="70aaf-171">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="70aaf-172">Seleccione la cuenta de salas de equipos de Microsoft y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.</span><span class="sxs-lookup"><span data-stu-id="70aaf-172">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="70aaf-173">Haga clic en la opción **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="70aaf-173">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="70aaf-174">En la sección **asignación de licencias** , es necesario seleccionar Skype para profesionales Online (Plan 2) o Skype para profesionales Online (Plan 3), en función de la concesión de licencias y que haya decidido en cuanto a la necesidad de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="70aaf-174">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="70aaf-175">Debe utilizar una licencia de planeación 3 si desea usar en la nube PBX en salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70aaf-175">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="70aaf-176">Para la conectividad de voz, como mínimo necesitará PBX en la nube.</span><span class="sxs-lookup"><span data-stu-id="70aaf-176">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="70aaf-177">Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC.</span><span class="sxs-lookup"><span data-stu-id="70aaf-177">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="70aaf-178">Para obtener más información, vea [las licencias de salas de equipos de Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .</span><span class="sxs-lookup"><span data-stu-id="70aaf-178">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="70aaf-179">Haga clic en **Guardar** para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="70aaf-179">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="70aaf-180">Ejemplo: Cuenta de sala del programa de instalación de Exchange Online y Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="70aaf-180">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="70aaf-181">Comandos de PowerShell en Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="70aaf-181">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="70aaf-182">Comandos de Azure Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="70aaf-182">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="70aaf-183">Skype para comandos de PowerShell de negocio:</span><span class="sxs-lookup"><span data-stu-id="70aaf-183">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="70aaf-184">De esta manera, se agregan CloudPBX y PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="70aaf-184">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="70aaf-185">Además, debe usar la interfaz de administración para asignar a un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="70aaf-185">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="70aaf-186">Validar</span><span class="sxs-lookup"><span data-stu-id="70aaf-186">Validate</span></span>

<span data-ttu-id="70aaf-187">Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en la cuenta que creó.</span><span class="sxs-lookup"><span data-stu-id="70aaf-187">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="70aaf-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="70aaf-188">See also</span></span>

[<span data-ttu-id="70aaf-189">Configurar las cuentas para salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="70aaf-189">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="70aaf-190">Plan para salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="70aaf-190">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="70aaf-191">Implementación de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="70aaf-191">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="70aaf-192">Configurar una consola de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="70aaf-192">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="70aaf-193">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70aaf-193">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="70aaf-194">Licencias de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="70aaf-194">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
