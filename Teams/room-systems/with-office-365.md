---
title: Implementar Salas de Microsoft Teams con Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Office 365.
ms.openlocfilehash: 8e41b06b8f5cf76a45fd09f4b8820fb2fcaaa6d5
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775035"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="8d511-103">Implementar Salas de Microsoft Teams con Office 365</span><span class="sxs-lookup"><span data-stu-id="8d511-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="8d511-104">Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Office 365, donde Microsoft Teams o Skype empresarial y Exchange están conectados.</span><span class="sxs-lookup"><span data-stu-id="8d511-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="8d511-105">La forma más sencilla de configurar cuentas de usuario es configurarlas con Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="8d511-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="8d511-106">Microsoft proporciona [SkypeRoomProvisioningScript. PS1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario compatibles con salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d511-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="8d511-107">Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que usará el dispositivo de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d511-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="8d511-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d511-108">Requirements</span></span>

<span data-ttu-id="8d511-109">Antes de implementar salas de Microsoft Teams con Office 365, asegúrese de que cumple con los requisitos.</span><span class="sxs-lookup"><span data-stu-id="8d511-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="8d511-110">Para obtener más información, consulte [requisitos de salas de Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d511-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="8d511-111">Para habilitar Skype empresarial, debe disponer de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d511-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="8d511-112">Skype empresarial online (plan 2 o un plan basado en la empresa) o superior en el plan 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="8d511-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="8d511-113">El plan debe permitir las capacidades de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="8d511-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="8d511-114">Si necesita capacidades de acceso telefónico desde una reunión, necesitará una licencia de audioconferencia y sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="8d511-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="8d511-115">Si necesita poder llamar desde una reunión, necesitará un plan de llamadas nacionales o nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="8d511-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="8d511-116">Los usuarios de inquilinos deben tener buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8d511-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="8d511-117">Su cuenta de salas de Microsoft Teams requiere, como mínimo, una licencia de Skype empresarial online (plan 2), pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8d511-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="8d511-118">Para obtener más información, vea [licencias de salas de Microsoft Teams](skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="8d511-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="8d511-119">Para obtener más información sobre los planes de Skype empresarial online, consulte la [Descripción del servicio de Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="8d511-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="8d511-120">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="8d511-120">Add a device account</span></span>

1. <span data-ttu-id="8d511-121">Conéctese a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d511-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="8d511-122">Para obtener instrucciones, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="8d511-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="8d511-123">En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="8d511-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="8d511-124">De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que tendrá que agregar una cuenta al crear o modificar un buzón de sala que le permita autenticarse con sistemas de la sala de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="8d511-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="8d511-125">Para crear un nuevo buzón de sala, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8d511-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="8d511-126">Este ejemplo crea un nuevo buzón de sala con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="8d511-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="8d511-127">Nombre: proyecto-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="8d511-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="8d511-128">Alias: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="8d511-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="8d511-129">Cuenta: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8d511-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="8d511-130">Contraseña de la cuenta: P @ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="8d511-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="8d511-131">Para modificar un buzón de sala existente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8d511-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="8d511-132">Este ejemplo habilita la cuenta del buzón de sala existente que tiene el valor de alias ProjectRigel02 y establece la contraseña en 9898P @ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="8d511-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="8d511-133">Observe que la cuenta se ProjectRigel02@contoso.onmicrosoft.com por el valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="8d511-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="8d511-134">Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="8d511-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="8d511-135">En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de la reunión:</span><span class="sxs-lookup"><span data-stu-id="8d511-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="8d511-136">AutomateProcessing: AutoAccept (los organizadores de reuniones reciben directamente la decisión de reserva de la sala sin intervención humana: gratis = aceptar; ocupado = rechazar).</span><span class="sxs-lookup"><span data-stu-id="8d511-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="8d511-137">AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).</span><span class="sxs-lookup"><span data-stu-id="8d511-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="8d511-138">DeleteComments: $false (mantener el texto en el cuerpo del mensaje de las convocatorias de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="8d511-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="8d511-139">DeleteSubject: $false (mantener el asunto de las convocatorias de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="8d511-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="8d511-140">RemovePrivateProperty: $false (garantiza que la marca privada que envió el organizador de la reunión en la convocatoria de reunión original permanece como se especifica).</span><span class="sxs-lookup"><span data-stu-id="8d511-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="8d511-141">AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).</span><span class="sxs-lookup"><span data-stu-id="8d511-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="8d511-142">AdditionalResponse: "este es un salón de reunión de Skype".</span><span class="sxs-lookup"><span data-stu-id="8d511-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="8d511-143">(El texto adicional que se agregará a la convocatoria de reunión).</span><span class="sxs-lookup"><span data-stu-id="8d511-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="8d511-144">En este ejemplo se configuran estas opciones de configuración en el buzón de sala denominado Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="8d511-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="8d511-145">Para obtener información detallada sobre la sintaxis y los parámetros, consulte [set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="8d511-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="8d511-146">Conéctese a MS online PowerShell para establecer la configuración de Active Directory `Connect-MsolService -Credential $cred` ejecutando el cmdlet de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d511-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="8d511-147">Para obtener más información sobre Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="8d511-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="8d511-148">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.</span><span class="sxs-lookup"><span data-stu-id="8d511-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="8d511-149">Si no desea que la contraseña caduque, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8d511-149">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="8d511-150">Este ejemplo establece la contraseña de la cuenta ProjectRigel01@contoso.onmicrosoft.com para que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="8d511-150">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="8d511-151">También puede configurar un número de teléfono para la cuenta ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8d511-151">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="8d511-152">La cuenta del dispositivo debe tener una licencia válida de Office 365, o bien Exchange y Microsoft Teams o Skype empresarial no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="8d511-152">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="8d511-153">Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de dispositivo, lo cual determina qué SKU de licencia están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="8d511-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="8d511-154">Puedes usar`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="8d511-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="8d511-155">para recuperar una lista de las SKU disponibles para su inquilino de Office 365 de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8d511-155">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="8d511-156">A continuación, puede Agregar una licencia mediante el`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="8d511-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="8d511-157">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8d511-157">cmdlet.</span></span> <span data-ttu-id="8d511-158">En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="8d511-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="8d511-159">Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="8d511-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="8d511-160">A continuación, debe habilitar la cuenta del dispositivo con Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="8d511-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="8d511-161">Asegúrese de que su entorno cumple con los requisitos definidos en [los requisitos de salas de Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d511-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="8d511-162">Inicie una sesión remota de [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de la siguiente manera (Asegúrese de [instalar los componentes de PowerShell de Skype empresarial online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="8d511-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="8d511-163">A continuación, habilite la cuenta de salas de Microsoft Teams para Skype empresarial Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8d511-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="8d511-164">Obtenga la información de RegistrarPool de la nueva cuenta de usuario que se está configurando, como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8d511-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="8d511-165">Es posible que no se creen nuevas cuentas de usuario en el mismo grupo de registradores que las cuentas de usuario existentes en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="8d511-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="8d511-166">El comando anterior evitará errores en la configuración de la cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="8d511-166">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="8d511-167">Una vez completados los pasos anteriores para habilitar su cuenta de salas de Microsoft Teams en Microsoft Teams o Skype empresarial online, debe asignar una licencia a un dispositivo de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d511-167">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="8d511-168">Con el portal administrativo de Office 365, asigne una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3) al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d511-168">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="8d511-169">Asignar una licencia a su cuenta</span><span class="sxs-lookup"><span data-stu-id="8d511-169">Assign a license to your account</span></span>

1. <span data-ttu-id="8d511-170">Inicie sesión como administrador de inquilinos, abra el portal administrativo de Office 365 y haga clic en la aplicación de administrador.</span><span class="sxs-lookup"><span data-stu-id="8d511-170">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="8d511-171">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="8d511-171">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="8d511-172">Seleccione la cuenta salas de Microsoft Teams y, a continuación, haga clic o pulse en el icono de lápiz, que significa editar.</span><span class="sxs-lookup"><span data-stu-id="8d511-172">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="8d511-173">Haga clic en la opción **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="8d511-173">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="8d511-174">En la sección **asignar licencias** , debe seleccionar Skype empresarial online (plan 2) o Skype empresarial online (Plan 3), en función de sus licencias y de lo que haya decidido en términos de necesidad de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="8d511-174">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="8d511-175">Tendrá que usar una licencia de Plan 3 Si quiere usar PBX en la nube en salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d511-175">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="8d511-176">Para la conectividad de voz, como mínimo necesitará PBX en la nube.</span><span class="sxs-lookup"><span data-stu-id="8d511-176">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="8d511-177">Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC.</span><span class="sxs-lookup"><span data-stu-id="8d511-177">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="8d511-178">Para obtener más información, vea [licencias de salas de Microsoft Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .</span><span class="sxs-lookup"><span data-stu-id="8d511-178">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="8d511-179">Haga clic en **Guardar** para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="8d511-179">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="8d511-180">Ejemplo: configuración de la cuenta de sala en Exchange Online y Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="8d511-180">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="8d511-181">Comandos de Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8d511-181">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="8d511-182">Comandos de Azure Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8d511-182">Azure Active Directory PowerShell commands:</span></span>

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

<span data-ttu-id="8d511-183">Comando de PowerShell de Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="8d511-183">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="8d511-184">De esta manera, se agregan CloudPBX y PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="8d511-184">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="8d511-185">Además, tendrá que usar la interfaz de administración para asignar un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="8d511-185">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="8d511-186">Valide</span><span class="sxs-lookup"><span data-stu-id="8d511-186">Validate</span></span>

<span data-ttu-id="8d511-187">Para la validación, debe poder usar cualquier cliente de Skype empresarial para iniciar sesión en la cuenta que ha creado.</span><span class="sxs-lookup"><span data-stu-id="8d511-187">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d511-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d511-188">See also</span></span>

[<span data-ttu-id="8d511-189">Configurar cuentas para salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d511-189">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="8d511-190">Plan para salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d511-190">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="8d511-191">Implementar salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d511-191">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="8d511-192">Configurar una consola de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d511-192">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="8d511-193">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d511-193">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="8d511-194">Licencias Rooms de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d511-194">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
