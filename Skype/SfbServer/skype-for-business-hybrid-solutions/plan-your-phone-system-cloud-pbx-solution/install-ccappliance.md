---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: El cmdlet Install-CcAppliance instala el dispositivo de Skype Empresarial Cloud Connector Edition(incluidas las máquinas virtuales de AD, Almacén de administración central, Servidor de mediación y Servidor perimetral) en el servidor host.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799880"
---
# <a name="install-ccappliance"></a><span data-ttu-id="85af7-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="85af7-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="85af7-104">El cmdlet Install-CcAppliance instala el dispositivo de Skype Empresarial Cloud Connector Edition(incluidas las máquinas virtuales de AD, Almacén de administración central, Servidor de mediación y Servidor perimetral) en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="85af7-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="85af7-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="85af7-105">Examples</span></span>
<span data-ttu-id="85af7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="85af7-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="85af7-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="85af7-107">Example 1</span></span>

<span data-ttu-id="85af7-108">En el siguiente ejemplo se instala un nuevo dispositivo de Cloud Connector en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="85af7-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="85af7-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="85af7-109">Example 2</span></span>

<span data-ttu-id="85af7-110">En el siguiente ejemplo se actualiza Cloud Connector a la versión más reciente:</span><span class="sxs-lookup"><span data-stu-id="85af7-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="85af7-111">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="85af7-111">Example 3</span></span>

<span data-ttu-id="85af7-112">En el siguiente ejemplo se quitan todas las credenciales de Cloud Connector almacenadas en caché en el servidor host, se solicita al usuario que vuelva a especificar toda la información de credenciales y, a continuación, se instala Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="85af7-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="85af7-113">Ejemplo 4</span><span class="sxs-lookup"><span data-stu-id="85af7-113">Example 4</span></span>

<span data-ttu-id="85af7-114">En el siguiente ejemplo se muestran todos los pasos de implementación en la consola de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="85af7-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="85af7-115">El parámetro -ShowStepsOnly es solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="85af7-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="85af7-116">Ejemplo 5</span><span class="sxs-lookup"><span data-stu-id="85af7-116">Example 5</span></span>

<span data-ttu-id="85af7-117">En el siguiente ejemplo se generan archivos de configuración para cada paso de implementación en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="85af7-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="85af7-118">Los archivos de configuración se guardan en \< la carpeta ApplianceRoot \> \Instances \\<Version \> -default\ExportedConfig en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="85af7-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="85af7-119">Para determinar la raíz del dispositivo, ejecute el cmdlet Get-CcApplianceDirectory aplicación.</span><span class="sxs-lookup"><span data-stu-id="85af7-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="85af7-120">Ejemplo 6</span><span class="sxs-lookup"><span data-stu-id="85af7-120">Example 6</span></span>

<span data-ttu-id="85af7-121">En el siguiente ejemplo, Cloud Connector ejecuta los pasos de implementación 1, 2 y 3 para crear conmutadores virtuales, crear una máquina virtual de AD e instalar el servicio de dominio en el servidor de AD.</span><span class="sxs-lookup"><span data-stu-id="85af7-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="85af7-122">Omite el paso si el paso ya se ha ejecutado:</span><span class="sxs-lookup"><span data-stu-id="85af7-122">It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="85af7-123">El parámetro SkipExistingObjects debe usarse junto con el parámetro Steps.</span><span class="sxs-lookup"><span data-stu-id="85af7-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85af7-124">El parámetro Steps es solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="85af7-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="85af7-125">No use este parámetro para implementar un dispositivo o para actualizar un dispositivo que esté en servicio.</span><span class="sxs-lookup"><span data-stu-id="85af7-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="85af7-126">Para determinar los pasos de la implementación, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="85af7-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="85af7-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="85af7-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="85af7-128">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="85af7-128">Detailed Description</span></span>
<span data-ttu-id="85af7-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="85af7-129"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="85af7-130">El cmdlet Install-CcAppliance se usa para implementar Cloud Connector en un nuevo dispositivo o para actualizar un dispositivo existente a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="85af7-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="85af7-131">Si tiene un nuevo dispositivo, asegúrese de leer primero Prepare your environment for Cloud Connector, ejecute el cmdlet Register-CcAppliance para registrar el dispositivo y, a continuación, ejecute el cmdlet Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="85af7-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="85af7-132">Para obtener más información, vea [Implementar un único sitio en Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e implementar varios sitios en Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="85af7-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="85af7-133">Si ya tiene una implementación de Cloud Connector y desea actualizar, siga las instrucciones de Actualización a una nueva versión [de Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="85af7-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="85af7-134">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85af7-134">Parameters</span></span>
<span data-ttu-id="85af7-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="85af7-135"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="85af7-136">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="85af7-136">**Parameter**</span></span>|<span data-ttu-id="85af7-137">**Required**</span><span class="sxs-lookup"><span data-stu-id="85af7-137">**Required**</span></span>|<span data-ttu-id="85af7-138">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="85af7-138">**Type**</span></span>|<span data-ttu-id="85af7-139">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="85af7-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85af7-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="85af7-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="85af7-141">Opcional</span><span class="sxs-lookup"><span data-stu-id="85af7-141">Optional</span></span>  <br/> |<span data-ttu-id="85af7-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="85af7-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="85af7-143">Generar archivos de configuración para cada paso de implementación.</span><span class="sxs-lookup"><span data-stu-id="85af7-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="85af7-144">Este parámetro es solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="85af7-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="85af7-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="85af7-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="85af7-146">Opcional</span><span class="sxs-lookup"><span data-stu-id="85af7-146">Optional</span></span>  <br/> |<span data-ttu-id="85af7-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="85af7-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="85af7-148">Mostrar solo nombres de pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="85af7-148">Display deployment step names only.</span></span> <span data-ttu-id="85af7-149">Este parámetro es solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="85af7-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="85af7-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="85af7-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="85af7-151">Opcional</span><span class="sxs-lookup"><span data-stu-id="85af7-151">Optional</span></span>  <br/> |<span data-ttu-id="85af7-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="85af7-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="85af7-153">Este parámetro debe usarse junto con el parámetro Steps.</span><span class="sxs-lookup"><span data-stu-id="85af7-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="85af7-154">Este parámetro es solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="85af7-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="85af7-155">Pasos</span><span class="sxs-lookup"><span data-stu-id="85af7-155">Steps</span></span>  <br/> |<span data-ttu-id="85af7-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="85af7-156">Optional</span></span>  <br/> |<span data-ttu-id="85af7-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="85af7-157">System.Array</span></span>  <br/> |<span data-ttu-id="85af7-158">Ejecute los pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="85af7-158">Run the deployment steps.</span></span> <span data-ttu-id="85af7-159">Este parámetro es solo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="85af7-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="85af7-160">Actualización</span><span class="sxs-lookup"><span data-stu-id="85af7-160">Upgrade</span></span>  <br/> |<span data-ttu-id="85af7-161">Opcional</span><span class="sxs-lookup"><span data-stu-id="85af7-161">Optional</span></span>  <br/> |<span data-ttu-id="85af7-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="85af7-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="85af7-163">Actualice Cloud Connector existente a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="85af7-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="85af7-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="85af7-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="85af7-165">Opcional</span><span class="sxs-lookup"><span data-stu-id="85af7-165">Optional</span></span>  <br/> |<span data-ttu-id="85af7-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="85af7-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="85af7-167">Quite todas las credenciales de Cloud Connector en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="85af7-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="85af7-168">Pida al usuario que especifique la nueva información de credenciales para la instalación.</span><span class="sxs-lookup"><span data-stu-id="85af7-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="85af7-169">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="85af7-169">Input Types</span></span>
<span data-ttu-id="85af7-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85af7-170"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="85af7-171">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85af7-171">None.</span></span> <span data-ttu-id="85af7-172">El Install-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="85af7-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="85af7-173">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="85af7-173">Return Types</span></span>
<span data-ttu-id="85af7-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85af7-174"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="85af7-175">Ninguno</span><span class="sxs-lookup"><span data-stu-id="85af7-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85af7-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="85af7-176">See also</span></span>
<span data-ttu-id="85af7-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85af7-177"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="85af7-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="85af7-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="85af7-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="85af7-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="85af7-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="85af7-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="85af7-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="85af7-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

