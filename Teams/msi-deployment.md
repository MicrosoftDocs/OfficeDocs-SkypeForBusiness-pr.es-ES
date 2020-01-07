---
title: Instalar Microsoft Teams con MSI (mediante SCCM)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Los administradores pueden usar el MSI de Teams para implementar Microsoft Teams en bloque y poder seleccionar usuarios o equipos.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a621c4e1cfcf9e485b68fd96a76d9179cef84a48
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952603"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="15072-103">Instalar Microsoft Teams con MSI</span><span class="sxs-lookup"><span data-stu-id="15072-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="15072-104">Vea la siguiente sesión para obtener información sobre las ventajas del cliente de escritorio de Windows, cómo se planea y cómo se implementa: [Teams cliente de escritorio de Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="15072-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="15072-105">Para usar System Center Configuration Manager, una directiva de grupo o cualquier mecanismo de distribución de terceros para una implementación ampliada, Microsoft ha proporcionado archivos MSI (32 de bits y 64 bits) que los administradores pueden usar para la implementación masiva de equipos para seleccionar usuarios o equipos.</span><span class="sxs-lookup"><span data-stu-id="15072-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="15072-106">Los administradores pueden usar estos archivos para implementar equipos de forma remota, de modo que los usuarios no tengan que descargar manualmente la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="15072-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="15072-107">Cuando se implementa, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="15072-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="15072-108">(Puede deshabilitar el inicio automático después de instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="15072-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="15072-109">[Consulte a continuación](#disable-auto-launch-for-the-msi-installer)). Le recomendamos que implemente el paquete en el equipo, de modo que todos los nuevos usuarios del equipo también se beneficien de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="15072-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="15072-110">Estos son los vínculos a los archivos MSI:</span><span class="sxs-lookup"><span data-stu-id="15072-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="15072-111">Entidad</span><span class="sxs-lookup"><span data-stu-id="15072-111">Entity</span></span>  |<span data-ttu-id="15072-112">32 bits</span><span class="sxs-lookup"><span data-stu-id="15072-112">32 bit</span></span>      |<span data-ttu-id="15072-113">64 bits</span><span class="sxs-lookup"><span data-stu-id="15072-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="15072-114">Publicidad</span><span class="sxs-lookup"><span data-stu-id="15072-114">Commercial</span></span>     | [<span data-ttu-id="15072-115">32 bits</span><span class="sxs-lookup"><span data-stu-id="15072-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="15072-116">64 bits</span><span class="sxs-lookup"><span data-stu-id="15072-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="15072-117">Gobierno federal-GCC</span><span class="sxs-lookup"><span data-stu-id="15072-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="15072-118">32 bits</span><span class="sxs-lookup"><span data-stu-id="15072-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="15072-119">64 bits</span><span class="sxs-lookup"><span data-stu-id="15072-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="15072-120">Gobierno Federal: GCC High</span><span class="sxs-lookup"><span data-stu-id="15072-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="15072-121">32 bits</span><span class="sxs-lookup"><span data-stu-id="15072-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="15072-122">64 bits</span><span class="sxs-lookup"><span data-stu-id="15072-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="15072-123">Gobierno Federal: DoD</span><span class="sxs-lookup"><span data-stu-id="15072-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="15072-124">32 bits</span><span class="sxs-lookup"><span data-stu-id="15072-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="15072-125">64 bits</span><span class="sxs-lookup"><span data-stu-id="15072-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="15072-126">Los equipos también pueden incluirse con una implementación de Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="15072-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="15072-127">Para obtener más información, consulte [implementar Microsoft Teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="15072-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="15072-128">Para obtener más información sobre SCCM, consulte [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="15072-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="15072-129">Procedimiento de implementación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="15072-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="15072-130">Recuperar el paquete más reciente.</span><span class="sxs-lookup"><span data-stu-id="15072-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="15072-131">Use los valores predeterminados rellenados previamente por el MSI.</span><span class="sxs-lookup"><span data-stu-id="15072-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="15072-132">Implementar en equipos siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="15072-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="15072-133">Cómo funciona el paquete MSI de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15072-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="15072-134">Instalación de PC</span><span class="sxs-lookup"><span data-stu-id="15072-134">PC installation</span></span>

<span data-ttu-id="15072-135">El MSI de Teams colocará un instalador en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="15072-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="15072-136">Cada vez que un usuario inicie sesión en un nuevo perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación de Teams en la carpeta appdata del usuario.</span><span class="sxs-lookup"><span data-stu-id="15072-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="15072-137">Si un usuario ya tiene la aplicación de Teams instalada en la carpeta appdata, el instalador MSI omitirá el proceso para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="15072-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="15072-138">No use el MSI para implementar actualizaciones, ya que el cliente se actualizará automáticamente cuando detecte que hay una nueva versión disponible en el servicio.</span><span class="sxs-lookup"><span data-stu-id="15072-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="15072-139">Para volver a implementar el último instalador, use el proceso de reimplementación de MSI que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="15072-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="15072-140">Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente (excepto en entornos de VDI) cuando sea posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="15072-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="15072-141">Si se implementa una versión muy antigua, el MSI desencadenará una actualización de la aplicación antes de que el usuario pueda usar Teams.</span><span class="sxs-lookup"><span data-stu-id="15072-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="15072-142">No recomendamos que cambie las ubicaciones de instalación predeterminadas, ya que esto podría interrumpir el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="15072-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="15072-143">Tener una versión demasiado antigua impedirá que los usuarios tengan acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="15072-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="15072-144">Requisitos del equipo de destino</span><span class="sxs-lookup"><span data-stu-id="15072-144">Target computer requirements</span></span>

- <span data-ttu-id="15072-145">.NET Framework 4,5 o posterior</span><span class="sxs-lookup"><span data-stu-id="15072-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="15072-146">Windows 7 o posterior</span><span class="sxs-lookup"><span data-stu-id="15072-146">Windows 7 or later</span></span>
- <span data-ttu-id="15072-147">3 GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="15072-147">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="15072-148">Instalación de VDI</span><span class="sxs-lookup"><span data-stu-id="15072-148">VDI installation</span></span>

<span data-ttu-id="15072-149">Para obtener instrucciones completas sobre cómo implementar la aplicación de escritorio de Teams en VDI, vea [Teams for virtualizated Desktop Infrastructure](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="15072-149">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="15072-150">Procedimiento de limpieza y reimplementación</span><span class="sxs-lookup"><span data-stu-id="15072-150">Clean up and redeployment procedure</span></span>

<span data-ttu-id="15072-151">Si un usuario desinstala equipos de su perfil de usuario, el instalador MSI realizará un seguimiento de que el usuario ha desinstalado la aplicación de Teams y ya no instalará Teams para ese perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="15072-151">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="15072-152">Para volver a implementar Teams para este usuario en un equipo determinado en el que se ha desinstalado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15072-152">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="15072-153">Desinstalar la aplicación de Teams instalada para todos los perfiles de usuario.</span><span class="sxs-lookup"><span data-stu-id="15072-153">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="15072-154">Después de la desinstalación, eliminar el directorio de forma recursiva en%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="15072-154">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="15072-155">Vuelva a implementar el paquete MSI en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="15072-155">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="15072-156">Puede usar nuestro script de limpieza de la [implementación de Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.</span><span class="sxs-lookup"><span data-stu-id="15072-156">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="15072-157">Deshabilitar el inicio automático para el instalador MSI</span><span class="sxs-lookup"><span data-stu-id="15072-157">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="15072-158">El comportamiento predeterminado del MSI es instalar el cliente de Teams en cuanto un usuario inicie sesión y, a continuación, inicie automáticamente Teams.</span><span class="sxs-lookup"><span data-stu-id="15072-158">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="15072-159">Puede modificar este comportamiento con los parámetros siguientes de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="15072-159">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="15072-160">Cuando un usuario inicia sesión en Windows, Teams se instalará con el MSI</span><span class="sxs-lookup"><span data-stu-id="15072-160">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="15072-161">Sin embargo, el cliente de Teams no se iniciará hasta que el usuario haya iniciado manualmente Teams</span><span class="sxs-lookup"><span data-stu-id="15072-161">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="15072-162">Se agregará un acceso directo para iniciar Teams en el escritorio del usuario</span><span class="sxs-lookup"><span data-stu-id="15072-162">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="15072-163">Una vez que se inicia manualmente, Teams se inicia automáticamente cuando el usuario inicia sesión</span><span class="sxs-lookup"><span data-stu-id="15072-163">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="15072-164">Para la versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="15072-164">For the 32-bit version</span></span>
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="15072-165">Para la versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="15072-165">For the 64-bit version</span></span>
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> <span data-ttu-id="15072-166">Si ejecuta el MSI manualmente, asegúrese de ejecutarlo con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="15072-166">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="15072-167">Incluso si lo ejecuta como administrador, sin ejecutarlo con permisos elevados, el instalador no podrá configurar la opción para deshabilitar el inicio automático.</span><span class="sxs-lookup"><span data-stu-id="15072-167">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
