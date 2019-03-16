---
title: Implementar Sistemas de salas de Skype v2 con Office 365
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Office 365.
ms.openlocfilehash: a931ec6cb55e654612c451f15d4a4895f61ba990
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645390"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="0ea01-103">Implementar Sistemas de salas de Skype v2 con Office 365 </span><span class="sxs-lookup"><span data-stu-id="0ea01-103">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="0ea01-104">Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Office 365, donde Skype para empresas y Exchange estén en línea.</span><span class="sxs-lookup"><span data-stu-id="0ea01-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="0ea01-105">La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="0ea01-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="0ea01-106">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudarle a convertirlas en cuentas de usuario de v2 de Skype salón sistemas compatibles.</span><span class="sxs-lookup"><span data-stu-id="0ea01-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="0ea01-107">Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="0ea01-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="0ea01-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ea01-108">Requirements</span></span>

<span data-ttu-id="0ea01-109">Antes de implementar sistemas de salón de Skype v2 con Office 365, asegúrese de que cumplen los requisitos.</span><span class="sxs-lookup"><span data-stu-id="0ea01-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="0ea01-110">Para más información, vea [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea01-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

<span data-ttu-id="0ea01-111">Para habilitar Skype para la empresa, debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ea01-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="0ea01-112">Skype para profesionales Online (Plan 2 o un plan de empresa) o superior en su plan de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ea01-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="0ea01-113">El plan debe permitir que las capacidades de conferencia de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="0ea01-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="0ea01-114">Si necesita capacidades de marcado de una reunión, necesitará una conferencia de audio y la licencia del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="0ea01-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="0ea01-115">Si necesita las capacidades de acceso telefónico de salida de una reunión, necesitará un nacionales o nacional e internacional de llamada Plan.</span><span class="sxs-lookup"><span data-stu-id="0ea01-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="0ea01-116">Los usuarios de inquilinos deben tener los buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ea01-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="0ea01-117">Su cuenta de Skype salón sistemas v2 requieren como mínimo un Skype para licencia empresarial Online (Plan 2), pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0ea01-117">Your Skype Room Systems v2 account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="0ea01-118">Para obtener información detallada, vea [sistemas de salón de Skype v2 licencia](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="0ea01-118">See [Skype Room Systems v2 Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="0ea01-119">Para obtener información detallada en Skype para planes de negocios de en línea, vea la [Skype para la descripción de servicio en línea de negocio](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ea01-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="0ea01-120">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0ea01-120">Add a device account</span></span>

https://docs.microsoft.com/en-us/powershell/module/msonline/?view=azureadps-1.0

https://docs.microsoft.com/en-us/powershell/module/Azuread/?view=azureadps-2.0 


1. <span data-ttu-id="0ea01-121">Conectarse a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ea01-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="0ea01-122">Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="0ea01-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="0ea01-123">En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="0ea01-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="0ea01-124">De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que necesitará para agregar una cuenta al crear o modificar un buzón de sala que le permite autenticar con sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="0ea01-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="0ea01-125">Para crear un nuevo buzón de sala, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0ea01-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="0ea01-126">En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="0ea01-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="0ea01-127">Nombre: Proyecto-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="0ea01-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="0ea01-128">Alias: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="0ea01-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="0ea01-129">Cuenta: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0ea01-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="0ea01-130">Contraseña de la cuenta: P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="0ea01-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="0ea01-131">Para modificar un buzón de sala existente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0ea01-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="0ea01-132">En este ejemplo se habilita la cuenta para el buzón de sala existente que tiene el valor de alias ProjectRigel02 y se establece la contraseña en 9898P@$$W0rd.</span><span class="sxs-lookup"><span data-stu-id="0ea01-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="0ea01-133">Tenga en cuenta que la cuenta será ProjectRigel02@contoso.onmicrosoft.com debido al valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="0ea01-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="0ea01-134">Para obtener información de parámetro y detallada sobre la sintaxis, vea [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="0ea01-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="0ea01-135">En Exchange Online PowerShell, configure las opciones siguientes en el buzón de sala para mejorar la experiencia de reunión:</span><span class="sxs-lookup"><span data-stu-id="0ea01-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="0ea01-136">AutomateProcessing: AutoAccept (los organizadores de reuniones reciben la decisión de reserva de sala directamente sin intervención humana: libre = acepte; ocupado = rechazar.)</span><span class="sxs-lookup"><span data-stu-id="0ea01-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="0ea01-137">AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).</span><span class="sxs-lookup"><span data-stu-id="0ea01-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="0ea01-138">DeleteComments: $false (mantener el texto del cuerpo del mensaje de convocatorias de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="0ea01-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="0ea01-139">DeleteSubject: $false (conservar el asunto de convocatorias de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="0ea01-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="0ea01-140">RemovePrivateProperty: $false (garantiza la marca privada que se envió el organizador de la reunión original permanece tal como se especifica de solicitudes).</span><span class="sxs-lookup"><span data-stu-id="0ea01-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="0ea01-141">AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).</span><span class="sxs-lookup"><span data-stu-id="0ea01-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="0ea01-142">AdditionalResponse: "ésta es una sala de reuniones de Skype!"</span><span class="sxs-lookup"><span data-stu-id="0ea01-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="0ea01-143">(El texto adicional para agregar a la convocatoria de reunión).</span><span class="sxs-lookup"><span data-stu-id="0ea01-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="0ea01-144">En este ejemplo se configura estas opciones de configuración en el buzón de sala denominado Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="0ea01-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="0ea01-145">Para obtener información de parámetro y detallada sobre la sintaxis, vea [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="0ea01-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="0ea01-146">Conectar con Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ea01-146">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="0ea01-147">Para obtener instrucciones, vea [Conectar con Azure Active Directory PowerShell para el módulo de gráfico](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="0ea01-147">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

5. <span data-ttu-id="0ea01-148">Si no desea que la contraseña a punto de caducar, use la siguiente sintaxis en Azure Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0ea01-148">If you do not want the password to expire, use the following syntax in Azure Active Directory PowerShell:</span></span>

   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```

   <span data-ttu-id="0ea01-149">En este ejemplo se establece la contraseña de la cuenta ProjectRigel01@contoso.onmicrosoft.com para que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="0ea01-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ```

   <span data-ttu-id="0ea01-150">También puede establecer un número de teléfono de la cuenta, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ea01-150">You can also set a phone number for the account by running the following command:</span></span>

   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```

6. <span data-ttu-id="0ea01-151">La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Skype para la empresa no funcionará.</span><span class="sxs-lookup"><span data-stu-id="0ea01-151">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="0ea01-152">Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="0ea01-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="0ea01-153">Puede usar Get-AzureADSubscribedSku para recuperar una lista de SKU disponibles para el inquilino de Office 365, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="0ea01-153">You can use Get-AzureADSubscribedSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```

   <span data-ttu-id="0ea01-154">A continuación, puede agregar una licencia con el cmdlet Set-AzureADUserLicense.</span><span class="sxs-lookup"><span data-stu-id="0ea01-154">Next, you can add a license using the Set-AzureADUserLicense cmdlet.</span></span> <span data-ttu-id="0ea01-155">En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="0ea01-155">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

   <span data-ttu-id="0ea01-156">Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0ea01-156">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="0ea01-157">A continuación, deberá habilitar la cuenta del dispositivo con Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="0ea01-157">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="0ea01-158">Asegúrese de que su entorno cumple con los requisitos tal como se define en [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea01-158">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

   <span data-ttu-id="0ea01-159">Iniciar una [sesión de Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de remota como se muestra a continuación (asegúrese de [instalar Skype para componentes de PowerShell en línea de negocio](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="0ea01-159">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="0ea01-160">A continuación, habilitar su cuenta de Skype salón sistemas v2 de Skype para Business Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0ea01-160">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="0ea01-161">Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0ea01-161">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="0ea01-162">No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="0ea01-162">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="0ea01-163">El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="0ea01-163">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="0ea01-164">Una vez haya completado los pasos anteriores para habilitar su cuenta de v2 de sistemas de salón de Skype en Skype para profesionales en línea, debe asignar una licencia a dispositivos de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="0ea01-164">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="0ea01-165">Uso del portal administrativo de Office 365, asignar puede ser un Skype para profesionales Online (Plan 2) o un Skype para licencia empresarial Online (Plan 3) para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ea01-165">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="0ea01-166">Asignar una licencia a su cuenta</span><span class="sxs-lookup"><span data-stu-id="0ea01-166">Assign a license to your account</span></span>

1. <span data-ttu-id="0ea01-167">Inicio de sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="0ea01-167">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="0ea01-168">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="0ea01-168">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="0ea01-169">Seleccione la cuenta de v2 de sistemas de salón de Skype y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.</span><span class="sxs-lookup"><span data-stu-id="0ea01-169">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="0ea01-170">Haga clic en la opción **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="0ea01-170">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="0ea01-171">En la sección **asignación de licencias** , es necesario seleccionar Skype para profesionales Online (Plan 2) o Skype para profesionales Online (Plan 3), en función de la concesión de licencias y que haya decidido en cuanto a la necesidad de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0ea01-171">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="0ea01-172">Debe utilizar una licencia de planeación 3 si desea usar en la nube PBX en sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="0ea01-172">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="0ea01-173">Para la conectividad de voz, como mínimo necesitará PBX en la nube.</span><span class="sxs-lookup"><span data-stu-id="0ea01-173">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="0ea01-174">Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC.</span><span class="sxs-lookup"><span data-stu-id="0ea01-174">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="0ea01-175">Para obtener más información, vea [sistemas de salón de Skype v2 licencias](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .</span><span class="sxs-lookup"><span data-stu-id="0ea01-175">See [Skype Room Systems v2 licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="0ea01-176">Haga clic en **Guardar** para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="0ea01-176">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="0ea01-177">Ejemplo: Cuenta de sala del programa de instalación de Exchange Online y Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="0ea01-177">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="0ea01-178">Comandos de PowerShell en Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="0ea01-178">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="0ea01-179">Comandos de Azure Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0ea01-179">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<span data-ttu-id="0ea01-180">Skype para comandos de PowerShell de negocio:</span><span class="sxs-lookup"><span data-stu-id="0ea01-180">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="0ea01-181">De esta manera, se agregan CloudPBX y PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="0ea01-181">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="0ea01-182">Además, debe usar la interfaz de administración para asignar a un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="0ea01-182">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="0ea01-183">Validar</span><span class="sxs-lookup"><span data-stu-id="0ea01-183">Validate</span></span>

<span data-ttu-id="0ea01-184">Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en la cuenta que creó.</span><span class="sxs-lookup"><span data-stu-id="0ea01-184">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ea01-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ea01-185">See also</span></span>

[<span data-ttu-id="0ea01-186">Configurar cuentas para sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="0ea01-186">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="0ea01-187">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="0ea01-187">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="0ea01-188">Implementar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="0ea01-188">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)

[<span data-ttu-id="0ea01-189">Configurar una consola de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="0ea01-189">Configure a Skype Room Systems v2 console</span></span>](console.md)

[<span data-ttu-id="0ea01-190">Administrar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="0ea01-190">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[<span data-ttu-id="0ea01-191">Licencias de v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="0ea01-191">Skype Room Systems v2 Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
