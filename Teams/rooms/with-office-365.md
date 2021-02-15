---
title: Implementar salas de Microsoft Teams con Microsoft 365 u Office 365
ms.author: v-cichur
author: cichur
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Microsoft 365 u Office 365, donde Teams o Skype Empresarial y Exchange están ambos en línea.
ms.openlocfilehash: 4ec54763379e4a13a69eb3e08019924708873faf
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196214"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="057e2-103">Implementar salas de Microsoft Teams con Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="057e2-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="057e2-104">Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Microsoft 365 u Office 365, donde Microsoft Teams o Skype Empresarial y Exchange están ambos en línea.</span><span class="sxs-lookup"><span data-stu-id="057e2-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="057e2-105">La manera más sencilla de configurar las cuentas de usuario es configurarlas mediante cuentas de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="057e2-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="057e2-106">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario, o validar las cuentas de recursos existentes que tiene con el fin de ayudarle a convertirlas en cuentas de usuario compatibles de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="057e2-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="057e2-107">Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que usará el dispositivo de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="057e2-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="057e2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="057e2-108">Requirements</span></span>

<span data-ttu-id="057e2-109">Antes de implementar Salas de Microsoft Teams con Microsoft 365 u Office 365, asegúrese de que cumple los requisitos.</span><span class="sxs-lookup"><span data-stu-id="057e2-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="057e2-110">Para obtener más información, consulte los [requisitos de salas de Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="057e2-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="057e2-111">Para habilitar Skype Empresarial, debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="057e2-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="057e2-112">Skype Empresarial Online (plan 2 o plan basado en Enterprise) o superior en su plan de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="057e2-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="057e2-113">El plan debe permitir las capacidades de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="057e2-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="057e2-114">Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una licencia de Audioconferencia y sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="057e2-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="057e2-115">Si necesita funcionalidades de llamada a una reunión, necesitará una licencia de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="057e2-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="057e2-116">Los usuarios inquilinos deben tener buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="057e2-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="057e2-117">Su cuenta de Microsoft Teams Rooms requiere como mínimo una licencia de Skype Empresarial Online (Plan 2), pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="057e2-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="057e2-118">Consulte [las licencias de Salas de Microsoft Teams](rooms-licensing.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="057e2-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="057e2-119">Para obtener más información sobre los planes de Skype Empresarial Online, consulte la [Descripción del servicio de Skype Empresarial Online.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="057e2-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="057e2-120">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="057e2-120">Add a device account</span></span>

1. <span data-ttu-id="057e2-121">Conéctese a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="057e2-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="057e2-122">Para obtener instrucciones, [consulte Conectarse a Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=396554)</span><span class="sxs-lookup"><span data-stu-id="057e2-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="057e2-123">En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="057e2-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="057e2-124">De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que tendrá que agregar una cuenta al crear o modificar un buzón de sala que permita la autenticación con Sistemas de sala de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="057e2-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="057e2-125">Para crear un nuevo buzón de sala, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="057e2-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="057e2-126">En este ejemplo se crea un buzón de sala con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="057e2-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="057e2-127">Nombre: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="057e2-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="057e2-128">Alias: Rigel1</span><span class="sxs-lookup"><span data-stu-id="057e2-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="057e2-129">Cuenta: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="057e2-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="057e2-130">Contraseña de la cuenta: P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="057e2-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="057e2-131">Para modificar un buzón de sala existente, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="057e2-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="057e2-132">En este ejemplo se habilita la cuenta para el buzón de sala existente que tiene el valor alias Rigel2 y se establece la contraseña en 9898P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="057e2-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="057e2-133">Tenga en cuenta que la cuenta se Rigel2@contoso.onmicrosoft.com debido al valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="057e2-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="057e2-134">Para obtener sintaxis detallada e información de parámetros, vea [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="057e2-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="057e2-135">En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:</span><span class="sxs-lookup"><span data-stu-id="057e2-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="057e2-136">AutomateProcessing: AutoAccept (los organizadores de reuniones reciben la decisión de reserva de la sala directamente sin intervención humana: free = accept; busy = decline).</span><span class="sxs-lookup"><span data-stu-id="057e2-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="057e2-137">AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="057e2-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="057e2-138">DeleteComments: $false (mantenga cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="057e2-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="057e2-139">DeleteSubject: $false (mantener el asunto de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="057e2-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="057e2-140">RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).</span><span class="sxs-lookup"><span data-stu-id="057e2-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="057e2-141">AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).</span><span class="sxs-lookup"><span data-stu-id="057e2-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="057e2-142">Respuesta adicional: "¡Esta es una sala de reuniones de Skype!".</span><span class="sxs-lookup"><span data-stu-id="057e2-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="057e2-143">(El texto adicional que se agregará a la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="057e2-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="057e2-144">Este ejemplo configura estas opciones en el buzón de sala denominado Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="057e2-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="057e2-145">Para obtener sintaxis detallada e información sobre los parámetros, [vea Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="057e2-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="057e2-146">Conéctese a MS Online PowerShell para establecer la configuración de Active Directory ejecutando el `Connect-MsolService -Credential $cred` cmdlet de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="057e2-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="057e2-147">Para obtener más información sobre Active Directory, [consulte Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="057e2-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="057e2-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.</span><span class="sxs-lookup"><span data-stu-id="057e2-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="057e2-149">Si no desea que la contraseña expire, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="057e2-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="057e2-150">En este ejemplo se establece la contraseña de la cuenta Rigel1@contoso.onmicrosoft.com que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="057e2-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="057e2-151">También puede establecer un número de teléfono para la cuenta ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="057e2-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> <span data-ttu-id="057e2-152">Si la contraseña no se establece en Nunca expirar, la cuenta ya no se inicia sesión en el dispositivo cuando la cuenta llegue al período de expiración.</span><span class="sxs-lookup"><span data-stu-id="057e2-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="057e2-153">A continuación, deberá cambiar la contraseña de la cuenta y también actualizarse localmente en el dispositivo MTR.</span><span class="sxs-lookup"><span data-stu-id="057e2-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="057e2-154">La cuenta del dispositivo debe tener una licencia válida de Microsoft 365 u Office 365, o Exchange y Microsoft Teams o Skype Empresarial no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="057e2-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="057e2-155">Si tienes la licencia, tienes que asignar una ubicación de uso a tu cuenta del dispositivo( esto determina qué SKU de licencia están disponibles para tu cuenta).</span><span class="sxs-lookup"><span data-stu-id="057e2-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="057e2-156">Puede usar `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="057e2-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="057e2-157">para recuperar una lista de SKU disponibles para su organización de Microsoft 365 u Office 365 de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="057e2-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="057e2-158">A continuación, puede agregar una licencia con el `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="057e2-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="057e2-159">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="057e2-159">cmdlet.</span></span> <span data-ttu-id="057e2-160">En este ejemplo se agrega la licencia de sala de reuniones a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="057e2-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="057e2-161">Para obtener instrucciones [detalladas, consulte Asignar licencias a cuentas de usuario con PowerShell de Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="057e2-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="057e2-162">También puede agregar funcionalidades de Sistema telefónico a esta cuenta, pero primero tiene que configurarla.</span><span class="sxs-lookup"><span data-stu-id="057e2-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="057e2-163">Consulte [¿Qué es el sistema telefónico?](../what-is-phone-system-in-office-365.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="057e2-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="057e2-164">En este ejemplo se agrega el plan de llamadas RTC nacionales e internacionales:</span><span class="sxs-lookup"><span data-stu-id="057e2-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="057e2-165">A continuación, debe habilitar la cuenta del dispositivo con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="057e2-165">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="057e2-166">Asegúrese de que su entorno cumple los requisitos definidos en los [requisitos de Salas de Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="057e2-166">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="057e2-167">Inicie una sesión [de Windows PowerShell remota](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de la siguiente manera (asegúrese de instalar los componentes de [PowerShell de Skype Empresarial Online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="057e2-167">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="057e2-168">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="057e2-168">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="057e2-169">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="057e2-169">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="057e2-170">Obtenga la información de RegistrarPool de la nueva cuenta de usuario que se está configurando, como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="057e2-170">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="057e2-171">A continuación, habilite la cuenta de Salas de Microsoft Teams para Skype Empresarial Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="057e2-171">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="057e2-172">Es posible que no se puedan crear cuentas de usuario nuevas en el mismo grupo de registradores que las cuentas de usuario existentes en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="057e2-172">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="057e2-173">El comando anterior evitará errores en la configuración de la cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="057e2-173">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="057e2-174">Validar</span><span class="sxs-lookup"><span data-stu-id="057e2-174">Validate</span></span>

<span data-ttu-id="057e2-175">Para la validación, debería poder usar cualquier cliente de Skype Empresarial para iniciar sesión en la cuenta que creó.</span><span class="sxs-lookup"><span data-stu-id="057e2-175">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="057e2-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="057e2-176">See also</span></span>

[<span data-ttu-id="057e2-177">Configurar cuentas de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="057e2-177">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="057e2-178">Plan para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="057e2-178">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="057e2-179">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="057e2-179">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="057e2-180">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="057e2-180">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="057e2-181">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="057e2-181">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="057e2-182">Licencias de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="057e2-182">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
