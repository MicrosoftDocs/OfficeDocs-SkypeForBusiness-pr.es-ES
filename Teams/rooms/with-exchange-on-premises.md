---
title: Implementar Salas de Microsoft Teams con Exchange local
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams en un entorno híbrido con Exchange local.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117358"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="f6945-103">Implementar Salas de Microsoft Teams con Exchange local</span><span class="sxs-lookup"><span data-stu-id="f6945-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="f6945-104">Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams en un entorno híbrido con Exchange local y Microsoft Teams o Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="f6945-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="f6945-105">Si su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea, la configuración dependerá de dónde se hospeda cada servicio.</span><span class="sxs-lookup"><span data-stu-id="f6945-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="f6945-106">En este tema se tratan las implementaciones híbridas para Salas de Microsoft Teams con Exchange hospedadas localmente.</span><span class="sxs-lookup"><span data-stu-id="f6945-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="f6945-107">Dado que hay muchas variaciones diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas.</span><span class="sxs-lookup"><span data-stu-id="f6945-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="f6945-108">El siguiente proceso funcionará para muchas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="f6945-108">The following process will work for many configurations.</span></span> <span data-ttu-id="f6945-109">Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para lograr el mismo resultado final que se documenta aquí y para otras opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="f6945-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="f6945-110">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario Salas de Microsoft Teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="f6945-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="f6945-111">Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que Salas de Microsoft Teams dispositivo usará.</span><span class="sxs-lookup"><span data-stu-id="f6945-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f6945-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="f6945-112">Requirements</span></span>

<span data-ttu-id="f6945-113">Antes de implementar Salas de Microsoft Teams con Exchange local, asegúrese de que ha cumplido los requisitos.</span><span class="sxs-lookup"><span data-stu-id="f6945-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="f6945-114">Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="f6945-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="f6945-115">Si va a implementar Salas de Microsoft Teams con Exchange local, va a usar las herramientas administrativas de Active Directory para agregar una dirección de correo electrónico para su cuenta de dominio local.</span><span class="sxs-lookup"><span data-stu-id="f6945-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="f6945-116">Esta cuenta se sincronizará con Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6945-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f6945-117">Tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6945-117">You will need to:</span></span>
  
- <span data-ttu-id="f6945-118">Crear una cuenta y sincronizarla con Active Directory</span><span class="sxs-lookup"><span data-stu-id="f6945-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="f6945-119">Habilitar el buzón de correo remoto y establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="f6945-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="f6945-120">Asigne una Microsoft 365 o Office 365 licencia.</span><span class="sxs-lookup"><span data-stu-id="f6945-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="f6945-121">Habilite la cuenta del dispositivo con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f6945-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="f6945-122">Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:</span><span class="sxs-lookup"><span data-stu-id="f6945-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="f6945-123">Necesitará tener Skype Empresarial en línea (Plan 2) o superior en su plan Microsoft 365 o Office 365 plan.</span><span class="sxs-lookup"><span data-stu-id="f6945-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="f6945-124">El plan debe admitir la funcionalidad de conferencias.</span><span class="sxs-lookup"><span data-stu-id="f6945-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="f6945-125">Si necesita Telefonía IP empresarial (telefonía RTC) con proveedores de servicios de telefonía para Salas de Microsoft Teams necesita Skype Empresarial En línea (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="f6945-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="f6945-126">Al configurar una cuenta de salón con Microsoft Teams o Skype Empresarial En línea, el número de teléfono debe asignarse antes de que la cuenta se habilite como una cuenta de salón.</span><span class="sxs-lookup"><span data-stu-id="f6945-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="f6945-127">Los usuarios de inquilino deben tener Exchange buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="f6945-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="f6945-128">Su Salas de Microsoft Teams cuenta requiere una licencia de Skype Empresarial Online (Plan 2) o Skype Empresarial Online (Plan 3), pero no requiere una licencia Exchange Online usuario.</span><span class="sxs-lookup"><span data-stu-id="f6945-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="f6945-129">Asigne una Skype Empresarial Server a su Salas de Microsoft Teams cuenta.</span><span class="sxs-lookup"><span data-stu-id="f6945-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="f6945-130">Crear una cuenta y sincronizarla con Active Directory</span><span class="sxs-lookup"><span data-stu-id="f6945-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="f6945-131">En la herramienta Usuarios y equipos de **Active Directory,** haga clic con el botón derecho en la carpeta o unidad organizativa en la que se crearán las cuentas de Salas de Microsoft Teams, haga clic en Nuevo y, a continuación, haga clic en **Usuario.**</span><span class="sxs-lookup"><span data-stu-id="f6945-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="f6945-p107">Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6945-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="f6945-p108">Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.</span><span class="sxs-lookup"><span data-stu-id="f6945-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6945-137">Seleccionar **Contraseña nunca expira es** un requisito para Skype Empresarial Server en Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6945-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="f6945-138">Es posible que las reglas de dominio prohíban las contraseñas que no expiran.</span><span class="sxs-lookup"><span data-stu-id="f6945-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="f6945-139">Si es así, deberá crear una excepción para cada cuenta Salas de Microsoft Teams dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f6945-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="f6945-140">Tras crear la cuenta, ejecute una sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="f6945-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="f6945-141">Cuando haya finalizado, vaya a la página usuarios de su centro de administración de Microsoft 365 y compruebe que la cuenta creada en los pasos anteriores se ha combinado con la en línea.</span><span class="sxs-lookup"><span data-stu-id="f6945-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="f6945-142">Habilitar el buzón de correo remoto y establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="f6945-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="f6945-143">[Abra el Exchange de administración](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o conéctese a su servidor Exchange con [PowerShell remoto.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="f6945-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="f6945-144">En Exchange PowerShell, cree un buzón para la cuenta (habilitar el buzón de la cuenta) ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f6945-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="f6945-145">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Habilitar buzón.](/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f6945-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="f6945-146">En Exchange PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:</span><span class="sxs-lookup"><span data-stu-id="f6945-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="f6945-147">AutomateProcessing: AutoAccept (Los organizadores de la reunión reciben la decisión de reserva de sala directamente sin intervención humana: gratis = aceptar; ocupado = rechazar).</span><span class="sxs-lookup"><span data-stu-id="f6945-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="f6945-148">AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="f6945-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="f6945-149">DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="f6945-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="f6945-150">DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="f6945-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="f6945-151">RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).</span><span class="sxs-lookup"><span data-stu-id="f6945-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="f6945-152">AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).</span><span class="sxs-lookup"><span data-stu-id="f6945-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="f6945-153">AdditionalResponse: "Esta es una sala Skype reunión"</span><span class="sxs-lookup"><span data-stu-id="f6945-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="f6945-154">(El texto adicional que se agregará a la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="f6945-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="f6945-155">En este ejemplo se configuran estas opciones en el buzón de sala Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="f6945-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="f6945-156">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="f6945-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="f6945-157">Asignar una Microsoft 365 o Office 365 licencia</span><span class="sxs-lookup"><span data-stu-id="f6945-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="f6945-158">Conectar Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6945-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="f6945-159">Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="f6945-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="f6945-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.</span><span class="sxs-lookup"><span data-stu-id="f6945-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="f6945-161">La cuenta del dispositivo debe tener una licencia Microsoft 365 o Office 365, o Exchange y Microsoft Teams no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="f6945-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="f6945-162">Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de dispositivo, lo que determina qué SKU de licencia están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="f6945-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="f6945-163">Puede usar `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="f6945-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="f6945-164">para recuperar una lista de SKU disponibles.</span><span class="sxs-lookup"><span data-stu-id="f6945-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="f6945-165">A continuación, puede agregar una licencia con el `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="f6945-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="f6945-166">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f6945-166">cmdlet.</span></span> <span data-ttu-id="f6945-167">En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="f6945-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="f6945-168">Para obtener instrucciones [detalladas,](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)vea Asignar licencias a cuentas de usuario con Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6945-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="f6945-169">Habilitar la cuenta del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f6945-169">Enable the device account</span></span>

<span data-ttu-id="f6945-170">Skype Empresarial PowerShell en línea se usa para administrar servicios para Microsoft Teams y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="f6945-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="f6945-171">Cree una sesión de Windows PowerShell remoto desde un equipo como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="f6945-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="f6945-172">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="f6945-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="f6945-173">Si usa la versión pública más [reciente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar el Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="f6945-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="f6945-174">Obtener la dirección SIP de la cuenta:</span><span class="sxs-lookup"><span data-stu-id="f6945-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="f6945-175">**Opcional.**</span><span class="sxs-lookup"><span data-stu-id="f6945-175">**Optional.**</span></span> <span data-ttu-id="f6945-176">Si desea asignar un número de teléfono a la cuenta, la operación debe realizarse en este momento.</span><span class="sxs-lookup"><span data-stu-id="f6945-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="f6945-177">Si desea asignar un número de teléfono de enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="f6945-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="f6945-178">Si va a asignar un número de teléfono proporcionado por Microsoft, use el cmdlet siguiente después de haber aprovisionado al usuario con una licencia de Plan de llamadas:</span><span class="sxs-lookup"><span data-stu-id="f6945-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="f6945-179">Para habilitar su Salas de Microsoft Teams cuenta, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="f6945-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="f6945-180">Si no está seguro del valor que debe usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario existente con este comando:</span><span class="sxs-lookup"><span data-stu-id="f6945-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="f6945-181">Asignar una licencia a su Salas de Microsoft Teams cuenta</span><span class="sxs-lookup"><span data-stu-id="f6945-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="f6945-182">Inicie sesión como administrador de inquilinos, abra el Microsoft 365 de administración y haga clic en la aplicación Administrador.</span><span class="sxs-lookup"><span data-stu-id="f6945-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="f6945-183">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="f6945-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="f6945-184">Haga clic en Salas de Microsoft Teams cuenta y, a continuación, haga clic en el icono del lápiz para editar la información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="f6945-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="f6945-185">Haga clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="f6945-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="f6945-186">En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f6945-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="f6945-187">Tendrá que usar una licencia de Plan 3 si desea usar Telefonía IP empresarial en su Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6945-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="f6945-188">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6945-188">Click **Save**.</span></span>

<span data-ttu-id="f6945-189">Para la validación, debería poder usar cualquier cliente para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="f6945-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f6945-190">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f6945-190">Related topics</span></span>

[<span data-ttu-id="f6945-191">Configurar cuentas para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6945-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="f6945-192">Plan para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6945-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="f6945-193">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6945-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="f6945-194">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6945-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="f6945-195">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6945-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)