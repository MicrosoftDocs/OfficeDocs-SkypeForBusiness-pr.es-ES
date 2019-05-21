---
title: Instalar Microsoft Teams con MSI (mediante SCCM)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Los administradores pueden usar el MSI de Teams para implementar Microsoft Teams en bloque y poder seleccionar usuarios o equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c009433696ac554114a2a06955b4f33beb6543f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281620"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="db96d-103">Instalar Microsoft Teams con MSI</span><span class="sxs-lookup"><span data-stu-id="db96d-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="db96d-104">Vea la siguiente sesión para obtener información sobre las ventajas del cliente de escritorio de Windows, cómo se planea y cómo se implementa: [Teams cliente de escritorio de Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="db96d-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="db96d-105">Para usar System Center Configuration Manager, una directiva de grupo o cualquier mecanismo de distribución de terceros para una implementación ampliada, Microsoft ha proporcionado archivos MSI (tanto [de 32](https://aka.ms/teams32bitmsi) bits como de [64](https://aka.ms/teams64bitmsi)bits) que los administradores pueden usar para la implementación masiva de equipos para seleccionar usuarios o equipos.</span><span class="sxs-lookup"><span data-stu-id="db96d-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="db96d-106">Los administradores pueden usar estos archivos para implementar equipos de forma remota, de modo que los usuarios no tengan que descargar manualmente la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="db96d-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="db96d-107">Cuando se implementa, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="db96d-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="db96d-108">(Puede deshabilitar el inicio automático después de instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db96d-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="db96d-109">[Consulte a continuación](#disable-auto-launch-for-the-msi-installer)). Le recomendamos que implemente el paquete en el equipo, de modo que todos los nuevos usuarios del equipo también se beneficien de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="db96d-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="db96d-110">Para obtener más información sobre SCCM, consulte [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="db96d-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="db96d-111">Procedimiento de implementación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="db96d-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="db96d-112">Recuperar el paquete más reciente.</span><span class="sxs-lookup"><span data-stu-id="db96d-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="db96d-113">Use los valores predeterminados rellenados previamente por el MSI.</span><span class="sxs-lookup"><span data-stu-id="db96d-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="db96d-114">Implementar en equipos siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="db96d-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="db96d-115">Cómo funciona el paquete MSI de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db96d-115">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="db96d-116">Instalación de PC</span><span class="sxs-lookup"><span data-stu-id="db96d-116">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="db96d-117">Vea [instalación de VDI](#vdi-installation) para obtener instrucciones sobre cómo implementar Teams en un entorno de DesktopInfrastructure virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="db96d-117">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="db96d-118">El MSI de Teams colocará un instalador en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="db96d-118">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="db96d-119">Cada vez que un usuario inicie sesión en un nuevo perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación de Teams en la carpeta appdata del usuario.</span><span class="sxs-lookup"><span data-stu-id="db96d-119">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="db96d-120">Si un usuario ya tiene la aplicación de Teams instalada en la carpeta appdata, el instalador MSI omitirá el proceso para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="db96d-120">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="db96d-121">No use el MSI para implementar actualizaciones, ya que el cliente se actualizará automáticamente cuando detecte que hay una nueva versión disponible en el servicio.</span><span class="sxs-lookup"><span data-stu-id="db96d-121">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="db96d-122">Para volver a implementar el último instalador, use el proceso de reimplementación de MSI que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="db96d-122">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="db96d-123">Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente cuando sea posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="db96d-123"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="db96d-124">Si se implementa una versión muy antigua, el MSI desencadenará una actualización de la aplicación antes de que el usuario pueda usar Teams.</span><span class="sxs-lookup"><span data-stu-id="db96d-124">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="db96d-125">No recomendamos que cambie las ubicaciones de instalación predeterminadas, ya que esto podría interrumpir el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="db96d-125">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="db96d-126">Tener una versión demasiado antigua impedirá que los usuarios tengan acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="db96d-126">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="db96d-127">Requisitos del equipo de destino</span><span class="sxs-lookup"><span data-stu-id="db96d-127">Target computer requirements</span></span>

- <span data-ttu-id="db96d-128">.NET Framework 4,5 o posterior</span><span class="sxs-lookup"><span data-stu-id="db96d-128">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="db96d-129">Windows 7 o posterior</span><span class="sxs-lookup"><span data-stu-id="db96d-129">Windows 7 or later</span></span>
- <span data-ttu-id="db96d-130">3 GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="db96d-130">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="db96d-131">Instalación de VDI</span><span class="sxs-lookup"><span data-stu-id="db96d-131">VDI installation</span></span>

<span data-ttu-id="db96d-132">Este es el proceso para implementar la aplicación de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="db96d-132">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="db96d-133">Para obtener instrucciones detalladas, vea [Teams para infraestructura de escritorio virtualizada](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="db96d-133">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="db96d-134">Descargue el paquete de MSI de Teams con uno de los siguientes vínculos en función del entorno.</span><span class="sxs-lookup"><span data-stu-id="db96d-134">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="db96d-135">Recomendamos la versión de 64 bits para una VM VDI con un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="db96d-135">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="db96d-136">versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="db96d-136">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="db96d-137">versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="db96d-137">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="db96d-138">Ejecute el siguiente comando para instalar el MSI en la máquina virtual de VDI (o actualizarlo).</span><span class="sxs-lookup"><span data-stu-id="db96d-138">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1

    <span data-ttu-id="db96d-139">Instala Teams en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="db96d-139">This installs Teams to Program Files.</span></span> <span data-ttu-id="db96d-140">En este momento, la configuración de la imagen de oro está completa.</span><span class="sxs-lookup"><span data-stu-id="db96d-140">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="db96d-141">La siguiente sesión de inicio de sesión interactivo inicia Teams y solicita las credenciales.</span><span class="sxs-lookup"><span data-stu-id="db96d-141">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="db96d-142">Tenga en cuenta que no es posible deshabilitar el inicio automático de equipos al instalar Teams en VDI con la propiedad ALLUSERS.</span><span class="sxs-lookup"><span data-stu-id="db96d-142">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSERS property.</span></span>

3. <span data-ttu-id="db96d-143">Ejecute el siguiente comando para desinstalar el MSI de la máquina virtual de VDI (o prepararse para actualizarlo).</span><span class="sxs-lookup"><span data-stu-id="db96d-143">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="db96d-144">Esto desinstalará Teams de archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="db96d-144">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="db96d-145">Procedimiento de limpieza y reimplementación</span><span class="sxs-lookup"><span data-stu-id="db96d-145">Clean up and redeployment procedure</span></span>

<span data-ttu-id="db96d-146">Si un usuario desinstala equipos de su perfil de usuario, el instalador MSI realizará un seguimiento de que el usuario ha desinstalado la aplicación de Teams y ya no instalará Teams para ese perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="db96d-146">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="db96d-147">Para volver a implementar Teams para este usuario en un equipo determinado en el que se ha desinstalado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db96d-147">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="db96d-148">Desinstalar la aplicación de Teams instalada para todos los perfiles de usuario.</span><span class="sxs-lookup"><span data-stu-id="db96d-148">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="db96d-149">Después de la desinstalación, eliminar el directorio de forma recursiva en%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="db96d-149">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="db96d-150">Vuelva a implementar el paquete MSI en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="db96d-150">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="db96d-151">Puede usar nuestro script de limpieza de la [implementación de Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.</span><span class="sxs-lookup"><span data-stu-id="db96d-151">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="db96d-152">Deshabilitar el inicio automático para el instalador MSI</span><span class="sxs-lookup"><span data-stu-id="db96d-152">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="db96d-153">El comportamiento predeterminado del MSI es instalar el cliente de Teams en cuanto un usuario inicie sesión y, a continuación, inicie automáticamente Teams.</span><span class="sxs-lookup"><span data-stu-id="db96d-153">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="db96d-154">Puede modificar este comportamiento con los parámetros siguientes de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="db96d-154">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="db96d-155">Cuando un usuario inicia sesión en Windows, Teams se instalará con el MSI</span><span class="sxs-lookup"><span data-stu-id="db96d-155">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="db96d-156">Sin embargo, el cliente de Teams no se iniciará hasta que el usuario haya iniciado manualmente Teams</span><span class="sxs-lookup"><span data-stu-id="db96d-156">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="db96d-157">Se agregará un acceso directo para iniciar Teams en el escritorio del usuario</span><span class="sxs-lookup"><span data-stu-id="db96d-157">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="db96d-158">Una vez que se inicia manualmente, Teams se inicia automáticamente cuando el usuario inicia sesión</span><span class="sxs-lookup"><span data-stu-id="db96d-158">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="db96d-159">Para la versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="db96d-159">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="db96d-160">Para la versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="db96d-160">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="db96d-161">Si ejecuta el MSI manualmente, asegúrese de ejecutarlo con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="db96d-161">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="db96d-162">Incluso si lo ejecuta como administrador, sin ejecutarlo con permisos elevados, el instalador no podrá configurar la opción para deshabilitar el inicio automático.</span><span class="sxs-lookup"><span data-stu-id="db96d-162">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
