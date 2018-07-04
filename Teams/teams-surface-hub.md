---
title: Implementación de equipos de Microsoft para el concentrador de superficie
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
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
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192183"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="ce73c-103">Implementación de equipos de Microsoft para el concentrador de superficie</span><span class="sxs-lookup"><span data-stu-id="ce73c-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="ce73c-104">Antes de implementar Microsoft Teams Microsoft Surface concentrador, asegúrese de que haya cumplido con el hardware, sistema operativo y otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="ce73c-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="ce73c-105">Para obtener más información, consulte la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="ce73c-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="ce73c-106">Configurar las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="ce73c-106">Set up user accounts</span></span>
 
<span data-ttu-id="ce73c-107">Para configurar las cuentas de usuario que se pueden usar con los equipos de superficie de concentradores, crear la cuenta del dispositivo, como lo haría para compatibilidad con Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="ce73c-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="ce73c-108">La cuenta del dispositivo debe tener la autenticación multifactor deshabilitada (para permitir el inicio de sesión automático) para los siguientes servicios dependientes de los equipos en Office 365:</span><span class="sxs-lookup"><span data-stu-id="ce73c-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="ce73c-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="ce73c-109">Exchange</span></span> 
- <span data-ttu-id="ce73c-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ce73c-110">SharePoint</span></span> 
- <span data-ttu-id="ce73c-111">Aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="ce73c-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="ce73c-112">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ce73c-112">Add a device account</span></span> 

<span data-ttu-id="ce73c-113">1\.</span><span class="sxs-lookup"><span data-stu-id="ce73c-113">1\.</span></span> <span data-ttu-id="ce73c-114">Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce73c-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="ce73c-115">Asegúrese de que tiene los permisos correctos establecer ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="ce73c-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="ce73c-116">Estos son algunos ejemplos de cmdlets que puede utilizar y modificar en su entorno.</span><span class="sxs-lookup"><span data-stu-id="ce73c-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="ce73c-117">2\.</span><span class="sxs-lookup"><span data-stu-id="ce73c-117">2\.</span></span> <span data-ttu-id="ce73c-118">Después de establecer una sesión, deberá crear un nuevo buzón de correo y habilitarlo como RoomMailboxAccount o bien, cambiar la configuración de un buzón de correo existente.</span><span class="sxs-lookup"><span data-stu-id="ce73c-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="ce73c-119">Esto le permitirá la cuenta autenticar a los equipos.</span><span class="sxs-lookup"><span data-stu-id="ce73c-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="ce73c-120">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="ce73c-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="ce73c-121">Si va a crear un buzón de recursos nuevo:</span><span class="sxs-lookup"><span data-stu-id="ce73c-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="ce73c-122">3\.</span><span class="sxs-lookup"><span data-stu-id="ce73c-122">3\.</span></span> <span data-ttu-id="ce73c-123">Para mejorar la experiencia de la reunión, es necesario configurar diversas propiedades de Exchange en la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce73c-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="ce73c-124">Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce73c-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="ce73c-125">4\.</span><span class="sxs-lookup"><span data-stu-id="ce73c-125">4\.</span></span> <span data-ttu-id="ce73c-126">Tendrá que conectarse a Azure Active Directory para aplicar algunas de las configuraciones de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="ce73c-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="ce73c-127">Para conectarse a Azure AD, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ce73c-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="ce73c-128">5\.</span><span class="sxs-lookup"><span data-stu-id="ce73c-128">5\.</span></span> <span data-ttu-id="ce73c-129">	Si no desea que expire la contraseña, ejecute el cmdlet Set-MsolUser con la opción PasswordNeverExpires como sigue:  </span><span class="sxs-lookup"><span data-stu-id="ce73c-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="ce73c-130">También puede configurar un número de teléfono para la sala de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ce73c-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="ce73c-131">6\.</span><span class="sxs-lookup"><span data-stu-id="ce73c-131">6\.</span></span> <span data-ttu-id="ce73c-132">La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Skype para la empresa no funcionará.</span><span class="sxs-lookup"><span data-stu-id="ce73c-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="ce73c-133">Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="ce73c-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="ce73c-134">Puede usar Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ce73c-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="ce73c-p109">A continuación, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="ce73c-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="ce73c-137">7\.</span><span class="sxs-lookup"><span data-stu-id="ce73c-137">7\.</span></span> <span data-ttu-id="ce73c-138">A continuación, tiene que habilitar la cuenta del dispositivo con los equipos de superficie de concentrador.</span><span class="sxs-lookup"><span data-stu-id="ce73c-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="ce73c-139">Asegúrese de que su entorno cumple los requisitos definidos en la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="ce73c-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="ce73c-140">Iniciar una sesión remota de Windows PowerShell de manera (asegúrese de instalar Skype para componentes de PowerShell en línea de negocio):</span><span class="sxs-lookup"><span data-stu-id="ce73c-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="ce73c-141">A continuación, habilitar sus equipos para la cuenta de concentrador de superficie ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ce73c-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="ce73c-142">Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ce73c-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="ce73c-143">No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="ce73c-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="ce73c-144">El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="ce73c-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="ce73c-145">Una vez haya completado los pasos anteriores para habilitar los equipos de la cuenta de concentrador de superficie, debe asignar una licencia para el dispositivo de v2 de concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="ce73c-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="ce73c-146">Uso del portal administrativo de Office 365, asignar los equipos de una licencia de concentrador de superficie para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce73c-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="ce73c-147">Asignar una licencia a la cuenta</span><span class="sxs-lookup"><span data-stu-id="ce73c-147">Assign a license to the account</span></span>

1. <span data-ttu-id="ce73c-148">Inicie sesión como administrador de inquilinos, abra el centro de administración de Office 365 y haga clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="ce73c-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="ce73c-149">Haga clic en **usuarios y grupos**y, a continuación, haga clic en **Agregar usuarios, restablecer contraseñas y mucho más**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="ce73c-150">Seleccione los equipos de cuenta de superficie concentrador y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.</span><span class="sxs-lookup"><span data-stu-id="ce73c-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="ce73c-151">Haga clic en la opción de **licencias** .</span><span class="sxs-lookup"><span data-stu-id="ce73c-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="ce73c-152">En la sección **asignación de licencias** , es necesario seleccionar el plan, dependiendo de su licencia.</span><span class="sxs-lookup"><span data-stu-id="ce73c-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="ce73c-153">Haga clic en **Guardar** para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="ce73c-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="ce73c-154">Instalación de los equipos para exponer concentrador desde el almacén de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce73c-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="ce73c-155">Estas instrucciones incluyen las soluciones alternativas actuales para la instalación de los equipos de concentrador de superficie de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ce73c-155">These instructions include the current workarounds for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="ce73c-156">Inicie el almacén de Windows:</span><span class="sxs-lookup"><span data-stu-id="ce73c-156">Start the Windows Store:</span></span><br>
   <span data-ttu-id="ce73c-157">a.</span><span class="sxs-lookup"><span data-stu-id="ce73c-157">a.</span></span> <span data-ttu-id="ce73c-158">Puntee en **Iniciar** > **todas las aplicaciones** > **configuración**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="ce73c-159">b.</span><span class="sxs-lookup"><span data-stu-id="ce73c-159">b.</span></span> <span data-ttu-id="ce73c-160">Puntee en **dispositivo de concentrador de superficie de cuenta, administración**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="ce73c-161">c.</span><span class="sxs-lookup"><span data-stu-id="ce73c-161">c.</span></span> <span data-ttu-id="ce73c-162">En la izquierda, puntee en la ficha **aplicaciones y características** .</span><span class="sxs-lookup"><span data-stu-id="ce73c-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="ce73c-163">d.</span><span class="sxs-lookup"><span data-stu-id="ce73c-163">d.</span></span> <span data-ttu-id="ce73c-164">En la derecha, puntee en el botón **Abrir almacén** .</span><span class="sxs-lookup"><span data-stu-id="ce73c-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="ce73c-165">De Microsoft Store, busque *Los equipos de Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="ce73c-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="ce73c-166">Se mostrarán los **Equipos de Microsoft para el concentrador de superficie (vista previa)** .</span><span class="sxs-lookup"><span data-stu-id="ce73c-166">The **Microsoft Teams for Surface Hub (Preview)** will be displayed.</span></span> <span data-ttu-id="ce73c-167">Puntee en el botón **obtener la aplicación** para instalar.</span><span class="sxs-lookup"><span data-stu-id="ce73c-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="ce73c-168">Una vez finalizada la instalación, reinicie el concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="ce73c-168">When the installation is complete, restart the Surface Hub.</span></span> 
4. <span data-ttu-id="ce73c-169">Una vez reiniciado el concentrador de superficie, debe ser capaz de iniciar la aplicación de los equipos desde el menú **Inicio** y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="ce73c-169">After the Surface Hub restarts, you should be able to start the Teams app from the **Start** menu and join a meeting from the calendar.</span></span> 

## <a name="make-teams-the-default-vtc-application"></a><span data-ttu-id="ce73c-170">Hacer que los equipos de la aplicación de VTC predeterminada</span><span class="sxs-lookup"><span data-stu-id="ce73c-170">Make Teams the default VTC application</span></span>

<span data-ttu-id="ce73c-171">Los equipos pueden ser configurados para que sea la aplicación predeterminada de VTC en lugar de Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="ce73c-171">Teams can be set up to be the default VTC application instead of Skype for Business.</span></span> <span data-ttu-id="ce73c-172">Una directiva de Mobile Device Management (MDM) debe aplicarse en el dispositivo del concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="ce73c-172">A Mobile Device Management (MDM) policy needs to be applied to the Surface Hub device.</span></span> 
 
<span data-ttu-id="ce73c-173">Hay dos opciones para configurar las directivas de MDM:</span><span class="sxs-lookup"><span data-stu-id="ce73c-173">There are two options for configuring MDM policies:</span></span> 

- <span data-ttu-id="ce73c-174">Si tiene una directiva configurada, agregarlo a través de la aplicación de administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce73c-174">If you have a policy configured, add it via the Device management app.</span></span> 
- <span data-ttu-id="ce73c-175">Si no tiene configurada una directiva de remota, tenemos un archivo de paquete suministrados que se puede cargar en una clave USB.</span><span class="sxs-lookup"><span data-stu-id="ce73c-175">If you do not have a remote policy configured, we have a provisioned package file that you can load onto an USB key.</span></span>

### <a name="device-management-configuration"></a><span data-ttu-id="ce73c-176">Configuración de administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ce73c-176">Device management configuration</span></span>

<span data-ttu-id="ce73c-177">El siguiente es un ejemplo de adición de una directiva MDM configurada desde una entidad de certificación MDM central.</span><span class="sxs-lookup"><span data-stu-id="ce73c-177">The following is an example of adding an MDM policy configured from a central MDM authority.</span></span> <span data-ttu-id="ce73c-178">Si se trata de la red corporativa, puede usar las siguientes instrucciones textual, incluida la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="ce73c-178">If you are on the corporate network, you can use the following instructions verbatim, including user account.</span></span> 
 
1. <span data-ttu-id="ce73c-179">En la sección **Administración de dispositivos** , puntee en **+**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-179">Under the **Device Management** section, tap **+**.</span></span><br>
   <span data-ttu-id="ce73c-180">Se abrirá el cuadro de diálogo **Conectar a trabajar o escuela** .</span><span class="sxs-lookup"><span data-stu-id="ce73c-180">The **Connect to work or school** dialog box will open.</span></span> 
2. <span data-ttu-id="ce73c-181">Escriba la dirección de correo electrónico de la directiva y la contraseña cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="ce73c-181">Enter the policy e-mail address and password when prompted.</span></span><br>
   <span data-ttu-id="ce73c-182">**Nota:**  Hay un error en el sistema operativo que no actualice automáticamente la interfaz de usuario después de haber especificado su cuenta de administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce73c-182">**NOTE:**  There's a bug in the OS that doesn't automatically refresh the UI after you've entered your device management account.</span></span> <span data-ttu-id="ce73c-183">Debe cerrar y volver a abrir Configuración para poder ver la cuenta que aparece.</span><span class="sxs-lookup"><span data-stu-id="ce73c-183">You'll need to close and re-open settings in order to see the account listed.</span></span> 
3. <span data-ttu-id="ce73c-184">Tardará unos minutos sincronizar la configuración de directiva MDM. Si desea forzar una sincronización, puntee en el botón **cuenta MDM** y, a continuación, puntee en el botón **Info** .</span><span class="sxs-lookup"><span data-stu-id="ce73c-184">It'll take a few minutes for the MDM policy settings to sync. If you want to force a sync, tap the **MDM account** button, and then tap the **Info** button.</span></span> <span data-ttu-id="ce73c-185">Este modo se abrirá la ventana de información donde, a continuación, puntee en **sincronización**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-185">This will bring up the Info window where you can then tap **Sync**.</span></span> 
4. <span data-ttu-id="ce73c-186">Para comprobar que tiene lo que necesita, puede comprobar el registro.</span><span class="sxs-lookup"><span data-stu-id="ce73c-186">To verify that you have what you need, you can check the registry.</span></span> <span data-ttu-id="ce73c-187">Debería ver dos claves en **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-187">You should see two keys under **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span></span> <br><br>
   <span data-ttu-id="ce73c-188">El valor DWORD **VtcAppMeetingHandlingMode** indica que los equipos es la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce73c-188">The **VtcAppMeetingHandlingMode** DWORD value indicates that Teams is the default app.</span></span> <span data-ttu-id="ce73c-189">Se reconocen los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="ce73c-189">The following values are recognized.</span></span> <br><br>
    |<span data-ttu-id="ce73c-190">Número</span><span class="sxs-lookup"><span data-stu-id="ce73c-190">Number</span></span> | <span data-ttu-id="ce73c-191">Valor</span><span class="sxs-lookup"><span data-stu-id="ce73c-191">Value</span></span>   |
    |-------|---------|
    |<span data-ttu-id="ce73c-192">0</span><span class="sxs-lookup"><span data-stu-id="ce73c-192">0</span></span>      | <span data-ttu-id="ce73c-193">SkypePreferred</span><span class="sxs-lookup"><span data-stu-id="ce73c-193">SkypePreferred</span></span>            |
    |<span data-ttu-id="ce73c-194">1</span><span class="sxs-lookup"><span data-stu-id="ce73c-194">1</span></span>      | <span data-ttu-id="ce73c-195">VtcPreferred (equipos)</span><span class="sxs-lookup"><span data-stu-id="ce73c-195">VtcPreferred (Teams)</span></span>      |
    |<span data-ttu-id="ce73c-196">2</span><span class="sxs-lookup"><span data-stu-id="ce73c-196">2</span></span>      | <span data-ttu-id="ce73c-197">VtcExclusive (sólo en los equipos)</span><span class="sxs-lookup"><span data-stu-id="ce73c-197">VtcExclusive (Teams only)</span></span> |

    <span data-ttu-id="ce73c-198">El **VtcCallAppPackageId** es el nombre del paquete de los equipos instalado.</span><span class="sxs-lookup"><span data-stu-id="ce73c-198">The **VtcCallAppPackageId** is the name of the installed Teams package.</span></span> <span data-ttu-id="ce73c-199">Si esto no se muestra, asegúrese de que ha instalado el paquete de los equipos y volver a sincronizar.</span><span class="sxs-lookup"><span data-stu-id="ce73c-199">If this doesn't show up, make sure you've installed the Teams package, and re-sync.</span></span> 
 
### <a name="configure-mdm-via-usb-key"></a><span data-ttu-id="ce73c-200">Configurar MDM a través de la clave USB</span><span class="sxs-lookup"><span data-stu-id="ce73c-200">Configure MDM via USB key</span></span> 
 
<span data-ttu-id="ce73c-201">Los paquetes se pueden encontrar en esta [página de descarga](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="ce73c-201">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="ce73c-202">Elija la adecuada para el paquete que va a instalar y cópielo a una clave USB.</span><span class="sxs-lookup"><span data-stu-id="ce73c-202">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="ce73c-203">El archivo .ppkg correcto para usar depende del paquete de los equipos que se ha instalado desde el almacén y la directiva que desea aplicar (Skype exclusivo, Skype preferido, los equipos preferidos, exclusiva de los equipos).</span><span class="sxs-lookup"><span data-stu-id="ce73c-203">The correct .ppkg file to use depends on the Teams package that has been installed from the store, and the policy you'd like to apply (Skype exclusive, Skype preferred, Teams preferred, Teams exclusive).</span></span> 
 
1. <span data-ttu-id="ce73c-204">Adjunta la clave USB en el dispositivo del concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="ce73c-204">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="ce73c-205">Abra la aplicación de **configuración** en un dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="ce73c-205">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="ce73c-206">Abra **administración de cuentas de dispositivo concentrador expuesta**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-206">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="ce73c-207">Abra **administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-207">Open **Device Management**.</span></span> 
5. <span data-ttu-id="ce73c-208">Haga clic en **Agregar o quitar un paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-208">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="ce73c-209">Haga clic en **Agregar paquete**.</span><span class="sxs-lookup"><span data-stu-id="ce73c-209">Click **Add Package**.</span></span>
7. <span data-ttu-id="ce73c-210">Seleccione la opción de **Medios extraíble** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="ce73c-210">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="ce73c-211">Agregue el **Allowbuildspreview.ppkg**y, a continuación, seleccione el paquete de concentrador de superficie que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="ce73c-211">Add the **Allowbuildspreview.ppkg**, and then select the Surface Hub package you want to add.</span></span> 
9. <span data-ttu-id="ce73c-212">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="ce73c-212">Restart the Surface Hub device.</span></span> 

> [!NOTE]
> <span data-ttu-id="ce73c-213">Si no se admite su dispositivo o dispositivos de su organización parte del programa de información confidencial de Windows y se encuentra en países cubiertos por el Reglamento General de protección de datos (GDPR) (o ha cambiado manualmente la configuración de telemetría en básico), a continuación, debe volver a comprobar que se ha permitido telemetría completo antes de unirse a la información confidencial de programa.</span><span class="sxs-lookup"><span data-stu-id="ce73c-213">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="ce73c-214">GDPR cambiar el comportamiento predeterminado de los dispositivos de concentradores de la superficie de la UE para establecer telemetría en básico.</span><span class="sxs-lookup"><span data-stu-id="ce73c-214">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>