---
title: Implementación de equipos de Microsoft para el concentrador de superficie
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
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
ms.openlocfilehash: aed0cc2b26fa55dcf47b2d90bbd974720c371663
ms.sourcegitcommit: 53c10589c284c6e4bbba574a7ba2df2d29519d1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "23829269"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="e6a58-103">Implementación de equipos de Microsoft para el concentrador de superficie</span><span class="sxs-lookup"><span data-stu-id="e6a58-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="e6a58-104">Antes de implementar Microsoft Teams Microsoft Surface concentrador, asegúrese de que haya cumplido con el hardware, sistema operativo y otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="e6a58-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="e6a58-105">Para obtener más información, consulte la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="e6a58-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="e6a58-106">Configurar las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e6a58-106">Set up user accounts</span></span>
 
<span data-ttu-id="e6a58-107">Para configurar las cuentas de usuario que se pueden usar con los equipos de superficie de concentradores, crear la cuenta del dispositivo, como lo haría para compatibilidad con Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="e6a58-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="e6a58-108">La cuenta del dispositivo debe tener la autenticación multifactor deshabilitada (para permitir el inicio de sesión automático) para los siguientes servicios dependientes de los equipos en Office 365:</span><span class="sxs-lookup"><span data-stu-id="e6a58-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="e6a58-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="e6a58-109">Exchange</span></span> 
- <span data-ttu-id="e6a58-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e6a58-110">SharePoint</span></span> 
- <span data-ttu-id="e6a58-111">Aplicaciones de Office</span><span class="sxs-lookup"><span data-stu-id="e6a58-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="e6a58-112">Agregar una cuenta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e6a58-112">Add a device account</span></span> 

<span data-ttu-id="e6a58-113">1\.</span><span class="sxs-lookup"><span data-stu-id="e6a58-113">1\.</span></span> <span data-ttu-id="e6a58-114">Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange.</span><span class="sxs-lookup"><span data-stu-id="e6a58-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="e6a58-115">Asegúrese de que tiene los permisos correctos establecer ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="e6a58-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="e6a58-116">Estos son algunos ejemplos de cmdlets que puede utilizar y modificar en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e6a58-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="e6a58-117">2\.</span><span class="sxs-lookup"><span data-stu-id="e6a58-117">2\.</span></span> <span data-ttu-id="e6a58-118">Después de establecer una sesión, deberá crear un nuevo buzón de correo y habilitarlo como RoomMailboxAccount o bien, cambiar la configuración de un buzón de correo existente.</span><span class="sxs-lookup"><span data-stu-id="e6a58-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="e6a58-119">Esto le permitirá la cuenta autenticar a los equipos.</span><span class="sxs-lookup"><span data-stu-id="e6a58-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="e6a58-120">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="e6a58-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="e6a58-121">Si va a crear un buzón de recursos nuevo:</span><span class="sxs-lookup"><span data-stu-id="e6a58-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="e6a58-122">3\.</span><span class="sxs-lookup"><span data-stu-id="e6a58-122">3\.</span></span> <span data-ttu-id="e6a58-123">Para mejorar la experiencia de la reunión, es necesario configurar diversas propiedades de Exchange en la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6a58-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="e6a58-124">Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e6a58-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="e6a58-125">4\.</span><span class="sxs-lookup"><span data-stu-id="e6a58-125">4\.</span></span> <span data-ttu-id="e6a58-126">Tendrá que conectarse a Azure Active Directory para aplicar algunas de las configuraciones de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e6a58-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="e6a58-127">Para conectarse a Azure AD, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e6a58-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="e6a58-128">5\.</span><span class="sxs-lookup"><span data-stu-id="e6a58-128">5\.</span></span> <span data-ttu-id="e6a58-129">	Si no desea que expire la contraseña, ejecute el cmdlet Set-MsolUser con la opción PasswordNeverExpires como sigue:  </span><span class="sxs-lookup"><span data-stu-id="e6a58-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="e6a58-130">También puede configurar un número de teléfono para la sala de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e6a58-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="e6a58-131">6\.</span><span class="sxs-lookup"><span data-stu-id="e6a58-131">6\.</span></span> <span data-ttu-id="e6a58-132">La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Skype para la empresa no funcionará.</span><span class="sxs-lookup"><span data-stu-id="e6a58-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="e6a58-133">Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="e6a58-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="e6a58-134">Puede usar Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e6a58-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="e6a58-p109">A continuación, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="e6a58-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="e6a58-137">7\.</span><span class="sxs-lookup"><span data-stu-id="e6a58-137">7\.</span></span> <span data-ttu-id="e6a58-138">A continuación, tiene que habilitar la cuenta del dispositivo con los equipos de superficie de concentrador.</span><span class="sxs-lookup"><span data-stu-id="e6a58-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="e6a58-139">Asegúrese de que su entorno cumple los requisitos definidos en la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="e6a58-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="e6a58-140">Iniciar una sesión remota de Windows PowerShell de manera (asegúrese de instalar Skype para componentes de PowerShell en línea de negocio):</span><span class="sxs-lookup"><span data-stu-id="e6a58-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="e6a58-141">A continuación, habilitar sus equipos para la cuenta de concentrador de superficie ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e6a58-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="e6a58-142">Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6a58-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="e6a58-143">No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="e6a58-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="e6a58-144">El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación.</span><span class="sxs-lookup"><span data-stu-id="e6a58-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="e6a58-145">Una vez haya completado los pasos anteriores para habilitar los equipos de la cuenta de concentrador de superficie, debe asignar una licencia para el dispositivo de v2 de concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="e6a58-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="e6a58-146">Uso del portal administrativo de Office 365, asignar los equipos de una licencia de concentrador de superficie para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e6a58-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="e6a58-147">Asignar una licencia a la cuenta</span><span class="sxs-lookup"><span data-stu-id="e6a58-147">Assign a license to the account</span></span>

1. <span data-ttu-id="e6a58-148">Inicie sesión como administrador de inquilinos, abra el centro de administración de Office 365 y haga clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="e6a58-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="e6a58-149">Haga clic en **usuarios y grupos**y, a continuación, haga clic en **Agregar usuarios, restablecer contraseñas y mucho más**.</span><span class="sxs-lookup"><span data-stu-id="e6a58-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="e6a58-150">Seleccione los equipos de cuenta de superficie concentrador y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.</span><span class="sxs-lookup"><span data-stu-id="e6a58-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="e6a58-151">Haga clic en la opción de **licencias** .</span><span class="sxs-lookup"><span data-stu-id="e6a58-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="e6a58-152">En la sección **asignación de licencias** , es necesario seleccionar el plan, dependiendo de su licencia.</span><span class="sxs-lookup"><span data-stu-id="e6a58-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="e6a58-153">Haga clic en **Guardar** para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="e6a58-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="e6a58-154">Instalación de los equipos para exponer concentrador desde el almacén de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6a58-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="e6a58-155">Estas instrucciones son para la instalación de los equipos de concentrador de superficie de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e6a58-155">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="e6a58-156">Iniciar el almacén de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e6a58-156">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="e6a58-157">a.</span><span class="sxs-lookup"><span data-stu-id="e6a58-157">a.</span></span> <span data-ttu-id="e6a58-158">Puntee en **Iniciar** > **todas las aplicaciones** > **configuración**.</span><span class="sxs-lookup"><span data-stu-id="e6a58-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="e6a58-159">b.</span><span class="sxs-lookup"><span data-stu-id="e6a58-159">b.</span></span> <span data-ttu-id="e6a58-160">Puntee en **dispositivo de concentrador de superficie de cuenta, administración**.</span><span class="sxs-lookup"><span data-stu-id="e6a58-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="e6a58-161">c.</span><span class="sxs-lookup"><span data-stu-id="e6a58-161">c.</span></span> <span data-ttu-id="e6a58-162">En la izquierda, puntee en la ficha **aplicaciones y características** .</span><span class="sxs-lookup"><span data-stu-id="e6a58-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="e6a58-163">d.</span><span class="sxs-lookup"><span data-stu-id="e6a58-163">d.</span></span> <span data-ttu-id="e6a58-164">En la derecha, puntee en el botón **Abrir almacén** .</span><span class="sxs-lookup"><span data-stu-id="e6a58-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="e6a58-165">De Microsoft Store, busque *Los equipos de Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="e6a58-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="e6a58-166">Se mostrarán los **Equipos de Microsoft para el concentrador de superficie** .</span><span class="sxs-lookup"><span data-stu-id="e6a58-166">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="e6a58-167">Puntee en el botón **obtener la aplicación** para instalar.</span><span class="sxs-lookup"><span data-stu-id="e6a58-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="e6a58-168">Una vez finalizada la instalación, reinicie el concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="e6a58-168">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="e6a58-169">Puntee en no en el **Inicio** de la lista de página de la tienda.</span><span class="sxs-lookup"><span data-stu-id="e6a58-169">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="e6a58-170">Hacer que los equipos de la aplicación de las reuniones y llamadas de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="e6a58-170">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="e6a58-171">Hay dos opciones para configurar la directiva de aplicación de llamadas y las reuniones de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="e6a58-171">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="e6a58-172">**Opción 1**: configurar a través de la clave USB.</span><span class="sxs-lookup"><span data-stu-id="e6a58-172">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="e6a58-173">**Opción 2**: configurar a través de MDM como Intune.</span><span class="sxs-lookup"><span data-stu-id="e6a58-173">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="e6a58-174">Opción 1: Configurar a través de la clave USB</span><span class="sxs-lookup"><span data-stu-id="e6a58-174">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="e6a58-175">Los paquetes se pueden encontrar en esta [página de descarga](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="e6a58-175">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="e6a58-176">Elija la adecuada para el paquete que va a instalar y cópielo a una clave USB.</span><span class="sxs-lookup"><span data-stu-id="e6a58-176">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="e6a58-177">El archivo .ppkg correcto para usar depende de la directiva de aplicación predeterminado que desea aplicar la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e6a58-177">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="e6a58-178">Número</span><span class="sxs-lookup"><span data-stu-id="e6a58-178">Number</span></span>  |<span data-ttu-id="e6a58-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6a58-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e6a58-180">0</span><span class="sxs-lookup"><span data-stu-id="e6a58-180">0</span></span>     | <span data-ttu-id="e6a58-181">Aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles</span><span class="sxs-lookup"><span data-stu-id="e6a58-181">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="e6a58-182">1</span><span class="sxs-lookup"><span data-stu-id="e6a58-182">1</span></span>     | <span data-ttu-id="e6a58-183">Aplicación preferida de los equipos en la pantalla de inicio, las reuniones de Skype disponibles</span><span class="sxs-lookup"><span data-stu-id="e6a58-183">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="e6a58-184">2</span><span class="sxs-lookup"><span data-stu-id="e6a58-184">2</span></span>     | <span data-ttu-id="e6a58-185">Aplicación exclusiva de los equipos en la pantalla de inicio (aplicación de Skype no está disponible)</span><span class="sxs-lookup"><span data-stu-id="e6a58-185">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="e6a58-186">Adjunta la clave USB en el dispositivo del concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="e6a58-186">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="e6a58-187">Abra la aplicación de **configuración** en un dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="e6a58-187">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="e6a58-188">Abra **administración de cuentas de dispositivo concentrador expuesta**.</span><span class="sxs-lookup"><span data-stu-id="e6a58-188">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="e6a58-189">Abra **administración de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e6a58-189">Open **Device Management**.</span></span> 
5. <span data-ttu-id="e6a58-190">Haga clic en **Agregar o quitar un paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="e6a58-190">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="e6a58-191">Haga clic en **Agregar paquete**.</span><span class="sxs-lookup"><span data-stu-id="e6a58-191">Click **Add Package**.</span></span>
7. <span data-ttu-id="e6a58-192">Seleccione la opción de **Medios extraíble** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="e6a58-192">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="e6a58-193">Agregar el paquete apropiado de **TeamsRTMMode\*.ppkg** que anteriormente se ha copiado a la clave USB.</span><span class="sxs-lookup"><span data-stu-id="e6a58-193">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="e6a58-194">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="e6a58-194">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="e6a58-195">Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="e6a58-195">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="e6a58-196">Opción 2: Configurar a través de MDM como Intune</span><span class="sxs-lookup"><span data-stu-id="e6a58-196">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="e6a58-197">Use lo siguiente para configurar la directiva de aplicación predeterminada llamadas y reuniones a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="e6a58-197">Use the following to configure the default calling and meetings application policy via Intune.</span></span>

<span data-ttu-id="e6a58-198">.</span><span class="sxs-lookup"><span data-stu-id="e6a58-198"></span></span>

|<span data-ttu-id="e6a58-199">Configuración</span><span class="sxs-lookup"><span data-stu-id="e6a58-199">Setting</span></span>   |<span data-ttu-id="e6a58-200">Valor</span><span class="sxs-lookup"><span data-stu-id="e6a58-200">Value</span></span>    |<span data-ttu-id="e6a58-201">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6a58-201">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="e6a58-202"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="e6a58-202">Path</span></span>      | <span data-ttu-id="e6a58-203">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="e6a58-203">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="e6a58-204">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e6a58-204">Data Type</span></span> | <span data-ttu-id="e6a58-205">entero (0-2)</span><span class="sxs-lookup"><span data-stu-id="e6a58-205">integer (0-2)</span></span>   |<span data-ttu-id="e6a58-206">0 - aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles</span><span class="sxs-lookup"><span data-stu-id="e6a58-206">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="e6a58-207">1 - equipos aplicación preferida en la pantalla de inicio, las reuniones de Skype disponibles</span><span class="sxs-lookup"><span data-stu-id="e6a58-207">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="e6a58-208">2 - equipos aplicación exclusivo en la pantalla de inicio (aplicación de Skype no está disponible)</span><span class="sxs-lookup"><span data-stu-id="e6a58-208">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="e6a58-209">Operaciones</span><span class="sxs-lookup"><span data-stu-id="e6a58-209">Operations</span></span>| <span data-ttu-id="e6a58-210">Obtener, establecer</span><span class="sxs-lookup"><span data-stu-id="e6a58-210">Get, Set</span></span>        |

|<span data-ttu-id="e6a58-211">Configuración</span><span class="sxs-lookup"><span data-stu-id="e6a58-211">Setting</span></span>   |<span data-ttu-id="e6a58-212">Valor</span><span class="sxs-lookup"><span data-stu-id="e6a58-212">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="e6a58-213"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="e6a58-213">Path</span></span>      | <span data-ttu-id="e6a58-214">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="e6a58-214">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="e6a58-215">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e6a58-215">Data Type</span></span> | <span data-ttu-id="e6a58-216">¡cadena - cadena de conjunto a los equipos el identificador del paquete de aplicación como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Los equipos**</span><span class="sxs-lookup"><span data-stu-id="e6a58-216">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="e6a58-217">Operaciones</span><span class="sxs-lookup"><span data-stu-id="e6a58-217">Operations</span></span>| <span data-ttu-id="e6a58-218">Obtener, establecer</span><span class="sxs-lookup"><span data-stu-id="e6a58-218">Get, Set</span></span>        |

<span data-ttu-id="e6a58-219">Reinicie el dispositivo concentrador de superficie.</span><span class="sxs-lookup"><span data-stu-id="e6a58-219">Restart the Surface Hub device.</span></span> <span data-ttu-id="e6a58-220">Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.</span><span class="sxs-lookup"><span data-stu-id="e6a58-220">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

