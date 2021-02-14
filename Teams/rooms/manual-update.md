---
title: Actualizar manualmente un dispositivo de Salas de Microsoft Teams
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
description: Obtenga información sobre cómo actualizar manualmente el dispositivo de salas de Microsoft Teams a una versión específica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731402"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="f5ff3-103">Actualizar manualmente un dispositivo de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5ff3-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="f5ff3-104">La aplicación Salas de Microsoft Teams se distribuye a través de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="f5ff3-105">Las actualizaciones de la aplicación se instalan automáticamente desde Microsoft Store durante el mantenimiento nocturno; este es el método recomendado para obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="f5ff3-106">Sin embargo, hay algunas situaciones en las que un dispositivo de Salas de Teams no puede recibir actualizaciones de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="f5ff3-107">Por ejemplo, es posible que las directivas de seguridad no permitan que los dispositivos se conecten a Internet o que no permitan que las aplicaciones se descarguen de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="f5ff3-108">O bien, es posible que quieras actualizar un dispositivo antes de realizar la configuración, durante el cual Microsoft Store no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="f5ff3-109">Si no puede obtener actualizaciones de Microsoft Store, puede usar un script de PowerShell de actualización de aplicaciones sin conexión para actualizar manualmente los dispositivos de salas de Teams a una versión más reciente de la aplicación Salas de Teams.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="f5ff3-110">Siga los pasos de este artículo para actualizar manualmente los dispositivos de salas de Teams.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="f5ff3-111">Este proceso solo puede actualizar un dispositivo de Salas de Teams con la aplicación Salas de Teams ya instalada.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="f5ff3-112">No se puede usar para realizar una nueva instalación.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="f5ff3-113">Tampoco se puede usar para degradar la aplicación a una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="f5ff3-114">Para realizar una nueva instalación de la aplicación Teams Rooms, póngase en contacto con el fabricante del dispositivo para obtener contenido multimedia específico para él o vea [Preparar el medio de instalación.](console.md#prepare-the-installation-media)</span><span class="sxs-lookup"><span data-stu-id="f5ff3-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="f5ff3-115">Paso 1: Descargar el script de actualización de aplicaciones sin conexión</span><span class="sxs-lookup"><span data-stu-id="f5ff3-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="f5ff3-116">Primero, descargue la última versión del script de actualización de aplicaciones sin conexión.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="f5ff3-117">Para descargar el script, haga clic <https://go.microsoft.com/fwlink/?linkid=2151817> en .</span><span class="sxs-lookup"><span data-stu-id="f5ff3-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="f5ff3-118">El script se descargará en la carpeta de descargas predeterminada del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="f5ff3-119">Los archivos descargados pueden estar marcados como bloqueados por Windows.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="f5ff3-120">Si necesita ejecutar el script sin ninguna interacción, tendrá que desbloquear el script.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="f5ff3-121">Para desbloquear el script, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5ff3-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="f5ff3-122">Haga clic con el botón derecho en el archivo en el Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="f5ff3-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="f5ff3-123">Haga clic **en Propiedades**</span><span class="sxs-lookup"><span data-stu-id="f5ff3-123">Click **Properties**</span></span>
3. <span data-ttu-id="f5ff3-124">Seleccione **Desbloquear**</span><span class="sxs-lookup"><span data-stu-id="f5ff3-124">Select **Unblock**</span></span>
4. <span data-ttu-id="f5ff3-125">Haga clic **en Aceptar**</span><span class="sxs-lookup"><span data-stu-id="f5ff3-125">Click **OK**</span></span>

<span data-ttu-id="f5ff3-126">Para desbloquear el script con PowerShell, vea [Desbloquear archivo.](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)</span><span class="sxs-lookup"><span data-stu-id="f5ff3-126">To unblock the script using PowerShell, see [Unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="f5ff3-127">Después de descargar el script de actualización de aplicaciones sin conexión, transfiera el archivo al dispositivo de Salas de Teams.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="f5ff3-128">Puede transferir un archivo al dispositivo mediante una unidad USB o accediendo al archivo desde un recurso compartido de archivos de red mientras está en modo de administración en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="f5ff3-129">Asegúrese de anote dónde guarda el archivo en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="f5ff3-130">Paso 2: Ejecutar el script para actualizar la aplicación Salas de Teams</span><span class="sxs-lookup"><span data-stu-id="f5ff3-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="f5ff3-131">El script de actualización de aplicaciones sin conexión debe ejecutarse desde un símbolo del sistema con privilegios elevados mientras el usuario de Skype (el usuario en el que se ejecuta la aplicación) sigue conectado.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="f5ff3-132">Para obtener más información sobre cómo iniciar sesión en una cuenta de administrador para usar el símbolo del sistema con privilegios elevados mientras el usuario de Skype todavía está conectado, consulte Cambiar al modo de administración y volver cuando se está ejecutando la aplicación [Microsoft Teams Rooms.](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)</span><span class="sxs-lookup"><span data-stu-id="f5ff3-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="f5ff3-133">Haga lo siguiente para ejecutar el script desde un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="f5ff3-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="f5ff3-134">Cambiar al modo de administración</span><span class="sxs-lookup"><span data-stu-id="f5ff3-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="f5ff3-135">Haga clic en el icono Inicio, escriba **Símbolo del sistema** y, después, seleccione Ejecutar como **administrador.**</span><span class="sxs-lookup"><span data-stu-id="f5ff3-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="f5ff3-136">Ejecute el comando siguiente, `<path to script>` donde se incluye la ruta de acceso completa al script y el nombre del archivo de script:</span><span class="sxs-lookup"><span data-stu-id="f5ff3-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="f5ff3-137">Por ejemplo, si el archivo de script se encuentra en y el nombre del archivo de `C:\Users\Admin\Downloads` script `MTR-Update-4.5.6.7.ps1` es, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f5ff3-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="f5ff3-138">Permita que se ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-138">Allow the script to run.</span></span> <span data-ttu-id="f5ff3-139">Cuando termine, el script reiniciará el dispositivo de Salas de Teams.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="f5ff3-140">También puede ejecutar el script mediante El PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="f5ff3-141">Para obtener más información sobre el uso de PowerShell remoto con dispositivos de salas de Teams, consulte Administración remota [con PowerShell.](rooms-operations.md#remote-management-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="f5ff3-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="f5ff3-142">Paso 3: Comprobar que la aplicación se ha actualizado correctamente</span><span class="sxs-lookup"><span data-stu-id="f5ff3-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="f5ff3-143">Si el script se ejecuta correctamente, el dispositivo se reiniciará en la aplicación Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="f5ff3-144">Si el script encuentra un problema, indicará cuál es el problema en la línea de comandos y registrará su salida en un archivo.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="f5ff3-145">Siga las instrucciones que proporciona el script.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="f5ff3-146">Si necesita ponerse en contacto con el soporte técnico de Microsoft, asegúrese de incluir el archivo de registro junto con la solicitud de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="f5ff3-147">El script le proporcionará la ruta de acceso al archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="f5ff3-147">The script will provide you with the path to the log file.</span></span>
