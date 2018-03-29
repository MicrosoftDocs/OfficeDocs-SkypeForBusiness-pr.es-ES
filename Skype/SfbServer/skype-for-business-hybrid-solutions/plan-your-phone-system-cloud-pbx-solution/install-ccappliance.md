---
title: Instalar CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 'El cmdlet Install-CcAppliance instala el dispositivo de Skype Empresarial Cloud Connector Edition, incluidas las máquinas virtuales de AD, del almacén de administración central, del servidor de mediación y del servidor perimetral en el servidor host. '
ms.openlocfilehash: a3717e510ccadaa930d50573f067888780f7dce5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-ccappliance"></a><span data-ttu-id="7dc4d-103">Instalar CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7dc4d-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="7dc4d-104">El cmdlet Install-CcAppliance instala el dispositivo de Skype Empresarial Cloud Connector Edition, incluidas las máquinas virtuales de AD, del almacén de administración central, del servidor de mediación y del servidor perimetral en el servidor host. </span><span class="sxs-lookup"><span data-stu-id="7dc4d-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]

```

## <a name="examples"></a><span data-ttu-id="7dc4d-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7dc4d-105">Examples</span></span>
<span data-ttu-id="7dc4d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7dc4d-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="7dc4d-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="7dc4d-107">Example 1</span></span>

<span data-ttu-id="7dc4d-108">En el ejemplo siguiente se instala un nuevo dispositivo de nube de conector en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="7dc4d-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="7dc4d-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="7dc4d-109">Example 2</span></span>

<span data-ttu-id="7dc4d-110">En el ejemplo siguiente se actualiza conector de nube a la versión más reciente:</span><span class="sxs-lookup"><span data-stu-id="7dc4d-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="7dc4d-111">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="7dc4d-111">Example 3</span></span>

<span data-ttu-id="7dc4d-112">En el ejemplo siguiente quita todas las credenciales de conector de nube en caché en el servidor host, pide al usuario que especifique toda la información credencial de nuevo y, a continuación, instala el conector de la nube:</span><span class="sxs-lookup"><span data-stu-id="7dc4d-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="7dc4d-113">Ejemplo 4</span><span class="sxs-lookup"><span data-stu-id="7dc4d-113">Example 4</span></span>

<span data-ttu-id="7dc4d-114">En el siguiente ejemplo se muestran todos los pasos de implementación en la consola de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7dc4d-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="7dc4d-115">El parámetro -ShowStepsOnly solo se usa para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="7dc4d-116">Ejemplo 5</span><span class="sxs-lookup"><span data-stu-id="7dc4d-116">Example 5</span></span>

<span data-ttu-id="7dc4d-117">En el siguiente ejemplo se generan los archivos de configuración de cada paso de implementación en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="7dc4d-118">Archivos de configuración se guardan en el \<ApplianceRoot\>\Instances\\< versión\>-default\ExportedConfig de carpeta en el servidor host:</span><span class="sxs-lookup"><span data-stu-id="7dc4d-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="7dc4d-119">Para determinar la raíz del dispositivo, ejecute el cmdlet Get-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="7dc4d-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="7dc4d-120">Ejemplo 6</span><span class="sxs-lookup"><span data-stu-id="7dc4d-120">Example 6</span></span>

<span data-ttu-id="7dc4d-p102">En el siguiente ejemplo, Cloud Connector ejecuta los pasos 1, 2 y 3 de la implementación para crear conmutadores virtuales, crear una máquina virtual de AD e instalar el servicio de dominio en el servidor de AD. Se omite el paso si este ya se ha ejecutado:</span><span class="sxs-lookup"><span data-stu-id="7dc4d-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="7dc4d-123">El parámetro SkipExistingObjects debe usarse junto con el parámetro Steps.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7dc4d-124">El parámetro Steps solo se usa con fines de resolución de problemas.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="7dc4d-125">No use el parámetro para implementar un dispositivo o para actualizar un dispositivo que esté en el servicio.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="7dc4d-126">Para determinar los pasos de la implementación, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="7dc4d-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="7dc4d-127">Install-CcAppliance - ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="7dc4d-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="7dc4d-128">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="7dc4d-128">Detailed Description</span></span>
<span data-ttu-id="7dc4d-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7dc4d-129"></span></span>

<span data-ttu-id="7dc4d-130">El cmdlet Install-CcAppliance se utiliza para implementar el conector de nube para un dispositivo nuevo o actualizar un dispositivo existente a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="7dc4d-131">Si tiene un dispositivo nuevo, asegúrese antes de leer Preparar el entorno para Cloud Connector, ejecute el cmdlet Register-CcAppliance para registrar el dispositivo y después ejecute el cmdlet Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="7dc4d-132">Para obtener más información, vea [implementar un único sitio en nube conector](deploy-a-single-site-in-cloud-connector.md) e [implementar varios sitios en el conector de la nube](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7dc4d-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="7dc4d-133">Si tiene una implementación existente de nube de conector y que desea actualizar, siga las instrucciones de [actualización a una nueva versión del conector de la nube](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7dc4d-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="7dc4d-134">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7dc4d-134">Parameters</span></span>
<span data-ttu-id="7dc4d-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7dc4d-135"></span></span>

|<span data-ttu-id="7dc4d-136">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="7dc4d-136">**Parameter**</span></span>|<span data-ttu-id="7dc4d-137">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="7dc4d-137">**Required**</span></span>|<span data-ttu-id="7dc4d-138">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7dc4d-138">**Type**</span></span>|<span data-ttu-id="7dc4d-139">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7dc4d-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7dc4d-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="7dc4d-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="7dc4d-141">Opcional</span><span class="sxs-lookup"><span data-stu-id="7dc4d-141">Optional</span></span>  <br/> |<span data-ttu-id="7dc4d-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7dc4d-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="7dc4d-p105"> Se generan archivos de configuración para cada paso de implementación. Este parámetro solo se usa para solucionar problemas. </span><span class="sxs-lookup"><span data-stu-id="7dc4d-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="7dc4d-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="7dc4d-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="7dc4d-146">Opcional</span><span class="sxs-lookup"><span data-stu-id="7dc4d-146">Optional</span></span>  <br/> |<span data-ttu-id="7dc4d-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7dc4d-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="7dc4d-p106">Solo se muestran los nombres de los pasos de la implementación. Este parámetro solo se usa para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="7dc4d-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="7dc4d-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="7dc4d-151">Opcional</span><span class="sxs-lookup"><span data-stu-id="7dc4d-151">Optional</span></span>  <br/> |<span data-ttu-id="7dc4d-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7dc4d-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="7dc4d-p107">Este parámetro se debe usar junto con el parámetro Steps. Este parámetro solo se usa para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="7dc4d-155">Steps</span><span class="sxs-lookup"><span data-stu-id="7dc4d-155">Steps</span></span>  <br/> |<span data-ttu-id="7dc4d-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="7dc4d-156">Optional</span></span>  <br/> |<span data-ttu-id="7dc4d-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="7dc4d-157">System.Array</span></span>  <br/> |<span data-ttu-id="7dc4d-p108">Se ejecutan los pasos de la implementación. Este parámetro solo se usa para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="7dc4d-160">Upgrade</span><span class="sxs-lookup"><span data-stu-id="7dc4d-160">Upgrade</span></span>  <br/> |<span data-ttu-id="7dc4d-161">Opcional</span><span class="sxs-lookup"><span data-stu-id="7dc4d-161">Optional</span></span>  <br/> |<span data-ttu-id="7dc4d-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7dc4d-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="7dc4d-163">Cloud Connector se actualiza a la última versión.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="7dc4d-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="7dc4d-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="7dc4d-165">Opcional</span><span class="sxs-lookup"><span data-stu-id="7dc4d-165">Optional</span></span>  <br/> |<span data-ttu-id="7dc4d-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7dc4d-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="7dc4d-167">Quitar todas las credenciales del conector de la nube en la caché.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="7dc4d-168">Se solicita al usuario que especifique toda la información de las credenciales nuevas para la instalación.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7dc4d-169">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="7dc4d-169">Input Types</span></span>
<span data-ttu-id="7dc4d-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7dc4d-170"></span></span>

<span data-ttu-id="7dc4d-p110">Ninguno. El cmdlet Install-CcAppliance no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="7dc4d-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7dc4d-173">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="7dc4d-173">Return Types</span></span>
<span data-ttu-id="7dc4d-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7dc4d-174"></span></span>

<span data-ttu-id="7dc4d-175">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7dc4d-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7dc4d-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7dc4d-176">See also</span></span>
<span data-ttu-id="7dc4d-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7dc4d-177"></span></span>

[<span data-ttu-id="7dc4d-178">CcAppliance publicar</span><span class="sxs-lookup"><span data-stu-id="7dc4d-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="7dc4d-179">Registro CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7dc4d-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="7dc4d-180">Anular el registro de CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7dc4d-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="7dc4d-181">CcAppliance desinstalar</span><span class="sxs-lookup"><span data-stu-id="7dc4d-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

