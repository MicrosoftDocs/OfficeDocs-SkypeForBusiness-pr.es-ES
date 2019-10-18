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
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567963"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="8ef7a-103">Instalar Microsoft Teams con MSI</span><span class="sxs-lookup"><span data-stu-id="8ef7a-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="8ef7a-104">Vea la siguiente sesión para obtener información sobre las ventajas del cliente de escritorio de Windows, cómo se planea y cómo se implementa: [Teams cliente de escritorio de Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="8ef7a-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="8ef7a-105">Para usar System Center Configuration Manager, una directiva de grupo o cualquier mecanismo de distribución de terceros para una implementación ampliada, Microsoft ha proporcionado archivos MSI (tanto [de 32](https://aka.ms/teams32bitmsi) bits como de [64](https://aka.ms/teams64bitmsi)bits) que los administradores pueden usar para la implementación masiva de equipos para seleccionar usuarios o equipos.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="8ef7a-106">Los administradores pueden usar estos archivos para implementar equipos de forma remota, de modo que los usuarios no tengan que descargar manualmente la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="8ef7a-107">Cuando se implementa, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="8ef7a-108">(Puede deshabilitar el inicio automático después de instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="8ef7a-109">[Consulte a continuación](#disable-auto-launch-for-the-msi-installer)). Le recomendamos que implemente el paquete en el equipo, de modo que todos los nuevos usuarios del equipo también se beneficien de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="8ef7a-110">Los equipos también pueden incluirse con una implementación de Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="8ef7a-111">Para obtener más información, consulte [implementar Microsoft Teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="8ef7a-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="8ef7a-112">Para obtener más información sobre SCCM, consulte [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="8ef7a-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="8ef7a-113">Procedimiento de implementación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="8ef7a-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="8ef7a-114">Recuperar el paquete más reciente.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="8ef7a-115">Use los valores predeterminados rellenados previamente por el MSI.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="8ef7a-116">Implementar en equipos siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="8ef7a-117">Cómo funciona el paquete MSI de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ef7a-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="8ef7a-118">Instalación de PC</span><span class="sxs-lookup"><span data-stu-id="8ef7a-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="8ef7a-119">Vea [instalación de VDI](#vdi-installation) para obtener instrucciones sobre cómo implementar Teams en un entorno de DesktopInfrastructure virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="8ef7a-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="8ef7a-120">El MSI de Teams colocará un instalador en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="8ef7a-121">Cada vez que un usuario inicie sesión en un nuevo perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación de Teams en la carpeta appdata del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="8ef7a-122">Si un usuario ya tiene la aplicación de Teams instalada en la carpeta appdata, el instalador MSI omitirá el proceso para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="8ef7a-123">No use el MSI para implementar actualizaciones, ya que el cliente se actualizará automáticamente cuando detecte que hay una nueva versión disponible en el servicio.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="8ef7a-124">Para volver a implementar el último instalador, use el proceso de reimplementación de MSI que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="8ef7a-125">Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente (excepto en entornos de VDI) cuando sea posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="8ef7a-126">Si se implementa una versión muy antigua, el MSI desencadenará una actualización de la aplicación antes de que el usuario pueda usar Teams.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="8ef7a-127">No recomendamos que cambie las ubicaciones de instalación predeterminadas, ya que esto podría interrumpir el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="8ef7a-128">Tener una versión demasiado antigua impedirá que los usuarios tengan acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="8ef7a-129">Requisitos del equipo de destino</span><span class="sxs-lookup"><span data-stu-id="8ef7a-129">Target computer requirements</span></span>

- <span data-ttu-id="8ef7a-130">.NET Framework 4,5 o posterior</span><span class="sxs-lookup"><span data-stu-id="8ef7a-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="8ef7a-131">Windows 7 o posterior</span><span class="sxs-lookup"><span data-stu-id="8ef7a-131">Windows 7 or later</span></span>
- <span data-ttu-id="8ef7a-132">3 GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="8ef7a-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="8ef7a-133">Instalación de VDI</span><span class="sxs-lookup"><span data-stu-id="8ef7a-133">VDI installation</span></span>

<span data-ttu-id="8ef7a-134">Este es el proceso para implementar la aplicación de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="8ef7a-135">Para obtener instrucciones detalladas, vea [Teams para infraestructura de escritorio virtualizada](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="8ef7a-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="8ef7a-136">Descargue el paquete de MSI de Teams con uno de los siguientes vínculos en función del entorno.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="8ef7a-137">Recomendamos la versión de 64 bits para una VM VDI con un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="8ef7a-138">versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="8ef7a-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="8ef7a-139">versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="8ef7a-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="8ef7a-140">Ejecute el siguiente comando para instalar el MSI en la máquina virtual de VDI (o actualizarlo).</span><span class="sxs-lookup"><span data-stu-id="8ef7a-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="8ef7a-141">Instala Teams en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="8ef7a-142">En este momento, la configuración de la imagen de oro está completa.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="8ef7a-143">La siguiente sesión de inicio de sesión interactivo inicia Teams y solicita las credenciales.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="8ef7a-144">Tenga en cuenta que no es posible deshabilitar el inicio automático de equipos al instalar Teams en VDI mediante la propiedad ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="8ef7a-145">Ejecute el siguiente comando para desinstalar el MSI de la máquina virtual de VDI (o prepararse para actualizarlo).</span><span class="sxs-lookup"><span data-stu-id="8ef7a-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="8ef7a-146">Esto desinstalará Teams de archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="8ef7a-147">Procedimiento de limpieza y reimplementación</span><span class="sxs-lookup"><span data-stu-id="8ef7a-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="8ef7a-148">Si un usuario desinstala equipos de su perfil de usuario, el instalador MSI realizará un seguimiento de que el usuario ha desinstalado la aplicación de Teams y ya no instalará Teams para ese perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="8ef7a-149">Para volver a implementar Teams para este usuario en un equipo determinado en el que se ha desinstalado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ef7a-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="8ef7a-150">Desinstalar la aplicación de Teams instalada para todos los perfiles de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="8ef7a-151">Después de la desinstalación, eliminar el directorio de forma recursiva en%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="8ef7a-152">Vuelva a implementar el paquete MSI en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="8ef7a-153">Puede usar nuestro script de limpieza de la [implementación de Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="8ef7a-154">Deshabilitar el inicio automático para el instalador MSI</span><span class="sxs-lookup"><span data-stu-id="8ef7a-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="8ef7a-155">El comportamiento predeterminado del MSI es instalar el cliente de Teams en cuanto un usuario inicie sesión y, a continuación, inicie automáticamente Teams.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="8ef7a-156">Puede modificar este comportamiento con los parámetros siguientes de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8ef7a-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="8ef7a-157">Cuando un usuario inicia sesión en Windows, Teams se instalará con el MSI</span><span class="sxs-lookup"><span data-stu-id="8ef7a-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="8ef7a-158">Sin embargo, el cliente de Teams no se iniciará hasta que el usuario haya iniciado manualmente Teams</span><span class="sxs-lookup"><span data-stu-id="8ef7a-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="8ef7a-159">Se agregará un acceso directo para iniciar Teams en el escritorio del usuario</span><span class="sxs-lookup"><span data-stu-id="8ef7a-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="8ef7a-160">Una vez que se inicia manualmente, Teams se inicia automáticamente cuando el usuario inicia sesión</span><span class="sxs-lookup"><span data-stu-id="8ef7a-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="8ef7a-161">Para la versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="8ef7a-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="8ef7a-162">Para la versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="8ef7a-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="8ef7a-163">Si ejecuta el MSI manualmente, asegúrese de ejecutarlo con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="8ef7a-164">Incluso si lo ejecuta como administrador, sin ejecutarlo con permisos elevados, el instalador no podrá configurar la opción para deshabilitar el inicio automático.</span><span class="sxs-lookup"><span data-stu-id="8ef7a-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
