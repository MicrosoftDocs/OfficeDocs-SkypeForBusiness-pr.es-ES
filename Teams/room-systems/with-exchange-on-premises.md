---
title: Implementar Salas de Microsoft Teams con Exchange local
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos en un entorno híbrido con Exchange local.
ms.openlocfilehash: 7ab9a582e26db15159677343d9edddd6bd9c45f9
ms.sourcegitcommit: 751035e1d35fc79a6b74955d7c6c46ecea0645e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2019
ms.locfileid: "34082725"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="7f6e0-103">Implementar Salas de Microsoft Teams con Exchange local</span><span class="sxs-lookup"><span data-stu-id="7f6e0-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="7f6e0-104">Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos en un entorno híbrido con Exchange en local y Microsoft Teams o Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="7f6e0-105">Si su organización tiene una mezcla de servicios, con algunas hospedado en local y algunas alojado en línea, a continuación, la configuración depende de donde se hospeda cada servicio.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="7f6e0-106">En este tema se trata las implementaciones híbridas en salas de equipos de Microsoft con Exchange hospedado localmente.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="7f6e0-107">Debido a que hay muchas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="7f6e0-108">El siguiente proceso funcionará para muchas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-108">The following process will work for many configurations.</span></span> <span data-ttu-id="7f6e0-109">Si el proceso no es adecuado para el programa de instalación, se recomienda que use Windows PowerShell para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="7f6e0-110">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudar a convertirlas en cuentas de usuario compatibles con salones de los equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="7f6e0-111">Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="7f6e0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f6e0-112">Requirements</span></span>

<span data-ttu-id="7f6e0-113">Antes de implementar Microsoft salones de los equipos con Exchange local, debe asegurarse de que cumplen los requisitos.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="7f6e0-114">Para obtener más información, vea [requisitos de salas de equipos de Microsoft](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="7f6e0-115">Si va a implementar Microsoft salones de los equipos con Exchange local, va a usar las herramientas administrativas de Active Directory para agregar una dirección de correo electrónico para su cuenta de dominio local.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="7f6e0-116">Esta cuenta se sincronizará con Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="7f6e0-117">Tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6e0-117">You will need to:</span></span>
  
- <span data-ttu-id="7f6e0-118">Crear una cuenta y sincronizarla con Active Directory</span><span class="sxs-lookup"><span data-stu-id="7f6e0-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="7f6e0-119">Habilitar el buzón de correo remoto y establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="7f6e0-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="7f6e0-120">Asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="7f6e0-121">Habilitar la cuenta del dispositivo con Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="7f6e0-122">Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:</span><span class="sxs-lookup"><span data-stu-id="7f6e0-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="7f6e0-123">Debe tener Skype para profesionales Online (Plan 2) o superior en su plan de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="7f6e0-124">El plan debe admitir la funcionalidad de conferencias.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="7f6e0-125">Si necesita Enterprise Voice (telefonía PSTN) con proveedores de servicios de telefonía para salas de equipos de Microsoft necesita Skype para profesionales en línea (planeación de 3).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="7f6e0-126">Los usuarios de inquilinos deben tener los buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="7f6e0-127">Su cuenta de salas de equipos de Microsoft requieren una Skype para profesionales Online (Plan 2) o Skype para licencia empresarial en línea (planeación de 3), pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="7f6e0-128">Asignar un Skype para licencia de servidor empresarial a su cuenta de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="7f6e0-129">Crear una cuenta y sincronizarla con Active Directory</span><span class="sxs-lookup"><span data-stu-id="7f6e0-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="7f6e0-130">En la herramienta de **equipos y usuarios de Active Directory** , haga clic en la carpeta o unidad organizativa que sus salones de los equipos de Microsoft se crearán cuentas en, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="7f6e0-p107">Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="7f6e0-p108">Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f6e0-136">Selección de **la contraseña nunca caduca** es un requisito para Skype para Business Server en salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="7f6e0-137">Es posible que las reglas de dominio prohíban las contraseñas que no expiran.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="7f6e0-138">Si es así, debe crear una excepción para cada cuenta de dispositivo de salas de equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="7f6e0-139">Tras crear la cuenta, ejecute una sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="7f6e0-140">Una vez finalizada, vaya a la página de los usuarios en el centro de administración de Microsoft 365 y compruebe que la cuenta creada en los pasos anteriores se combinado en línea.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="7f6e0-141">Habilitar el buzón de correo remoto y establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="7f6e0-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="7f6e0-142">[Abra el Shell de administración de Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [conectarse a su servidor de Exchange mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="7f6e0-143">En Exchange PowerShell, crear un buzón de correo para la cuenta (la cuenta de buzón de correo habilitar) ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7f6e0-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="7f6e0-144">Para obtener información de parámetro y detallada sobre la sintaxis, consulte [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="7f6e0-145">En PowerShell de Exchange, configure las opciones siguientes en el buzón de sala para mejorar la experiencia de reunión:</span><span class="sxs-lookup"><span data-stu-id="7f6e0-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="7f6e0-146">AutomateProcessing: AutoAccept (los organizadores de reuniones reciben la decisión de reserva de sala directamente sin intervención humana: libre = acepte; ocupado = rechazar.)</span><span class="sxs-lookup"><span data-stu-id="7f6e0-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="7f6e0-147">AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="7f6e0-148">DeleteComments: $false (mantener el texto del cuerpo del mensaje de convocatorias de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="7f6e0-149">DeleteSubject: $false (conservar el asunto de convocatorias de reunión entrantes).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="7f6e0-150">RemovePrivateProperty: $false (garantiza la marca privada que se envió el organizador de la reunión original permanece tal como se especifica de solicitudes).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="7f6e0-151">AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="7f6e0-152">AdditionalResponse: "ésta es una sala de reuniones de Skype!"</span><span class="sxs-lookup"><span data-stu-id="7f6e0-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="7f6e0-153">(El texto adicional para agregar a la convocatoria de reunión).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="7f6e0-154">En este ejemplo se configura estas opciones de configuración en el buzón de sala denominado Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="7f6e0-155">Para obtener información de parámetro y detallada sobre la sintaxis, vea [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="7f6e0-156">Asignar una licencia de Office 365</span><span class="sxs-lookup"><span data-stu-id="7f6e0-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="7f6e0-157">Conectar con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="7f6e0-158">Para obtener información detallada acerca de Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="7f6e0-159">No se admite [de Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="7f6e0-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="7f6e0-160">La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Microsoft Teams no funcionará.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="7f6e0-161">Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="7f6e0-162">Puede usar`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="7f6e0-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="7f6e0-163">para recuperar una lista de SKU disponibles.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="7f6e0-164">A continuación, puede agregar una licencia mediante la`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="7f6e0-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="7f6e0-165">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-165">cmdlet.</span></span> <span data-ttu-id="7f6e0-166">En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="7f6e0-167">Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7f6e0-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="7f6e0-168">Habilitar la cuenta del dispositivo</span><span class="sxs-lookup"><span data-stu-id="7f6e0-168">Enable the device account</span></span>

<span data-ttu-id="7f6e0-169">Skype para PowerShell en línea de negocio se usa para administrar los servicios de Microsoft Teams y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="7f6e0-170">Crear una sesión remota de Windows PowerShell desde un PC de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7f6e0-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="7f6e0-171">Para habilitar la cuenta de salas de equipos de Microsoft, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="7f6e0-171">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="7f6e0-172">Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en el entorno, puede obtener el valor de un usuario existente con este comando:</span><span class="sxs-lookup"><span data-stu-id="7f6e0-172">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="7f6e0-173">Asignar una licencia a su cuenta de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f6e0-173">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="7f6e0-174">Inicie sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-174">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="7f6e0-175">Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-175">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="7f6e0-176">Haga clic en la cuenta de salas de equipos de Microsoft y, a continuación, haga clic en el icono de lápiz para editar la información de cuenta.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-176">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="7f6e0-177">Haga clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-177">Click **Licenses**.</span></span>
5. <span data-ttu-id="7f6e0-178">En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-178">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="7f6e0-179">Debe utilizar una licencia de planeación 3 si desea usar Enterprise Voice en sus salones de los equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-179">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="7f6e0-180">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-180">Click **Save**.</span></span>

<span data-ttu-id="7f6e0-181">Para la validación, debe utilizar a cualquier cliente para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="7f6e0-181">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7f6e0-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f6e0-182">See also</span></span>

[<span data-ttu-id="7f6e0-183">Configurar las cuentas para salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f6e0-183">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="7f6e0-184">Plan para salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f6e0-184">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="7f6e0-185">Implementación de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f6e0-185">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="7f6e0-186">Configurar una consola de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f6e0-186">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="7f6e0-187">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f6e0-187">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
