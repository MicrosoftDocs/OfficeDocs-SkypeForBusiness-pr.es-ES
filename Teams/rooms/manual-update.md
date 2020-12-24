---
title: Actualizar manualmente un dispositivo de salas de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo actualizar manualmente el dispositivo de las salas de Microsoft Teams a una versión específica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731402"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="e95e7-103">Actualizar manualmente un dispositivo de salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e95e7-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="e95e7-104">La aplicación salas de Microsoft Teams se distribuye a través de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e95e7-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="e95e7-105">Las actualizaciones de la aplicación se instalan automáticamente desde Microsoft Store durante el mantenimiento nocturno; Este es el método recomendado para obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="e95e7-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="e95e7-106">Sin embargo, hay algunas situaciones en las que un dispositivo de salas de equipos no puede recibir actualizaciones de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e95e7-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="e95e7-107">Por ejemplo, es posible que las directivas de seguridad no permitan que los dispositivos se conecten a Internet o que no permitan la descarga de aplicaciones de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e95e7-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="e95e7-108">O bien, es posible que desee actualizar un dispositivo antes de realizar la instalación, durante el cual Microsoft Store no está disponible.</span><span class="sxs-lookup"><span data-stu-id="e95e7-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="e95e7-109">Si no puede obtener actualizaciones de Microsoft Store, puede usar un script de PowerShell de actualización de aplicaciones sin conexión para actualizar manualmente los dispositivos de las salas de equipos a una versión más reciente de la aplicación salas de equipos.</span><span class="sxs-lookup"><span data-stu-id="e95e7-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="e95e7-110">Siga los pasos que se indican en este artículo para actualizar manualmente los dispositivos de salas de equipos.</span><span class="sxs-lookup"><span data-stu-id="e95e7-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="e95e7-111">Este proceso solo puede actualizar un dispositivo de salas de equipos con la aplicación salas de equipos ya instalada.</span><span class="sxs-lookup"><span data-stu-id="e95e7-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="e95e7-112">No se puede usar para realizar una instalación nueva.</span><span class="sxs-lookup"><span data-stu-id="e95e7-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="e95e7-113">Tampoco se puede usar para degradar la aplicación a una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="e95e7-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="e95e7-114">Para realizar una nueva instalación de la aplicación salas de equipos, póngase en contacto con el fabricante del dispositivo para obtener medios específicos o vea [preparar los medios de instalación](console.md#prepare-the-installation-media).</span><span class="sxs-lookup"><span data-stu-id="e95e7-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="e95e7-115">Paso 1: descargar el script de actualización de la aplicación sin conexión</span><span class="sxs-lookup"><span data-stu-id="e95e7-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="e95e7-116">En primer lugar, descargue la última versión del script de actualización de aplicaciones sin conexión.</span><span class="sxs-lookup"><span data-stu-id="e95e7-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="e95e7-117">Para descargar el script, haga clic en <https://go.microsoft.com/fwlink/?linkid=2151817> .</span><span class="sxs-lookup"><span data-stu-id="e95e7-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="e95e7-118">El script se descargará en la carpeta de descargas predeterminada de su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e95e7-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="e95e7-119">Los archivos descargados pueden estar marcados como bloqueados por Windows.</span><span class="sxs-lookup"><span data-stu-id="e95e7-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="e95e7-120">Si necesita ejecutar el script sin ninguna interacción, tendrá que desbloquear el script.</span><span class="sxs-lookup"><span data-stu-id="e95e7-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="e95e7-121">Para desbloquear el script, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e95e7-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="e95e7-122">Haga clic con el botón derecho en el archivo en el explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="e95e7-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="e95e7-123">Haga clic en **propiedades**</span><span class="sxs-lookup"><span data-stu-id="e95e7-123">Click **Properties**</span></span>
3. <span data-ttu-id="e95e7-124">Seleccionar **desbloquear**</span><span class="sxs-lookup"><span data-stu-id="e95e7-124">Select **Unblock**</span></span>
4. <span data-ttu-id="e95e7-125">Haga clic en **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="e95e7-125">Click **OK**</span></span>

<span data-ttu-id="e95e7-126">Para desbloquear el script con PowerShell, consulte [unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span><span class="sxs-lookup"><span data-stu-id="e95e7-126">To unblock the script using PowerShell, see [Unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="e95e7-127">Una vez descargado el script de actualización de la aplicación sin conexión, transfiera el archivo al dispositivo salas de equipos.</span><span class="sxs-lookup"><span data-stu-id="e95e7-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="e95e7-128">Puede transferir un archivo al dispositivo mediante una unidad USB o accediendo al archivo desde un recurso compartido de archivos de red mientras está en el modo de administrador del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e95e7-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="e95e7-129">Asegúrese de anotar dónde guarda el archivo en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e95e7-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="e95e7-130">Paso 2: ejecutar el script para actualizar la aplicación salas de equipos</span><span class="sxs-lookup"><span data-stu-id="e95e7-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="e95e7-131">El script de actualización de la aplicación sin conexión debe ejecutarse desde un símbolo del sistema con privilegios elevados mientras el usuario de Skype (el usuario en el que se ejecuta la aplicación) aún ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="e95e7-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="e95e7-132">Para obtener más información sobre cómo iniciar sesión en una cuenta de administrador para usar el símbolo del sistema con privilegios elevados mientras el usuario de Skype aún ha iniciado sesión, consulte [cambiar al modo de administración y volver cuando se está ejecutando la aplicación salas de Microsoft Teams](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span><span class="sxs-lookup"><span data-stu-id="e95e7-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="e95e7-133">Siga este procedimiento para ejecutar el script desde un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="e95e7-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="e95e7-134">Cambiar al modo de administración</span><span class="sxs-lookup"><span data-stu-id="e95e7-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="e95e7-135">Haga clic en el icono Inicio, escriba **símbolo del sistema** y, a continuación, seleccione **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="e95e7-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="e95e7-136">Ejecute el siguiente comando `<path to script>` , donde incluye la ruta de acceso completa del script y el nombre del archivo de script:</span><span class="sxs-lookup"><span data-stu-id="e95e7-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="e95e7-137">Por ejemplo, si el archivo de script se encuentra en `C:\Users\Admin\Downloads` y el nombre de archivo de script es `MTR-Update-4.5.6.7.ps1` , ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e95e7-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="e95e7-138">Permita que se ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="e95e7-138">Allow the script to run.</span></span> <span data-ttu-id="e95e7-139">Cuando termine, el script reiniciará el dispositivo de salas de equipos.</span><span class="sxs-lookup"><span data-stu-id="e95e7-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="e95e7-140">También puede ejecutar el script mediante PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="e95e7-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="e95e7-141">Para obtener más información sobre el uso de PowerShell remoto con dispositivos de salas de equipos, vea [administración remota con PowerShell](rooms-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="e95e7-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="e95e7-142">Paso 3: comprobar que la aplicación se ha actualizado correctamente</span><span class="sxs-lookup"><span data-stu-id="e95e7-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="e95e7-143">Si el script se ejecuta correctamente, el dispositivo se reiniciará en la aplicación salas de equipos.</span><span class="sxs-lookup"><span data-stu-id="e95e7-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="e95e7-144">Si la secuencia de comandos encuentra un problema, indicará el problema en la línea de comandos y grabará el resultado en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e95e7-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="e95e7-145">Siga las instrucciones proporcionadas por el script.</span><span class="sxs-lookup"><span data-stu-id="e95e7-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="e95e7-146">Si necesita ponerse en contacto con el soporte técnico de Microsoft, asegúrese de incluir el archivo de registro junto con la solicitud de asistencia.</span><span class="sxs-lookup"><span data-stu-id="e95e7-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="e95e7-147">El script le proporcionará la ruta de acceso al archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="e95e7-147">The script will provide you with the path to the log file.</span></span>
