---
title: Instalar Microsoft Teams que usan MSI
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Los administradores pueden utilizar el MSI de equipos a granel implementar Microsoft Teams para seleccionar usuarios o equipos.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="e79af-103">Instalar Microsoft Teams que usan MSI</span><span class="sxs-lookup"><span data-stu-id="e79af-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="e79af-104">Para aprovechar de System Center Configuration Manager, o directiva de grupo o cualquier mecanismos de distribución parte 3ª de amplia distribución, Microsoft ha proporcionado archivos MSI ( [32-bit](http://aka.ms/teams32bitmsi) y [64-bit](http://aka.ms/teams64bitmsi)) para los administradores aprovechar durante la implementación masiva de Teams de Microsoft para seleccionar los usuarios o equipos.</span><span class="sxs-lookup"><span data-stu-id="e79af-104">To leverage System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) for admins to leverage during bulk deployment of Microsoft Teams to select users or machines.</span></span> <span data-ttu-id="e79af-105">Administradores pueden utilizar estos archivos para desplegar de forma remota los equipos para que los usuarios no tienen que descargar manualmente los equipos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e79af-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="e79af-106">Cuando se implementa, equipos auto inicio para todos los usuarios iniciar sesión en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e79af-106">When deployed, Teams will auto launch for all users who sign-in on that machine.</span></span> <span data-ttu-id="e79af-107">Se recomienda implementar el paquete en el equipo, por lo que todos los usuarios nuevos a las máquinas también se beneficiarán de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="e79af-107">It is recommended that you deploy the package to the machine, so all new users to the machines will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="e79af-108">Para obtener más información acerca de SCCM, consulte.</span><span class="sxs-lookup"><span data-stu-id="e79af-108">To learn more about SCCM, see.</span></span> [<span data-ttu-id="e79af-109">Introducción a System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e79af-109">Introduction to System Center Configuration Manager</span></span>](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a><span data-ttu-id="e79af-110">Procedimiento de implementación (recomendaciones)</span><span class="sxs-lookup"><span data-stu-id="e79af-110">Deployment Procedure (Recommendations)</span></span>
1. <span data-ttu-id="e79af-111">Recuperar el paquete más reciente</span><span class="sxs-lookup"><span data-stu-id="e79af-111">Retrieve the latest package</span></span>
2. <span data-ttu-id="e79af-112">Utilice los valores predeterminados rellenadas previamente por MSI</span><span class="sxs-lookup"><span data-stu-id="e79af-112">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="e79af-113">Implementar en equipos cuando sea posible</span><span class="sxs-lookup"><span data-stu-id="e79af-113">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="e79af-114">Cómo funciona el paquete MSI de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e79af-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="e79af-115">El MSI de equipos colocará a un instalador en archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="e79af-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="e79af-116">Cada vez que un usuario cierre la sesión en un perfil de usuario de Windows, se iniciará el instalador y una copia de la aplicación de los equipos se instalarán en la carpeta de appdata del usuario.</span><span class="sxs-lookup"><span data-stu-id="e79af-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="e79af-117">Si un usuario ya ha instalado en la carpeta appdata de la aplicación de los equipos, el instalador MSI omitirá el proceso para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="e79af-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="e79af-118">No aprovechan el MSI para implementar actualizaciones, el cliente se actualización automática cuando se detecta que una nueva versión está disponible en el servicio.</span><span class="sxs-lookup"><span data-stu-id="e79af-118">Do not leverage the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="e79af-119">Para volver a implementar el programa de instalación más reciente utilice el proceso de reimplementación de MSI que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="e79af-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="e79af-120">Si implementa una versión anterior del paquete de MSI, el cliente se actualizará automáticamente siempre que sea posible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="e79af-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="e79af-121">Si se implementa una versión muy antigua, el archivo MSI activará una actualización de la aplicación antes de que el usuario es capaz de utilizar los equipos.</span><span class="sxs-lookup"><span data-stu-id="e79af-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="e79af-122">No se recomienda que cambiar las ubicaciones de instalación como esto podría interrumpir el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="e79af-122">It's not recommended you change any install locations as this could break the update flow.</span></span> <span data-ttu-id="e79af-123">Que, a continuación, eventualmente bloqueará los usuarios tengan acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="e79af-123">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="e79af-124">Requisitos del equipo de destino:</span><span class="sxs-lookup"><span data-stu-id="e79af-124">Target machine requirements:</span></span>

1. <span data-ttu-id="e79af-125">.NET framework 4.5 o posterior</span><span class="sxs-lookup"><span data-stu-id="e79af-125">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="e79af-126">Windows 7 o posterior</span><span class="sxs-lookup"><span data-stu-id="e79af-126">Windows 7 or later</span></span>
2. <span data-ttu-id="e79af-127">32GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="e79af-127">32GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-upredeployment-procedure"></a><span data-ttu-id="e79af-128">Procedimiento de limpieza up\redeployment</span><span class="sxs-lookup"><span data-stu-id="e79af-128">Clean up\redeployment Procedure</span></span>
<span data-ttu-id="e79af-129">Si un usuario desinstala los equipos de su perfil de usuario, el instalador MSI realizará el seguimiento que el usuario ha desinstalado la aplicación de los equipos y ya no instalar equipos para dicho perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="e79af-129">If a user uninstalls Teams from for their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="e79af-130">Para volver a implementar los equipos para este usuario en un equipo concreto en el que fue había desinstalado necesitará:</span><span class="sxs-lookup"><span data-stu-id="e79af-130">To redeploy Teams for this user on a particular machine where it was uninstalled you will need to:</span></span>

1. <span data-ttu-id="e79af-131">Desinstalar la aplicación de los equipos instalados para cada perfil de usuario</span><span class="sxs-lookup"><span data-stu-id="e79af-131">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="e79af-132">Después de la desinstalación, elimine los directorios de forma recursiva en %localappdata%\Microsoft\Teams\\</span><span class="sxs-lookup"><span data-stu-id="e79af-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="e79af-133">Implementar el paquete MSI a ese equipo</span><span class="sxs-lookup"><span data-stu-id="e79af-133">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="e79af-134">Puede aprovechar nuestra secuencia de comandos de [limpiar la implementación de equipos de Microsoft](.\scripts\Powershell-script-teams-deployment-clean-up.md) para llevar a cabo estos pasos 1 y 2 a través de SCCM.</span><span class="sxs-lookup"><span data-stu-id="e79af-134">You can leverage our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish this steps 1 and 2 via SCCM.</span></span>                                

