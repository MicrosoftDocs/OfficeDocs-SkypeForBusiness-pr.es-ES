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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Obtenga más información sobre cómo actualizar la implementación de Cloud Connector Edition.
ms.openlocfilehash: c2613069f1626f8fc7e28b4fb5a246fc7647cf98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286630"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="4c56c-103">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4c56c-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="4c56c-104">Obtenga más información sobre cómo actualizar la implementación de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4c56c-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="4c56c-p101">Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado las actualizaciones automáticas, la implementación existente de Skype Empresarial Cloud Connector Edition se actualizará a la versión más reciente automáticamente de acuerdo con la configuración de tiempo de la actualización automática. También puede realizar una actualización manual. </span><span class="sxs-lookup"><span data-stu-id="4c56c-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="4c56c-107">En la versión 1.4.1 y en la versión del conector en la nube se realizan actualizaciones automáticas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4c56c-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="4c56c-108">Si desea actualizar de forma manual la versión más reciente (2,1), vea [actualizar un único sitio a una nueva versión](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="4c56c-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="4c56c-109">La actualización automática requiere que el servicio de conector de nube se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4c56c-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="4c56c-110">Los siguientes pasos describen el proceso de las actualizaciones automáticas:</span><span class="sxs-lookup"><span data-stu-id="4c56c-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="4c56c-111">El proceso de actualización automática se ejecutará de acuerdo con el programa que haya configurado para las actualizaciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="4c56c-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="4c56c-112">Tareas de actualización del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="4c56c-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="4c56c-113">Comprobar y descargar actualizaciones del sistema operativo para todas las máquinas virtuales de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4c56c-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="4c56c-114">Instale y actualice todas las máquinas virtuales de conector de nube una por una y reinicie.</span><span class="sxs-lookup"><span data-stu-id="4c56c-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="4c56c-115">Después de reiniciar la MV del conector de nube, compruebe si es necesario otro reinicio.</span><span class="sxs-lookup"><span data-stu-id="4c56c-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="4c56c-116">Después de que se hayan revisado correctamente las máquinas virtuales del conector de nube, repita el proceso para el equipo host del conector de nube.</span><span class="sxs-lookup"><span data-stu-id="4c56c-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="4c56c-117">Una vez que el host del conector de nube se inicia correctamente, se completan las tareas pendientes de actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4c56c-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="4c56c-118">Tareas de actualización del conector en la nube</span><span class="sxs-lookup"><span data-stu-id="4c56c-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="4c56c-119">Descargue y compruebe el archivo de la versión desde el sitio de descargas.</span><span class="sxs-lookup"><span data-stu-id="4c56c-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="4c56c-120">Descargue el nuevo archivo .msi. </span><span class="sxs-lookup"><span data-stu-id="4c56c-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="4c56c-121">Desinstale el archivo MSI antiguo; Instale el nuevo archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="4c56c-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="4c56c-122">Descargue la nueva versión de Skype for Business bits.</span><span class="sxs-lookup"><span data-stu-id="4c56c-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="4c56c-123">Registre el dispositivo llamando a Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="4c56c-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="4c56c-124">Instale la nueva versión de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="4c56c-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="4c56c-125">Depure el antiguo dispositivo y cambie la conexión de red al nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c56c-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="4c56c-126">Cuando el conector de nube se actualiza a una nueva compilación, es posible que los cmdlets de conector de nube no se actualicen.</span><span class="sxs-lookup"><span data-stu-id="4c56c-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="4c56c-127">Esto puede suceder, por ejemplo, si se deja abierta una ventana de PowerShell mientras se produce la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="4c56c-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="4c56c-128">Para cargar los cmdlets actualizados, puede realizar cualquiera de los pasos siguientes: > cierre PowerShell en el dispositivo Cloud Connector y, a continuación, vuelva a abrir PowerShell. > o bien, puede ejecutar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="4c56c-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="4c56c-129">Actualizar un sitio único a una versión nueva</span><span class="sxs-lookup"><span data-stu-id="4c56c-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="4c56c-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="4c56c-130"></span></span>

<span data-ttu-id="4c56c-131">Si solo hay un dispositivo en el sitio que desea actualizar, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c56c-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="4c56c-132">Desinstalar la versión del conector de nube existente en el **panel \> de control \> programas programas y características**.</span><span class="sxs-lookup"><span data-stu-id="4c56c-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="4c56c-133">Instale la nueva versión de CloudConnector. msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="4c56c-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="4c56c-134">Confirme que tiene el archivo CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores requeridos para su entorno.</span><span class="sxs-lookup"><span data-stu-id="4c56c-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="4c56c-135">No puede usar el archivo .ini de una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="4c56c-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="4c56c-136">Si está actualizando Cloud Connector, consulte el tema [preparar el dispositivo de conexión en la nube](prepare-your-cloud-connector-appliance.md) y asegúrese de que el valor de NombreDeSitio y EnableReferSupport está establecido en el valor correcto en el archivo CloudConnector. ini.</span><span class="sxs-lookup"><span data-stu-id="4c56c-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="4c56c-137">Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="4c56c-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```
   Register-CcAppliance
   ```

5. <span data-ttu-id="4c56c-138">Ejecute el siguiente cmdlet para registrar la última versión:</span><span class="sxs-lookup"><span data-stu-id="4c56c-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```
   Start-CcDownload
   ```

6. <span data-ttu-id="4c56c-139">Ejecute el siguiente cmdlet para iniciar la instalación: </span><span class="sxs-lookup"><span data-stu-id="4c56c-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="4c56c-140">Ejecute el siguiente cmdlet para activar la nueva implementación y desactivar la versión anterior:</span><span class="sxs-lookup"><span data-stu-id="4c56c-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```
   Switch-CcVersion
   ```

<span data-ttu-id="4c56c-141">Si hay más de un dispositivo en el sitio, siga los pasos anteriores para actualizar cada dispositivo de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="4c56c-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="4c56c-142">Si desea actualizar el administrador de dominio, administrador de máquina virtual, credenciales de administrador de modo seguro y administrador de inquilinos, puede ejecutar el cmdlet con el parámetro _UpdateAllCredentials_ para restablecer todas las credenciales:</span><span class="sxs-lookup"><span data-stu-id="4c56c-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="4c56c-143">Después, cuando comience a actualizar a una nueva versión, podrá introducir las nuevas credenciales. </span><span class="sxs-lookup"><span data-stu-id="4c56c-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="4c56c-144">Si solo desea restablecer las credenciales de administrador de inquilinos, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4c56c-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="4c56c-145">Actualizar varios sitios a una versión nueva</span><span class="sxs-lookup"><span data-stu-id="4c56c-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="4c56c-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="4c56c-146"></span></span>

<span data-ttu-id="4c56c-p106">Siga los pasos para actualizar un sitio único, para actualizar un sitio cada vez para cada sitio de la implementación. Asegúrese de realizar la [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) después de actualizar cada sitio.</span><span class="sxs-lookup"><span data-stu-id="4c56c-p106">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment. Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

