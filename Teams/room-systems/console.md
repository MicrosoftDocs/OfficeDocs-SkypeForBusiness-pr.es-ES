---
title: Configurar una consola de salas de Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar la consola de salas de Microsoft Teams y sus periféricos.
ms.openlocfilehash: 1bb1e45eca95628222b799d94c953bb49da1ea17
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243481"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="bbe13-103">Configurar una consola de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbe13-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="bbe13-104">En este artículo se describe cómo configurar la consola de salas de Microsoft Teams y sus periféricos.</span><span class="sxs-lookup"><span data-stu-id="bbe13-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="bbe13-105">Solo debe realizar estos pasos si ya se han creado y probado las cuentas de Microsoft Teams o Skype empresarial y Exchange, tal como se describe en [implementar salas de Microsoft Teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="bbe13-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="bbe13-106">Necesitará el hardware y el software descritos en [los requisitos de salas de Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbe13-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="bbe13-107">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bbe13-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="bbe13-108">Preparar los medios de instalación</span><span class="sxs-lookup"><span data-stu-id="bbe13-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="bbe13-109">Instalar un certificado de una entidad emisora privada en la consola</span><span class="sxs-lookup"><span data-stu-id="bbe13-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="bbe13-110">Instalar Windows 10 y la aplicación Microsoft Teams Room Console</span><span class="sxs-lookup"><span data-stu-id="bbe13-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="bbe13-111">Configuración inicial de la consola</span><span class="sxs-lookup"><span data-stu-id="bbe13-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="bbe13-112">Lista de comprobación de implementación de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbe13-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="bbe13-113">Las salas de Microsoft Teams solo funcionarán en un entorno de Microsoft Teams o Skype empresarial configurado correctamente, en el que las cuentas de dispositivos están configuradas correctamente, como se describe en [implementar salas de Microsoft Teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="bbe13-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="bbe13-114">Preparar los medios de instalación</span><span class="sxs-lookup"><span data-stu-id="bbe13-114">Prepare the installation media</span></span>
<span data-ttu-id="bbe13-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe13-115"></span></span>

<span data-ttu-id="bbe13-116">La instalación de la aplicación de la consola de Microsoft Team Rooms requiere un dispositivo de almacenamiento USB con un mínimo de 32 GB de capacidad.</span><span class="sxs-lookup"><span data-stu-id="bbe13-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="bbe13-117">No debe haber otros archivos en el dispositivo; los archivos existentes en el almacenamiento USB se perderán.</span><span class="sxs-lookup"><span data-stu-id="bbe13-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbe13-118">Si no se crean los medios de instalación de Microsoft Teams Rooms según estas instrucciones, es posible que se produzcan comportamientos inesperados.</span><span class="sxs-lookup"><span data-stu-id="bbe13-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="bbe13-119">El proceso que se muestra a continuación es para crear medios de instalación para crear nuevos dispositivos de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbe13-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="bbe13-120">Los dispositivos existentes, de forma predeterminada, se actualizan automáticamente desde Windows Update y la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="bbe13-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="bbe13-121">Descargue el [script CreateSrsMedia. PS1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="bbe13-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="bbe13-122">Ejecute el script CreateSrsMedia.ps1 desde un símbolo de sistema con privilegios elevados en un equipo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bbe13-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="bbe13-123">Siga las instrucciones de la secuencia de comandos para crear un disco de instalación de cámaras USB de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbe13-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="bbe13-124">Cada vez que se inicie el script CreateSrsMedia. ps1, el resultado de la pantalla incluirá el nombre de un archivo de registro o transcripción de la sesión.</span><span class="sxs-lookup"><span data-stu-id="bbe13-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="bbe13-125">Si hay problemas para ejecutar el script, asegúrese de tener una copia de esa transcripción disponible cuando solicite asistencia.</span><span class="sxs-lookup"><span data-stu-id="bbe13-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="bbe13-126">El script CreateSrsMedia. PS1 automatiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="bbe13-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="bbe13-127">Descargue el programa de instalación MSI más reciente para salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbe13-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="bbe13-128">Determine la compilación de Windows que el usuario debe proporcionar.</span><span class="sxs-lookup"><span data-stu-id="bbe13-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="bbe13-129">Las versiones publicadas más recientes pueden ser o no probadas y admitidas para su uso con dispositivos de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbe13-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="bbe13-130">Descargar componentes auxiliares necesarios.</span><span class="sxs-lookup"><span data-stu-id="bbe13-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="bbe13-131">Ensamble los componentes necesarios en los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="bbe13-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="bbe13-132">Se necesita una versión específica de Windows 10 y esta versión solo está disponible para los clientes de licencias por volumen.</span><span class="sxs-lookup"><span data-stu-id="bbe13-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="bbe13-133">Puede obtener una copia en el [centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/).</span><span class="sxs-lookup"><span data-stu-id="bbe13-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="bbe13-134">Cuando termine, quite el disco USB de su equipo y continúe para [instalar Windows 10 y la aplicación Microsoft Teams Rooms Console](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="bbe13-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="bbe13-135">Instalar Windows 10 y la aplicación Microsoft Teams Room Console</span><span class="sxs-lookup"><span data-stu-id="bbe13-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="bbe13-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe13-136"></span></span>

<span data-ttu-id="bbe13-137">Ahora debe aplicar los medios de configuración que ha creado.</span><span class="sxs-lookup"><span data-stu-id="bbe13-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="bbe13-138">El dispositivo de destino se ejecutará como un dispositivo y el usuario predeterminado se configurará para que solo ejecute la aplicación Microsoft Teams Rooms Console.</span><span class="sxs-lookup"><span data-stu-id="bbe13-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="bbe13-139">Si el dispositivo de destino se va a instalar en un muelle (p. ej., una Surface Pro), desconéctelo del Dock.</span><span class="sxs-lookup"><span data-stu-id="bbe13-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="bbe13-140">Asegúrate de que el dispositivo de destino no esté conectado a la red.</span><span class="sxs-lookup"><span data-stu-id="bbe13-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="bbe13-141">Asegúrate de que el dispositivo de destino esté conectado a la alimentación de CA.</span><span class="sxs-lookup"><span data-stu-id="bbe13-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="bbe13-142">Conecte el disco de instalación USB en el dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="bbe13-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="bbe13-143">Inicie el disco de instalación de USB.</span><span class="sxs-lookup"><span data-stu-id="bbe13-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="bbe13-144">Consulte las instrucciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="bbe13-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="bbe13-145">Si el dispositivo de destino es Surface Pro, siga estos pasos para arrancar en el disco de instalación de USB:</span><span class="sxs-lookup"><span data-stu-id="bbe13-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="bbe13-146">a.</span><span class="sxs-lookup"><span data-stu-id="bbe13-146">a.</span></span> <span data-ttu-id="bbe13-147">Pulsa y continúa con el botón bajar de volumen (-).</span><span class="sxs-lookup"><span data-stu-id="bbe13-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="bbe13-148">b.</span><span class="sxs-lookup"><span data-stu-id="bbe13-148">b.</span></span> <span data-ttu-id="bbe13-149">Presione y suelte el botón Power (encendido).</span><span class="sxs-lookup"><span data-stu-id="bbe13-149">Press and release the power button.</span></span>

    <span data-ttu-id="bbe13-150">c.</span><span class="sxs-lookup"><span data-stu-id="bbe13-150">c.</span></span> <span data-ttu-id="bbe13-151">Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).</span><span class="sxs-lookup"><span data-stu-id="bbe13-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="bbe13-152">El sistema se cerrará cuando se complete la instalación.</span><span class="sxs-lookup"><span data-stu-id="bbe13-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="bbe13-153">Una vez que el sistema se ha cerrado, es seguro quitar el disco de instalación de USB.</span><span class="sxs-lookup"><span data-stu-id="bbe13-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="bbe13-154">En este punto, puede colocar el dispositivo de destino en su muelle (si usa un producto basado en el muelle), adjuntar los periféricos necesarios para la sala de reuniones y conectarse a la red.</span><span class="sxs-lookup"><span data-stu-id="bbe13-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="bbe13-155">Consulte las instrucciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="bbe13-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="bbe13-156">Selección de un idioma</span><span class="sxs-lookup"><span data-stu-id="bbe13-156">Selecting a language</span></span> 

<span data-ttu-id="bbe13-157">En la actualización del creador, tendrá que usar el script ApplyCurrentRegionAndLanguage. PS1 en escenarios en los que la selección de lenguaje implícito no proporciona al usuario el lenguaje de aplicaciones que quieren (por ejemplo, desea que la aplicación de consola aparezca en francés, pero está llegando en inglés).</span><span class="sxs-lookup"><span data-stu-id="bbe13-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbe13-158">Las siguientes instrucciones solo funcionan con las consolas creadas con la actualización de Windows Creator.</span><span class="sxs-lookup"><span data-stu-id="bbe13-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="bbe13-159">Los sistemas heredados o en el mercado que no se hayan configurado con medios en el nuevo sistema de aprovisionamiento no podrán usar estas instrucciones, pero tampoco deben sufrir el problema inicial que requiere esta intervención manual (la edición de aniversario le permite elegir su idioma de la aplicación explícitamente como parte de la configuración).</span><span class="sxs-lookup"><span data-stu-id="bbe13-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="bbe13-160">Para aplicar el idioma deseado</span><span class="sxs-lookup"><span data-stu-id="bbe13-160">To apply your desired language</span></span>

1. <span data-ttu-id="bbe13-161">Cambie al modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="bbe13-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="bbe13-162">Seleccione el menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="bbe13-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="bbe13-163">Seleccione el icono de engranaje para iniciar la aplicación **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="bbe13-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="bbe13-164">Seleccione **idioma &amp; de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="bbe13-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="bbe13-165">Seleccione **el &amp; idioma**de la región.</span><span class="sxs-lookup"><span data-stu-id="bbe13-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="bbe13-166">Seleccione **Agregar un idioma**.</span><span class="sxs-lookup"><span data-stu-id="bbe13-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="bbe13-167">Seleccione el idioma que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="bbe13-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="bbe13-168">Seleccione el idioma que acaba de agregar a la lista "idiomas".</span><span class="sxs-lookup"><span data-stu-id="bbe13-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="bbe13-169">Haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="bbe13-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="bbe13-170">Si desea eliminar algún idioma:</span><span class="sxs-lookup"><span data-stu-id="bbe13-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="bbe13-p114">a. Seleccione el idioma que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="bbe13-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="bbe13-p115">b. Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="bbe13-p115">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="bbe13-175">Inicie un símbolo de sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="bbe13-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="bbe13-176">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbe13-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="bbe13-177">Reinicie el sistema.</span><span class="sxs-lookup"><span data-stu-id="bbe13-177">Restart the system.</span></span>
    
<span data-ttu-id="bbe13-178">El idioma deseado se aplica ahora a la consola de salones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbe13-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="bbe13-179">Configuración inicial de la consola</span><span class="sxs-lookup"><span data-stu-id="bbe13-179">Initial set up of the console</span></span>
<span data-ttu-id="bbe13-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe13-180"></span></span>

<span data-ttu-id="bbe13-181">Una vez instalado Windows, la aplicación Microsoft Teams Rooms Console pasará a su proceso de configuración inicial cuando se inicie a continuación o si se eligió la opción/Reboot.</span><span class="sxs-lookup"><span data-stu-id="bbe13-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="bbe13-182">Aparece la pantalla Cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="bbe13-182">The User Account screen appears.</span></span> <span data-ttu-id="bbe13-183">Escribe la dirección de inicio de sesión de Skype (en el formato usuario @ dominio) de la cuenta de la cuenta Room para usarla con la consola.</span><span class="sxs-lookup"><span data-stu-id="bbe13-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="bbe13-184">Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="bbe13-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="bbe13-185">En "Configurar dominio", establezca el FQDN de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bbe13-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="bbe13-186">Si el dominio SIP de Skype empresarial es diferente del dominio de Exchange del usuario, escriba el dominio de Exchange en este campo.</span><span class="sxs-lookup"><span data-stu-id="bbe13-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="bbe13-187">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bbe13-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="bbe13-188">Seleccione los dispositivos indicados en la pantalla características y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bbe13-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="bbe13-189">De manera predeterminada, la opción Pantalla compartida automática está activada y Ocultar nombres de las reuniones está desactivada.</span><span class="sxs-lookup"><span data-stu-id="bbe13-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="bbe13-190">Los dispositivos que se deben seleccionar son:</span><span class="sxs-lookup"><span data-stu-id="bbe13-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="bbe13-191">Micrófono para conferencias: el micrófono predeterminado de esta sala de conferencias.</span><span class="sxs-lookup"><span data-stu-id="bbe13-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="bbe13-192">Altavoz para conferencias: el altavoz predeterminado para las conferencias. </span><span class="sxs-lookup"><span data-stu-id="bbe13-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="bbe13-193">Altavoz predeterminado: el altavoz que se usa para el audio de la transmisión por HDMI.</span><span class="sxs-lookup"><span data-stu-id="bbe13-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="bbe13-p119">Cada elemento tiene un menú desplegable en el que puede hacer selecciones. Deberá realizar una selección para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbe13-p119">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="bbe13-196">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bbe13-196">Click **Finish**.</span></span>
    
<span data-ttu-id="bbe13-197">La aplicación Microsoft Team Rooms Console debe empezar a iniciar sesión en Skype empresarial Server inmediatamente con las credenciales especificadas anteriormente, y también debe empezar a sincronizar su calendario con Exchange con las mismas credenciales.</span><span class="sxs-lookup"><span data-stu-id="bbe13-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="bbe13-198">Para obtener información sobre el uso de la aplicación de consola, consulte la [ayuda de Microsoft Teams Rooms](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="bbe13-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bbe13-199">Las salas de Microsoft Teams se basan en la presencia de un hardware de consola certificado.</span><span class="sxs-lookup"><span data-stu-id="bbe13-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="bbe13-200">Incluso una imagen creada correctamente que contenga la aplicación salas de Microsoft Teams en la consola, no arrancará más allá del procedimiento de configuración inicial, a menos que se detecte el hardware de la consola.</span><span class="sxs-lookup"><span data-stu-id="bbe13-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="bbe13-201">Para las soluciones basadas en Surface Pro, la Surface Pro debe estar conectada a su hardware de acoplamiento adjunto para pasar esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="bbe13-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbe13-202">Es posible que algunos usuarios de idiomas no ingleses necesiten un teclado físico conectado a la consola durante la configuración inicial, en el caso de que los símbolos no se admitan en el teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="bbe13-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="bbe13-203">Instalar un certificado de una entidad emisora privada en la consola</span><span class="sxs-lookup"><span data-stu-id="bbe13-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="bbe13-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe13-204"></span></span>

<span data-ttu-id="bbe13-205">La consola de salones de Microsoft Teams necesita confiar en los certificados que usan los servidores a los que se conecta.</span><span class="sxs-lookup"><span data-stu-id="bbe13-205">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="bbe13-206">Para O365, este proceso se realiza automáticamente, puesto que los servidores utilizan entidades de certificación públicas y Windows 10 confía en ellas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bbe13-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="bbe13-207">En el caso de que la entidad emisora de certificados sea privada, por ejemplo, una implementación local con Active Directory y la entidad emisora de certificados de Windows, puede Agregar el certificado a la consola de salas de Microsoft Teams de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="bbe13-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="bbe13-208">Puede unirse a la consola a Active Directory y se agregarán automáticamente los certificados necesarios dados que la entidad emisora de certificados se publique en Active Directory (opción de implementación normal).</span><span class="sxs-lookup"><span data-stu-id="bbe13-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="bbe13-209">Puede instalar el certificado manualmente después del proceso de creación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="bbe13-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="bbe13-210">Antes de hacerlo, debe completar [la configuración inicial de la consola](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="bbe13-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="bbe13-211">Para instalar manualmente el certificado </span><span class="sxs-lookup"><span data-stu-id="bbe13-211">To manually install the certificate</span></span>

1. <span data-ttu-id="bbe13-212">Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="bbe13-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="bbe13-213">Coloque la consola en el modo de administración (consulte [modo de administración y administración de dispositivos](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="bbe13-213">Place the console in admin mode (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="bbe13-214">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbe13-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="bbe13-215">Unirse a un dominio de Active Directory (opcional)</span><span class="sxs-lookup"><span data-stu-id="bbe13-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="bbe13-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe13-216"></span></span>

<span data-ttu-id="bbe13-217">Puede unirse a las consolas de salas de Microsoft Teams en su dominio.</span><span class="sxs-lookup"><span data-stu-id="bbe13-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="bbe13-218">Las consolas de salas de Microsoft Teams deben colocarse en una OU independiente de las estaciones de trabajo de PC porque muchas directivas de estación de trabajo no son compatibles con las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbe13-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="bbe13-219">Un ejemplo común son las directivas de aplicación de contraseñas que evitarán que las salas de Microsoft Teams se inicien automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bbe13-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="bbe13-220">Para obtener información sobre la administración de la configuración de GPO, consulte [administrar salas de Microsoft Teams](room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="bbe13-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="bbe13-221">Para unirse a salas de Microsoft Teams a un dominio</span><span class="sxs-lookup"><span data-stu-id="bbe13-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="bbe13-222">Inicie sesión en la consola desde la cuenta de administrador (consulte [modo de administración y administración de dispositivos](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="bbe13-222">Sign into the console from the admin account (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="bbe13-223">Inicie un símbolo de sistema de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="bbe13-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="bbe13-224">Introduzca el siguiente comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbe13-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="bbe13-225">Por ejemplo, si su dominio completo es redmond.corp.microsoft.com y desea que las consolas de salas de Microsoft Teams estén en una OU "salas de Microsoft Teams" que sea un elemento secundario de una unidad organizativa "recursos", el comando será:</span><span class="sxs-lookup"><span data-stu-id="bbe13-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="bbe13-226">Si desea cambiar el nombre del equipo cuando se une a un dominio, use la bandera-NewName seguida del nombre nuevo del equipo.</span><span class="sxs-lookup"><span data-stu-id="bbe13-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="bbe13-227">Lista de comprobación de implementación de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbe13-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="bbe13-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe13-228"></span></span>

<span data-ttu-id="bbe13-229">Use la siguiente lista de comprobación para realizar una verificación final de que la consola y todos sus periféricos estén totalmente configurados:</span><span class="sxs-lookup"><span data-stu-id="bbe13-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="bbe13-230">**Configuración de la aplicación**</span><span class="sxs-lookup"><span data-stu-id="bbe13-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bbe13-231">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-231">☐</span></span>  <br/> |<span data-ttu-id="bbe13-232">El número de teléfono y el nombre de cuenta de la sala (si RTC está habilitado) se muestran correctamente en la parte superior derecha de la pantalla de la consola.</span><span class="sxs-lookup"><span data-stu-id="bbe13-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="bbe13-233">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-233">☐</span></span>  <br/> |<span data-ttu-id="bbe13-234">El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).</span><span class="sxs-lookup"><span data-stu-id="bbe13-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="bbe13-235">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-235">☐</span></span>  <br/> |<span data-ttu-id="bbe13-236">La contraseña de la cuenta de administrador está configurada y comprobada.</span><span class="sxs-lookup"><span data-stu-id="bbe13-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="bbe13-237">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-237">☐</span></span>  <br/> |<span data-ttu-id="bbe13-238">Se han aplicado todas las actualizaciones de firmware</span><span class="sxs-lookup"><span data-stu-id="bbe13-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="bbe13-239">**Periféricos de audio y vídeo**</span><span class="sxs-lookup"><span data-stu-id="bbe13-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bbe13-240">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-240">☐</span></span>  <br/> |<span data-ttu-id="bbe13-241">La versión de firmware del periférico de cámara es correcta (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="bbe13-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="bbe13-242">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-242">☐</span></span>  <br/> |<span data-ttu-id="bbe13-243">Funciones de cámara y posición óptima</span><span class="sxs-lookup"><span data-stu-id="bbe13-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="bbe13-244">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-244">☐</span></span>  <br/> |<span data-ttu-id="bbe13-245">Configuración del dispositivo de reproducción predeterminado y del dispositivo de comunicaciones predeterminado para la reproducción establecida en el periférico de audio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bbe13-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="bbe13-246">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-246">☐</span></span>  <br/> |<span data-ttu-id="bbe13-247">Configuración del dispositivo de comunicaciones predeterminado para la grabación establecida en el periférico de audio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bbe13-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="bbe13-248">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-248">☐</span></span>  <br/> |<span data-ttu-id="bbe13-249">La versión de firmware del periférico de audio es correcta (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="bbe13-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="bbe13-250">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-250">☐</span></span>  <br/> |<span data-ttu-id="bbe13-251">El dispositivo de entrada de audio funciona y está posicionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbe13-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="bbe13-252">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-252">☐</span></span>  <br/> |<span data-ttu-id="bbe13-253">El dispositivo de salida de audio funciona y está posicionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbe13-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="bbe13-254">**Base**</span><span class="sxs-lookup"><span data-stu-id="bbe13-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bbe13-255">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-255">☐</span></span>  <br/> |<span data-ttu-id="bbe13-256">Los cables están protegidos y no están apretados.</span><span class="sxs-lookup"><span data-stu-id="bbe13-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="bbe13-257">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-257">☐</span></span>  <br/> |<span data-ttu-id="bbe13-258">La transmisión de audio a través de HDMI funciona.</span><span class="sxs-lookup"><span data-stu-id="bbe13-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="bbe13-259">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-259">☐</span></span>  <br/> |<span data-ttu-id="bbe13-260">La transmisión de vídeo a través de HDMI funciona.</span><span class="sxs-lookup"><span data-stu-id="bbe13-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="bbe13-261">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-261">☐</span></span>  <br/> |<span data-ttu-id="bbe13-262">La base puede girar sin obstáculos.</span><span class="sxs-lookup"><span data-stu-id="bbe13-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="bbe13-263">☐</span><span class="sxs-lookup"><span data-stu-id="bbe13-263">☐</span></span>  <br/> |<span data-ttu-id="bbe13-264">El brillo de la pantalla es el adecuado para el entorno.</span><span class="sxs-lookup"><span data-stu-id="bbe13-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bbe13-265">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbe13-265">See also</span></span>
<span data-ttu-id="bbe13-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="bbe13-266"></span></span>

[<span data-ttu-id="bbe13-267">Plan para salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbe13-267">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="bbe13-268">Implementar salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbe13-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="bbe13-269">Configurar una consola de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbe13-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="bbe13-270">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbe13-270">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
