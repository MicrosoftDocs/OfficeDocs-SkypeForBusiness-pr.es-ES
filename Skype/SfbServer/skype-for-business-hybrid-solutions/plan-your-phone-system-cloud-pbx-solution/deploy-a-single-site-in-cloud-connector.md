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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Obtenga información sobre cómo implementar un solo sitio RTC en Cloud Connector Edition.
ms.openlocfilehash: 334454645be3361794fdd0d16076095a518e58b0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220540"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="b08a8-103">Implementar un solo sitio en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b08a8-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="b08a8-104">Obtenga información sobre cómo implementar un solo sitio RTC en Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b08a8-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="b08a8-105">Puede implementar Skype empresarial Cloud Connector Edition con compatibilidad con o sin alta disponibilidad (HA).</span><span class="sxs-lookup"><span data-stu-id="b08a8-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="b08a8-106">Si desea habilitar HA, debe implementar dos o más dispositivos dentro de un sitio.</span><span class="sxs-lookup"><span data-stu-id="b08a8-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="b08a8-107">También puede convertir un dispositivo existente para que sea compatible con HA una vez que se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="b08a8-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="b08a8-108">Implementar el primer dispositivo de Skype empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="b08a8-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="b08a8-109">Para implementar el primer dispositivo en un sitio, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b08a8-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="b08a8-110">Siga las instrucciones para proporcionar el nombre y la contraseña de la cuenta de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b08a8-110">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="b08a8-111">Use la cuenta que ha creado para la administración en línea de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b08a8-111">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="b08a8-112">Además, siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de administración en modo seguro, la contraseña de administrador de dominio y la contraseña de administrador de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="b08a8-112">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="b08a8-113">En la versión 1.4.2 y anteriores, siga también las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de administrador en modo seguro, la contraseña del administrador de dominio y la contraseña de administrador de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="b08a8-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="b08a8-114">En la versión 2,0 y posteriores, siga también las instrucciones para proporcionar la contraseña del certificado externo, CceService contraseña y CABackupFile contraseña.</span><span class="sxs-lookup"><span data-stu-id="b08a8-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="b08a8-115">Para iniciar la instalación, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b08a8-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="b08a8-116">Agregar un dispositivo a un sitio existente</span><span class="sxs-lookup"><span data-stu-id="b08a8-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="b08a8-117">Puede ampliar un sitio existente de Cloud Connector para que admita HA si agrega dispositivos adicionales al sitio.</span><span class="sxs-lookup"><span data-stu-id="b08a8-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="b08a8-118">Siga los pasos para preparar el dispositivo de Cloud Connector como se describe en [preparar el dispositivo de Cloud Connector](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="b08a8-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="b08a8-119">Tenga en cuenta que algunos pasos solo son necesarios para el primer dispositivo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b08a8-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="b08a8-120">Confirme que el directorio de sitios existe y que está configurado correctamente para la compatibilidad con HA.</span><span class="sxs-lookup"><span data-stu-id="b08a8-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="b08a8-121">Ejecute el siguiente cmdlet solo en el servidor host recién agregado para actualizar la información de topología en la configuración de la organización de Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="b08a8-121">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="b08a8-122">Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada uno de los servidores host recién agregados uno por uno:</span><span class="sxs-lookup"><span data-stu-id="b08a8-122">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="b08a8-123">Actualice la topología de los dispositivos existentes mediante la ejecución del siguiente cmdlet en cada servidor host.</span><span class="sxs-lookup"><span data-stu-id="b08a8-123">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="b08a8-124">Solo ejecute el cmdlet en los dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="b08a8-124">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="b08a8-125">Ejecute el siguiente cmdlet solo en servidores host recién agregados.</span><span class="sxs-lookup"><span data-stu-id="b08a8-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="b08a8-126">No ejecute este cmdlet en el dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="b08a8-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="b08a8-127">Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada uno de los servidores host recién agregados uno a uno.</span><span class="sxs-lookup"><span data-stu-id="b08a8-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="b08a8-128">Si el directorio de sitios se estableció en una ruta de acceso de carpeta local, debe definir un recurso compartido de archivos para esta carpeta y usar una ruta de acceso UNC para el directorio de sitios en el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b08a8-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="b08a8-129">Puede dejar el primer directorio de sitios de dispositivo con la ruta de acceso local o modificarlo para que use la ruta UNC para el recurso compartido en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="b08a8-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="b08a8-130">Si la ubicación del directorio de sitios compartidos cambia, es necesario desinstalar y volver a instalar cualquier dispositivo previamente instalado.</span><span class="sxs-lookup"><span data-stu-id="b08a8-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="b08a8-131">> importante: la contraseña de la cuenta CceService y de la cuenta CABackupFile debe ser la misma en todos los dispositivos que se implementen dentro del sitio, de modo que los dispositivos puedan acceder al directorio compartido de sitios y al archivo de copia de seguridad de CA cifrado en el directorio de sitios.</span><span class="sxs-lookup"><span data-stu-id="b08a8-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="b08a8-132">Quitar un dispositivo de un sitio existente</span><span class="sxs-lookup"><span data-stu-id="b08a8-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="b08a8-133">Si desea quitar un dispositivo de un sitio existente:</span><span class="sxs-lookup"><span data-stu-id="b08a8-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="b08a8-134">Ejecute el siguiente cmdlet solo en los servidores host que desea quitar del sitio para actualizar la información de topología en la configuración de la organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="b08a8-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="b08a8-135">Ejecute el siguiente cmdlet solo en los servidores host de los que desea quitar todas las máquinas virtuales del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b08a8-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


