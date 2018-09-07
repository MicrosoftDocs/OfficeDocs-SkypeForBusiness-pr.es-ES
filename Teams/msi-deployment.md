---
title: Instalar Teams Microsoft con MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Los administradores pueden utilizar el MSI de los equipos de forma masiva implementar Microsoft Teams para seleccionar usuarios o equipos.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7176b990c41f2792f0955ac3ca2e937632a707d7
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854144"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="2d42f-103">Instalar Teams Microsoft con MSI</span><span class="sxs-lookup"><span data-stu-id="2d42f-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="2d42f-104">Para usar System Center Configuration Manager, o directiva de grupo o los mecanismos de distribución de terceros para amplia implementación, Microsoft ha proporcionado archivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) y [64 bits](https://aka.ms/teams64bitmsi)) que los administradores pueden utilizar para la implementación de forma masiva de los equipos para seleccionar los usuarios o equipos.</span><span class="sxs-lookup"><span data-stu-id="2d42f-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="2d42f-105">Los administradores pueden utilizar estos archivos para implementar de forma remota los equipos para que los usuarios no tienen que descargar manualmente la aplicación de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2d42f-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="2d42f-106">Cuando se implementa, los equipos automáticamente inicio para todos los usuarios que inician una sesión en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="2d42f-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="2d42f-107">Se recomienda que implemente el paquete en el equipo, por lo que todos los nuevos usuarios de la máquina también se beneficiarán de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="2d42f-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="2d42f-108">Para obtener más información acerca de SCCM, vea [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="2d42f-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="2d42f-109">Procedimiento de implementación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="2d42f-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="2d42f-110">Recuperar el último paquete.</span><span class="sxs-lookup"><span data-stu-id="2d42f-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="2d42f-111">Use los valores predeterminados que se rellena automáticamente por el archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="2d42f-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="2d42f-112">Implementar en equipos cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="2d42f-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="2d42f-113">Cómo funciona el paquete MSI de los equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d42f-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="2d42f-114">El archivo MSI de los equipos colocará a un instalador en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="2d42f-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="2d42f-115">Cada vez que un usuario firma en un nuevo perfil de usuario de Windows, se iniciará el programa de instalación y una copia de la aplicación de los equipos que se va a instalar en la carpeta appdata de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="2d42f-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="2d42f-116">Si un usuario ya tiene la aplicación de los equipos instalada en la carpeta appdata, el instalador MSI omitirá el proceso de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="2d42f-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="2d42f-117">No use el archivo MSI para implementar actualizaciones, debido a que el cliente se actualización automática cuando se detecta que una nueva versión está disponible desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="2d42f-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="2d42f-118">Para volver a implementar el programa de instalación más reciente usar el proceso de reimplementación de MSI se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="2d42f-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="2d42f-119">Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente siempre que sea posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="2d42f-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="2d42f-120">Si se implementa una versión muy antigua, el archivo MSI activará una actualización de la aplicación antes de que el usuario se pueden utilizar los equipos.</span><span class="sxs-lookup"><span data-stu-id="2d42f-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="2d42f-121">No recomendamos que cambiar las ubicaciones de instalación predeterminadas, como esto podría interrumpir el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="2d42f-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="2d42f-122">Tener una versión demasiado antigua finalmente se bloquearán a los usuarios acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="2d42f-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="2d42f-123">Requisitos del equipo de destino</span><span class="sxs-lookup"><span data-stu-id="2d42f-123">Target computer requirements</span></span>

- <span data-ttu-id="2d42f-124">.NET framework 4.5 o posterior</span><span class="sxs-lookup"><span data-stu-id="2d42f-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="2d42f-125">Windows 7 o posterior</span><span class="sxs-lookup"><span data-stu-id="2d42f-125">Windows 7 or later</span></span>
- <span data-ttu-id="2d42f-126">3 GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="2d42f-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="2d42f-127">Limpieza y procedimiento de reimplementación</span><span class="sxs-lookup"><span data-stu-id="2d42f-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="2d42f-128">Si un usuario desinstala los equipos de su perfil de usuario, el instalador MSI realizará el seguimiento que el usuario ha desinstalado la aplicación de los equipos y ya no instalar los equipos para ese perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="2d42f-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="2d42f-129">Para volver a implementar los equipos de este usuario en un equipo concreto donde se ha desinstalado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d42f-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="2d42f-130">Desinstalar la aplicación de los equipos instalados para cada perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="2d42f-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="2d42f-131">Después de la desinstalación, eliminar directorios de forma recursiva en % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="2d42f-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="2d42f-132">Vuelva a implementar el paquete MSI en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="2d42f-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="2d42f-133">Puede usar nuestra secuencia de comandos de [limpieza de implementación de equipos de Microsoft](.\scripts\Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.</span><span class="sxs-lookup"><span data-stu-id="2d42f-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

