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
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094838"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="92b81-103">Implementar un solo sitio en Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="92b81-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="92b81-104">Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="92b81-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="92b81-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="92b81-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="92b81-106">Obtenga información sobre cómo implementar un solo sitio RTC en Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="92b81-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="92b81-107">Puede implementar Skype Empresarial Cloud Connector Edition con o sin compatibilidad con alta disponibilidad (HA).</span><span class="sxs-lookup"><span data-stu-id="92b81-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="92b81-108">Si desea habilitar HA, deberá implementar dos o más dispositivos dentro de un sitio.</span><span class="sxs-lookup"><span data-stu-id="92b81-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="92b81-109">También puede convertir un dispositivo existente para que admita HA después de implementarlo.</span><span class="sxs-lookup"><span data-stu-id="92b81-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="92b81-110">Implementar el primer dispositivo de Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="92b81-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="92b81-111">Para implementar el primer dispositivo en un sitio, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet para registrar el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="92b81-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="92b81-112">Siga las instrucciones para proporcionar el nombre y la contraseña de la cuenta de administrador del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="92b81-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="92b81-113">Use la cuenta que ha creado para la administración en línea de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="92b81-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="92b81-114">Además, siga las instrucciones para proporcionar la contraseña de certificado externo, la contraseña de administrador del modo seguro, la contraseña de administrador de dominio y la contraseña de administrador de vm.</span><span class="sxs-lookup"><span data-stu-id="92b81-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="92b81-115">En la versión 1.4.2 y versiones anteriores, también sigue las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de administrador del modo seguro, la contraseña de administrador de dominio y la contraseña de administrador de vm.</span><span class="sxs-lookup"><span data-stu-id="92b81-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="92b81-116">En la versión 2.0 y posteriores, también siga las instrucciones para proporcionar la contraseña del certificado externo, la contraseña de CceService y la contraseña CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="92b81-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="92b81-117">Para iniciar la instalación, abra una consola de PowerShell como administrador y ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="92b81-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="92b81-118">Agregar un dispositivo a un sitio existente</span><span class="sxs-lookup"><span data-stu-id="92b81-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="92b81-119">Puede ampliar un sitio existente de Cloud Connector para admitir HA agregando dispositivos adicionales al sitio.</span><span class="sxs-lookup"><span data-stu-id="92b81-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="92b81-120">Siga los pasos para preparar el dispositivo de Cloud Connector, tal como se describe [en Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="92b81-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="92b81-121">Tenga en cuenta que solo es necesario realizar algunos pasos para el primer dispositivo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="92b81-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="92b81-122">Confirme que el directorio del sitio existe y está configurado correctamente para la compatibilidad con HA.</span><span class="sxs-lookup"><span data-stu-id="92b81-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="92b81-123">Ejecute el siguiente cmdlet solo en el servidor host recién agregado para actualizar la información de topología en la configuración de la organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="92b81-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="92b81-124">Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada servidor host recién agregado uno por uno:</span><span class="sxs-lookup"><span data-stu-id="92b81-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="92b81-125">Actualice la topología en los dispositivos existentes ejecutando el siguiente cmdlet en cada servidor host.</span><span class="sxs-lookup"><span data-stu-id="92b81-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="92b81-126">Solo ejecute el cmdlet en los dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="92b81-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="92b81-127">Ejecute el siguiente cmdlet solo en servidores host recién agregados.</span><span class="sxs-lookup"><span data-stu-id="92b81-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="92b81-128">No ejecute este cmdlet en el dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="92b81-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="92b81-129">Si desea agregar varios dispositivos al mismo tiempo, ejecute el cmdlet en cada servidor host recién agregado uno por uno.</span><span class="sxs-lookup"><span data-stu-id="92b81-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="92b81-130">Si el directorio del sitio se estableció en una ruta de acceso de carpeta local, debe definir un recurso compartido de archivos para esta carpeta y usar una ruta de acceso UNC para el directorio del sitio en el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92b81-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="92b81-131">Puede dejar el primer directorio de sitio del dispositivo con la ruta de acceso local o modificarlo para usar la ruta UNC para el recurso compartido en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="92b81-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="92b81-132">Si cambia la ubicación del directorio del sitio compartido, los dispositivos instalados anteriormente deben desinstalarse y volver a instalarse.</span><span class="sxs-lookup"><span data-stu-id="92b81-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="92b81-133">> Importante: la contraseña de la cuenta CceService y la cuenta CABackupFile debe ser la misma en todos los dispositivos implementados en el sitio, de modo que los dispositivos puedan tener acceso al recurso compartido de directorios del sitio y al archivo de copia de seguridad de ca cifrada en el directorio del sitio.</span><span class="sxs-lookup"><span data-stu-id="92b81-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="92b81-134">Quitar un dispositivo de un sitio existente</span><span class="sxs-lookup"><span data-stu-id="92b81-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="92b81-135">Si desea quitar un dispositivo de un sitio existente:</span><span class="sxs-lookup"><span data-stu-id="92b81-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="92b81-136">Ejecute el siguiente cmdlet solo en los servidores host que desea quitar del sitio para actualizar la información de topología en la configuración de la organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="92b81-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="92b81-137">Ejecute el siguiente cmdlet solo en los servidores host de los que desea quitar todas las máquinas virtuales del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92b81-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```