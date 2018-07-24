---
title: Implementación de equipos de Microsoft para el concentrador de superficie
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Configuración de administración para Microsoft Teams para concentrador de superficie.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7757f7d220ae58914a296e3dc3850179219b475
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20981582"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="2bb0f-103">Implementación de equipos de Microsoft para el concentrador de superficie</span><span class="sxs-lookup"><span data-stu-id="2bb0f-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="2bb0f-104">Antes de implementar Microsoft Teams Microsoft Surface concentrador, asegúrese de que haya cumplido con el hardware, sistema operativo y otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="2bb0f-105">Para obtener más información, consulte la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="2bb0f-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="2bb0f-106">Configurar las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="2bb0f-106">Set up user accounts</span></span>
 
<span data-ttu-id="2bb0f-107">Para configurar las cuentas de usuario que se pueden usar con los equipos de superficie de concentradores, crear la cuenta del dispositivo, como lo haría para compatibilidad con Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="2bb0f-108">La cuenta del dispositivo debe tener la autenticación multifactor deshabilitada (para permitir el inicio de sesión automático) para los siguientes servicios dependientes de los equipos en Office 365:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="2bb0f-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="2bb0f-109">Exchange</span></span> 
- <span data-ttu-id="2bb0f-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2bb0f-110">SharePoint</span></span> 
- <span data-ttu-id="2bb0f-111">Aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="2bb0f-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="2bb0f-112">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="2bb0f-112">Add a device account</span></span> 

<span data-ttu-id="2bb0f-113">1\.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-113">1\.</span></span> <span data-ttu-id="2bb0f-114">Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="2bb0f-115">Asegúrese de que tiene los permisos correctos establecer ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="2bb0f-116">Estos son algunos ejemplos de cmdlets que puede utilizar y modificar en su entorno.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="2bb0f-117">2\.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-117">2\.</span></span> <span data-ttu-id="2bb0f-118">Después de establecer una sesión, deberá crear un nuevo buzón de correo y habilitarlo como RoomMailboxAccount o bien, cambiar la configuración de un buzón de correo existente.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="2bb0f-119">Esto le permitirá la cuenta autenticar a los equipos.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="2bb0f-120">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="2bb0f-121">Si va a crear un buzón de recursos nuevo:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="2bb0f-122">3\.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-122">3\.</span></span> <span data-ttu-id="2bb0f-123">Para mejorar la experiencia de la reunión, es necesario configurar diversas propiedades de Exchange en la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="2bb0f-124">Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="2bb0f-125">4\.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-125">4\.</span></span> <span data-ttu-id="2bb0f-126">Tendrá que conectarse a Azure Active Directory para aplicar algunas de las configuraciones de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="2bb0f-127">Para conectarse a Azure AD, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="2bb0f-128">5\.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-128">5\.</span></span> <span data-ttu-id="2bb0f-129">	Si no desea que expire la contraseña, ejecute el cmdlet Set-MsolUser con la opción PasswordNeverExpires como sigue:  </span><span class="sxs-lookup"><span data-stu-id="2bb0f-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="2bb0f-130">También puede configurar un número de teléfono para la sala de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="2bb0f-131">6\.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-131">6\.</span></span> <span data-ttu-id="2bb0f-132">La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Skype para la empresa no funcionará.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="2bb0f-133">Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="2bb0f-134">Puede usar Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="2bb0f-p109">A continuación, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="2bb0f-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="2bb0f-137">7\.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-137">7\.</span></span> <span data-ttu-id="2bb0f-138">A continuación, tiene que habilitar la cuenta del dispositivo con los equipos de superficie de concentrador.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="2bb0f-139">Asegúrese de que su entorno cumple los requisitos definidos en la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="2bb0f-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="2bb0f-140">Iniciar una sesión remota de Windows PowerShell de manera (asegúrese de instalar Skype para componentes de PowerShell en línea de negocio):</span><span class="sxs-lookup"><span data-stu-id="2bb0f-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="2bb0f-141">A continuación, habilitar sus equipos para la cuenta de concentrador de superficie ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="2bb0f-142">Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="2bb0f-143">No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="2bb0f-144">El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="2bb0f-145">Una vez haya completado los pasos anteriores para habilitar los equipos de la cuenta de concentrador de superficie, debe asignar una licencia para el dispositivo de v2 de concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="2bb0f-146">Uso del portal administrativo de Office 365, asignar los equipos de una licencia de concentrador de superficie para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="2bb0f-147">Asignar una licencia a la cuenta</span><span class="sxs-lookup"><span data-stu-id="2bb0f-147">Assign a license to the account</span></span>

1. <span data-ttu-id="2bb0f-148">Inicie sesión como administrador de inquilinos, abra el centro de administración de Office 365 y haga clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="2bb0f-149">Haga clic en **usuarios y grupos**y, a continuación, haga clic en **Agregar usuarios, restablecer contraseñas y mucho más**.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="2bb0f-150">Seleccione los equipos de cuenta de superficie concentrador y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="2bb0f-151">Haga clic en la opción de **licencias** .</span><span class="sxs-lookup"><span data-stu-id="2bb0f-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="2bb0f-152">En la sección **asignación de licencias** , es necesario seleccionar el plan, dependiendo de su licencia.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="2bb0f-153">Haga clic en **Guardar** para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="2bb0f-154">Instalación de los equipos para exponer concentrador desde el almacén de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2bb0f-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

> [!NOTE]
> <span data-ttu-id="2bb0f-155">Para usar Microsoft Teams para concentrador de superficie (vista previa), el dispositivo debe ser inscritos en el programa de información confidencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-155">To use Microsoft Teams for Surface Hub (Preview), your device must be enrolled in the Windows Insider Program.</span></span> <span data-ttu-id="2bb0f-156">Para dejar el programa de información confidencial, debe restablecer el concentrador de superficie de uso de recuperación en la nube.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-156">To leave the Insider Program, you must reset the Surface Hub using Cloud Recovery.</span></span><br> <span data-ttu-id="2bb0f-157">Para convertirse en un miembro del programa de información confidencial de Windows, se debe establecer el concentrador de superficie en telemetría completo antes de entrar en el programa de información confidencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-157">To become a Windows Insider Program member, the Surface Hub must be set to Full Telemetry prior to joining the Windows Insider Program.</span></span> <span data-ttu-id="2bb0f-158">Debido a las normativas de GDPR, la configuración predeterminada de Windows telemetría recientemente cambiado de completa a básica en países de la UE.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-158">Due to GDPR regulations, the default settings of Windows Telemetry recently changed from Full to Basic in EU countries.</span></span> <span data-ttu-id="2bb0f-159">Debe comprobar la configuración antes de unirse al programa de información confidencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-159">You should verify your settings prior to joining the Windows Insider Program.</span></span> <span data-ttu-id="2bb0f-160">Si se intenta participar en el programa de información confidencial de Windows cuando se establece en básico telemetry podría requerir un restablecimiento del concentrador de superficie de.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-160">Attempting to join the Windows Insider Program when set to Basic telemetry might require a reset of the Surface Hub.</span></span> <span data-ttu-id="2bb0f-161">Para validar la configuración de telemetría de Windows en un concentrador de superficie, elija **configuración** > **Privacy** > **comentarios y diagnósticos**y establecida en **completa**.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-161">To validate the Windows Telemetry settings on a Surface Hub, choose **Settings** > **Privacy** > **Feedback and Diagnostics**, and set to **Full**.</span></span>

<span data-ttu-id="2bb0f-162">Estas instrucciones son para la instalación de los equipos de concentrador de superficie de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-162">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="2bb0f-163">Iniciar el almacén de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-163">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="2bb0f-164">a.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-164">a.</span></span> <span data-ttu-id="2bb0f-165">Puntee en **Iniciar** > **todas las aplicaciones** > **configuración**.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-165">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="2bb0f-166">b.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-166">b.</span></span> <span data-ttu-id="2bb0f-167">Puntee en **dispositivo de concentrador de superficie de cuenta, administración**.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-167">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="2bb0f-168">c.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-168">c.</span></span> <span data-ttu-id="2bb0f-169">En la izquierda, puntee en la ficha **aplicaciones y características** .</span><span class="sxs-lookup"><span data-stu-id="2bb0f-169">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="2bb0f-170">d.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-170">d.</span></span> <span data-ttu-id="2bb0f-171">En la derecha, puntee en el botón **Abrir almacén** .</span><span class="sxs-lookup"><span data-stu-id="2bb0f-171">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="2bb0f-172">De Microsoft Store, busque *Los equipos de Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-172">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="2bb0f-173">Se mostrarán los **Equipos de Microsoft para el concentrador de superficie** .</span><span class="sxs-lookup"><span data-stu-id="2bb0f-173">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="2bb0f-174">Puntee en el botón **obtener la aplicación** para instalar.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-174">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="2bb0f-175">Una vez finalizada la instalación, reinicie el concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-175">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="2bb0f-176">Puntee en no en el **Inicio** de la lista de página de la tienda.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-176">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="2bb0f-177">Hacer que los equipos de la aplicación de las reuniones y llamadas de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="2bb0f-177">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="2bb0f-178">Hay dos opciones para configurar la directiva de aplicación de llamadas y las reuniones de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-178">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="2bb0f-179">**Opción 1**: configurar a través de la clave USB.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-179">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="2bb0f-180">**Opción 2**: configurar a través de MDM como InTune.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-180">**Option 2**: Configure via MDM such as InTune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="2bb0f-181">Opción 1: Configurar a través de la clave USB</span><span class="sxs-lookup"><span data-stu-id="2bb0f-181">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="2bb0f-182">Los paquetes se pueden encontrar en esta [página de descarga](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="2bb0f-182">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="2bb0f-183">Elija la adecuada para el paquete que va a instalar y cópielo a una clave USB.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-183">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="2bb0f-184">El archivo .ppkg correcto para usar depende de la directiva de aplicación predeterminado que desea aplicar la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-184">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="2bb0f-185">Número</span><span class="sxs-lookup"><span data-stu-id="2bb0f-185">Number</span></span>  |<span data-ttu-id="2bb0f-186">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bb0f-186">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2bb0f-187">0</span><span class="sxs-lookup"><span data-stu-id="2bb0f-187">0</span></span>     | <span data-ttu-id="2bb0f-188">Aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles</span><span class="sxs-lookup"><span data-stu-id="2bb0f-188">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="2bb0f-189">1</span><span class="sxs-lookup"><span data-stu-id="2bb0f-189">1</span></span>     | <span data-ttu-id="2bb0f-190">Aplicación preferida de los equipos en la pantalla de inicio, las reuniones de Skype disponibles</span><span class="sxs-lookup"><span data-stu-id="2bb0f-190">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="2bb0f-191">2</span><span class="sxs-lookup"><span data-stu-id="2bb0f-191">2</span></span>     | <span data-ttu-id="2bb0f-192">Aplicación exclusiva de los equipos en la pantalla de inicio (aplicación de Skype no está disponible)</span><span class="sxs-lookup"><span data-stu-id="2bb0f-192">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="2bb0f-193">Adjunta la clave USB en el dispositivo del concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-193">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="2bb0f-194">Abra la aplicación de **configuración** en un dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-194">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="2bb0f-195">Abra **administración de cuentas de dispositivo concentrador expuesta**.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-195">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="2bb0f-196">Abra **administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-196">Open **Device Management**.</span></span> 
5. <span data-ttu-id="2bb0f-197">Haga clic en **Agregar o quitar un paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-197">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="2bb0f-198">Haga clic en **Agregar paquete**.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-198">Click **Add Package**.</span></span>
7. <span data-ttu-id="2bb0f-199">Seleccione la opción de **Medios extraíble** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-199">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="2bb0f-200">Agregar el paquete apropiado de **TeamsRTMMode\*.ppkg** que anteriormente se ha copiado a la clave USB.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-200">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="2bb0f-201">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-201">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="2bb0f-202">Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-202">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="2bb0f-203">Opción 2: Configurar a través de MDM como InTune</span><span class="sxs-lookup"><span data-stu-id="2bb0f-203">Option 2: Configure via MDM such as InTune</span></span> 

<span data-ttu-id="2bb0f-204">Use lo siguiente para configurar la directiva de aplicación predeterminada llamadas y reuniones a través de InTune.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-204">Use the following to configure the default calling and meetings application policy via InTune.</span></span>

|<span data-ttu-id="2bb0f-205">Configuración</span><span class="sxs-lookup"><span data-stu-id="2bb0f-205">Setting</span></span>   |<span data-ttu-id="2bb0f-206">Valor</span><span class="sxs-lookup"><span data-stu-id="2bb0f-206">Value</span></span>    |<span data-ttu-id="2bb0f-207">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bb0f-207">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="2bb0f-208"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="2bb0f-208">Path</span></span>      | <span data-ttu-id="2bb0f-209">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="2bb0f-209">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="2bb0f-210">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2bb0f-210">Data Type</span></span> | <span data-ttu-id="2bb0f-211">entero (0-2)</span><span class="sxs-lookup"><span data-stu-id="2bb0f-211">integer (0-2)</span></span>   |<span data-ttu-id="2bb0f-212">0 - aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles</span><span class="sxs-lookup"><span data-stu-id="2bb0f-212">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="2bb0f-213">1 - equipos aplicación preferida en la pantalla de inicio, las reuniones de Skype disponibles</span><span class="sxs-lookup"><span data-stu-id="2bb0f-213">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="2bb0f-214">2 - equipos aplicación exclusivo en la pantalla de inicio (aplicación de Skype no está disponible)</span><span class="sxs-lookup"><span data-stu-id="2bb0f-214">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="2bb0f-215">Operaciones</span><span class="sxs-lookup"><span data-stu-id="2bb0f-215">Operations</span></span>| <span data-ttu-id="2bb0f-216">Obtener, establecer</span><span class="sxs-lookup"><span data-stu-id="2bb0f-216">Get, Set</span></span>        |

|<span data-ttu-id="2bb0f-217">Configuración</span><span class="sxs-lookup"><span data-stu-id="2bb0f-217">Setting</span></span>   |<span data-ttu-id="2bb0f-218">Valor</span><span class="sxs-lookup"><span data-stu-id="2bb0f-218">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="2bb0f-219"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="2bb0f-219">Path</span></span>      | <span data-ttu-id="2bb0f-220">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="2bb0f-220">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="2bb0f-221">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2bb0f-221">Data Type</span></span> | <span data-ttu-id="2bb0f-222">¡cadena - cadena de conjunto a los equipos el identificador del paquete de aplicación como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Los equipos**</span><span class="sxs-lookup"><span data-stu-id="2bb0f-222">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="2bb0f-223">Operaciones</span><span class="sxs-lookup"><span data-stu-id="2bb0f-223">Operations</span></span>| <span data-ttu-id="2bb0f-224">Obtener, establecer</span><span class="sxs-lookup"><span data-stu-id="2bb0f-224">Get, Set</span></span>        |

<span data-ttu-id="2bb0f-225">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-225">Restart the Surface Hub device.</span></span> <span data-ttu-id="2bb0f-226">Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-226">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

> [!NOTE]
> <span data-ttu-id="2bb0f-227">Si no se admite su dispositivo o dispositivos de su organización parte del programa de información confidencial de Windows y se encuentra en países cubiertos por el Reglamento General de protección de datos (GDPR) (o ha cambiado manualmente la configuración de telemetría en básico), a continuación, debe volver a comprobar que se ha permitido telemetría completo antes de unirse a la información confidencial de programa.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-227">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="2bb0f-228">GDPR cambiar el comportamiento predeterminado de los dispositivos de concentradores de la superficie de la UE para establecer telemetría en básico.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-228">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>