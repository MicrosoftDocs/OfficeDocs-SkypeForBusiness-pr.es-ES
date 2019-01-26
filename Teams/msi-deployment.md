---
title: Instalar Teams Microsoft con MSI a través de SCCM
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Los administradores pueden usar el MSI de Teams para implementar Microsoft Teams en bloque y poder seleccionar usuarios o equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad0564d491302ae6b934cca1ae8501329951d9fd
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562592"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="2c9f7-103">Instalar Microsoft Teams con MSI</span><span class="sxs-lookup"><span data-stu-id="2c9f7-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="2c9f7-104">Vea la sesión para obtener más información acerca de las ventajas del cliente de escritorio de Windows, cómo planear para él y cómo implementarlo siguiente: [Los equipos cliente de escritorio de Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="2c9f7-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="2c9f7-105">Para usar System Center Configuration Manager, o directiva de grupo o los mecanismos de distribución de terceros para amplia implementación, Microsoft ha proporcionado archivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) y [64 bits](https://aka.ms/teams64bitmsi)) que los administradores pueden utilizar para la implementación de forma masiva de los equipos para seleccionar los usuarios o equipos.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="2c9f7-106">Los administradores pueden utilizar estos archivos para implementar de forma remota los equipos para que los usuarios no tienen que descargar manualmente la aplicación de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="2c9f7-107">Cuando se implementa, los equipos automáticamente inicio para todos los usuarios que inician una sesión en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="2c9f7-108">(Puede deshabilitar el inicio automático después de instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="2c9f7-109">[Vea más adelante](#disable-auto-lanuch-for-the-msi-installer)). Se recomienda que implemente el paquete en el equipo, por lo que todos los nuevos usuarios de la máquina también se beneficiarán de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-109">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="2c9f7-110">Para obtener más información acerca de SCCM, vea [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="2c9f7-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="2c9f7-111">Procedimiento de implementación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="2c9f7-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="2c9f7-112">Recuperar el último paquete.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="2c9f7-113">Use los valores predeterminados que se rellena automáticamente por el archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="2c9f7-114">Implementar en equipos cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="2c9f7-115">Cómo funciona el paquete MSI de los equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c9f7-115">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="2c9f7-116">El archivo MSI de los equipos colocará a un instalador en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-116">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="2c9f7-117">Cada vez que un usuario firma en un nuevo perfil de usuario de Windows, se iniciará el programa de instalación y una copia de la aplicación de los equipos que se va a instalar en la carpeta appdata de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-117">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="2c9f7-118">Si un usuario ya tiene la aplicación de los equipos instalada en la carpeta appdata, el instalador MSI omitirá el proceso de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-118">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="2c9f7-119">No use el archivo MSI para implementar actualizaciones, debido a que el cliente se actualización automática cuando se detecta que una nueva versión está disponible desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-119">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="2c9f7-120">Para volver a implementar el programa de instalación más reciente usar el proceso de reimplementación de MSI se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-120">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="2c9f7-121">Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente siempre que sea posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-121"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="2c9f7-122">Si se implementa una versión muy antigua, el archivo MSI activará una actualización de la aplicación antes de que el usuario se pueden utilizar los equipos.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-122">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="2c9f7-123">No recomendamos que cambiar las ubicaciones de instalación predeterminadas, como esto podría interrumpir el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-123">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="2c9f7-124">Tener una versión demasiado antigua finalmente se bloquearán a los usuarios acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-124">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="2c9f7-125">Requisitos del equipo de destino</span><span class="sxs-lookup"><span data-stu-id="2c9f7-125">Target computer requirements</span></span>

- <span data-ttu-id="2c9f7-126">.NET framework 4.5 o posterior</span><span class="sxs-lookup"><span data-stu-id="2c9f7-126">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="2c9f7-127">Windows 7 o posterior</span><span class="sxs-lookup"><span data-stu-id="2c9f7-127">Windows 7 or later</span></span>
- <span data-ttu-id="2c9f7-128">3 GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="2c9f7-128">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="2c9f7-129">Limpieza y procedimiento de reimplementación</span><span class="sxs-lookup"><span data-stu-id="2c9f7-129">Clean up and redeployment procedure</span></span>
<span data-ttu-id="2c9f7-130">Si un usuario desinstala los equipos de su perfil de usuario, el instalador MSI realizará el seguimiento que el usuario ha desinstalado la aplicación de los equipos y ya no instalar los equipos para ese perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-130">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="2c9f7-131">Para volver a implementar los equipos de este usuario en un equipo concreto donde se ha desinstalado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9f7-131">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="2c9f7-132">Desinstalar la aplicación de los equipos instalados para cada perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-132">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="2c9f7-133">Después de la desinstalación, eliminar directorios de forma recursiva en % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-133">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="2c9f7-134">Vuelva a implementar el paquete MSI en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-134">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="2c9f7-135">Puede usar nuestra secuencia de comandos de [limpieza de implementación de equipos de Microsoft](scripts/Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-135">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>    
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="2c9f7-136">Deshabilitar el inicio automático para el instalador MSI</span><span class="sxs-lookup"><span data-stu-id="2c9f7-136">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="2c9f7-137">Comportamiento predeterminado de MSI es instalar al cliente de los equipos tan pronto como un usuario inicia sesión y, a continuación, iniciar automáticamente los equipos.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-137">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="2c9f7-138">Puede modificar este comportamiento con los parámetros debajo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2c9f7-138">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="2c9f7-139">Cuando un usuario inicia sesión en Windows, los equipos se instalará con el archivo MSI</span><span class="sxs-lookup"><span data-stu-id="2c9f7-139">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="2c9f7-140">Sin embargo, no se iniciará el cliente de los equipos hasta que el usuario ha iniciado los equipos manualmente</span><span class="sxs-lookup"><span data-stu-id="2c9f7-140">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="2c9f7-141">Se agregará un acceso directo para iniciar los equipos en el escritorio del usuario</span><span class="sxs-lookup"><span data-stu-id="2c9f7-141">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="2c9f7-142">Una vez que se inicie manualmente, los equipos se inicio automático cada vez que el usuario inicia sesión</span><span class="sxs-lookup"><span data-stu-id="2c9f7-142">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="2c9f7-143">Para la versión de 32 bits</span><span class="sxs-lookup"><span data-stu-id="2c9f7-143">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="2c9f7-144">Para la versión de 64 bits</span><span class="sxs-lookup"><span data-stu-id="2c9f7-144">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```
> [!Note] 
>  <span data-ttu-id="2c9f7-145">Si se ejecuta el archivo MSI manualmente, asegúrese de ejecutar con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-145">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="2c9f7-146">Incluso si se ejecuta como un administrador, sin ejecutar con permisos elevados, el programa de instalación no podrá configurar la opción para deshabilitar el inicio automático.</span><span class="sxs-lookup"><span data-stu-id="2c9f7-146">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
