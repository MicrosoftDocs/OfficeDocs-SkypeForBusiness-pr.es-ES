---
title: Crear Microsoft Teams de recursos para barras de colaboración para Microsoft Teams usar PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar barras de colaboración para Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115608"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="29631-103">Crear una Microsoft 365 de recursos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="29631-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="29631-104">Lea este tema para obtener información sobre cómo crear cuentas de recursos para barras de colaboración Microsoft Teams usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29631-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="29631-105">La forma más sencilla de crear una cuenta de recursos es mediante el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="29631-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="29631-106">[Vea este artículo sobre cómo hacerlo](resource-account-ui.md).</span><span class="sxs-lookup"><span data-stu-id="29631-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="29631-107">Requirements</span><span class="sxs-lookup"><span data-stu-id="29631-107">Requirements</span></span>

<span data-ttu-id="29631-108">Antes de implementar Salas de Microsoft Teams con Office 365, asegúrese de que ha cumplido los requisitos.</span><span class="sxs-lookup"><span data-stu-id="29631-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="29631-109">Para obtener más información, vea [Implementar barras de colaboración para Microsoft Teams](collab-bar-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="29631-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="29631-110">Si necesita funcionalidades RTC para la barra de colaboración, necesitará Sistema telefónico licencia.</span><span class="sxs-lookup"><span data-stu-id="29631-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="29631-111">Las cuentas de recursos deben tener Exchange buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="29631-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="29631-112">Como se trata de cuentas de recursos, no Exchange licencia.</span><span class="sxs-lookup"><span data-stu-id="29631-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="29631-113">Se recomienda el uso de la licencia salas de reuniones para cuentas de recursos.</span><span class="sxs-lookup"><span data-stu-id="29631-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="29631-114">Agregar una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="29631-114">Add a resource account</span></span>

1. <span data-ttu-id="29631-115">Conectar para Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29631-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="29631-116">Para obtener instrucciones, [vea Conectar para Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span><span class="sxs-lookup"><span data-stu-id="29631-116">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="29631-117">En Exchange Online PowerShell, cree un buzón de sala o modifique un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="29631-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="29631-118">Para crear un buzón de sala nuevo, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="29631-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="29631-119">En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="29631-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="29631-120">Nombre: Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="29631-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="29631-121">Alias: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="29631-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="29631-122">Cuenta: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="29631-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="29631-123">Contraseña de la cuenta: P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="29631-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="29631-124">Para modificar un buzón de sala existente, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="29631-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="29631-125">Este ejemplo habilita la cuenta para el buzón de sala existente que tiene el valor de alias HuddleRoom02 y establece la contraseña en 808P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="29631-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="29631-126">Tenga en cuenta que la cuenta se HuddleRoom02@contoso.onmicrosoft.com debido al valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="29631-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="29631-127">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Nuevo buzón](/powershell/module/exchange/mailboxes/new-mailbox) y Conjunto [de buzones.](/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="29631-127">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="29631-128">En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de la reunión:</span><span class="sxs-lookup"><span data-stu-id="29631-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="29631-129">AutomateProcessing: AutoAccept (Los organizadores de la reunión reciben la decisión de reserva de sala directamente sin intervención humana: gratis = aceptar; ocupado = rechazar).</span><span class="sxs-lookup"><span data-stu-id="29631-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="29631-130">AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="29631-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="29631-131">DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="29631-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="29631-132">DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="29631-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="29631-133">RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).</span><span class="sxs-lookup"><span data-stu-id="29631-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="29631-134">AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).</span><span class="sxs-lookup"><span data-stu-id="29631-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="29631-135">AdditionalResponse: "Esta sala tiene una barra de colaboración para Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="29631-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="29631-136">(El texto adicional que se agregará a la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="29631-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="29631-137">En este ejemplo se configuran estas opciones en el buzón de sala llamado Huddle-Room-01.</span><span class="sxs-lookup"><span data-stu-id="29631-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="29631-138">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="29631-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="29631-139">Conectar PowerShell de MS Online para realizar la configuración de Active Directory ejecutando el `Connect-MsolService -Credential $cred` cmdlet de powershell.</span><span class="sxs-lookup"><span data-stu-id="29631-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="29631-140">Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="29631-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="29631-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.</span><span class="sxs-lookup"><span data-stu-id="29631-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="29631-142">Establezca la contraseña de huddleroom01@contoso.onmicrosoft.com que no expire con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="29631-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="29631-143">La cuenta de recursos debe tener una licencia Office 365, preferiblemente la SKU Sala de reuniones recursos.</span><span class="sxs-lookup"><span data-stu-id="29631-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="29631-144">También debe asignar una ubicación de uso a su cuenta de dispositivo, lo que determina qué SKU de licencia están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="29631-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="29631-145">Puede usarlo para recuperar una lista de SKU disponibles `Get-MsolAccountSku` para su Office 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="29631-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="29631-146">Puede asignar la licencia con Set-MsolUserLicense.</span><span class="sxs-lookup"><span data-stu-id="29631-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="29631-147">Para obtener instrucciones [detalladas,](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)vea Asignar licencias a cuentas de usuario con Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29631-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="29631-148">Configurar cuentas para barras de colaboración para Microsoft Teams usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="29631-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="29631-149">Implementar barras de colaboración para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29631-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="29631-150">Barras de colaboración para Microsoft Teams licencias</span><span class="sxs-lookup"><span data-stu-id="29631-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)