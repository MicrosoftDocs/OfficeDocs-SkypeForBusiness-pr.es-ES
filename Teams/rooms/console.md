---
title: Configurar una consola de sala de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar y configurar la consola salas de Microsoft Teams y sus periféricos.
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117578"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="7a49e-103">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="7a49e-104">En este artículo se describe cómo configurar la consola salas de Microsoft Teams y sus periféricos.</span><span class="sxs-lookup"><span data-stu-id="7a49e-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="7a49e-105">Solo debe realizar estos pasos si las cuentas de Microsoft Teams o Skype Empresarial y Exchange necesarias ya se han creado y probado como se describe en Implementar [salas de Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="7a49e-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="7a49e-106">Necesitará el hardware y el software descritos en [requisitos de Salas de Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="7a49e-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="7a49e-107">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a49e-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="7a49e-108">Preparar los medios de instalación</span><span class="sxs-lookup"><span data-stu-id="7a49e-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="7a49e-109">Instalar un certificado de CA privado en la consola</span><span class="sxs-lookup"><span data-stu-id="7a49e-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="7a49e-110">Instalar Windows 10 y la aplicación de consola Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="7a49e-111">Configuración inicial de la consola</span><span class="sxs-lookup"><span data-stu-id="7a49e-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="7a49e-112">Lista de comprobación de implementación de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="7a49e-113">Microsoft Teams Rooms solo funcionará en un entorno de Microsoft Teams o Skype Empresarial configurado correctamente, donde las cuentas de dispositivo se configuran correctamente como se describe en Implementar salas [de Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="7a49e-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="7a49e-114">Preparar los medios de instalación</span><span class="sxs-lookup"><span data-stu-id="7a49e-114">Prepare the installation media</span></span>
<span data-ttu-id="7a49e-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="7a49e-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="7a49e-116">Instalar la aplicación de consola Salas de Microsoft Teams requiere un dispositivo de almacenamiento USB con al menos 32 GB de capacidad.</span><span class="sxs-lookup"><span data-stu-id="7a49e-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="7a49e-117">No debería haber otros archivos en el dispositivo; los archivos existentes en el almacenamiento USB se perderán.</span><span class="sxs-lookup"><span data-stu-id="7a49e-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a49e-118">Si no se crean los medios de instalación de Salas de Microsoft Teams de acuerdo con estas instrucciones, es probable que se deba a un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="7a49e-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="7a49e-119">El proceso siguiente es crear medios de instalación para crear imágenes de nuevos dispositivos de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a49e-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="7a49e-120">Los dispositivos existentes, de forma predeterminada, se actualizan automáticamente desde Windows Update y la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="7a49e-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a49e-121">El equipo con Windows 10 usado para crear los medios de instalación de Salas de Microsoft Teams debe estar en la misma versión o posterior de Windows que el medio de instalación de destino.</span><span class="sxs-lookup"><span data-stu-id="7a49e-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="7a49e-122">Descargue el [ scriptCreateSrsMedia.ps1 archivo](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="7a49e-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="7a49e-123">Ejecute el script CreateSrsMedia.ps1 desde un símbolo de sistema con privilegios elevados en un equipo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7a49e-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="7a49e-124">Siga las instrucciones del script para crear un disco de configuración USB de Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a49e-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="7a49e-125">Cada vez que CreateSrsMedia.ps1 script, el resultado de la pantalla incluirá el nombre de un archivo de registro o transcripción para la sesión.</span><span class="sxs-lookup"><span data-stu-id="7a49e-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="7a49e-126">Si hay problemas con la ejecución del script, asegúrese de tener una copia de esa transcripción disponible al solicitar soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="7a49e-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="7a49e-127">El CreateSrsMedia.ps1 script automatiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7a49e-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="7a49e-128">Descargue el instalador MSI más reciente para Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a49e-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="7a49e-129">Determine la compilación de Windows que debe proporcionar el usuario.</span><span class="sxs-lookup"><span data-stu-id="7a49e-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="7a49e-130">Las versiones publicadas más recientemente pueden o no probarse y ser compatibles para su uso con dispositivos Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="7a49e-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="7a49e-131">Descargue los componentes de soporte necesarios.</span><span class="sxs-lookup"><span data-stu-id="7a49e-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="7a49e-132">Ensamble los componentes necesarios en el medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="7a49e-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="7a49e-133">Se requiere una versión específica de Windows 10 y esta versión solo está disponible para los clientes de licencias por volumen.</span><span class="sxs-lookup"><span data-stu-id="7a49e-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="7a49e-134">Puede obtener una copia del Centro de servicios de licencias [por volumen.](https://www.microsoft.com/Licensing/servicecenter/)</span><span class="sxs-lookup"><span data-stu-id="7a49e-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="7a49e-135">Cuando termine, quite el disco USB del equipo y continúe con [Instalar Windows 10 y](console.md#Reimage)la aplicación de consola Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a49e-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="7a49e-136">Instalar Windows 10 y la aplicación de consola Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="7a49e-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="7a49e-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="7a49e-138">Ahora debe aplicar los medios de configuración que ha creado.</span><span class="sxs-lookup"><span data-stu-id="7a49e-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="7a49e-139">El dispositivo de destino se ejecutará como un dispositivo y el usuario predeterminado se establecerá para ejecutar solo la aplicación de consola Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a49e-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="7a49e-140">Si el dispositivo de destino se instalará en un dock (por ejemplo, un Surface Pro), desconéctelo del dock.</span><span class="sxs-lookup"><span data-stu-id="7a49e-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="7a49e-141">Asegúrese de que el dispositivo de destino no está conectado a la red.</span><span class="sxs-lookup"><span data-stu-id="7a49e-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="7a49e-142">Asegúrese de que el dispositivo de destino está conectado a la alimentación de CA.</span><span class="sxs-lookup"><span data-stu-id="7a49e-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="7a49e-143">Conecta el disco de configuración USB al dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="7a49e-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="7a49e-144">Inicie en el disco de configuración USB.</span><span class="sxs-lookup"><span data-stu-id="7a49e-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="7a49e-145">Consulte las instrucciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="7a49e-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="7a49e-146">Si el dispositivo de destino es un Surface Pro, siga estos pasos para iniciar en el disco de configuración USB:</span><span class="sxs-lookup"><span data-stu-id="7a49e-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="7a49e-147">a.</span><span class="sxs-lookup"><span data-stu-id="7a49e-147">a.</span></span> <span data-ttu-id="7a49e-148">Mantén presionado el botón de bajar el volumen (-).</span><span class="sxs-lookup"><span data-stu-id="7a49e-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="7a49e-149">b.</span><span class="sxs-lookup"><span data-stu-id="7a49e-149">b.</span></span> <span data-ttu-id="7a49e-150">Presione y suelte el botón de encendido.</span><span class="sxs-lookup"><span data-stu-id="7a49e-150">Press and release the power button.</span></span>

    <span data-ttu-id="7a49e-151">c.</span><span class="sxs-lookup"><span data-stu-id="7a49e-151">c.</span></span> <span data-ttu-id="7a49e-152">Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).</span><span class="sxs-lookup"><span data-stu-id="7a49e-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="7a49e-153">El sistema se cerrará una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="7a49e-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="7a49e-154">Después de que el sistema se haya apagado, es seguro quitar el disco de configuración USB.</span><span class="sxs-lookup"><span data-stu-id="7a49e-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="7a49e-155">En este punto, puede colocar el dispositivo de destino en su dock (si usa un producto basado en dock), adjuntar los periféricos necesarios para la sala de reuniones y conectarse a la red.</span><span class="sxs-lookup"><span data-stu-id="7a49e-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="7a49e-156">Consulte las instrucciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="7a49e-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="7a49e-157">Las actualizaciones de software para salas de Microsoft Teams se descargan automáticamente desde Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="7a49e-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="7a49e-158">Consulte [Requisitos previos de Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business) para empresas y educación para comprobar que la consola de la sala podrá acceder a la tienda y actualizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7a49e-158">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="7a49e-159">Seleccionar un idioma</span><span class="sxs-lookup"><span data-stu-id="7a49e-159">Selecting a language</span></span> 

<span data-ttu-id="7a49e-160">En Creator's Update, tendrá que usar el script ApplyCurrentRegionAndLanguage.ps1 en escenarios en los que la selección implícita de idioma no proporciona al usuario el idioma real de la aplicación que quiere (por ejemplo, quiere que la aplicación de consola se desprotega en francés, pero está en inglés).</span><span class="sxs-lookup"><span data-stu-id="7a49e-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a49e-161">Las instrucciones siguientes solo funcionan para consolas creadas con Windows Creator's Update.</span><span class="sxs-lookup"><span data-stu-id="7a49e-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="7a49e-162">Los sistemas heredados o en el mercado que no se hayan configurado con medios con el nuevo sistema de aprovisionamiento no podrán usar estas instrucciones, pero tampoco deben sufrir el problema inicial que requiere esta intervención manual (Edición de aniversario le permite elegir el idioma de la aplicación explícitamente como parte de la configuración).</span><span class="sxs-lookup"><span data-stu-id="7a49e-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="7a49e-163">Para aplicar el idioma deseado</span><span class="sxs-lookup"><span data-stu-id="7a49e-163">To apply your desired language</span></span>

1. <span data-ttu-id="7a49e-164">Cambie al modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="7a49e-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="7a49e-165">Seleccione el menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="7a49e-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="7a49e-166">Seleccione el icono de engranaje para iniciar la aplicación **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="7a49e-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="7a49e-167">Seleccione **Idioma &amp; de hora**.</span><span class="sxs-lookup"><span data-stu-id="7a49e-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="7a49e-168">Seleccione **Idioma de &amp; región**.</span><span class="sxs-lookup"><span data-stu-id="7a49e-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="7a49e-169">Seleccione **Agregar un idioma**.</span><span class="sxs-lookup"><span data-stu-id="7a49e-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="7a49e-170">Seleccione el idioma que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="7a49e-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="7a49e-171">Seleccione el idioma que acaba de agregar a la lista "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="7a49e-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="7a49e-172">Haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="7a49e-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="7a49e-173">Si desea eliminar algún idioma:</span><span class="sxs-lookup"><span data-stu-id="7a49e-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="7a49e-p115">a. Seleccione el idioma que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="7a49e-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="7a49e-p116">b. Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="7a49e-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="7a49e-178">Inicie un símbolo de sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="7a49e-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="7a49e-179">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7a49e-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="7a49e-180">Reinicie el sistema.</span><span class="sxs-lookup"><span data-stu-id="7a49e-180">Restart the system.</span></span>
    
<span data-ttu-id="7a49e-181">El idioma que desee ahora se aplica a la consola salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a49e-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="7a49e-182">Configuración inicial de la consola</span><span class="sxs-lookup"><span data-stu-id="7a49e-182">Initial set up of the console</span></span>
<span data-ttu-id="7a49e-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="7a49e-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="7a49e-184">Una vez instalado Windows, la aplicación de consola Salas de Microsoft Teams pasará a su proceso de configuración inicial cuando se inicia a continuación o si se ha elegido la opción /reboot.</span><span class="sxs-lookup"><span data-stu-id="7a49e-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="7a49e-185">Aparece la pantalla Cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7a49e-185">The User Account screen appears.</span></span> <span data-ttu-id="7a49e-186">Escriba la dirección de inicio de sesión de Skype (en user@domain) de la cuenta de salón que se usará con la consola.</span><span class="sxs-lookup"><span data-stu-id="7a49e-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="7a49e-187">Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="7a49e-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="7a49e-188">En "Configurar dominio", establezca el FQDN para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7a49e-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="7a49e-189">Si el dominio SIP de Skype Empresarial es diferente del dominio de Exchange del usuario, escriba el dominio de Exchange en este campo.</span><span class="sxs-lookup"><span data-stu-id="7a49e-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="7a49e-190">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a49e-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="7a49e-191">Seleccione los dispositivos indicados en la pantalla Características y haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="7a49e-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="7a49e-192">De manera predeterminada, la opción Pantalla compartida automática está activada y Ocultar nombres de las reuniones está desactivada.</span><span class="sxs-lookup"><span data-stu-id="7a49e-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="7a49e-193">Los dispositivos que se deben seleccionar son:</span><span class="sxs-lookup"><span data-stu-id="7a49e-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="7a49e-194">Micrófono para conferencias: el micrófono predeterminado de esta sala de conferencias.</span><span class="sxs-lookup"><span data-stu-id="7a49e-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="7a49e-195">Altavoz para conferencias: el altavoz predeterminado para las conferencias. </span><span class="sxs-lookup"><span data-stu-id="7a49e-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="7a49e-196">Altavoz predeterminado: el altavoz que se usa para el audio de la transmisión por HDMI.</span><span class="sxs-lookup"><span data-stu-id="7a49e-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="7a49e-p120">Cada elemento tiene un menú desplegable en el que puede hacer selecciones. Deberá realizar una selección para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a49e-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="7a49e-199">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7a49e-199">Click **Finish**.</span></span>
    
<span data-ttu-id="7a49e-200">La aplicación de consola Salas de Microsoft Teams debería iniciar sesión inmediatamente en Skype Empresarial Server con las credenciales especificadas anteriormente y también debería empezar a sincronizar su calendario con Exchange con esas mismas credenciales.</span><span class="sxs-lookup"><span data-stu-id="7a49e-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="7a49e-201">Para obtener más información sobre el uso de la aplicación de consola, consulte la [ayuda de Salas de Microsoft Teams.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)</span><span class="sxs-lookup"><span data-stu-id="7a49e-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7a49e-202">Microsoft Teams Rooms depende de la presencia de hardware de consola certificado.</span><span class="sxs-lookup"><span data-stu-id="7a49e-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="7a49e-203">Incluso una imagen creada correctamente que contenga la aplicación de consola Salas de Microsoft Teams no se arrancará más allá del procedimiento de configuración inicial a menos que se detecte el hardware de la consola.</span><span class="sxs-lookup"><span data-stu-id="7a49e-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="7a49e-204">Para las soluciones basadas en Surface Pro, el Surface Pro debe estar conectado a su hardware de base adjunto para pasar esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="7a49e-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a49e-205">Es posible que algunos usuarios que no estén en inglés necesiten un teclado físico conectado a la consola durante la configuración inicial en caso de que los símbolos no sean compatibles con el teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="7a49e-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="7a49e-206">Instalar un certificado de CA privado en la consola</span><span class="sxs-lookup"><span data-stu-id="7a49e-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="7a49e-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="7a49e-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="7a49e-208">La consola salas de Microsoft Teams debe confiar en los certificados usados por los servidores a los que se conecta.</span><span class="sxs-lookup"><span data-stu-id="7a49e-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="7a49e-209">Para O365, este proceso se realiza automáticamente, puesto que los servidores utilizan entidades de certificación públicas y Windows 10 confía en ellas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7a49e-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="7a49e-210">En un caso en el que la entidad de certificación es privada, por ejemplo, una implementación local con Active Directory y la entidad de certificación de Windows, puede agregar el certificado a la consola salas de Microsoft Teams de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="7a49e-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="7a49e-211">Puede unirse a la consola a Active Directory y eso agregará automáticamente los certificados necesarios dado que la entidad de certificación se publica en Active Directory (opción de implementación normal).</span><span class="sxs-lookup"><span data-stu-id="7a49e-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="7a49e-212">Puede instalar el certificado manualmente después del proceso de creación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="7a49e-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="7a49e-213">Antes de hacerlo, debe completar la [configuración inicial de la consola.](console.md#Initial)</span><span class="sxs-lookup"><span data-stu-id="7a49e-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="7a49e-214">Para instalar manualmente el certificado </span><span class="sxs-lookup"><span data-stu-id="7a49e-214">To manually install the certificate</span></span>

1. <span data-ttu-id="7a49e-215">Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="7a49e-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="7a49e-216">Coloque la consola en modo de administrador (vea [Modo de administración y administración de dispositivos).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="7a49e-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="7a49e-217">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7a49e-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="7a49e-218">Unirse a un dominio de Active Directory (opcional)</span><span class="sxs-lookup"><span data-stu-id="7a49e-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="7a49e-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="7a49e-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="7a49e-220">Puede unirse a las consolas de Salas de Microsoft Teams a su dominio.</span><span class="sxs-lookup"><span data-stu-id="7a49e-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="7a49e-221">Las consolas de Salas de Microsoft Teams deben colocarse en una unidad organizativa independiente de las estaciones de trabajo del equipo, ya que muchas directivas de estaciones de trabajo no son compatibles con salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a49e-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="7a49e-222">Un ejemplo común son las directivas de aplicación de contraseñas que impedirán que los salas de Microsoft Teams se inicien automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7a49e-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="7a49e-223">Para obtener información sobre la administración de la configuración de GPO, consulte Administrar [salas de Microsoft Teams.](rooms-operations.md)</span><span class="sxs-lookup"><span data-stu-id="7a49e-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="7a49e-224">Para unirse a Salas de Microsoft Teams a un dominio</span><span class="sxs-lookup"><span data-stu-id="7a49e-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="7a49e-225">Inicie sesión en la consola desde la cuenta de administrador (consulte [Modo de administración y administración de dispositivos).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="7a49e-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="7a49e-226">Inicie un símbolo de sistema de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="7a49e-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="7a49e-227">Introduzca el siguiente comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7a49e-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="7a49e-228">Por ejemplo, si su dominio completo es redmond.corp.microsoft.com y desea que las consolas de Salas de Microsoft Teams se usen en una unidad organizativa "Salas de Microsoft Teams" que sea un elemento secundario de una unidad organizativa "Recursos", el comando será:</span><span class="sxs-lookup"><span data-stu-id="7a49e-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="7a49e-229">Si desea cambiar el nombre del equipo al unirse a un dominio, use la marca -NewName seguida del nuevo nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="7a49e-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="7a49e-230">Lista de comprobación de implementación de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="7a49e-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="7a49e-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="7a49e-232">Use la siguiente lista de comprobación mientras hace una comprobación final de que la consola y todos sus periféricos están totalmente configurados:</span><span class="sxs-lookup"><span data-stu-id="7a49e-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="7a49e-233">**Configuración de la aplicación**</span><span class="sxs-lookup"><span data-stu-id="7a49e-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7a49e-234">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-234">☐</span></span>  <br/> |<span data-ttu-id="7a49e-235">El número de teléfono y el nombre de cuenta de la sala (si RTC está habilitado) se muestran correctamente en la parte superior derecha de la pantalla de la consola.</span><span class="sxs-lookup"><span data-stu-id="7a49e-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="7a49e-236">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-236">☐</span></span>  <br/> |<span data-ttu-id="7a49e-237">El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).</span><span class="sxs-lookup"><span data-stu-id="7a49e-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="7a49e-238">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-238">☐</span></span>  <br/> |<span data-ttu-id="7a49e-239">La contraseña de la cuenta de administrador está configurada y comprobada.</span><span class="sxs-lookup"><span data-stu-id="7a49e-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="7a49e-240">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-240">☐</span></span>  <br/> |<span data-ttu-id="7a49e-241">Se han aplicado todas las actualizaciones de firmware</span><span class="sxs-lookup"><span data-stu-id="7a49e-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="7a49e-242">**Periféricos de audio y vídeo**</span><span class="sxs-lookup"><span data-stu-id="7a49e-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7a49e-243">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-243">☐</span></span>  <br/> |<span data-ttu-id="7a49e-244">La versión de firmware del periférico de cámara es correcta (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="7a49e-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="7a49e-245">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-245">☐</span></span>  <br/> |<span data-ttu-id="7a49e-246">Cámara funcional y posicionada de forma óptima</span><span class="sxs-lookup"><span data-stu-id="7a49e-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="7a49e-247">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-247">☐</span></span>  <br/> |<span data-ttu-id="7a49e-248">Configuración del dispositivo de reproducción predeterminado y del dispositivo de comunicaciones predeterminado para la reproducción establecida en el periférico de audio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7a49e-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="7a49e-249">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-249">☐</span></span>  <br/> |<span data-ttu-id="7a49e-250">Configuración del dispositivo de comunicaciones predeterminado para la grabación establecida en el periférico de audio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7a49e-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="7a49e-251">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-251">☐</span></span>  <br/> |<span data-ttu-id="7a49e-252">La versión de firmware del periférico de audio es correcta (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="7a49e-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="7a49e-253">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-253">☐</span></span>  <br/> |<span data-ttu-id="7a49e-254">El dispositivo de entrada de audio funciona y está posicionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7a49e-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="7a49e-255">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-255">☐</span></span>  <br/> |<span data-ttu-id="7a49e-256">El dispositivo de salida de audio funciona y está posicionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7a49e-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="7a49e-257">**Base**</span><span class="sxs-lookup"><span data-stu-id="7a49e-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7a49e-258">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-258">☐</span></span>  <br/> |<span data-ttu-id="7a49e-259">Los cables están protegidos y no están apretados.</span><span class="sxs-lookup"><span data-stu-id="7a49e-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="7a49e-260">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-260">☐</span></span>  <br/> |<span data-ttu-id="7a49e-261">La transmisión de audio a través de HDMI funciona.</span><span class="sxs-lookup"><span data-stu-id="7a49e-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="7a49e-262">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-262">☐</span></span>  <br/> |<span data-ttu-id="7a49e-263">La transmisión de vídeo a través de HDMI funciona.</span><span class="sxs-lookup"><span data-stu-id="7a49e-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="7a49e-264">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-264">☐</span></span>  <br/> |<span data-ttu-id="7a49e-265">La base puede girar sin obstáculos.</span><span class="sxs-lookup"><span data-stu-id="7a49e-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="7a49e-266">☐</span><span class="sxs-lookup"><span data-stu-id="7a49e-266">☐</span></span>  <br/> |<span data-ttu-id="7a49e-267">El brillo de la pantalla es el adecuado para el entorno.</span><span class="sxs-lookup"><span data-stu-id="7a49e-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7a49e-268">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a49e-268">See also</span></span>
<span data-ttu-id="7a49e-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="7a49e-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="7a49e-270">Plan para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="7a49e-271">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="7a49e-272">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="7a49e-273">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a49e-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)