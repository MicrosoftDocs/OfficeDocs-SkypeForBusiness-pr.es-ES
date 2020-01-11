---
title: Implementar un solo sitio en Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Obtenga información sobre cómo implementar un único sitio de RTC en Cloud Connector Edition.
ms.openlocfilehash: a2cc8933276bc85b19ee79559ca4bcf9e88a079f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001030"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="8bb1a-103">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="8bb1a-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="8bb1a-104">Obtenga información sobre cómo implementar un único sitio de RTC en Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="8bb1a-105">Puede implementar Skype empresarial Cloud Connector Edition con compatibilidad o sin disponibilidad alta (HA).</span><span class="sxs-lookup"><span data-stu-id="8bb1a-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="8bb1a-106">Si desea habilitar HA, tendrá que implementar dos o más dispositivos dentro de un sitio.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="8bb1a-107">También puede convertir un dispositivo existente para que admita HA después de su implementación.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="8bb1a-108">Implementar el primer dispositivo de Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="8bb1a-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="8bb1a-109">Para implementar la primera aplicación en un sitio, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="8bb1a-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="8bb1a-p102">Siga las instrucciones para proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos. Use la cuenta que creó para la administración en línea de Cloud Connector. Además, siga las instrucciones para proporcionar la contraseña del certificado externo, la del administrador de modo seguro, la del administrador de dominio y la del administrador de máquinas virtuales. 
</span><span class="sxs-lookup"><span data-stu-id="8bb1a-p102">Follow the instructions to provide the tenant admin account name and password. Use the account you have created for Cloud Connector online management. Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="8bb1a-113">En la versión 1.4.2 y anterior, también puede seguir las instrucciones para proporcionar la contraseña del certificado externo, la contraseña del administrador en el modo seguro, la contraseña del administrador del dominio y la contraseña de administrador de la VM.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="8bb1a-114">En la versión 2,0 y posteriores, también puede seguir las instrucciones para proporcionar la contraseña del certificado externo, CceService contraseña y CABackupFile contraseña.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="8bb1a-115">Para iniciar la instalación, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8bb1a-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="8bb1a-116">Agregar una aplicación a un sitio existente</span><span class="sxs-lookup"><span data-stu-id="8bb1a-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="8bb1a-117">Puede extender un sitio de conector de nube existente para que sea compatible con HA agregando dispositivos adicionales al sitio.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="8bb1a-118">Siga los pasos para preparar el dispositivo de conector de nube como se describe en [preparar el dispositivo de conector de nube](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="8bb1a-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="8bb1a-119">Tenga en cuenta que algunos pasos solo se requieren para el primer dispositivo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="8bb1a-120">Confirme que exista el directorio del sitio y que esté configurado correctamente para la compatibilidad con HA.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="8bb1a-p104">Ejecute el siguiente cmdlet solo en un servidor host recién agregado para actualizar la información de topología en la configuración de inquilino de Office 365. Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada uno de los hosts recién agregados, uno por uno:</span><span class="sxs-lookup"><span data-stu-id="8bb1a-p104">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 tenant configuration. If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="8bb1a-p105">Actualice la topología en los dispositivos existentes ejecutando el siguiente cmdlet en cada servidor host. Solo ejecute el cmdlet en los dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-p105">Update the topology on existing appliances by running the following cmdlet on each host server. Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="8bb1a-125">Ejecute el siguiente cmdlet solo en servidores host recién agregados.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="8bb1a-126">No ejecute este cmdlet en el dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="8bb1a-127">Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada uno de los hosts recién agregados, uno por uno.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="8bb1a-128">Si el directorio de sitios se ha establecido en la ruta de acceso a una carpeta local, tiene que definir un recurso compartido de archivos para esta carpeta y usar una ruta de acceso UNC para el directorio de sitios en el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="8bb1a-129">Puede dejar el directorio de sitios del primer dispositivo con la ruta de acceso local o modificarla para usar la ruta de acceso UNC para el recurso compartido en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="8bb1a-130">Si modifica la ubicación del directorio de sitios del recurso compartido, tendrá que desinstalar y volver a instalar después los dispositivos que se hayan instalado previamente.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="8bb1a-131">> importante: la contraseña de la cuenta de CceService y de la cuenta de CABackupFile debe ser la misma en todos los dispositivos instalados dentro del sitio, de modo que los dispositivos puedan acceder al recurso compartido de directorio de sitios y al archivo de copia de seguridad de la entidad emisora cifrada en el directorio de sitios.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="8bb1a-132">Quitar una aplicación de un sitio existente</span><span class="sxs-lookup"><span data-stu-id="8bb1a-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="8bb1a-133">Si desea quitar una aplicación de un sitio existente:</span><span class="sxs-lookup"><span data-stu-id="8bb1a-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="8bb1a-134">Ejecute el siguiente cmdlet solo en los servidores host que desee quitar del sitio para actualizar la información de topología en la configuración de inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 tenant configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="8bb1a-135">Ejecute el siguiente cmdlet solo en los servidores host de los que desee quitar todas las máquinas virtuales del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8bb1a-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


