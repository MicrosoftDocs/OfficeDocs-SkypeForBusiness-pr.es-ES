---
title: Actualizar a una versión nueva de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Obtenga información sobre cómo actualizar la implementación de Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359296"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="7a4c2-103">Actualizar a una versión nueva de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7a4c2-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="7a4c2-104">Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="7a4c2-105">Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="7a4c2-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="7a4c2-106">Obtenga información sobre cómo actualizar la implementación de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="7a4c2-107">Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado las actualizaciones automáticas, la implementación existente de Skype Empresarial Cloud Connector Edition se actualizará automáticamente a la versión más reciente, según la configuración de la ventana de tiempo de actualización automática.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="7a4c2-108">También puede realizar una actualización manual.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="7a4c2-109">Las versiones 1.4.1 y posteriores de Cloud Connector Edition realizan actualizaciones automáticas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="7a4c2-110">Si desea actualizar manualmente a la última versión (2.1), consulte Actualizar un único sitio [a](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) una nueva versión más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="7a4c2-111">La actualización automática requiere que se ejecute el servicio de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="7a4c2-112">Los siguientes pasos describen el proceso de actualizaciones automáticas:</span><span class="sxs-lookup"><span data-stu-id="7a4c2-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="7a4c2-113">El proceso de actualización automática se ejecutará según la programación que haya configurado para las actualizaciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="7a4c2-114">Tareas de actualización del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7a4c2-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="7a4c2-115">Compruebe y descargue las actualizaciones del sistema operativo en todas las máquinas virtuales de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="7a4c2-116">Instale y actualice todas las máquinas virtuales de Cloud Connector una por una y reinicie.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="7a4c2-117">Después de reiniciar las máquinas virtuales de Cloud Connector, compruebe si se necesita otro reinicio.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="7a4c2-118">Una vez que las máquinas virtuales de Cloud Connector se hayan parcheado correctamente, repita el proceso para el equipo host de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="7a4c2-119">Después de que el equipo host de Cloud Connector se inicie correctamente, se completan las tareas pendientes de actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="7a4c2-120">Tareas de actualización de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7a4c2-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="7a4c2-121">Descargue y compruebe el archivo de versión del sitio de descarga.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="7a4c2-122">Descargue el archivo .msi de la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="7a4c2-123">Desinstale el archivo msi antiguo; instalar el nuevo archivo msi.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="7a4c2-124">Descargue la nueva versión de los bits de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="7a4c2-125">Registre el dispositivo llamando a Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="7a4c2-126">Instale la nueva versión de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="7a4c2-127">Purga el dispositivo antiguo y cambia la conexión de red al nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="7a4c2-128">Cuando Cloud Connector se actualiza a una nueva compilación, es posible que los cmdlets de Cloud Connector no se actualicen.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="7a4c2-129">Esto puede suceder, por ejemplo, si se deja abierta una ventana de PowerShell mientras se produce la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="7a4c2-130">Para cargar los cmdlets actualizados, puede realizar uno de los siguientes pasos: > Cerrar PowerShell en el dispositivo de Cloud Connector y, a continuación, volver a abrir PowerShell.> O bien, puede ejecutar Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="7a4c2-131">Actualizar un único sitio a una nueva versión</span><span class="sxs-lookup"><span data-stu-id="7a4c2-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="7a4c2-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="7a4c2-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="7a4c2-133">Si solo hay un dispositivo en el sitio que desea actualizar, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a4c2-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="7a4c2-134">Desinstale la versión existente de Cloud Connector en Programas y características del Panel de **\> \> control.**</span><span class="sxs-lookup"><span data-stu-id="7a4c2-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="7a4c2-135">Instale la nueva versión de CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) desde .</span><span class="sxs-lookup"><span data-stu-id="7a4c2-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="7a4c2-136">Confirme que tiene el archivo CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores necesarios para su entorno.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="7a4c2-137">No puede usar el archivo .ini de una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="7a4c2-138">Si va a actualizar Cloud Connector, consulte el tema Prepare [your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="7a4c2-139">Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="7a4c2-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="7a4c2-140">Ejecute el siguiente cmdlet para descargar la versión más reciente:</span><span class="sxs-lookup"><span data-stu-id="7a4c2-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="7a4c2-141">Ejecute el siguiente cmdlet para iniciar la instalación:</span><span class="sxs-lookup"><span data-stu-id="7a4c2-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="7a4c2-142">Ejecute el siguiente cmdlet para activar la nueva implementación y desactivar la versión anterior:</span><span class="sxs-lookup"><span data-stu-id="7a4c2-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="7a4c2-143">Si hay más de un dispositivo en el sitio, siga los pasos anteriores para actualizar cada dispositivo uno por uno.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="7a4c2-144">Si desea actualizar las credenciales de administrador de dominio, administrador de máquina virtual, administrador de modo seguro y administrador de inquilinos, puede ejecutar el cmdlet con el parámetro  _UpdateAllCredentials_ para restablecer todas las credenciales:</span><span class="sxs-lookup"><span data-stu-id="7a4c2-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="7a4c2-145">A continuación, cuando empiece a actualizar a una nueva versión, se le promoverá para que introduzca las nuevas credenciales.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="7a4c2-146">Si solo desea restablecer las credenciales de administrador de inquilinos, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7a4c2-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="7a4c2-147">Actualizar varios sitios a una nueva versión</span><span class="sxs-lookup"><span data-stu-id="7a4c2-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="7a4c2-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="7a4c2-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="7a4c2-149">Siga los pasos para actualizar un solo sitio y actualizar un sitio cada vez para cada sitio de la implementación.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="7a4c2-150">Asegúrese de validar [la implementación de Cloud Connector después](validate-your-cloud-connector-deployment.md) de actualizar cada sitio.</span><span class="sxs-lookup"><span data-stu-id="7a4c2-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

