---
title: Instalar Microsoft Teams con MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Los administradores pueden usar el MSI de Teams para implementar Microsoft Teams en bloque y poder seleccionar usuarios o equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7aaf355c1f1fc65855c7bffb7c5632929a084b88
ms.sourcegitcommit: 3a7d2131717327d9b2d16848758e31e10326a0bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "24057606"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="929bf-103">Instalar Microsoft Teams con MSI</span><span class="sxs-lookup"><span data-stu-id="929bf-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="929bf-104">Para usar System Center Configuration Manager, o directiva de grupo o los mecanismos de distribución de terceros para amplia implementación, Microsoft ha proporcionado archivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) y [64 bits](https://aka.ms/teams64bitmsi)) que los administradores pueden utilizar para la implementación de forma masiva de los equipos para seleccionar los usuarios o equipos.</span><span class="sxs-lookup"><span data-stu-id="929bf-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="929bf-105">Los administradores pueden utilizar estos archivos para implementar de forma remota los equipos para que los usuarios no tienen que descargar manualmente la aplicación de los equipos.</span><span class="sxs-lookup"><span data-stu-id="929bf-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="929bf-106">Cuando se implementa, los equipos automáticamente inicio para todos los usuarios que inician una sesión en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="929bf-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="929bf-107">(Puede deshabilitar el inicio automático después de instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="929bf-107">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="929bf-108">[Vea más adelante](#disable-auto-lanuch-for-the-msi-installer)). Se recomienda que implemente el paquete en el equipo, por lo que todos los nuevos usuarios de la máquina también se beneficiarán de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="929bf-108">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="929bf-109">Para obtener más información acerca de SCCM, vea [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="929bf-109">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="929bf-110">Procedimiento de implementación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="929bf-110">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="929bf-111">Recuperar el último paquete.</span><span class="sxs-lookup"><span data-stu-id="929bf-111">Retrieve the latest package.</span></span>
2. <span data-ttu-id="929bf-112">Use los valores predeterminados que se rellena automáticamente por el archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="929bf-112">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="929bf-113">Implementar en equipos cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="929bf-113">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="929bf-114">Cómo funciona el paquete MSI de los equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="929bf-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="929bf-115">El archivo MSI de los equipos colocará a un instalador en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="929bf-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="929bf-116">Cada vez que un usuario firma en un nuevo perfil de usuario de Windows, se iniciará el programa de instalación y una copia de la aplicación de los equipos que se va a instalar en la carpeta appdata de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="929bf-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="929bf-117">Si un usuario ya tiene la aplicación de los equipos instalada en la carpeta appdata, el instalador MSI omitirá el proceso de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="929bf-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="929bf-118">No use el archivo MSI para implementar actualizaciones, debido a que el cliente se actualización automática cuando se detecta que una nueva versión está disponible desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="929bf-118">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="929bf-119">Para volver a implementar el programa de instalación más reciente usar el proceso de reimplementación de MSI se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="929bf-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="929bf-120">Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente siempre que sea posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="929bf-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="929bf-121">Si se implementa una versión muy antigua, el archivo MSI activará una actualización de la aplicación antes de que el usuario se pueden utilizar los equipos.</span><span class="sxs-lookup"><span data-stu-id="929bf-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="929bf-122">No recomendamos que cambiar las ubicaciones de instalación predeterminadas, como esto podría interrumpir el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="929bf-122">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="929bf-123">Tener una versión demasiado antigua finalmente se bloquearán a los usuarios acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="929bf-123">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="929bf-124">Requisitos del equipo de destino</span><span class="sxs-lookup"><span data-stu-id="929bf-124">Target computer requirements</span></span>

- <span data-ttu-id="929bf-125">.NET framework 4.5 o posterior</span><span class="sxs-lookup"><span data-stu-id="929bf-125">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="929bf-126">Windows 7 o posterior</span><span class="sxs-lookup"><span data-stu-id="929bf-126">Windows 7 or later</span></span>
- <span data-ttu-id="929bf-127">3 GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="929bf-127">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="929bf-128">Limpieza y procedimiento de reimplementación</span><span class="sxs-lookup"><span data-stu-id="929bf-128">Clean up and redeployment procedure</span></span>
<span data-ttu-id="929bf-129">Si un usuario desinstala los equipos de su perfil de usuario, el instalador MSI realizará el seguimiento que el usuario ha desinstalado la aplicación de los equipos y ya no instalar los equipos para ese perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="929bf-129">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="929bf-130">Para volver a implementar los equipos de este usuario en un equipo concreto donde se ha desinstalado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="929bf-130">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="929bf-131">Desinstalar la aplicación de los equipos instalados para cada perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="929bf-131">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="929bf-132">Después de la desinstalación, eliminar directorios de forma recursiva en % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="929bf-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="929bf-133">Vuelva a implementar el paquete MSI en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="929bf-133">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="929bf-134">Puede usar nuestra secuencia de comandos de [limpieza de implementación de equipos de Microsoft](.\scripts\Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.</span><span class="sxs-lookup"><span data-stu-id="929bf-134">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>  
                    
## <a name="disable-auto-lanuch-for-the-msi-installer"></a><span data-ttu-id="929bf-135">Deshabilitar lanuch automático para el instalador MSI</span><span class="sxs-lookup"><span data-stu-id="929bf-135">Disable auto lanuch for the MSI installer</span></span>

<span data-ttu-id="929bf-136">Si desea deshabilitar el inicio automático, escriba el siguiente símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="929bf-136">If you want to disable auto launch, enter the following command prompt:</span></span>

`msiexec /i Teams_windows.exe OPTIONS="noAutoStart=false"`

