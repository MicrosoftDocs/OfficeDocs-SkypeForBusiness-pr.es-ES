---
title: Actualizar manualmente un dispositivo salas de Microsoft Teams
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
description: Obtenga información sobre cómo actualizar manualmente el dispositivo Salas de Microsoft Teams a una versión específica.
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117518"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="0ff5a-103">Actualizar manualmente un dispositivo salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ff5a-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="0ff5a-104">La aplicación Salas de Microsoft Teams se distribuye a través de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="0ff5a-105">Las actualizaciones de la aplicación se instalan automáticamente desde Microsoft Store durante el mantenimiento nocturno; este es el método recomendado para obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="0ff5a-106">Sin embargo, hay algunas situaciones en las que un dispositivo salas de Teams no puede recibir actualizaciones de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="0ff5a-107">Por ejemplo, es posible que las directivas de seguridad no permitan que los dispositivos se conecten a Internet o que no permitan que las aplicaciones se descarguen desde Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="0ff5a-108">O bien, es posible que quiera actualizar un dispositivo antes de realizar la configuración, durante la cual microsoft Store no está disponible.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="0ff5a-109">Si no puede obtener actualizaciones de Microsoft Store, puede usar un script de PowerShell de actualización de aplicaciones sin conexión para actualizar manualmente los dispositivos teams Rooms a una versión más reciente de la aplicación Salas de Teams.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="0ff5a-110">Siga los pasos de este artículo para actualizar manualmente los dispositivos de Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="0ff5a-111">Este proceso solo puede actualizar un dispositivo salas de Teams con la aplicación Salas de Teams ya instalada.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="0ff5a-112">No se puede usar para realizar una nueva instalación.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="0ff5a-113">Tampoco se puede usar para degradar la aplicación a una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="0ff5a-114">Para realizar una nueva instalación de la aplicación Salas de Teams, póngase en contacto con el fabricante del dispositivo para obtener contenido multimedia específico de él o vea [Preparar los medios de instalación.](console.md#prepare-the-installation-media)</span><span class="sxs-lookup"><span data-stu-id="0ff5a-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="0ff5a-115">Paso 1: Descargar el script de actualización de aplicaciones sin conexión</span><span class="sxs-lookup"><span data-stu-id="0ff5a-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="0ff5a-116">En primer lugar, descargue la versión más reciente del script de actualización de aplicaciones sin conexión.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="0ff5a-117">Para descargar el script, haga clic en <https://go.microsoft.com/fwlink/?linkid=2151817> .</span><span class="sxs-lookup"><span data-stu-id="0ff5a-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="0ff5a-118">El script se descargará en la carpeta de descargas predeterminada del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="0ff5a-119">Windows puede marcar los archivos descargados como bloqueados.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="0ff5a-120">Si necesita ejecutar el script sin ninguna interacción, tendrá que desbloquear el script.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="0ff5a-121">Para desbloquear el script, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ff5a-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="0ff5a-122">Haga clic con el botón derecho en el archivo en el Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="0ff5a-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="0ff5a-123">Haga clic **en Propiedades**</span><span class="sxs-lookup"><span data-stu-id="0ff5a-123">Click **Properties**</span></span>
3. <span data-ttu-id="0ff5a-124">Seleccione **Desbloquear**</span><span class="sxs-lookup"><span data-stu-id="0ff5a-124">Select **Unblock**</span></span>
4. <span data-ttu-id="0ff5a-125">Haga clic **en Aceptar**</span><span class="sxs-lookup"><span data-stu-id="0ff5a-125">Click **OK**</span></span>

<span data-ttu-id="0ff5a-126">Para desbloquear el script con PowerShell, vea [Desbloquear archivo.](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)</span><span class="sxs-lookup"><span data-stu-id="0ff5a-126">To unblock the script using PowerShell, see [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="0ff5a-127">Después de descargar el script de actualización de la aplicación sin conexión, transfiera el archivo al dispositivo Salas de Teams.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="0ff5a-128">Puede transferir un archivo al dispositivo mediante una unidad USB o accediendo al archivo desde un recurso compartido de archivos de red mientras está en modo administrador en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="0ff5a-129">Asegúrese de tener en cuenta dónde guarda el archivo en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="0ff5a-130">Paso 2: Ejecutar el script para actualizar la aplicación Salas de Teams</span><span class="sxs-lookup"><span data-stu-id="0ff5a-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="0ff5a-131">El script de actualización de aplicaciones sin conexión debe ejecutarse desde un símbolo del sistema con privilegios elevados mientras el usuario de Skype (el usuario en el que se ejecuta la aplicación) sigue iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="0ff5a-132">Para obtener más información sobre cómo iniciar sesión en una cuenta de administrador para usar el símbolo del sistema con privilegios elevados mientras el usuario de Skype sigue conectado, vea Cambiar al modo de administración y volver cuando se esté ejecutando la aplicación Salas de [Microsoft Teams.](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)</span><span class="sxs-lookup"><span data-stu-id="0ff5a-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="0ff5a-133">Haga lo siguiente para ejecutar el script desde un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="0ff5a-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="0ff5a-134">Cambiar al modo administrador</span><span class="sxs-lookup"><span data-stu-id="0ff5a-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="0ff5a-135">Haga clic en el icono Inicio, escriba **Símbolo del** sistema y, a continuación, seleccione Ejecutar **como administrador**</span><span class="sxs-lookup"><span data-stu-id="0ff5a-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="0ff5a-136">Ejecute el siguiente comando en el `<path to script>` que se incluye la ruta completa al script y el nombre del archivo de script:</span><span class="sxs-lookup"><span data-stu-id="0ff5a-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="0ff5a-137">Por ejemplo, si el archivo de script se encuentra en y el nombre del archivo de `C:\Users\Admin\Downloads` script es , ejecute el siguiente `MTR-Update-4.5.6.7.ps1` comando:</span><span class="sxs-lookup"><span data-stu-id="0ff5a-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="0ff5a-138">Permitir que se ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-138">Allow the script to run.</span></span> <span data-ttu-id="0ff5a-139">Cuando haya terminado, el script reiniciará el dispositivo Salas de Teams.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="0ff5a-140">También puede ejecutar el script con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="0ff5a-141">Para obtener más información sobre el uso de PowerShell remoto con dispositivos teams Rooms, vea [Administración remota con PowerShell.](rooms-operations.md#remote-management-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="0ff5a-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="0ff5a-142">Paso 3: Comprobar que la aplicación se ha actualizado correctamente</span><span class="sxs-lookup"><span data-stu-id="0ff5a-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="0ff5a-143">Si el script se ejecuta correctamente, el dispositivo se reiniciará en la aplicación Salas de Teams.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="0ff5a-144">Si el script encuentra un problema, indicará cuál es el problema en la línea de comandos y registrará su salida en un archivo.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="0ff5a-145">Siga las instrucciones que proporciona el script.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="0ff5a-146">Si necesita ponerse en contacto con el soporte técnico de Microsoft, asegúrese de incluir el archivo de registro junto con la solicitud de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="0ff5a-147">El script le proporcionará la ruta de acceso al archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="0ff5a-147">The script will provide you with the path to the log file.</span></span>