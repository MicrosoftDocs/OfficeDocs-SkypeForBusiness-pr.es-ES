---
title: Implementar salas de Microsoft Teams con Exchange local
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
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams en un entorno híbrido con Exchange local.
ms.openlocfilehash: f9f80f5b993b9be95e35c8178d996973558e2512
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662325"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="bd6df-103">Implementar Salas de Microsoft Teams con Exchange local</span><span class="sxs-lookup"><span data-stu-id="bd6df-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="bd6df-104">Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams en un entorno híbrido con Exchange local y Microsoft Teams o Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bd6df-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="bd6df-105">Si su organización tiene una combinación de servicios, con algunos hospedados de forma local y otros en línea, la configuración dependerá de dónde se hospeda cada servicio.</span><span class="sxs-lookup"><span data-stu-id="bd6df-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="bd6df-106">Este tema trata sobre las implementaciones híbridas de salas de Microsoft Teams con Exchange hospedado localmente.</span><span class="sxs-lookup"><span data-stu-id="bd6df-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="bd6df-107">Debido a que hay tantas variantes diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas.</span><span class="sxs-lookup"><span data-stu-id="bd6df-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="bd6df-108">El proceso siguiente funcionará para muchas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="bd6df-108">The following process will work for many configurations.</span></span> <span data-ttu-id="bd6df-109">Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para lograr el mismo resultado final que se ha documentado aquí y para otras opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="bd6df-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="bd6df-110">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario, o validar las cuentas de recursos existentes que tiene con el fin de ayudarle a convertirlas en cuentas de usuario compatibles de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bd6df-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="bd6df-111">Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que usará el dispositivo de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="bd6df-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="bd6df-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd6df-112">Requirements</span></span>

<span data-ttu-id="bd6df-113">Antes de implementar salas de Microsoft Teams con Exchange local, asegúrese de que cumple los requisitos.</span><span class="sxs-lookup"><span data-stu-id="bd6df-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="bd6df-114">Para obtener más información, consulte los [requisitos de salas de Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="bd6df-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="bd6df-115">Si va a implementar Salas de Microsoft Teams con Exchange local, estará usando herramientas administrativas de Active Directory para agregar una dirección de correo electrónico para su cuenta de dominio local.</span><span class="sxs-lookup"><span data-stu-id="bd6df-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="bd6df-116">Esta cuenta se sincronizará con Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd6df-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bd6df-117">Tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd6df-117">You will need to:</span></span>
  
- <span data-ttu-id="bd6df-118">Crear una cuenta y sincronizarla con Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd6df-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="bd6df-119">Habilitar el buzón de correo remoto y establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="bd6df-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="bd6df-120">Asigne una licencia de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd6df-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="bd6df-121">Habilite la cuenta del dispositivo con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bd6df-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="bd6df-122">Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:</span><span class="sxs-lookup"><span data-stu-id="bd6df-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="bd6df-123">Necesitará tener Skype Empresarial Online (Plan 2) o posterior en su plan de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd6df-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="bd6df-124">El plan debe admitir la funcionalidad de conferencias.</span><span class="sxs-lookup"><span data-stu-id="bd6df-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="bd6df-125">Si necesita usar Telefonía IP empresarial (telefonía RTC) con proveedores de servicios de telefonía para salas de Microsoft Teams, necesita Skype Empresarial Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="bd6df-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="bd6df-126">Los usuarios inquilinos deben tener buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd6df-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="bd6df-127">Su cuenta de Salas de Microsoft Teams requiere una licencia de Skype Empresarial Online (Plan 2) o skype empresarial Online (Plan 3), pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bd6df-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="bd6df-128">Asigne una licencia de Skype Empresarial Server a su cuenta de Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="bd6df-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="bd6df-129">Crear una cuenta y sincronizarla con Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd6df-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="bd6df-130">En la herramienta Usuarios y equipos de **Active Directory,** haga clic con el botón derecho en la carpeta o unidad organizativa en la que se crearán sus cuentas de Salas de Microsoft Teams, haga clic en Nuevo **y,** a continuación, haga clic en **Usuario.**</span><span class="sxs-lookup"><span data-stu-id="bd6df-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="bd6df-p107">Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bd6df-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="bd6df-p108">Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.</span><span class="sxs-lookup"><span data-stu-id="bd6df-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd6df-136">Seleccionar la **contraseña nunca expira es** un requisito de Skype Empresarial Server en salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bd6df-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="bd6df-137">Es posible que las reglas de dominio prohíban las contraseñas que no expiran.</span><span class="sxs-lookup"><span data-stu-id="bd6df-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="bd6df-138">Si es así, tendrá que crear una excepción para cada cuenta de dispositivo de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bd6df-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="bd6df-139">Tras crear la cuenta, ejecute una sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="bd6df-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="bd6df-140">Cuando se complete, vaya a la página usuarios de su centro de administración de Microsoft 365 y compruebe que la cuenta creada con los pasos anteriores se ha combinado con la de Online.</span><span class="sxs-lookup"><span data-stu-id="bd6df-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="bd6df-141">Habilitar el buzón de correo remoto y establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="bd6df-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="bd6df-142">[Abra el Shell de administración de Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [conéctese al servidor de Exchange con PowerShell remoto.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="bd6df-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="bd6df-143">En Exchange PowerShell, cree un buzón para la cuenta (buzón habilitado para la cuenta) ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bd6df-143">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="bd6df-144">Para obtener sintaxis detallada e información sobre los parámetros, [vea Habilitar buzón.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="bd6df-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="bd6df-145">En Exchange PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:</span><span class="sxs-lookup"><span data-stu-id="bd6df-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="bd6df-146">AutomateProcessing: AutoAccept (los organizadores de reuniones reciben la decisión de reserva de sala directamente sin intervención humana: free = accept; busy = decline).</span><span class="sxs-lookup"><span data-stu-id="bd6df-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="bd6df-147">AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="bd6df-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="bd6df-148">DeleteComments: $false (mantenga cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="bd6df-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="bd6df-149">DeleteSubject: $false (mantener el asunto de las solicitudes de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="bd6df-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="bd6df-150">RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).</span><span class="sxs-lookup"><span data-stu-id="bd6df-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="bd6df-151">AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).</span><span class="sxs-lookup"><span data-stu-id="bd6df-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="bd6df-152">Respuesta adicional: "¡Esta es una sala de reuniones de Skype!".</span><span class="sxs-lookup"><span data-stu-id="bd6df-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="bd6df-153">(El texto adicional que se agregará a la solicitud de reunión).</span><span class="sxs-lookup"><span data-stu-id="bd6df-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="bd6df-154">Este ejemplo configura estas opciones en el buzón de sala denominado Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="bd6df-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="bd6df-155">Para obtener sintaxis detallada e información sobre los parámetros, [vea Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="bd6df-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="bd6df-156">Asignar una licencia de Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="bd6df-156">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="bd6df-157">Conectarse a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bd6df-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="bd6df-158">Para obtener más información sobre Active Directory, [consulte Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="bd6df-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="bd6df-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.</span><span class="sxs-lookup"><span data-stu-id="bd6df-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="bd6df-160">La cuenta del dispositivo debe tener una licencia válida de Microsoft 365 u Office 365, o Exchange y Microsoft Teams no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="bd6df-160">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="bd6df-161">Si tienes la licencia, tienes que asignar una ubicación de uso a tu cuenta del dispositivo( esto determina qué SKU de licencia están disponibles para tu cuenta).</span><span class="sxs-lookup"><span data-stu-id="bd6df-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="bd6df-162">Puede usar `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="bd6df-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="bd6df-163">para recuperar una lista de SKU disponibles.</span><span class="sxs-lookup"><span data-stu-id="bd6df-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="bd6df-164">A continuación, puede agregar una licencia con el `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="bd6df-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="bd6df-165">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd6df-165">cmdlet.</span></span> <span data-ttu-id="bd6df-166">En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="bd6df-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="bd6df-167">Para obtener instrucciones [detalladas, consulte Asignar licencias a cuentas de usuario con PowerShell de Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="bd6df-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="bd6df-168">Habilitar la cuenta del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd6df-168">Enable the device account</span></span>

<span data-ttu-id="bd6df-169">PowerShell de Skype Empresarial Online se usa para administrar servicios tanto para Microsoft Teams como para Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bd6df-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="bd6df-170">Crea una sesión Windows PowerShell sesión remota desde un equipo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bd6df-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="bd6df-171">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="bd6df-171">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="bd6df-172">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="bd6df-172">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="bd6df-173">Obtener la dirección SIP de la cuenta:</span><span class="sxs-lookup"><span data-stu-id="bd6df-173">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="bd6df-174">Para habilitar la cuenta de Salas de Microsoft Teams, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="bd6df-174">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="bd6df-175">Si no está seguro de qué valor usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario existente mediante este comando:</span><span class="sxs-lookup"><span data-stu-id="bd6df-175">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="bd6df-176">Asignar una licencia a su cuenta de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="bd6df-176">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="bd6df-177">Inicie sesión como administrador de inquilinos, abra el Centro de administración de Microsoft 365 y haga clic en la aplicación Administración.</span><span class="sxs-lookup"><span data-stu-id="bd6df-177">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="bd6df-178">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="bd6df-178">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="bd6df-179">Haga clic en la cuenta de Salas de Microsoft Teams y, a continuación, haga clic en el icono de lápiz para editar la información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="bd6df-179">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="bd6df-180">Haga clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="bd6df-180">Click **Licenses**.</span></span>
5. <span data-ttu-id="bd6df-181">En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="bd6df-181">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="bd6df-182">Tendrá que usar una licencia de Plan 3 si quiere usar Telefonía IP empresarial en sus salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bd6df-182">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="bd6df-183">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bd6df-183">Click **Save**.</span></span>

<span data-ttu-id="bd6df-184">Para la validación, debería poder usar cualquier cliente para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="bd6df-184">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bd6df-185">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bd6df-185">Related topics</span></span>

[<span data-ttu-id="bd6df-186">Configurar cuentas de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd6df-186">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="bd6df-187">Plan para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd6df-187">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="bd6df-188">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd6df-188">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="bd6df-189">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd6df-189">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="bd6df-190">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd6df-190">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
