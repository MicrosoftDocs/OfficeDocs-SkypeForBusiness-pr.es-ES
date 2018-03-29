---
title: Actualizar a una versión nueva de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Obtenga información sobre cómo actualizar su implementación de nube conector Edition.
ms.openlocfilehash: 0538b5d43c6e11aa11f7d265e43eb5f283e2b74e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="3fc7f-103">Actualizar a una versión nueva de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3fc7f-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="3fc7f-104">Obtenga información sobre cómo actualizar su implementación de nube conector Edition.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="3fc7f-p101">Si ha configurado una cuenta de inquilino de administración en línea y ha habilitado las actualizaciones automáticas, la implementación existente de Skype Empresarial Cloud Connector Edition se actualizará a la versión más reciente automáticamente de acuerdo con la configuración de tiempo de la actualización automática. También puede realizar una actualización manual. </span><span class="sxs-lookup"><span data-stu-id="3fc7f-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="3fc7f-107">Versiones de conector Edition 1.4.1 en nube y posteriormente realicen actualizaciones automáticas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="3fc7f-108">Si desea actualizar a la versión más reciente (2.1) manualmente, vea [actualizar un único sitio a una nueva versión](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="3fc7f-109">Actualización automática requiere que se está ejecutando el servicio del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="3fc7f-110">Los siguientes pasos describen el proceso de las actualizaciones automáticas:</span><span class="sxs-lookup"><span data-stu-id="3fc7f-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="3fc7f-111">El proceso de actualización automática se ejecutará de acuerdo con el programa que haya configurado para las actualizaciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="3fc7f-112">Tareas de actualización del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="3fc7f-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="3fc7f-113">Comprobar y descargar actualizaciones del sistema operativo en todas las máquinas virtuales de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="3fc7f-114">Instalar y actualizar todas las máquinas virtuales de nube conector uno por uno y reiniciar.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="3fc7f-115">Después de reiniciar las máquinas virtuales de conector de nube, compruebe si es necesario volver a reiniciar.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="3fc7f-116">Después de las VMs de nube conector haya correctamente revisado, repita el proceso con el equipo host de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="3fc7f-117">Después de que el equipo host de nube conector correctamente inicia, se completan las tareas de actualización excelente sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="3fc7f-118">Las tareas de actualización del conector de la nube</span><span class="sxs-lookup"><span data-stu-id="3fc7f-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="3fc7f-119">Descargue y compruebe el archivo de la versión desde el sitio de descargas.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="3fc7f-120">Descargue el nuevo archivo .msi. </span><span class="sxs-lookup"><span data-stu-id="3fc7f-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="3fc7f-121">Desinstalar el antiguo archivo msi; instalar el nuevo archivo msi.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="3fc7f-122">Descargue la nueva versión de Skype para los bits de negocios.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="3fc7f-123">Registre el dispositivo llamando a Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="3fc7f-124">Instale la nueva versión del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="3fc7f-125">Depure el antiguo dispositivo y cambie la conexión de red al nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="3fc7f-126">Cuando el conector de nube se actualiza a una nueva compilación, cmdlets de conector de nube podría no actualizarse.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="3fc7f-127">Esto puede suceder, por ejemplo, si se deja abierta una ventana de PowerShell mientras se produce la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="3fc7f-128">Para cargar los cmdlets actualizados, puede hacer cualquiera de los siguientes pasos: > Cerrar PowerShell en el dispositivo conector de nube y volver a abrirla PowerShell. > o bien, puede ejecutar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="3fc7f-129">Actualizar un sitio único a una versión nueva</span><span class="sxs-lookup"><span data-stu-id="3fc7f-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="3fc7f-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="3fc7f-130"></span></span>

<span data-ttu-id="3fc7f-131">Si solo hay una aplicación en el sitio que desea actualizar, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3fc7f-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="3fc7f-132">Desinstale la versión existente de la nube de conector de **Panel de Control \> programas \> programas y características**.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="3fc7f-133">Instalar la nueva versión de CloudConnector.msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="3fc7f-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="3fc7f-134">Confirme que tiene el archivo CloudConnector.ini para la versión que va a instalar y que ha actualizado todos los valores requeridos para su entorno.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="3fc7f-135">No puede usar el archivo .ini de una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="3fc7f-136">Si va a actualizar el conector de nube, por favor, consulte el tema de [Preparar el dispositivo conector de nube](prepare-your-cloud-connector-appliance.md) y asegúrese de nombreDeSitio y EnableReferSupport se establecen en el valor correcto en el archivo CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="3fc7f-137">Inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo actual:</span><span class="sxs-lookup"><span data-stu-id="3fc7f-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
  ```
  Register-CcAppliance
  ```

5. <span data-ttu-id="3fc7f-138">Ejecute el siguiente cmdlet para registrar la última versión:</span><span class="sxs-lookup"><span data-stu-id="3fc7f-138">Run the following cmdlet to download the latest version:</span></span>
    
  ```
  Start-CcDownload
  ```

6. <span data-ttu-id="3fc7f-139">Ejecute el siguiente cmdlet para iniciar la instalación: </span><span class="sxs-lookup"><span data-stu-id="3fc7f-139">Run the following cmdlet to start the installation:</span></span> 
    
  ```
  Install-CcAppliance -Upgrade
  ```

7. <span data-ttu-id="3fc7f-140">Ejecute el siguiente cmdlet para activar la nueva implementación y desactivar la versión anterior:</span><span class="sxs-lookup"><span data-stu-id="3fc7f-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
  ```
  Switch-CcVersion
  ```

<span data-ttu-id="3fc7f-141">Si hay más de un dispositivo en el sitio, siga los pasos anteriores para actualizar cada dispositivo de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="3fc7f-142">Si desea actualizar el Administrador de dominio, Administrador de Virtual machine, Administrador de modo seguro y credenciales de administrador de inquilinos, puede ejecutar el cmdlet con el parámetro _UpdateAllCredentials_ para restablecer todas las credenciales:</span><span class="sxs-lookup"><span data-stu-id="3fc7f-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="3fc7f-143">Después, cuando comience a actualizar a una nueva versión, podrá introducir las nuevas credenciales. </span><span class="sxs-lookup"><span data-stu-id="3fc7f-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="3fc7f-144">Si solo desea restablecer las credenciales de administrador de inquilinos, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3fc7f-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="3fc7f-145">Actualizar varios sitios a una versión nueva</span><span class="sxs-lookup"><span data-stu-id="3fc7f-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="3fc7f-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="3fc7f-146"></span></span>

<span data-ttu-id="3fc7f-147">Siga los pasos para actualizar un sitio único, para actualizar un sitio cada vez para cada sitio de la implementación.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-147">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="3fc7f-148">Asegúrese de que y [validar la implementación de nube conector](validate-your-cloud-connector-deployment.md) después de la actualización de cada sitio.</span><span class="sxs-lookup"><span data-stu-id="3fc7f-148">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

