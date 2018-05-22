---
title: Configurar una consola de Sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar el dispositivo de consola de los Sistemas de sala de Skype v2 y sus periféricos.
ms.openlocfilehash: 96fb2a88d699ca364f02f24af58d2f17dc555e11
ms.sourcegitcommit: 1cb8ab7d1e3debb84f051be404403e4a116ee741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="173a1-103">Configurar una consola de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="173a1-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="173a1-104">En este artículo se describe cómo configurar el dispositivo de consola de los Sistemas de sala de Skype v2 y sus periféricos.</span><span class="sxs-lookup"><span data-stu-id="173a1-104">This article describes how to set up the Skype Room Systems v2 console device and its peripherals.</span></span>
  
<span data-ttu-id="173a1-105">Sólo debe realizar estos pasos si el Skype es necesario para las cuentas empresariales y de Exchange ya se han creado y probado tal como se describe en [implementar sistemas de salón de Skype v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="173a1-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="173a1-106">Necesitará el hardware y software descritos en [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="173a1-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="173a1-107">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="173a1-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="173a1-108">Preparación de la imagen de instalación</span><span class="sxs-lookup"><span data-stu-id="173a1-108">Prepare the installation image</span></span>](console.md#Prep_Image)
    
- [<span data-ttu-id="173a1-109">Instalar un certificado de entidad de certificación privado en el dispositivo de tableta</span><span class="sxs-lookup"><span data-stu-id="173a1-109">Install a private CA certificate on the tablet device</span></span>](console.md#Certs)
    
- [<span data-ttu-id="173a1-110">Instalar Windows 10 y la aplicación de consola de v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="173a1-110">Install Windows 10 and the Skype Room Systems v2 console app </span></span>](console.md#Reimage)
   
- [<span data-ttu-id="173a1-111">Configuración inicial de la consola</span><span class="sxs-lookup"><span data-stu-id="173a1-111">Initial set up of the Console </span></span>](console.md#Initial)
    
- [<span data-ttu-id="173a1-112">Lista de comprobación de implementación de v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="173a1-112">Skype Room Systems v2 Deployment Checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="173a1-113">Sistemas de salón de Skype v2 sólo funciona en un Skype configurada correctamente para el entorno empresarial donde las cuentas de dispositivos estén configuradas correctamente, tal como se describe en [implementar sistemas de salón de Skype v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="173a1-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-image"></a><span data-ttu-id="173a1-114">Preparación de la imagen de instalación</span><span class="sxs-lookup"><span data-stu-id="173a1-114">Prepare the installation image</span></span>
<span data-ttu-id="173a1-115"><a name="Prep_Image"> </a></span><span class="sxs-lookup"><span data-stu-id="173a1-115"></span></span>

<span data-ttu-id="173a1-116">Instalar la aplicación v2 de sistemas de salón de Skype en un Surface Pro 4 o Surface Pro requiere un dispositivo de almacenamiento USB con al menos 32GB de memoria con formato de un disco FAT32.</span><span class="sxs-lookup"><span data-stu-id="173a1-116">Installing the Skype Room Systems v2 app on a Surface Pro 4 or Surface Pro requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="173a1-117">No debe haber ningún otro archivo en el dispositivo, se perderán todos los archivos existentes en el almacenamiento USB.</span><span class="sxs-lookup"><span data-stu-id="173a1-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="173a1-118">Si no se lograr crear la imagen de consola de acuerdo con estas instrucciones, el resultado probablemente será un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="173a1-118">Failure to create your console image according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="173a1-119">Actualización de aniversario de empresa de Windows 10 (versión 1607) ya no se admite para la creación de sistemas de salón de Skype v2 imagen.</span><span class="sxs-lookup"><span data-stu-id="173a1-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 image creation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="173a1-120">Funcionará un v2 de Skype salón sistemas existentes con Windows 10 Enterprise aniversario de actualización de mover a sistemas de salón de Skype v2 actualización 3 mediante el almacén de Windows, pero se debe realizar una nueva instalación tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="173a1-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="173a1-121">Descargue la [MSU para KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span><span class="sxs-lookup"><span data-stu-id="173a1-121">Download the [MSU for KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span></span>
2. <span data-ttu-id="173a1-122">Descargar el [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="173a1-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
3. <span data-ttu-id="173a1-123">Colocar la MSU para KB4056892 en el mismo directorio que la secuencia de comandos CreateSrsMedia.ps1.</span><span class="sxs-lookup"><span data-stu-id="173a1-123">Place the MSU for KB4056892 in the same directory as the CreateSrsMedia.ps1 script.</span></span>
4. <span data-ttu-id="173a1-124">Ejecute el script CreateSrsMedia.ps1 desde un símbolo del sistema con privilegios elevados en un equipo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="173a1-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="173a1-125">Siga las instrucciones de la secuencia de comandos para crear un disco de instalación de sistemas de salón de Skype v2 USB.</span><span class="sxs-lookup"><span data-stu-id="173a1-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="173a1-126">Cuando haya terminado, quitar el disco USB de su equipo y proceda a [instalar 10 de Windows y la aplicación de consola de sistemas de salón de Skype v2 ](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="173a1-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app ](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="173a1-127">Instalación de Windows 10 y la aplicación de consola Sistemas de salas de Skype </span><span class="sxs-lookup"><span data-stu-id="173a1-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="173a1-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="173a1-128"></span></span>

<span data-ttu-id="173a1-129">En este momento, deberá aplicar la imagen que ha creado.</span><span class="sxs-lookup"><span data-stu-id="173a1-129">You now need to apply the image you've created.</span></span> <span data-ttu-id="173a1-130">La tableta se ejecutará como un dispositivo y el usuario predeterminado se establecerá en sólo ejecutar la aplicación de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="173a1-130">The tablet will run as an appliance and the default user will be set to only run the Skype Room Systems v2 app.</span></span> 
  
1. <span data-ttu-id="173a1-131">Tablet PC debe estar conectado a una fuente de alimentación.</span><span class="sxs-lookup"><span data-stu-id="173a1-131">The tablet should be connected to a power source.</span></span> <span data-ttu-id="173a1-132">Iníciela cuando esté completamente apagada.</span><span class="sxs-lookup"><span data-stu-id="173a1-132">Start from a completely powered-off state.</span></span> <span data-ttu-id="173a1-133">Si es necesario, presione y mantener al presionar el botón de encendido hasta que se desactiva la tableta.</span><span class="sxs-lookup"><span data-stu-id="173a1-133">If necessary, press and keep pressing the Power button until the tablet switches off.</span></span>
    
2. <span data-ttu-id="173a1-134">Conecte el disco de instalación de USB en Tablet PC.</span><span class="sxs-lookup"><span data-stu-id="173a1-134">Plug your USB Setup disk into the tablet.</span></span>
    
3. <span data-ttu-id="173a1-135">Presione y mantenga el volumen hacia abajo (-) situado en el equipo Tablet PC.</span><span class="sxs-lookup"><span data-stu-id="173a1-135">Press and continue to hold the volume down (-) button on the tablet.</span></span> 
    
4. <span data-ttu-id="173a1-136">Presione y suelte el botón de encendido en el equipo Tablet PC.</span><span class="sxs-lookup"><span data-stu-id="173a1-136">Press and release the power button on the tablet.</span></span>
    
5. <span data-ttu-id="173a1-137">Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).</span><span class="sxs-lookup"><span data-stu-id="173a1-137">Once Windows setup is booted, release the volume down (-) button.</span></span>
    
6. <span data-ttu-id="173a1-138">El sistema se cerrará una vez finalizada la instalación.</span><span class="sxs-lookup"><span data-stu-id="173a1-138">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="173a1-139">Después de que se apague el sistema, es seguro quitar el disco de instalación de USB.</span><span class="sxs-lookup"><span data-stu-id="173a1-139">After the system has shut down, it is safe to remove the USB Setup Disk.</span></span> <span data-ttu-id="173a1-140">En este momento, puede colocar Tablet PC en el muelle y vincular los periféricos necesarios para la sala de reuniones.</span><span class="sxs-lookup"><span data-stu-id="173a1-140">At this point, you can place the tablet in the dock and attach the peripherals needed for your meeting room.</span></span> <span data-ttu-id="173a1-141">Consulte las instrucciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="173a1-141">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="173a1-142">Selección de un idioma en la actualización del creador</span><span class="sxs-lookup"><span data-stu-id="173a1-142">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="173a1-143">En la actualización del creador, necesitará utilizar la secuencia de comandos ApplyCurrentRegionAndLanguage.ps1 en escenarios donde selección del idioma implícita no proporciona al usuario con el idioma de la aplicación real que desean (por ejemplo, desean que la aplicación para que surjan en francés, pero es próximamente en inglés).</span><span class="sxs-lookup"><span data-stu-id="173a1-143">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="173a1-144">Las instrucciones siguientes sólo funcionan para los dispositivos creados con Update del creador de Windows.</span><span class="sxs-lookup"><span data-stu-id="173a1-144">The following instructions work only for devices created using Windows Creator's Update.</span></span> <span data-ttu-id="173a1-145">No podrá usar estas instrucciones sistemas heredados/en-mercado que no hayan sido renovados correctamente para el nuevo sistema de aprovisionamiento, pero también no debe verse afectado desde el problema inicial que requiere esta intervención manual (aniversario Edition le permiten elegir su idioma de la aplicación explícitamente como parte del programa de instalación).</span><span class="sxs-lookup"><span data-stu-id="173a1-145">Legacy/in-market systems that have not been re-imaged properly to the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span> 
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="173a1-146">Para aplicar el idioma deseado</span><span class="sxs-lookup"><span data-stu-id="173a1-146">To apply your desired language</span></span>

1. <span data-ttu-id="173a1-147">Cambiar al modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="173a1-147">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="173a1-148">Seleccione el menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="173a1-148">Select the Start menu.</span></span>
    
3. <span data-ttu-id="173a1-149">Seleccione el icono de engranaje para iniciar la aplicación de **configuración** .</span><span class="sxs-lookup"><span data-stu-id="173a1-149">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="173a1-150">Seleccione **tiempo &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="173a1-150">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="173a1-151">Seleccione **región &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="173a1-151">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="173a1-152">Seleccione **Agregar un idioma**.</span><span class="sxs-lookup"><span data-stu-id="173a1-152">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="173a1-153">Seleccione el idioma que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="173a1-153">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="173a1-154">Seleccione el idioma que acaba de agregar a la lista de "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="173a1-154">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="173a1-155">Seleccione **establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="173a1-155">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="173a1-156">Para los idiomas que desea quitar:</span><span class="sxs-lookup"><span data-stu-id="173a1-156">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="173a1-157">a.</span><span class="sxs-lookup"><span data-stu-id="173a1-157">a.</span></span> <span data-ttu-id="173a1-158">Seleccione el idioma que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="173a1-158">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="173a1-159">b.</span><span class="sxs-lookup"><span data-stu-id="173a1-159">b.</span></span> <span data-ttu-id="173a1-160">Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="173a1-160">Select **Remove**.</span></span>
    
11. <span data-ttu-id="173a1-161">Inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="173a1-161">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="173a1-162">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="173a1-162">Run the following command:</span></span> 
    
    <span data-ttu-id="173a1-163">PowerShell - executionpolicy sin restricciones c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="173a1-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="173a1-164">Reinicie el sistema.</span><span class="sxs-lookup"><span data-stu-id="173a1-164">Restart the system.</span></span>
    
<span data-ttu-id="173a1-165">El idioma que desee ahora se aplica al dispositivo v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="173a1-165">Your desired language is now applied to the Skype Room Systems v2 device.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="173a1-166">Configuración inicial de la consola </span><span class="sxs-lookup"><span data-stu-id="173a1-166">Initial set up of the Console</span></span>
<span data-ttu-id="173a1-167"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="173a1-167"></span></span>

<span data-ttu-id="173a1-168">Después de instalar Windows, la aplicación de sistemas de salón de Skype v2 entra en su proceso de instalación inicial cuando se inicia siguiente o si se ha seleccionado la opción Reboot.</span><span class="sxs-lookup"><span data-stu-id="173a1-168">After Windows is installed, the Skype Room Systems v2 app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="173a1-p111">Aparece la pantalla Cuenta de usuario. Introduzca la dirección de inicio de sesión de Skype (con el formato usuario@dominio) de la cuenta de la sala que se va a utilizar con el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="173a1-p111">The User Account screen appears. Enter the Skype sign-in address (in user@domain format) of the room account to be used with the device.</span></span>
    
2. <span data-ttu-id="173a1-171">Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="173a1-171">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="173a1-172">Bajo "Configuración de dominio", establecer el FQDN para el Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="173a1-172">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="173a1-173">Si el Skype para el dominio SIP empresarial es diferente del dominio de Exchange del usuario, escriba el dominio de Exchange en este campo.</span><span class="sxs-lookup"><span data-stu-id="173a1-173">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="173a1-174">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="173a1-174">Click **Next**.</span></span>
    
5. <span data-ttu-id="173a1-175">Seleccione los dispositivos indicados en la pantalla de las características y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="173a1-175">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="173a1-176">De manera predeterminada, la opción Pantalla compartida automática está activada y Ocultar nombres de las reuniones está desactivada.</span><span class="sxs-lookup"><span data-stu-id="173a1-176">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="173a1-177">Los dispositivos que se deben seleccionar son:</span><span class="sxs-lookup"><span data-stu-id="173a1-177">The devices to select are:</span></span>
    
   - <span data-ttu-id="173a1-178">Micrófono para conferencias: el micrófono predeterminado de esta sala de conferencias.</span><span class="sxs-lookup"><span data-stu-id="173a1-178">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="173a1-179">Altavoz para conferencias: el altavoz predeterminado para las conferencias. </span><span class="sxs-lookup"><span data-stu-id="173a1-179">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="173a1-180">Altavoz predeterminado: el altavoz que se usa para el audio de la transmisión por HDMI.</span><span class="sxs-lookup"><span data-stu-id="173a1-180">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="173a1-p114">Cada elemento tiene un menú desplegable en el que puede hacer selecciones. Deberá realizar una selección para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="173a1-p114">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="173a1-183">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="173a1-183">Click **Finish**.</span></span>
    
<span data-ttu-id="173a1-184">La aplicación debe iniciar inmediatamente el inicio de sesión en Skype para Business Server 2015 con las credenciales especificadas anteriormente y también debe comenzar a sincronizar su calendario con Exchange utilizando las mismas credenciales.</span><span class="sxs-lookup"><span data-stu-id="173a1-184">The app should immediately start signing in to Skype for Business Server 2015 with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="173a1-185">Para obtener información detallada sobre el uso de la aplicación, consulte la [Ayuda de sistemas de salón de Skype versión 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="173a1-185">For details on using the app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="173a1-186">Sistemas de salón de Skype v2 se basa en la presencia de hardware de consola certificadas (el Logitech SmartDock).</span><span class="sxs-lookup"><span data-stu-id="173a1-186">Skype Room Systems v2 relies on the presence of certified console hardware (the Logitech SmartDock).</span></span> <span data-ttu-id="173a1-187">No se iniciará incluso una imagen creada correctamente que contiene la aplicación v2 de sistemas de salón de Skype cargada en un Surface Pro 4 o Surface Pro pasadas de un documento el procedimiento de instalación inicial, a menos que se detecta el hardware de la consola.</span><span class="sxs-lookup"><span data-stu-id="173a1-187">Even a correctly created image containing the Skype Room Systems v2 app loaded on a Surface Pro 4 or Surface Pro will not boot past the initial setup procedure unless the console hardware is detected.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="173a1-188">Es posible que algunos usuarios que no sean de habla inglesa deban conectar un teclado físico a la consola durante la configuración inicial en caso de que los símbolos no se admitan en el teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="173a1-188">Some non-English language users may need a physical keyboard connected to the Console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span> 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a><span data-ttu-id="173a1-189">Instalar un certificado de entidad de certificación privado en el dispositivo de tableta</span><span class="sxs-lookup"><span data-stu-id="173a1-189">Install a private CA certificate on the tablet device</span></span>
<span data-ttu-id="173a1-190"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="173a1-190"></span></span>

<span data-ttu-id="173a1-191">El dispositivo de v2 de sistemas de salón de Skype debe confiar en los certificados usados por el Skype para servidores empresariales y de Exchange a que se conecta.</span><span class="sxs-lookup"><span data-stu-id="173a1-191">The Skype Room Systems v2 device needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="173a1-192">Para O365, este proceso se realiza automáticamente, puesto que los servidores utilizan entidades de certificación públicas y Windows 10 confía en ellas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="173a1-192">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="173a1-193">En un caso donde la entidad emisora de certificados es privada, por ejemplo, una implementación local con Active Directory y la entidad emisora de certificados de Windows, puede agregar el certificado en el dispositivo de v2 de sistemas de salón de Skype en un par de maneras:</span><span class="sxs-lookup"><span data-stu-id="173a1-193">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 device in a couple of ways:</span></span>
  
- <span data-ttu-id="173a1-194">Puede unir el dispositivo a Active Directory y este agregará automáticamente los certificados necesarios, dado que la entidad de certificación los publica para Active Directory (opción de implementación normal).</span><span class="sxs-lookup"><span data-stu-id="173a1-194">You can join the device to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="173a1-p118">Puede instalar el certificado manualmente después del proceso de creación de imágenes. Antes de hacerlo, deberá completar la [Configuración inicial de la consola](console.md#Initial). </span><span class="sxs-lookup"><span data-stu-id="173a1-p118">You can install the certificate manually after the imaging process. Before you do this, you must complete [Initial set up of the Console ](console.md#Initial).</span></span> 
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="173a1-197">Para instalar manualmente el certificado </span><span class="sxs-lookup"><span data-stu-id="173a1-197">To manually install the certificate</span></span>

1. <span data-ttu-id="173a1-198">Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="173a1-198">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="173a1-199">Colocar la superficie de 4 en modo de administrador (consulte [administración de modo y el dispositivo de administración](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="173a1-199">Place the Surface 4 in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="173a1-200">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="173a1-200">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="173a1-201">Unión al dominio de Active Directory (opcional)</span><span class="sxs-lookup"><span data-stu-id="173a1-201">Join an Active Directory Domain (Optional)</span></span>
<span data-ttu-id="173a1-202"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="173a1-202"></span></span>

<span data-ttu-id="173a1-203">Puede participar en los dispositivos de sistemas de salón de Skype v2 a su dominio.</span><span class="sxs-lookup"><span data-stu-id="173a1-203">You can join Skype Room Systems v2 devices to your domain.</span></span> <span data-ttu-id="173a1-204">Dispositivos de sistemas de salón de Skype v2 deben ubicarse en una unidad organizativa independiente desde estaciones de trabajo de sus PC debido a que muchas de las directivas de estación de trabajo no son compatibles con sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="173a1-204">Skype Room Systems v2 devices should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="173a1-205">Un ejemplo común son las directivas de cumplimiento de contraseña que se impiden que se inicie automáticamente sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="173a1-205">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="173a1-206">Para obtener información acerca de la administración de configuraciones de GPO, consulte [administrar sistemas de salón de Skype v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="173a1-206">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span> 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="173a1-207">Para unir Sistemas de salas de Skype v2 a un dominio</span><span class="sxs-lookup"><span data-stu-id="173a1-207">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="173a1-208">Inicio de sesión en la consola de la administración de cuenta (consulte [administración de modo y el dispositivo de administración](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="173a1-208">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="173a1-209">Inicie un símbolo de sistema de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="173a1-209">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="173a1-210">Introduzca el siguiente comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="173a1-210">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="173a1-211">Por ejemplo, si su nombre de dominio completo es redmond.corp.microsoft.com y desea que los dispositivos de v2 de sistemas de salón de Skype para estar en un "v2 de sistemas de las salas de Skype" unidad organizativa que es un elemento secundario de una unidad organizativa "recursos", el comando será:</span><span class="sxs-lookup"><span data-stu-id="173a1-211">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 devices to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="173a1-212">Si desea cambiar el nombre del equipo al unir a un dominio, use la marca - NewName seguida por el nombre del equipo nuevo.</span><span class="sxs-lookup"><span data-stu-id="173a1-212">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="173a1-213">Lista de comprobación para la implementación de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="173a1-213">Skype Room Systems v2 Deployment Checklist</span></span>
<span data-ttu-id="173a1-214"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="173a1-214"></span></span>

<span data-ttu-id="173a1-215">Para realizar una comprobación final y asegurarse de que el dispositivo de consola y todos sus periféricos están totalmente configurados, utilice la siguiente lista de comprobación:</span><span class="sxs-lookup"><span data-stu-id="173a1-215">Use the following checklist while doing a final verification that the console device and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="173a1-216">**Configuración de la aplicación**</span><span class="sxs-lookup"><span data-stu-id="173a1-216">**Application Settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="173a1-217">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-217">☐</span></span>  <br/> |<span data-ttu-id="173a1-218">El número de teléfono y el nombre de cuenta de la sala (si RTC está habilitado) se muestran correctamente en la parte superior derecha de la pantalla de la consola.</span><span class="sxs-lookup"><span data-stu-id="173a1-218">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="173a1-219">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-219">☐</span></span>  <br/> |<span data-ttu-id="173a1-220">El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).</span><span class="sxs-lookup"><span data-stu-id="173a1-220">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="173a1-221">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-221">☐</span></span>  <br/> |<span data-ttu-id="173a1-222">La contraseña de la cuenta de administrador está configurada y comprobada.</span><span class="sxs-lookup"><span data-stu-id="173a1-222">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="173a1-223">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-223">☐</span></span>  <br/> |<span data-ttu-id="173a1-224">Se han aplicado todos los 4 Surface Pro o actualizaciones del sistema Surface Pro</span><span class="sxs-lookup"><span data-stu-id="173a1-224">All Surface Pro 4 or Surface Pro System Updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="173a1-225">**Periféricos de audio y vídeo**</span><span class="sxs-lookup"><span data-stu-id="173a1-225">**Audio/Video Peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="173a1-226">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-226">☐</span></span>  <br/> |<span data-ttu-id="173a1-227">La versión de firmware del periférico de cámara es correcta (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="173a1-227">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="173a1-228">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-228">☐</span></span>  <br/> |<span data-ttu-id="173a1-229">Cámara funcional y colocado de manera óptima</span><span class="sxs-lookup"><span data-stu-id="173a1-229">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="173a1-230">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-230">☐</span></span>  <br/> |<span data-ttu-id="173a1-231">Configuración del dispositivo de reproducción predeterminado y del dispositivo de comunicaciones predeterminado para la reproducción establecida en el periférico de audio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="173a1-231">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="173a1-232">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-232">☐</span></span>  <br/> |<span data-ttu-id="173a1-233">Configuración del dispositivo de comunicaciones predeterminado para la grabación establecida en el periférico de audio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="173a1-233">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="173a1-234">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-234">☐</span></span>  <br/> |<span data-ttu-id="173a1-235">La versión de firmware del periférico de audio es correcta (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="173a1-235">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="173a1-236">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-236">☐</span></span>  <br/> |<span data-ttu-id="173a1-237">El dispositivo de entrada de audio funciona y está posicionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="173a1-237">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="173a1-238">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-238">☐</span></span>  <br/> |<span data-ttu-id="173a1-239">El dispositivo de salida de audio funciona y está posicionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="173a1-239">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="173a1-240">**Muelle**</span><span class="sxs-lookup"><span data-stu-id="173a1-240">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="173a1-241">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-241">☐</span></span>  <br/> |<span data-ttu-id="173a1-242">Los cables están protegidos y no están apretados.</span><span class="sxs-lookup"><span data-stu-id="173a1-242">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="173a1-243">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-243">☐</span></span>  <br/> |<span data-ttu-id="173a1-244">La transmisión de audio a través de HDMI funciona.</span><span class="sxs-lookup"><span data-stu-id="173a1-244">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="173a1-245">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-245">☐</span></span>  <br/> |<span data-ttu-id="173a1-246">La transmisión de vídeo a través de HDMI funciona.</span><span class="sxs-lookup"><span data-stu-id="173a1-246">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="173a1-247">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-247">☐</span></span>  <br/> |<span data-ttu-id="173a1-248">La base puede girar sin obstáculos.</span><span class="sxs-lookup"><span data-stu-id="173a1-248">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="173a1-249">☐</span><span class="sxs-lookup"><span data-stu-id="173a1-249">☐</span></span>  <br/> |<span data-ttu-id="173a1-250">El brillo de la pantalla es el adecuado para el entorno.</span><span class="sxs-lookup"><span data-stu-id="173a1-250">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="173a1-251">Vea también</span><span class="sxs-lookup"><span data-stu-id="173a1-251">See also</span></span>
<span data-ttu-id="173a1-252"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="173a1-252"></span></span>

#### 

[<span data-ttu-id="173a1-253">Planeación de la sala de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="173a1-253">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="173a1-254">Implementación de salón de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="173a1-254">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="173a1-255">Configurar una consola de v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="173a1-255">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="173a1-256">Administración de salón de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="173a1-256">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

