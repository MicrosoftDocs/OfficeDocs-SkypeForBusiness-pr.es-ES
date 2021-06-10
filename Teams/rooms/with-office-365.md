---
title: Implementar Salas de Microsoft Teams con Microsoft 365 o Office 365
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
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Microsoft 365 o Office 365, donde Teams o Skype Empresarial y Exchange están en línea.
ms.openlocfilehash: 64567cd9925a0a11d9e9b896c522a2c4bfe13f40
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739650"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="da9ce-103">Implementar Salas de Microsoft Teams con Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="da9ce-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="da9ce-104">Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Microsoft 365 o Office 365, donde Microsoft Teams o Skype Empresarial y Exchange están en línea.</span><span class="sxs-lookup"><span data-stu-id="da9ce-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="da9ce-105">La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante el uso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da9ce-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="da9ce-106">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario Salas de Microsoft Teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="da9ce-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="da9ce-107">Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que Salas de Microsoft Teams dispositivo usará.</span><span class="sxs-lookup"><span data-stu-id="da9ce-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="da9ce-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="da9ce-108">Requirements</span></span>

<span data-ttu-id="da9ce-109">Antes de implementar Salas de Microsoft Teams con Microsoft 365 o Office 365, asegúrese de que ha cumplido los requisitos.</span><span class="sxs-lookup"><span data-stu-id="da9ce-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="da9ce-110">Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="da9ce-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="da9ce-111">Para habilitar Skype Empresarial, debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da9ce-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="da9ce-112">Skype Empresarial En línea (Plan 2 o un plan basado Enterprise) o superior en su plan Microsoft 365 o Office 365 plan.</span><span class="sxs-lookup"><span data-stu-id="da9ce-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="da9ce-113">El plan debe permitir las capacidades de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="da9ce-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="da9ce-114">Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una licencia de audioconferencia y Sistema telefónico local.</span><span class="sxs-lookup"><span data-stu-id="da9ce-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="da9ce-115">Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una licencia de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="da9ce-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="da9ce-116">Los usuarios de inquilino deben tener Exchange buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="da9ce-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="da9ce-117">Su Salas de Microsoft Teams cuenta requiere como mínimo una licencia de Skype Empresarial Online (Plan 2), pero no requiere una Exchange Online licencia.</span><span class="sxs-lookup"><span data-stu-id="da9ce-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="da9ce-118">Vea [Salas de Microsoft Teams licencias para](rooms-licensing.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="da9ce-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="da9ce-119">Para obtener más información Skype Empresarial planes en línea, vea [la Skype Empresarial descripción del servicio en línea.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="da9ce-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="da9ce-120">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="da9ce-120">Add a device account</span></span>

1. <span data-ttu-id="da9ce-121">Conectar para Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da9ce-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="da9ce-122">Para obtener instrucciones, [vea Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="da9ce-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="da9ce-123">En Exchange Online PowerShell, cree un buzón de sala o modifique un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="da9ce-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="da9ce-124">De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que deberá agregar una cuenta al crear o modificar un buzón de sala que le permita autenticarse con Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="da9ce-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="da9ce-125">Para crear un buzón de sala nuevo, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="da9ce-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="da9ce-126">En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="da9ce-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="da9ce-127">Nombre: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="da9ce-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="da9ce-128">Alias: Rigel1</span><span class="sxs-lookup"><span data-stu-id="da9ce-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="da9ce-129">Cuenta: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="da9ce-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="da9ce-130">Contraseña de la cuenta: P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="da9ce-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="da9ce-131">Para modificar un buzón de sala existente, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="da9ce-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="da9ce-132">En este ejemplo, se habilita la cuenta para el buzón de sala existente que tiene el valor de alias Rigel2 y se establece la contraseña en 9898P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="da9ce-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="da9ce-133">Tenga en cuenta que la cuenta se Rigel2@contoso.onmicrosoft.com debido al valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="da9ce-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="da9ce-134">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Nuevo buzón](/powershell/module/exchange/mailboxes/new-mailbox) y Conjunto [de buzones.](/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="da9ce-134">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="da9ce-135">En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de la reunión:</span><span class="sxs-lookup"><span data-stu-id="da9ce-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="da9ce-136">AutomateProcessing: AutoAccept (Los organizadores de la reunión reciben la decisión de reserva de sala directamente sin intervención humana: gratis = aceptar; ocupado = rechazar).</span><span class="sxs-lookup"><span data-stu-id="da9ce-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="da9ce-137">AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="da9ce-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="da9ce-138">DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="da9ce-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="da9ce-139">DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="da9ce-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="da9ce-140">RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).</span><span class="sxs-lookup"><span data-stu-id="da9ce-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="da9ce-141">AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).</span><span class="sxs-lookup"><span data-stu-id="da9ce-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="da9ce-142">AdditionalResponse: "Esta es una sala Skype reunión"</span><span class="sxs-lookup"><span data-stu-id="da9ce-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="da9ce-143">(El texto adicional que se agregará a la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="da9ce-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="da9ce-144">En este ejemplo se configuran estas opciones en el buzón de sala denominado Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="da9ce-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="da9ce-145">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="da9ce-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="da9ce-146">Conectar a MS Online PowerShell para realizar la configuración de Active Directory ejecutando el `Connect-MsolService -Credential $cred` cmdlet de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da9ce-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="da9ce-147">Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="da9ce-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="da9ce-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.</span><span class="sxs-lookup"><span data-stu-id="da9ce-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="da9ce-149">Si no desea que la contraseña expire, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="da9ce-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="da9ce-150">En este ejemplo se establece la contraseña de la cuenta Rigel1@contoso.onmicrosoft.com que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="da9ce-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="da9ce-151">También puede establecer un número de teléfono para la cuenta ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="da9ce-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > <span data-ttu-id="da9ce-152">Si la contraseña no está establecida en Nunca expirar, la cuenta ya no iniciará sesión en el dispositivo cuando la cuenta llegue al período de expiración.</span><span class="sxs-lookup"><span data-stu-id="da9ce-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="da9ce-153">La contraseña tendrá que cambiarse para la cuenta y también actualizarse localmente en el dispositivo MTR.</span><span class="sxs-lookup"><span data-stu-id="da9ce-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="da9ce-154">La cuenta del dispositivo debe tener una licencia Microsoft 365 o Office 365 válida, o Exchange y Microsoft Teams o Skype Empresarial no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="da9ce-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="da9ce-155">Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de dispositivo, lo que determina qué SKU de licencia están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="da9ce-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="da9ce-156">Puede usar `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="da9ce-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="da9ce-157">para recuperar una lista de SKU disponibles para su Microsoft 365 o Office 365 organización de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="da9ce-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="da9ce-158">A continuación, puede agregar una licencia con el `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="da9ce-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="da9ce-159">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="da9ce-159">cmdlet.</span></span> <span data-ttu-id="da9ce-160">En este ejemplo se agrega Sala de reuniones licencia a la cuenta:</span><span class="sxs-lookup"><span data-stu-id="da9ce-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="da9ce-161">Para obtener instrucciones [detalladas,](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)vea Asignar licencias a cuentas de usuario con Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da9ce-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="da9ce-162">También puede agregar Sistema telefónico a esta cuenta, pero primero tiene que configurarla.</span><span class="sxs-lookup"><span data-stu-id="da9ce-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="da9ce-163">Vea [¿Qué Sistema telefónico?](../what-is-phone-system-in-office-365.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="da9ce-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="da9ce-164">En este ejemplo se agrega el plan de llamadas RTC nacionales e internacionales:</span><span class="sxs-lookup"><span data-stu-id="da9ce-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > <span data-ttu-id="da9ce-165">Si está configurando Salas de Teams unirse de forma nativa a Microsoft Teams reuniones, no debe continuar con el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="da9ce-165">If you are configuring Teams Rooms to only natively join Microsoft Teams meetings, you should not proceed with the following step.</span></span> <span data-ttu-id="da9ce-166">Lo siguiente solo es necesario si también habilitará la compatibilidad con Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="da9ce-166">The following is only required if you will also be enabling support for Skype for Business on-premises.</span></span>

7. <span data-ttu-id="da9ce-167">Para habilitar la cuenta del dispositivo Skype Empresarial local, asegúrese de que su entorno cumple los requisitos definidos [en Salas de Microsoft Teams requisitos.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="da9ce-167">To enable the device account with Skype for Business on-premises, be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="da9ce-168">Inicie una sesión [Windows PowerShell remoto](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de la siguiente manera (asegúrese de instalar Skype Empresarial [de PowerShell en línea):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="da9ce-168">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   > [!NOTE]
   > <span data-ttu-id="da9ce-169">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="da9ce-169">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="da9ce-170">Si usa la versión pública más [reciente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar el Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="da9ce-170">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   <span data-ttu-id="da9ce-171">Obtenga la información de RegistrarPool de la nueva cuenta de usuario que se está configurando, como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="da9ce-171">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="da9ce-172">A continuación, habilite Salas de Microsoft Teams cuenta de Skype Empresarial Server ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="da9ce-172">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="da9ce-173">Es posible que las nuevas cuentas de usuario no se crean en el mismo grupo de registradores que las cuentas de usuario existentes en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="da9ce-173">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="da9ce-174">El comando anterior evitará errores en la configuración de la cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="da9ce-174">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="da9ce-175">Validar</span><span class="sxs-lookup"><span data-stu-id="da9ce-175">Validate</span></span>

<span data-ttu-id="da9ce-176">Para la validación, debería poder usar cualquier Skype Empresarial cliente para iniciar sesión en la cuenta que creó.</span><span class="sxs-lookup"><span data-stu-id="da9ce-176">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="da9ce-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="da9ce-177">See also</span></span>

[<span data-ttu-id="da9ce-178">Configurar cuentas para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da9ce-178">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="da9ce-179">Plan para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da9ce-179">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="da9ce-180">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da9ce-180">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="da9ce-181">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da9ce-181">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="da9ce-182">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da9ce-182">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="da9ce-183">Salas de Microsoft Teams Licencias</span><span class="sxs-lookup"><span data-stu-id="da9ce-183">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
