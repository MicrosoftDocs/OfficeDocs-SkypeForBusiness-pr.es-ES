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
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882041"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="c0f59-103">Instalar Microsoft Teams con MSI</span><span class="sxs-lookup"><span data-stu-id="c0f59-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="c0f59-104">Si prefiere usar System Center Configuration Manager, la directiva de grupos o cualquier otro mecanismo de distribución de terceros para llevar a cabo una implementación general, Microsoft ofrece archivos MSI (de [32 bits](https://aka.ms/teams32bitmsi) y [64 bits](https://aka.ms/teams64bitmsi)) que los administradores de Teams pueden usar para seleccionar usuarios u ordenadores.</span><span class="sxs-lookup"><span data-stu-id="c0f59-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="c0f59-105">Los administradores pueden usar estos archivos para implementar Teams de forma remota de manera que los usuarios no tengan que descargar manualmente la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="c0f59-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="c0f59-106">Una vez que la aplicación se haya implementado, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en esa máquina.</span><span class="sxs-lookup"><span data-stu-id="c0f59-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="c0f59-107">Le recomendamos que implemente el paquete en el equipo para que todos los usuarios nuevos de la máquina se beneficien también de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="c0f59-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="c0f59-108">Si desea saber más sobre SCCM, consulte [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="c0f59-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="c0f59-109">Procedimiento de implementación (recomendado)</span><span class="sxs-lookup"><span data-stu-id="c0f59-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="c0f59-110">Recupere el paquete más reciente.</span><span class="sxs-lookup"><span data-stu-id="c0f59-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="c0f59-111">Use los valores predeterminados que el MSI habrá rellenado previamente.</span><span class="sxs-lookup"><span data-stu-id="c0f59-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="c0f59-112">Realice la implementación en ordenadores siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="c0f59-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="c0f59-113">Cómo funciona el paquete MSI de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0f59-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="c0f59-114">El MSI de Teams colocará un programa de instalación en Archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="c0f59-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="c0f59-115">Cada vez que un usuario inicie sesión en un nuevo perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación de Teams en la carpeta AppData de ese usuario.</span><span class="sxs-lookup"><span data-stu-id="c0f59-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="c0f59-116">En el caso de que el usuario ya tenga esta aplicación instalada en esta carpeta, el instalador MSI omitirá el proceso para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="c0f59-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="c0f59-117">No use el MSI para implementar actualizaciones, puesto que el cliente se encargará de actualizar de forma automática cuando detecte una nueva versión del servicio.</span><span class="sxs-lookup"><span data-stu-id="c0f59-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="c0f59-118">Para volver a implementar la última versión del instalador, use el proceso que se describe a continuación para implementar de nuevo el MSI.</span><span class="sxs-lookup"><span data-stu-id="c0f59-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="c0f59-119">Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente en cuanto pueda el usuario.</span><span class="sxs-lookup"><span data-stu-id="c0f59-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="c0f59-120">Si la versión que se implementa es mucho anterior, el MSI activará una actualización de la aplicación antes de que el usuario pueda usar Teams.</span><span class="sxs-lookup"><span data-stu-id="c0f59-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="c0f59-121">No se recomienda cambiar las ubicaciones predeterminadas para la instalación para evitar que se interrumpa el flujo de actualización.</span><span class="sxs-lookup"><span data-stu-id="c0f59-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="c0f59-122">Asimismo, si mantiene una versión demasiado antigua, los usuarios acabarían por no poder acceder al servicio.</span><span class="sxs-lookup"><span data-stu-id="c0f59-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="c0f59-123">Requisitos del ordenador de destino</span><span class="sxs-lookup"><span data-stu-id="c0f59-123">Target computer requirements</span></span>

- <span data-ttu-id="c0f59-124">.NET Framework 4.5 o posterior</span><span class="sxs-lookup"><span data-stu-id="c0f59-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="c0f59-125">Windows 7 o posterior</span><span class="sxs-lookup"><span data-stu-id="c0f59-125">Windows 7 or later</span></span>
- <span data-ttu-id="c0f59-126">3 GB de espacio en disco para cada perfil de usuario (recomendado)</span><span class="sxs-lookup"><span data-stu-id="c0f59-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="c0f59-127">Procedimiento de limpieza y reimplementación</span><span class="sxs-lookup"><span data-stu-id="c0f59-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="c0f59-128">Si un usuario desinstala Teams de su perfil de usuario, el instalador MSI rastreará que el usuario haya desinstalado la aplicación de Teams y que no la haya vuelto a instalar para ese perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="c0f59-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="c0f59-129">Para volver a implementar Teams para este usuario en un ordenador determinado en el que se había desinstalado antes, tiene que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0f59-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="c0f59-130">Desinstale la aplicación de Teams que hay instalada para cada perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="c0f59-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="c0f59-131">Después de desinstalar, elimine el directorio repetidamente en %localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="c0f59-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="c0f59-132">Vuelva a implementar el paquete MSI en ese ordenador.</span><span class="sxs-lookup"><span data-stu-id="c0f59-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="c0f59-133">Puede usar nuestro script para [limpieza de implementaciones de Microsoft Teams](.\scripts\Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.</span><span class="sxs-lookup"><span data-stu-id="c0f59-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

