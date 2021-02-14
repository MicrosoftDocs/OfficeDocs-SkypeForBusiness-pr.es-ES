---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: El Convert-CcIsoToVhdx cmdlet crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802430"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="8b321-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="8b321-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="8b321-105">El Convert-CcIsoToVhdx cmdlet crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="8b321-105">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file.</span></span> <span data-ttu-id="8b321-106">El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8b321-106">The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="8b321-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b321-107">Parameters</span></span>

|<span data-ttu-id="8b321-108">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="8b321-108">**Parameter**</span></span>|<span data-ttu-id="8b321-109">**Required**</span><span class="sxs-lookup"><span data-stu-id="8b321-109">**Required**</span></span>|<span data-ttu-id="8b321-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8b321-110">**Type**</span></span>|<span data-ttu-id="8b321-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8b321-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b321-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="8b321-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="8b321-113">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8b321-113">Required</span></span> <br/> |<span data-ttu-id="8b321-114">System.String</span><span class="sxs-lookup"><span data-stu-id="8b321-114">System.String</span></span>  <br/> | <span data-ttu-id="8b321-115">La ruta de acceso al archivo ISO de Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="8b321-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="8b321-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="8b321-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="8b321-117">Opcional</span><span class="sxs-lookup"><span data-stu-id="8b321-117">Optional</span></span>  <br/> |<span data-ttu-id="8b321-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8b321-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8b321-119">Si se produce un error en el proceso de conversión durante la actualización de Windows, puedes intentar configurar una red o proxy y actualizar Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="8b321-119">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually.</span></span> <span data-ttu-id="8b321-120">Una vez finalizado el trabajo manual, puede ejecutar este cmdlet con el parámetro -GeneralizeOnly y completará los trabajos restantes.</span><span class="sxs-lookup"><span data-stu-id="8b321-120">After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="8b321-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="8b321-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="8b321-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="8b321-122">Optional</span></span>  <br/> |<span data-ttu-id="8b321-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8b321-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8b321-124">Para actualizar Windows, es posible que sea necesario realizar alguna configuración manual de red o proxy en la máquina virtual base.</span><span class="sxs-lookup"><span data-stu-id="8b321-124">To update Windows, some manual network/proxy configuration on the base VM might be necessary.</span></span> <span data-ttu-id="8b321-125">El proceso de conversión se pausará antes de la actualización de Windows si se proporciona este parámetro.</span><span class="sxs-lookup"><span data-stu-id="8b321-125">The conversion process will pause before Windows update if this parameter is provided.</span></span> <span data-ttu-id="8b321-126">Una vez realizada la configuración manual, puede reanudar el proceso.</span><span class="sxs-lookup"><span data-stu-id="8b321-126">After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="8b321-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="8b321-127">Examples</span></span>
<span data-ttu-id="8b321-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8b321-128"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="8b321-129">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="8b321-129">Example 1</span></span>

<span data-ttu-id="8b321-130">En el siguiente ejemplo se prepara el archivo VHDX base mediante un archivo ISO de Windows Server 2012 R2 ubicado en "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span><span class="sxs-lookup"><span data-stu-id="8b321-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="8b321-131">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="8b321-131">Example 2</span></span>

<span data-ttu-id="8b321-132">Si se produce Convert-CcIsoToVhdx cmdlet durante la actualización de Windows, es probable que se deba a una configuración de red o proxy incorrecta.</span><span class="sxs-lookup"><span data-stu-id="8b321-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="8b321-133">Puede seguir las instrucciones del mensaje de error e iniciar sesión en la máquina virtual base para solucionar el problema y actualizar Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="8b321-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="8b321-134">Una vez finalizado el trabajo manual, vuelva a ejecutar el cmdlet con el parámetro -GeneralizeOnly para completar los trabajos restantes:</span><span class="sxs-lookup"><span data-stu-id="8b321-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="8b321-135">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="8b321-135">Example 3</span></span>

<span data-ttu-id="8b321-136">Si la configuración manual es necesaria para actualizar Windows, puedes usar el parámetro -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="8b321-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="8b321-137">Con este parámetro, Cloud Connector se pausará antes del proceso de actualización de Windows.</span><span class="sxs-lookup"><span data-stu-id="8b321-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="8b321-138">A continuación, puede completar la configuración manual y reanudar el proceso de conversión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8b321-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="8b321-139">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="8b321-139">Detailed Description</span></span>
<span data-ttu-id="8b321-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8b321-140"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="8b321-141">El cmdlet Convert-CcIsoToVhdx crea primero una máquina virtual base, instala algunos componentes básicos de los que depende Cloud Connector y, a continuación, instala las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="8b321-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="8b321-142">Por último, generaliza la máquina virtual (sysprep) para obtener un archivo VHDX base que usarán las máquinas virtuales de un dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8b321-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="8b321-143">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="8b321-143">Input Types</span></span>
<span data-ttu-id="8b321-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8b321-144"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="8b321-145">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8b321-145">None.</span></span> <span data-ttu-id="8b321-146">El Convert-CcIsoToVhdx no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="8b321-146">The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="8b321-147">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="8b321-147">Return Types</span></span>
<span data-ttu-id="8b321-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8b321-148"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="8b321-149">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8b321-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b321-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b321-150">See also</span></span>
<span data-ttu-id="8b321-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8b321-151"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="8b321-152">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8b321-152">None</span></span>
  

