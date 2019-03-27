---
title: Operaciones y mantenimiento de sistemas de salón de Skype v2
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lea este tema para obtener más información acerca de la administración de sistemas de salón de Skype v2, la próxima generación de sistemas de salón de Skype.
ms.openlocfilehash: 29c3af2b73f9a8b1277abdc6a47afeb69cb26ef2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889325"
---
# <a name="skype-room-systems-v2-maintenance-and-operations"></a><span data-ttu-id="44115-103">Operaciones y mantenimiento de sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="44115-103">Skype Room Systems v2 maintenance and operations</span></span> 
 
<span data-ttu-id="44115-104">Lea este tema para obtener más información acerca de la administración de sistemas de salón de Skype v2, la próxima generación de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="44115-104">Read this topic to learn about management of Skype Room Systems v2, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="44115-105">V2 de sistemas de salón de Skype es la solución de conferencia más reciente de Microsoft diseñada para transformar la sala de reuniones en un Skype enriquecido, colaboración para que la experiencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="44115-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="44115-106">Los usuarios disfrutarán de su Skype familiar para la interfaz de negocios y los administradores de TI apreciará una aplicación de Windows 10 Skype reunión fácil de implementar y administrada.</span><span class="sxs-lookup"><span data-stu-id="44115-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="44115-107">Sistemas de salón de Skype v2 está diseñado para aprovechar equipamiento existente como paneles LCD para facilitar la de instalación para incorporar Skype para la empresa en la sala de reuniones.</span><span class="sxs-lookup"><span data-stu-id="44115-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="44115-108">Con una configuración adicional, es posible usar el Monitor de Azure de Microsoft como se describe en la [administración de sistemas de planeación de las salas Skype v2 con el Monitor de Azure](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [implementar sistemas de salón de Skype v2 administración con el Monitor de Azure](../../deploy/deploy-clients/azure-monitor.md), [administrar administración remota Dispositivos de sistemas de salón de Skype v2 con Azure Monitor](azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="44115-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Skype Room Systems v2 management with Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Skype Room Systems v2 management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md), [Manage Skype Room Systems v2 devices with Azure Monitor](azure-monitor.md).</span></span> <span data-ttu-id="44115-109">También puede ver [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), que incluye la aplicación de un tema de pantalla personalizado.</span><span class="sxs-lookup"><span data-stu-id="44115-109">You may also [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a><span data-ttu-id="44115-110">Recopilación de registros en los Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="44115-110">Collecting logs on Skype Room Systems v2</span></span>
<span data-ttu-id="44115-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-111"></span></span>

<span data-ttu-id="44115-112">Para recopilar los registros, se debe invocar la secuencia de comandos de la colección de registro que se distribuye con la aplicación de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="44115-112">To collect logs, you must invoke the log collection script that ships with the Skype Room Systems v2 app.</span></span> <span data-ttu-id="44115-113">En el modo de administrador, inicie un símbolo del sistema con privilegios elevados y emita el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="44115-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="44115-114">Los registros de será salida como un archivo ZIP en c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="44115-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="44115-115">Configuración de la pantalla frontal de la sala</span><span class="sxs-lookup"><span data-stu-id="44115-115">Front of Room Display Settings</span></span>
<span data-ttu-id="44115-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-116"></span></span>

<span data-ttu-id="44115-117">Configure la pantalla frontal de la sala en modo Extendido.</span><span class="sxs-lookup"><span data-stu-id="44115-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="44115-118">Al hacerlo, se asegurará de que la consola de la interfaz de usuario que no se repitan en que se muestran cuando se interrumpa la alimentación en la presentación.</span><span class="sxs-lookup"><span data-stu-id="44115-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44115-119">Una televisión de consumo usada como una parte delantera del salón de mostrar las necesidades de soporte técnico o habilitar la característica de Control de electrónica de consumidor (CEC) de HDMI para que puede cambiar automáticamente a un origen de vídeo activo de modo de espera.</span><span class="sxs-lookup"><span data-stu-id="44115-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="44115-120">Esta característica no se admite en todos los televisores.</span><span class="sxs-lookup"><span data-stu-id="44115-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a><span data-ttu-id="44115-121">Restablecer los Sistemas de salas de Skype v2 (a valores de fábrica)</span><span class="sxs-lookup"><span data-stu-id="44115-121">Skype Room Systems v2 Reset (Factory Restore)</span></span>
<span data-ttu-id="44115-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-122"></span></span>

<span data-ttu-id="44115-123">Si v2 de sistemas de salón de Skype no se está ejecutando bien, realizar un restablecimiento de fábrica puede ayudarle a.</span><span class="sxs-lookup"><span data-stu-id="44115-123">If Skype Room Systems v2 isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="44115-124">Esto puede realizarse en la aplicación de configuración en la ficha **recuperación** bajo **restablecer este equipo**, seleccione **empezar a**y, a continuación, **Quitar todo el contenido**.</span><span class="sxs-lookup"><span data-stu-id="44115-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="44115-125">Siga las indicaciones restantes para restablecer el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44115-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44115-126">Hay un problema conocido donde el v2 de sistemas de salón de Skype puede convertirse en no se puede usar si se selecciona la opción de **Guardar los archivos - quita aplicaciones y configuración, pero mantiene los archivos personales** durante el proceso de restablecimiento de Windows.</span><span class="sxs-lookup"><span data-stu-id="44115-126">There is a known issue where the Skype Room Systems v2 can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="44115-127">Hacer _no_ usar esta opción.</span><span class="sxs-lookup"><span data-stu-id="44115-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="44115-128">Opciones remotas admitidas</span><span class="sxs-lookup"><span data-stu-id="44115-128">Supported Remote Options</span></span>
<span data-ttu-id="44115-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-129"></span></span>

<span data-ttu-id="44115-130">La tabla siguiente resume las operaciones remotas posibles y los métodos que se pueden utilizar para llevarlas a cabo.</span><span class="sxs-lookup"><span data-stu-id="44115-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="44115-131">\*\*Grupo de trabajo \*\*</span><span class="sxs-lookup"><span data-stu-id="44115-131">**Workgroup**</span></span>|<span data-ttu-id="44115-132">**No unido a dominio**</span><span class="sxs-lookup"><span data-stu-id="44115-132">**Not domain joined**</span></span>|<span data-ttu-id="44115-133">**Unido a dominio**</span><span class="sxs-lookup"><span data-stu-id="44115-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44115-134">Reinicio</span><span class="sxs-lookup"><span data-stu-id="44115-134">Restart</span></span>  <br/> |<span data-ttu-id="44115-135">Escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="44115-135">Remote desktop</span></span>  <br/> <span data-ttu-id="44115-136">Powershell remoto</span><span class="sxs-lookup"><span data-stu-id="44115-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="44115-137">Escritorio remoto (requiere una configuración adicional)</span><span class="sxs-lookup"><span data-stu-id="44115-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="44115-138">Powershell remoto (requiere una configuración adicional)</span><span class="sxs-lookup"><span data-stu-id="44115-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="44115-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="44115-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="44115-140">Actualizar SO</span><span class="sxs-lookup"><span data-stu-id="44115-140">Update OS</span></span>  <br/> |<span data-ttu-id="44115-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="44115-141">Windows Update</span></span>  <br/> |<span data-ttu-id="44115-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="44115-142">Windows Update</span></span>  <br/> <span data-ttu-id="44115-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="44115-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="44115-144">Actualización de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="44115-144">App update</span></span>  <br/> |<span data-ttu-id="44115-145">Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="44115-145">Windows Store</span></span>  <br/> |<span data-ttu-id="44115-146">Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="44115-146">Windows Store</span></span>  <br/> <span data-ttu-id="44115-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="44115-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="44115-148">Configuración de cuenta de Skype</span><span class="sxs-lookup"><span data-stu-id="44115-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="44115-149">No se admite actualmente</span><span class="sxs-lookup"><span data-stu-id="44115-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="44115-150">No se admite actualmente</span><span class="sxs-lookup"><span data-stu-id="44115-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="44115-151">Registros de acceso</span><span class="sxs-lookup"><span data-stu-id="44115-151">Access logs</span></span>  <br/> |<span data-ttu-id="44115-152">No se admite actualmente</span><span class="sxs-lookup"><span data-stu-id="44115-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="44115-153">No se admite actualmente</span><span class="sxs-lookup"><span data-stu-id="44115-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a><span data-ttu-id="44115-154">Configurar la directiva de grupo para los Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="44115-154">Configuring Group Policy for Skype Room Systems v2</span></span>
<span data-ttu-id="44115-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-155"></span></span>

<span data-ttu-id="44115-156">En esta sección, se explica la configuración del sistema que depende de sistemas de salón de Skype v2 funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="44115-156">This section covers system settings that Skype Room Systems v2 depends on to function properly.</span></span> <span data-ttu-id="44115-157">Al unirse a sistemas de salón de Skype v2 a un dominio, asegúrese de que la directiva de grupo no invalidar la configuración en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="44115-157">When joining Skype Room Systems v2 to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="44115-158">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="44115-158">**Setting**</span></span>|<span data-ttu-id="44115-159">**Permite**</span><span class="sxs-lookup"><span data-stu-id="44115-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44115-160">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = 1 (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="44115-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="44115-161">Permite v2 de sistemas de salón de Skype iniciar copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="44115-161">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="44115-162">Administración de energía -\> en AC, desactivar pantalla después de 10 minutos</span><span class="sxs-lookup"><span data-stu-id="44115-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="44115-163">Administración de energía -\> en AC, nunca colocar del sistema al modo de suspensión</span><span class="sxs-lookup"><span data-stu-id="44115-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="44115-164">Permite v2 de sistemas de salón de Skype para desactivar muestra adjunto y reactivar automáticamente</span><span class="sxs-lookup"><span data-stu-id="44115-164">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="44115-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="44115-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="44115-166">O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local.</span><span class="sxs-lookup"><span data-stu-id="44115-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="44115-167">Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado.</span><span class="sxs-lookup"><span data-stu-id="44115-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="44115-168">Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.</span><span class="sxs-lookup"><span data-stu-id="44115-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="44115-169">Permite que la cuenta de Skype siempre inicie sesión</span><span class="sxs-lookup"><span data-stu-id="44115-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="44115-170">Transferencia de archivos mediante directivas de grupo se describe en [configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="44115-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="44115-171">Administración remota con PowerShell</span><span class="sxs-lookup"><span data-stu-id="44115-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="44115-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-172"></span></span>

<span data-ttu-id="44115-173">Puede realizar las siguientes operaciones de administración de forma remota mediante el uso de PowerShell (vea la tabla siguiente para ejemplos de secuencia de comandos):</span><span class="sxs-lookup"><span data-stu-id="44115-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="44115-174">Obtener dispositivos conectados</span><span class="sxs-lookup"><span data-stu-id="44115-174">Get attached devices</span></span>
    
- <span data-ttu-id="44115-175">Obtener estado de la aplicación</span><span class="sxs-lookup"><span data-stu-id="44115-175">Get app status</span></span>
    
- <span data-ttu-id="44115-176">Obtener información del sistema</span><span class="sxs-lookup"><span data-stu-id="44115-176">Get system info</span></span>
    
- <span data-ttu-id="44115-177">Reiniciar el sistema</span><span class="sxs-lookup"><span data-stu-id="44115-177">Reboot system</span></span>
    
- <span data-ttu-id="44115-178">Recuperar registros</span><span class="sxs-lookup"><span data-stu-id="44115-178">Retrieve logs</span></span>
    
- <span data-ttu-id="44115-179">Transferencia de archivos (requiere una v2 de Skype salón sistemas unidos a un dominio)</span><span class="sxs-lookup"><span data-stu-id="44115-179">Transfer files (requires a domain-joined Skype Room Systems v2)</span></span>
    
> [!NOTE]
> <span data-ttu-id="44115-180">Esta funcionalidad está desactivada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="44115-180">This functionality is off by default.</span></span> <span data-ttu-id="44115-181">Tiene que habilitar PowerShell remoto para el entorno en el sistema de v2 de sistemas de salón de Skype para llevar a cabo las operaciones que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="44115-181">You need to enable remote PowerShell for your environment on the Skype Room Systems v2 system to perform the operations below.</span></span> <span data-ttu-id="44115-182">Consulte la documentación en **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** para obtener información acerca de cómo habilitar PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="44115-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="44115-183">Por ejemplo, puede habilitar PowerShell remoto de esta manera:</span><span class="sxs-lookup"><span data-stu-id="44115-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="44115-184">Inicie sesión como administrador en un dispositivo de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="44115-184">Sign in as Admin on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="44115-185">Abra un símbolo del sistema de PowerShell comando con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="44115-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="44115-186">Escriba el siguiente comando: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="44115-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="44115-187">Para ejecutar una operación de administración:</span><span class="sxs-lookup"><span data-stu-id="44115-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="44115-188">Inicie sesión en un equipo con las credenciales de cuenta que tiene permiso para ejecutar los comandos de PowerShell en un dispositivo de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="44115-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="44115-189">Abra un símbolo PowerShell regular en su PC.</span><span class="sxs-lookup"><span data-stu-id="44115-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="44115-190">Copie el texto del comando de la tabla siguiente y péguelo en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="44115-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="44115-191">Reemplace `<Device fqdn>` campos con valores FQDN apropiados para su entorno.</span><span class="sxs-lookup"><span data-stu-id="44115-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="44115-192">Reemplace \* \<ruta de acceso\> \* con el nombre de archivo y ruta de acceso local del archivo de configuración de SkypeSettings.xml maestra (o imagen de tema).</span><span class="sxs-lookup"><span data-stu-id="44115-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="44115-193">Para obtener los dispositivos conectados</span><span class="sxs-lookup"><span data-stu-id="44115-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="44115-194">Obtener estado de la aplicación</span><span class="sxs-lookup"><span data-stu-id="44115-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="44115-195">Obtener información del sistema</span><span class="sxs-lookup"><span data-stu-id="44115-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="44115-196">Reiniciar el sistema</span><span class="sxs-lookup"><span data-stu-id="44115-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="44115-197">Recuperar registros</span><span class="sxs-lookup"><span data-stu-id="44115-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="44115-198">Inserción de un archivo de configuración XML (o gráficos)</span><span class="sxs-lookup"><span data-stu-id="44115-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="44115-199">Actualizaciones de software</span><span class="sxs-lookup"><span data-stu-id="44115-199">Software updates</span></span>
<span data-ttu-id="44115-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-200"></span></span>

<span data-ttu-id="44115-201">De forma predeterminada, sistemas de salón de Skype v2 intenta conectarse a la tienda de Windows para obtener la versión más reciente de software de sistemas de salón de Skype v2, por lo que el dispositivo requiere acceso a internet de regular.</span><span class="sxs-lookup"><span data-stu-id="44115-201">By default, Skype Room Systems v2 attempts to connect to the Windows Store to get the latest version of Skype Room Systems v2 software, so the device will require regular internet access.</span></span> <span data-ttu-id="44115-202">Antes de ponerse en contacto con Microsoft con problemas de soporte técnico, asegúrese de que el dispositivo de v2 de sistemas de salón de Skype se carga con la versión más reciente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="44115-202">Before contacting Microsoft with support issues, be sure the Skype Room Systems v2 device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="44115-203">De forma predeterminada, v2 de sistemas de salón de Skype se conecta a Windows Update para recuperar el sistema operativo y actualizaciones de firmware del dispositivo periférico USB y las instala fuera del horario configurado.</span><span class="sxs-lookup"><span data-stu-id="44115-203">By default, Skype Room Systems v2 connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="44115-204">Para configurar horarios comerciales, puede iniciar sesión en la cuenta de administrador y ejecutar la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="44115-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="44115-205">Si desea administrar manualmente las actualizaciones y no puede seguir el procedimiento normal para el [Almacén de Microsoft para la empresa](https://businessstore.microsoft.com/store) para [distribuir las aplicaciones sin conexión](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), puede adquirir el archivo APPX correspondiente y las dependencias desde el [kit de implementación](https://go.microsoft.com/fwlink/?linkid=851168) (desde las instrucciones para [Configurar una consola de v2 de sistemas de salón de Skype](../../deploy/deploy-clients/console.md)) que se pueden utilizar con SCCM.</span><span class="sxs-lookup"><span data-stu-id="44115-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="44115-206">La versión del kit de implementación queda muy por detrás de la versión de almacenamiento, por lo que es posible que no siempre coincide con la compilación más reciente disponible.</span><span class="sxs-lookup"><span data-stu-id="44115-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="44115-207">Para actualizar el uso de Powershell</span><span class="sxs-lookup"><span data-stu-id="44115-207">To update using Powershell</span></span>

1. <span data-ttu-id="44115-208">Extraer el paquete de la instalación que se puede tener acceso a [MSI](https://go.microsoft.com/fwlink/?linkid=851168) en un recurso compartido del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44115-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="44115-209">Ejecute el siguiente script de identificación de los dispositivos de v2 de sistemas de salón de Skype, cambiar \<compartir\> al dispositivo compartir según corresponda:</span><span class="sxs-lookup"><span data-stu-id="44115-209">Run the following script targeting the Skype Room Systems v2 devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="44115-210">Modo de administrador y administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="44115-210">Admin mode and device management</span></span>
<span data-ttu-id="44115-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-211"></span></span>

<span data-ttu-id="44115-212">Algunas funciones de administración, al igual que la instalación manual de un certificado de entidad de certificación privado, requieren colocar el dispositivo Surface Pro en modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="44115-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a><span data-ttu-id="44115-213">Cambia al modo de administrador y cuando se ejecuta la aplicación v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="44115-213">Switching to Admin Mode and back when the Skype Room Systems v2 app is running</span></span>

1. <span data-ttu-id="44115-214">Colgar las llamadas en curso y volver a la pantalla principal.</span><span class="sxs-lookup"><span data-stu-id="44115-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="44115-215">Seleccione el icono del engranaje y abrir el menú (son de las opciones de **configuración**, la **accesibilidad**y **Reinicie el dispositivo** ).</span><span class="sxs-lookup"><span data-stu-id="44115-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="44115-216">Seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="44115-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="44115-217">Introduzca la contraseña de administrador.</span><span class="sxs-lookup"><span data-stu-id="44115-217">Enter the Administrator Password.</span></span> <span data-ttu-id="44115-218">Se abrirá la pantalla Configuración.</span><span class="sxs-lookup"><span data-stu-id="44115-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="44115-219">Si el dispositivo no está unido a un dominio, se usará la cuenta administrativa local (nombre de usuario "Admin") de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="44115-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="44115-220">La contraseña predeterminada de esta cuenta es "sfb", aunque se recomienda a la organización que la cambie por motivos de seguridad tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="44115-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="44115-221">Si el equipo está unido a un dominio, puede iniciar sesión con una cuenta de dominio con privilegios de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="44115-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="44115-222">Seleccione **Configuración de Windows** en la columna izquierda.</span><span class="sxs-lookup"><span data-stu-id="44115-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="44115-223">Seleccione **Ir a inicio de sesión de administrador**.</span><span class="sxs-lookup"><span data-stu-id="44115-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="44115-224">Introduzca la contraseña de administrador.</span><span class="sxs-lookup"><span data-stu-id="44115-224">Enter the Administrator Password.</span></span> <span data-ttu-id="44115-225">De este modo, se cierra la sesión de la aplicación y se le dirige a la pantalla de inicio de sesión de Windows.</span><span class="sxs-lookup"><span data-stu-id="44115-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="44115-226">Inicie sesión en el escritorio con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="44115-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="44115-227">Tendrá los privilegios necesarios para administrar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44115-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="44115-228">Realice las tareas de administración que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="44115-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="44115-229">Cierre la sesión de la cuenta del administrador.</span><span class="sxs-lookup"><span data-stu-id="44115-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="44115-230">Volver a sistemas de salón de Skype v2, seleccione el icono de la cuenta de usuario en el extremo izquierdo de la pantalla y, a continuación, seleccione **Skype**.</span><span class="sxs-lookup"><span data-stu-id="44115-230">Return to Skype Room Systems v2 by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="44115-231">Si el usuario de **Skype** no aparece, es posible que deba seleccione **otro usuario** y escriba **. \skype** como el nombre de usuario y de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="44115-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="44115-232">La consola ahora es nuevo en el modo de funcionamiento normal. El siguiente procedimiento requiere adjuntar un teclado al dispositivo si uno no está asociado.</span><span class="sxs-lookup"><span data-stu-id="44115-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a><span data-ttu-id="44115-233">Cambia al modo de administrador y cuando se bloquea la aplicación v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="44115-233">Switching to Admin Mode and back when the Skype Room Systems v2 app crashes</span></span>

1. <span data-ttu-id="44115-234">Presione rápidamente la tecla Windows cinco veces.</span><span class="sxs-lookup"><span data-stu-id="44115-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="44115-235">De este modo accederá a la pantalla de inicio de sesión de Windows.</span><span class="sxs-lookup"><span data-stu-id="44115-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="44115-236">Inicie sesión en el escritorio con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="44115-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="44115-237">Este método no cierre la sesión del usuario de Skype o finalizar correctamente la aplicación, pero usaría si no se responde a la aplicación y el otro método no estaba disponible.</span><span class="sxs-lookup"><span data-stu-id="44115-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="44115-238">Realice las tareas de administración que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="44115-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="44115-239">Cuando haya terminado, reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="44115-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="44115-240">La consola se reinicia en su modo de funcionamiento normal, que ejecuta la aplicación de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="44115-240">The console restarts into its normal operation mode, running the Skype Room Systems v2 app.</span></span> <span data-ttu-id="44115-241">Puede quitar el teclado, si estaba asociado para que pueda llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="44115-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="44115-242">Sugerencias para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="44115-242">Troubleshooting tips</span></span>
   <span data-ttu-id="44115-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="44115-243"></span></span>

- <span data-ttu-id="44115-244">No es posible que aparezcan las invitaciones a reuniones cuando se envían a través de los límites del dominio (por ejemplo, entre las dos compañías).</span><span class="sxs-lookup"><span data-stu-id="44115-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="44115-245">En estos casos, los administradores de TI deben decidir si desea permitir que los usuarios externos programar una reunión.</span><span class="sxs-lookup"><span data-stu-id="44115-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="44115-246">Sistemas de salón de Skype v2 no admite redirecciones de detección automática de Exchange a través de Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="44115-246">Skype Room Systems v2 doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="44115-247">En general, es una práctica recomendada para los administradores de TI deshabilitar los extremos de audio que no desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="44115-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="44115-248">En el caso de que una imagen reflejada aparezca en la vista previa de la sala, el administrador de TI puede corregir desconectando y volviendo a conectar la cámara o volteando la orientación de la imagen con el control remoto de la cámara.</span><span class="sxs-lookup"><span data-stu-id="44115-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="44115-249">Ha habido casos de pérdida de acceso táctil a la consola.</span><span class="sxs-lookup"><span data-stu-id="44115-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="44115-250">En estos casos, el problema a veces se resuelve reiniciando el sistema v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="44115-250">In such cases, the issue is sometimes resolved by restarting the Skype Room Systems v2 system.</span></span>
    
- <span data-ttu-id="44115-251">Ha habido casos de pérdida de audio local al conectar un PC a la consola mediante una transmisión integrada.</span><span class="sxs-lookup"><span data-stu-id="44115-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="44115-252">En esos casos, el problema de reproducción de audio local se puede resolver reiniciando el PC.</span><span class="sxs-lookup"><span data-stu-id="44115-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
