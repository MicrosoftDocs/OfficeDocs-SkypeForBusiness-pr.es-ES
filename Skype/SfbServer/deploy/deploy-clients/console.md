---
title: Configurar una consola de Sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar la consola de v2 de sistemas de salón de Skype y sus periféricos.
ms.openlocfilehash: bb23f0dad26f37554657a101dc68dc7d776080b2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371064"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="bbe60-103">Configurar una consola de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="bbe60-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="bbe60-104">En este artículo se describe cómo configurar la consola de v2 de sistemas de salón de Skype y sus periféricos.</span><span class="sxs-lookup"><span data-stu-id="bbe60-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="bbe60-105">Sólo debe realizar estos pasos si el Skype es necesario para las cuentas empresariales y de Exchange ya se han creado y probado tal como se describe en [implementar sistemas de salón de Skype v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="bbe60-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="bbe60-106">Necesitará el hardware y software descritos en [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbe60-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="bbe60-107">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bbe60-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="bbe60-108">Preparar los medios de instalación</span><span class="sxs-lookup"><span data-stu-id="bbe60-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="bbe60-109">Instalar un certificado de entidad de certificación privado en la consola</span><span class="sxs-lookup"><span data-stu-id="bbe60-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="bbe60-110">Instalación de Windows 10 y la aplicación de consola Sistemas de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="bbe60-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="bbe60-111">Configuración inicial de la consola</span><span class="sxs-lookup"><span data-stu-id="bbe60-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="bbe60-112">Lista de comprobación de implementación de sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="bbe60-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="bbe60-113">Sistemas de salón de Skype v2 sólo funciona en un Skype configurada correctamente para el entorno empresarial donde las cuentas de dispositivos estén configuradas correctamente, tal como se describe en [implementar sistemas de salón de Skype v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="bbe60-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="bbe60-114">Preparar los medios de instalación</span><span class="sxs-lookup"><span data-stu-id="bbe60-114">Prepare the installation media</span></span>
<span data-ttu-id="bbe60-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe60-115"></span></span>

<span data-ttu-id="bbe60-116">Instalación de la aplicación de consola de sistemas de salón de Skype v2 requiere un dispositivo de almacenamiento USB con al menos 32GB de memoria con formato de un disco FAT32.</span><span class="sxs-lookup"><span data-stu-id="bbe60-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="bbe60-117">No debería haber otros archivos en el dispositivo; cualquier archivo que esté en el almacenamiento USB se perderá.</span><span class="sxs-lookup"><span data-stu-id="bbe60-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbe60-118">Error al crear los discos de instalación de sistemas de salón de Skype v2 según estas instrucciones probablemente tendrá como resultado un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="bbe60-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="bbe60-119">Actualización de aniversario de empresa de Windows 10 (versión 1607) ya no se admite para la creación de medios de instalación de sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="bbe60-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 installation media creation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbe60-120">Funcionará un v2 de Skype salón sistemas existentes con Windows 10 Enterprise aniversario de actualización de mover a sistemas de salón de Skype v2 actualización 3 mediante el almacén de Windows, pero se debe realizar una nueva instalación tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="bbe60-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="bbe60-121">Descargar el [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="bbe60-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="bbe60-122">(Opcional) Descargue y coloque los archivos CAB de paquete de idioma deseado en el mismo directorio que la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="bbe60-122">(Optional) Download and place any desired language pack CAB files in the same directory as the script.</span></span> <span data-ttu-id="bbe60-123">La secuencia de comandos que le indicará que puede descargar los archivos de paquete de idioma apropiados para el tipo de medios que se va a crear, si no está seguro de dónde adquirir los paquetes de idioma de.</span><span class="sxs-lookup"><span data-stu-id="bbe60-123">The script will indicate where you can download language pack files appropriate for the type of media you are creating, if you're unsure where to acquire the language packs from.</span></span>
3. <span data-ttu-id="bbe60-124">Ejecute el script CreateSrsMedia.ps1 desde un símbolo de sistema con privilegios elevados en un equipo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bbe60-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="bbe60-125">Siga las instrucciones de la secuencia de comandos para crear un disco de instalación de sistemas de salón de Skype v2 USB.</span><span class="sxs-lookup"><span data-stu-id="bbe60-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="bbe60-126">Cuando haya terminado, quitar el disco USB de su equipo y proceda a [instalar 10 de Windows y la aplicación de consola de sistemas de salón de Skype v2](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="bbe60-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="bbe60-127">Instalación de Windows 10 y la aplicación de consola Sistemas de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="bbe60-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="bbe60-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe60-128"></span></span>

<span data-ttu-id="bbe60-129">Debe aplicar el medio de instalación que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="bbe60-129">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="bbe60-130">El dispositivo de destino se ejecutará como un dispositivo y el usuario predeterminado se establecerá en sólo ejecutar la aplicación de consola de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="bbe60-130">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="bbe60-131">Si el dispositivo de destino se instalará en un muelle (por ejemplo, un Surface Pro), desconectar desde el muelle.</span><span class="sxs-lookup"><span data-stu-id="bbe60-131">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="bbe60-132">Asegúrese de que el dispositivo de destino no está conectado a la red.</span><span class="sxs-lookup"><span data-stu-id="bbe60-132">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="bbe60-133">Asegúrese de que el dispositivo de destino está conectado a la alimentación de CA.</span><span class="sxs-lookup"><span data-stu-id="bbe60-133">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="bbe60-134">Conecte el disco de instalación USB en el dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="bbe60-134">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="bbe60-135">Inicie desde el disco de instalación USB.</span><span class="sxs-lookup"><span data-stu-id="bbe60-135">Boot to the USB setup disk.</span></span> <span data-ttu-id="bbe60-136">Consulte las instrucciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="bbe60-136">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="bbe60-137">Si el dispositivo de destino es un Surface Pro, siga estos pasos para que arranque en el disco de instalación USB:</span><span class="sxs-lookup"><span data-stu-id="bbe60-137">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="bbe60-138">Presione y mantenga el volumen hacia abajo botón (-).</span><span class="sxs-lookup"><span data-stu-id="bbe60-138">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="bbe60-139">Presione y suelte el botón de encendido.</span><span class="sxs-lookup"><span data-stu-id="bbe60-139">Press and release the power button.</span></span>

    3. <span data-ttu-id="bbe60-140">Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).</span><span class="sxs-lookup"><span data-stu-id="bbe60-140">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="bbe60-141">El sistema se cerrará una vez finalizada la instalación.</span><span class="sxs-lookup"><span data-stu-id="bbe60-141">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="bbe60-142">Después de que se apague el sistema, es seguro quitar el disco de instalación USB.</span><span class="sxs-lookup"><span data-stu-id="bbe60-142">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="bbe60-143">En este momento, puede colocar el devcie de destino en su muelle (si se usa un producto de acoplamiento), adjunta los periféricos necesarios para la sala de reuniones y conectarse a la red.</span><span class="sxs-lookup"><span data-stu-id="bbe60-143">At this point, you can place the target devcie in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="bbe60-144">Consulte las instrucciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="bbe60-144">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="bbe60-145">Selección de un idioma en la actualización de Creator</span><span class="sxs-lookup"><span data-stu-id="bbe60-145">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="bbe60-146">En la actualización del creador, necesitará utilizar la secuencia de comandos ApplyCurrentRegionAndLanguage.ps1 en escenarios donde selección del idioma implícita no proporciona al usuario con el idioma de la aplicación real que desean (por ejemplo, desean que la aplicación de consola para que surjan en francés, pero se explica más adelante en inglés).</span><span class="sxs-lookup"><span data-stu-id="bbe60-146">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbe60-147">Las instrucciones siguientes sólo funcionan para consolas creadas mediante la actualización del creador de Windows.</span><span class="sxs-lookup"><span data-stu-id="bbe60-147">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="bbe60-148">No podrá usar estas instrucciones sistemas heredados/en-mercado que no se ha configurado el uso de medios con el nuevo sistema de aprovisionamiento, pero también no debe verse afectado desde el problema inicial que requiere esta intervención manual (aniversario Edition le permiten elegir su idioma de la aplicación explícitamente como parte del programa de instalación).</span><span class="sxs-lookup"><span data-stu-id="bbe60-148">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="bbe60-149">Para aplicar el idioma deseado</span><span class="sxs-lookup"><span data-stu-id="bbe60-149">To apply your desired language</span></span>

1. <span data-ttu-id="bbe60-150">Cambie al modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="bbe60-150">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="bbe60-151">Seleccione el menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="bbe60-151">Select the Start menu.</span></span>
    
3. <span data-ttu-id="bbe60-152">Seleccione el icono de engranaje para iniciar la aplicación **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-152">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="bbe60-153">Seleccione **tiempo &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-153">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="bbe60-154">Seleccione **región &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-154">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="bbe60-155">Seleccione **Agregar un idioma**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-155">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="bbe60-156">Seleccione el idioma que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="bbe60-156">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="bbe60-157">Seleccione el idioma que acaba de agregar a la lista de "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="bbe60-157">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="bbe60-158">Haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-158">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="bbe60-159">Si desea eliminar algún idioma:</span><span class="sxs-lookup"><span data-stu-id="bbe60-159">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="bbe60-160">a.</span><span class="sxs-lookup"><span data-stu-id="bbe60-160">a.</span></span> <span data-ttu-id="bbe60-161">Seleccione el idioma que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="bbe60-161">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="bbe60-162">b.</span><span class="sxs-lookup"><span data-stu-id="bbe60-162">b.</span></span> <span data-ttu-id="bbe60-163">Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-163">Select **Remove**.</span></span>
    
11. <span data-ttu-id="bbe60-164">Inicie un símbolo de sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="bbe60-164">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="bbe60-165">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbe60-165">Run the following command:</span></span> 
    
    <span data-ttu-id="bbe60-166">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="bbe60-166">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="bbe60-167">Reinicie el sistema.</span><span class="sxs-lookup"><span data-stu-id="bbe60-167">Restart the system.</span></span>
    
<span data-ttu-id="bbe60-168">El idioma deseado ahora se aplica a la consola de v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="bbe60-168">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="bbe60-169">Configuración inicial de la consola</span><span class="sxs-lookup"><span data-stu-id="bbe60-169">Initial set up of the console</span></span>
<span data-ttu-id="bbe60-170"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe60-170"></span></span>

<span data-ttu-id="bbe60-171">Después de instalar Windows, la aplicación de consola de sistemas de salón de Skype v2 entra en su proceso de instalación inicial cuando se inicia siguiente o si se ha seleccionado la opción Reboot.</span><span class="sxs-lookup"><span data-stu-id="bbe60-171">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="bbe60-172">Aparece la pantalla Cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="bbe60-172">The User Account screen appears.</span></span> <span data-ttu-id="bbe60-173">Escriba la Skype inicio de sesión de dirección (en formato user@domain) de la cuenta de sala para usarse con la consola.</span><span class="sxs-lookup"><span data-stu-id="bbe60-173">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="bbe60-174">Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="bbe60-174">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="bbe60-175">Bajo "Configuración de dominio", establecer el FQDN para el Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="bbe60-175">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="bbe60-176">Si el Skype para el dominio SIP empresarial es diferente del dominio de Exchange del usuario, escriba el dominio de Exchange en este campo.</span><span class="sxs-lookup"><span data-stu-id="bbe60-176">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="bbe60-177">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-177">Click **Next**.</span></span>
    
5. <span data-ttu-id="bbe60-178">Seleccione los dispositivos indicados en la pantalla de las características y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-178">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="bbe60-179">De manera predeterminada, la opción Pantalla compartida automática está activada y Ocultar nombres de las reuniones está desactivada.</span><span class="sxs-lookup"><span data-stu-id="bbe60-179">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="bbe60-180">Los dispositivos que se deben seleccionar son:</span><span class="sxs-lookup"><span data-stu-id="bbe60-180">The devices to select are:</span></span>
    
   - <span data-ttu-id="bbe60-181">Micrófono para conferencias: el micrófono predeterminado de esta sala de conferencias.</span><span class="sxs-lookup"><span data-stu-id="bbe60-181">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="bbe60-182">Altavoz para conferencias: el altavoz predeterminado para las conferencias. </span><span class="sxs-lookup"><span data-stu-id="bbe60-182">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="bbe60-183">Altavoz predeterminado: el altavoz que se usa para el audio de la transmisión por HDMI.</span><span class="sxs-lookup"><span data-stu-id="bbe60-183">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="bbe60-p115">Cada elemento tiene un menú desplegable en el que puede hacer selecciones. Deberá realizar una selección para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbe60-p115">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="bbe60-186">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bbe60-186">Click **Finish**.</span></span>
    
<span data-ttu-id="bbe60-187">La aplicación de consola de sistemas de salón de Skype v2 debe iniciar inmediatamente el inicio de sesión en Skype para Business Server con las credenciales especificadas anteriormente y también debe comenzar a sincronizar su calendario con Exchange utilizando las mismas credenciales.</span><span class="sxs-lookup"><span data-stu-id="bbe60-187">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="bbe60-188">Para obtener información detallada sobre el uso de la aplicación de consola, consulte la [Ayuda de sistemas de salón de Skype versión 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="bbe60-188">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bbe60-189">Sistemas de salón de Skype v2 se basa en la presencia de hardware de la consola certificados.</span><span class="sxs-lookup"><span data-stu-id="bbe60-189">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="bbe60-190">Incluso una imagen creada correctamente que contiene la aplicación de consola de sistemas de salón de Skype v2 no se iniciará pasadas de un documento el procedimiento de instalación inicial, a menos que se detecta el hardware de la consola.</span><span class="sxs-lookup"><span data-stu-id="bbe60-190">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="bbe60-191">Para las soluciones Surface Pro en función, debe estar conectado el Surface Pro a su hardware de acoplamiento que lo acompaña para pasar esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="bbe60-191">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbe60-192">Algunos usuarios de idiomas distintos del inglés pueden necesitar un teclado físico conectado a la consola durante la instalación inicial en caso de que no se admiten los símbolos en el teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="bbe60-192">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="bbe60-193">Instalar un certificado de entidad de certificación privado en la consola</span><span class="sxs-lookup"><span data-stu-id="bbe60-193">Install a private CA certificate on the console</span></span>
<span data-ttu-id="bbe60-194"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe60-194"></span></span>

<span data-ttu-id="bbe60-195">La consola de sistemas de salón de Skype v2 debe confiar en los certificados usados por el Skype para servidores empresariales y de Exchange a que se conecta.</span><span class="sxs-lookup"><span data-stu-id="bbe60-195">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="bbe60-196">Para O365, este proceso se realiza automáticamente, puesto que los servidores utilizan entidades de certificación públicas y Windows 10 confía en ellas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bbe60-196">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="bbe60-197">En un caso donde la entidad emisora de certificados es privada, por ejemplo, una implementación local con Active Directory y la entidad emisora de certificados de Windows, puede agregar el certificado a la consola de v2 de sistemas de salón de Skype en un par de maneras:</span><span class="sxs-lookup"><span data-stu-id="bbe60-197">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="bbe60-198">Puede unirse a la consola a Active Directory y que agregará automáticamente los certificados necesarios, dado la entidad emisora de certificados se publica en Active Directory (opción de implementación normal).</span><span class="sxs-lookup"><span data-stu-id="bbe60-198">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="bbe60-199">Puede instalar el certificado manualmente después del proceso de creación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="bbe60-199">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="bbe60-200">Antes de hacerlo, debe completar la [configuración inicial de la consola](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="bbe60-200">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="bbe60-201">Para instalar manualmente el certificado </span><span class="sxs-lookup"><span data-stu-id="bbe60-201">To manually install the certificate</span></span>

1. <span data-ttu-id="bbe60-202">Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="bbe60-202">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="bbe60-203">Coloque la consola en modo de administrador (consulte [administración de modo y el dispositivo de administración](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="bbe60-203">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="bbe60-204">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbe60-204">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="bbe60-205">Unirse a un dominio de Active Directory (opcional)</span><span class="sxs-lookup"><span data-stu-id="bbe60-205">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="bbe60-206"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe60-206"></span></span>

<span data-ttu-id="bbe60-207">Puede unirse a consolas de sistemas de salón de Skype v2 a su dominio.</span><span class="sxs-lookup"><span data-stu-id="bbe60-207">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="bbe60-208">Consolas de sistemas de salón de Skype v2 deben ubicarse en una unidad organizativa independiente desde estaciones de trabajo de sus PC debido a que muchas de las directivas de estación de trabajo no son compatibles con sistemas de salas de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="bbe60-208">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="bbe60-209">Un ejemplo común son las directivas de cumplimiento de contraseña que se impiden que se inicie automáticamente sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="bbe60-209">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="bbe60-210">Para obtener información acerca de la administración de configuraciones de GPO, consulte [administrar sistemas de salón de Skype v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="bbe60-210">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="bbe60-211">Para unir Sistemas de salas de Skype v2 a un dominio</span><span class="sxs-lookup"><span data-stu-id="bbe60-211">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="bbe60-212">Inicio de sesión en la consola de la administración de cuenta (consulte [administración de modo y el dispositivo de administración](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="bbe60-212">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="bbe60-213">Inicie un símbolo de sistema de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="bbe60-213">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="bbe60-214">Introduzca el siguiente comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbe60-214">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="bbe60-215">Por ejemplo, si su nombre de dominio completo es redmond.corp.microsoft.com y desea que las consolas de v2 de sistemas de salón de Skype para estar en un "v2 de sistemas de las salas de Skype" unidad organizativa que es un elemento secundario de una unidad organizativa "recursos", el comando será:</span><span class="sxs-lookup"><span data-stu-id="bbe60-215">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="bbe60-216">Si desea cambiar el nombre del equipo al unir a un dominio, use la marca - NewName seguida por el nombre del equipo nuevo.</span><span class="sxs-lookup"><span data-stu-id="bbe60-216">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="bbe60-217">Lista de comprobación de implementación de sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="bbe60-217">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="bbe60-218"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe60-218"></span></span>

<span data-ttu-id="bbe60-219">Utilizar la lista de comprobación siguiente mientras se hace una comprobación final que se han configurado totalmente la consola y todas sus periféricos:</span><span class="sxs-lookup"><span data-stu-id="bbe60-219">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="bbe60-220">**Configuración de la aplicación**</span><span class="sxs-lookup"><span data-stu-id="bbe60-220">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bbe60-221">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-221">☐</span></span>  <br/> |<span data-ttu-id="bbe60-222">El número de teléfono y el nombre de cuenta de la sala (si RTC está habilitado) se muestran correctamente en la parte superior derecha de la pantalla de la consola.</span><span class="sxs-lookup"><span data-stu-id="bbe60-222">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="bbe60-223">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-223">☐</span></span>  <br/> |<span data-ttu-id="bbe60-224">El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).</span><span class="sxs-lookup"><span data-stu-id="bbe60-224">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="bbe60-225">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-225">☐</span></span>  <br/> |<span data-ttu-id="bbe60-226">La contraseña de la cuenta de administrador está configurada y comprobada.</span><span class="sxs-lookup"><span data-stu-id="bbe60-226">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="bbe60-227">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-227">☐</span></span>  <br/> |<span data-ttu-id="bbe60-228">Se han aplicado todas las actualizaciones de firmware</span><span class="sxs-lookup"><span data-stu-id="bbe60-228">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="bbe60-229">**Periféricos de audio y vídeo**</span><span class="sxs-lookup"><span data-stu-id="bbe60-229">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bbe60-230">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-230">☐</span></span>  <br/> |<span data-ttu-id="bbe60-231">La versión de firmware del periférico de cámara es correcta (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="bbe60-231">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="bbe60-232">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-232">☐</span></span>  <br/> |<span data-ttu-id="bbe60-233">Cámara funcional y colocado de manera óptima</span><span class="sxs-lookup"><span data-stu-id="bbe60-233">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="bbe60-234">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-234">☐</span></span>  <br/> |<span data-ttu-id="bbe60-235">Configuración del dispositivo de reproducción predeterminado y del dispositivo de comunicaciones predeterminado para la reproducción establecida en el periférico de audio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bbe60-235">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="bbe60-236">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-236">☐</span></span>  <br/> |<span data-ttu-id="bbe60-237">Configuración del dispositivo de comunicaciones predeterminado para la grabación establecida en el periférico de audio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bbe60-237">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="bbe60-238">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-238">☐</span></span>  <br/> |<span data-ttu-id="bbe60-239">La versión de firmware del periférico de audio es correcta (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="bbe60-239">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="bbe60-240">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-240">☐</span></span>  <br/> |<span data-ttu-id="bbe60-241">El dispositivo de entrada de audio funciona y está posicionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbe60-241">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="bbe60-242">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-242">☐</span></span>  <br/> |<span data-ttu-id="bbe60-243">El dispositivo de salida de audio funciona y está posicionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbe60-243">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="bbe60-244">**Base**</span><span class="sxs-lookup"><span data-stu-id="bbe60-244">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bbe60-245">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-245">☐</span></span>  <br/> |<span data-ttu-id="bbe60-246">Los cables están protegidos y no están apretados.</span><span class="sxs-lookup"><span data-stu-id="bbe60-246">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="bbe60-247">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-247">☐</span></span>  <br/> |<span data-ttu-id="bbe60-248">La transmisión de audio a través de HDMI funciona.</span><span class="sxs-lookup"><span data-stu-id="bbe60-248">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="bbe60-249">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-249">☐</span></span>  <br/> |<span data-ttu-id="bbe60-250">La transmisión de vídeo a través de HDMI funciona.</span><span class="sxs-lookup"><span data-stu-id="bbe60-250">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="bbe60-251">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-251">☐</span></span>  <br/> |<span data-ttu-id="bbe60-252">La base puede girar sin obstáculos.</span><span class="sxs-lookup"><span data-stu-id="bbe60-252">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="bbe60-253">☐</span><span class="sxs-lookup"><span data-stu-id="bbe60-253">☐</span></span>  <br/> |<span data-ttu-id="bbe60-254">El brillo de la pantalla es el adecuado para el entorno.</span><span class="sxs-lookup"><span data-stu-id="bbe60-254">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bbe60-255">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbe60-255">See also</span></span>
<span data-ttu-id="bbe60-256"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe60-256"></span></span>

[<span data-ttu-id="bbe60-257">Plan para Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="bbe60-257">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="bbe60-258">Implementar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="bbe60-258">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="bbe60-259">Configurar una consola de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="bbe60-259">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="bbe60-260">Administrar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="bbe60-260">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)