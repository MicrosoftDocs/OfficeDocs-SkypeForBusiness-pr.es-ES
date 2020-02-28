---
title: Instalar Microsoft Teams mediante MSI mediante el administrador de configuración de Microsoft Endpoint
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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c048e321241f4403fbb69f71e56b3fc179346951
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327832"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="b307d-103">Instalar Microsoft Teams mediante el administrador de configuración de Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="b307d-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="b307d-104">Vea la siguiente sesión para obtener información sobre las ventajas del cliente de escritorio de Windows, cómo se planea y cómo se implementa: [Teams cliente de escritorio de Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="b307d-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="b307d-105">Para usar Microsoft Endpoint Configuration Manager, una directiva de grupo o cualquier mecanismo de distribución de terceros para una implementación ampliada, Microsoft ha proporcionado archivos MSI (tanto de 32 bits como de 64 bits) que los administradores pueden usar para la implementación masiva de equipos con el fin de seleccionar usuarios o equipo.</span><span class="sxs-lookup"><span data-stu-id="b307d-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="b307d-106">Los administradores pueden usar estos archivos para implementar equipos de forma remota, de modo que los usuarios no tengan que descargar manualmente la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="b307d-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="b307d-107">Cuando se implementa, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="b307d-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="b307d-108">(Puede deshabilitar el inicio automático después de instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b307d-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="b307d-109">[Consulte a continuación](#disable-auto-launch-for-the-msi-installer)). Le recomendamos que implemente el paquete en el equipo, de modo que todos los nuevos usuarios del equipo también se beneficien de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="b307d-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="b307d-110">Estos son los vínculos a los archivos MSI:</span><span class="sxs-lookup"><span data-stu-id="b307d-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="b307d-111">Entidad</span><span class="sxs-lookup"><span data-stu-id="b307d-111">Entity</span></span>  |<span data-ttu-id="b307d-112">32 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-112">32 bit</span></span>      |<span data-ttu-id="b307d-113">64 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="b307d-114">Publicidad</span><span class="sxs-lookup"><span data-stu-id="b307d-114">Commercial</span></span>     | [<span data-ttu-id="b307d-115">32 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="b307d-116">64 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="b307d-117">Gobierno federal-GCC</span><span class="sxs-lookup"><span data-stu-id="b307d-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="b307d-118">32 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="b307d-119">64 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="b307d-120">Gobierno Federal: GCC High</span><span class="sxs-lookup"><span data-stu-id="b307d-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="b307d-121">32 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="b307d-122">64 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="b307d-123">Gobierno Federal: DoD</span><span class="sxs-lookup"><span data-stu-id="b307d-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="b307d-124">32 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="b307d-125">64 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="b307d-126">Los equipos también pueden incluirse con una implementación de Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="b307d-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="b307d-127">Para obtener más información, consulte [implementar Microsoft Teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="b307d-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="b307d-128">Para obtener más información sobre Microsoft Endpoint Configuration Manager, vea [¿Qué es Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="b307d-128">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="b307d-129">Procedimiento de implementación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="b307d-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="b307d-130">Recuperar el paquete más reciente.</span><span class="sxs-lookup"><span data-stu-id="b307d-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="b307d-131">Use los valores predeterminados rellenados previamente por el MSI.</span><span class="sxs-lookup"><span data-stu-id="b307d-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="b307d-132">Implementar en equipos siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="b307d-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="b307d-133">Cómo funciona el paquete MSI de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b307d-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="b307d-134">Instalación de PC</span><span class="sxs-lookup"><span data-stu-id="b307d-134">PC installation</span></span>

<span data-ttu-id="b307d-135">El MSI de Teams colocará un instalador en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="b307d-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="b307d-136">Cada vez que un usuario inicie sesión en un nuevo perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación `AppData` de Teams en la carpeta del usuario.</span><span class="sxs-lookup"><span data-stu-id="b307d-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="b307d-137">Si un usuario ya tiene la aplicación Teams instalada en `AppData` la carpeta, el instalador MSI omitirá el proceso para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="b307d-137">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="b307d-138">No use el MSI para implementar actualizaciones, ya que el cliente se actualizará automáticamente cuando detecte que hay una nueva versión disponible en el servicio.</span><span class="sxs-lookup"><span data-stu-id="b307d-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="b307d-139">Para volver a implementar el último instalador, use el proceso de reimplementación de MSI que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="b307d-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="b307d-140">Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente (excepto en entornos de VDI) cuando sea posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b307d-140">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="b307d-141">Si se implementa una versión muy antigua, el MSI desencadenará una actualización de la aplicación antes de que el usuario pueda usar Teams.</span><span class="sxs-lookup"><span data-stu-id="b307d-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="b307d-142">No recomendamos que cambie las ubicaciones de instalación predeterminadas, ya que esto podría interrumpir el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="b307d-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="b307d-143">Tener una versión demasiado antigua impedirá que los usuarios tengan acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="b307d-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="b307d-144">Requisitos del equipo de destino</span><span class="sxs-lookup"><span data-stu-id="b307d-144">Target computer requirements</span></span>

- <span data-ttu-id="b307d-145">.NET Framework 4,5 o posterior</span><span class="sxs-lookup"><span data-stu-id="b307d-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="b307d-146">Windows 8,1 o posterior</span><span class="sxs-lookup"><span data-stu-id="b307d-146">Windows 8.1 or later</span></span>
- <span data-ttu-id="b307d-147">Windows Server 2012 R2 o posterior</span><span class="sxs-lookup"><span data-stu-id="b307d-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="b307d-148">3 GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="b307d-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="b307d-149">Instalación de VDI</span><span class="sxs-lookup"><span data-stu-id="b307d-149">VDI installation</span></span>

<span data-ttu-id="b307d-150">Para obtener instrucciones completas sobre cómo implementar la aplicación de escritorio de Teams en VDI, vea [Teams for virtualizated Desktop Infrastructure](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="b307d-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="b307d-151">Procedimiento de limpieza y reimplementación</span><span class="sxs-lookup"><span data-stu-id="b307d-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="b307d-152">Si un usuario desinstala equipos de su perfil de usuario, el instalador MSI realizará un seguimiento de que el usuario ha desinstalado la aplicación de Teams y ya no instalará Teams para ese perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="b307d-152">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="b307d-153">Para volver a implementar Teams para este usuario en un equipo determinado en el que se ha desinstalado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b307d-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="b307d-154">Desinstalar la aplicación de Teams instalada para todos los perfiles de usuario.</span><span class="sxs-lookup"><span data-stu-id="b307d-154">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="b307d-155">Después de la desinstalación, eliminar el directorio de `%localappdata%\Microsoft\Teams\`forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="b307d-155">After uninstall, delete directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="b307d-156">Vuelva a implementar el paquete MSI en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="b307d-156">Redeploy the MSI package to that particular computer.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="b307d-157">Impedir que los equipos se inicien automáticamente después de la instalación</span><span class="sxs-lookup"><span data-stu-id="b307d-157">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="b307d-158">El comportamiento predeterminado del MSI es instalar la aplicación de Teams en cuanto un usuario inicia sesión y, a continuación, iniciar automáticamente Teams.</span><span class="sxs-lookup"><span data-stu-id="b307d-158">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="b307d-159">Si no quiere que los usuarios se inicien automáticamente para los usuarios después de la instalación, puede usar la Directiva de grupo para establecer una configuración de directiva o deshabilitar el inicio automático para el instalador MSI.</span><span class="sxs-lookup"><span data-stu-id="b307d-159">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

#### <a name="use-group-policy-recommended"></a><span data-ttu-id="b307d-160">Usar la Directiva de grupo (recomendado)</span><span class="sxs-lookup"><span data-stu-id="b307d-160">Use Group Policy (recommended)</span></span>

<span data-ttu-id="b307d-161">Habilite la opción **impedir que Microsoft Teams se inicie automáticamente después de la instalación** .</span><span class="sxs-lookup"><span data-stu-id="b307d-161">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="b307d-162">Puede encontrar esta configuración de directiva en Usuario\directivas\plantillas Administrativas\microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b307d-162">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="b307d-163">Este es el método recomendado porque puede desactivar o activar la configuración de directiva según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="b307d-163">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="b307d-164">Al habilitar esta configuración de Directiva antes de instalar Teams, Teams no se inicia automáticamente cuando los usuarios inician sesión en Windows.</span><span class="sxs-lookup"><span data-stu-id="b307d-164">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="b307d-165">Después de que un usuario inicia sesión en Teams por primera vez, Teams se inicia automáticamente la próxima vez que el usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="b307d-165">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="b307d-166">Para obtener más información, vea [usar la Directiva de grupo para evitar que los equipos se inicien automáticamente después de la instalación](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span><span class="sxs-lookup"><span data-stu-id="b307d-166">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="b307d-167">Si ya ha implementado Teams y desea configurar esta directiva para deshabilitar la función AutoStart de Teams, primero establezca la configuración de directiva de grupo en el valor que desee y, a continuación, ejecute el [script de restablecimiento de equipos de AutoStart](scripts/powershell-script-teams-reset-autostart.md) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="b307d-167">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="b307d-168">Deshabilitar el inicio automático para el instalador MSI</span><span class="sxs-lookup"><span data-stu-id="b307d-168">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="b307d-169">Puede deshabilitar el inicio automático para el instalador MSI mediante el parámetro **Options = "noautostart = true"** de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="b307d-169">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="b307d-170">Para la versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-170">For the 32-bit version</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="b307d-171">Para la versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="b307d-171">For the 64-bit version</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="b307d-172">Cuando un usuario inicia sesión en Windows, Teams se instala con el MSI y se agrega un acceso directo a iniciar Teams en el escritorio del usuario.</span><span class="sxs-lookup"><span data-stu-id="b307d-172">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="b307d-173">Los equipos no se iniciarán hasta que el usuario inicie manualmente Teams.</span><span class="sxs-lookup"><span data-stu-id="b307d-173">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="b307d-174">Una vez que el usuario inicia manualmente Teams, Teams se inicia automáticamente cada vez que el usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="b307d-174">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

> [!Note]
> <span data-ttu-id="b307d-175">Si ejecuta el MSI manualmente, asegúrese de ejecutarlo con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="b307d-175">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="b307d-176">Incluso si lo ejecuta como administrador, sin ejecutarlo con permisos elevados, el instalador no podrá configurar la opción para deshabilitar el inicio automático.</span><span class="sxs-lookup"><span data-stu-id="b307d-176">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
