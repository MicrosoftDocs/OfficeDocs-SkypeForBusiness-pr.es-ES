---
title: Convert-CcIsoToVhdx
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: El cmdlet Convert-CcIsoToVhdx crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 181d1af762d1f8c9c8f3e65a4411b317ab36ce4a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898490"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="c69b4-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="c69b4-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="c69b4-p102">El cmdlet Convert-CcIsoToVhdx crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c69b4-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="c69b4-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c69b4-107">Parameters</span></span>

|<span data-ttu-id="c69b4-108">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="c69b4-108">**Parameter**</span></span>|<span data-ttu-id="c69b4-109">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="c69b4-109">**Required**</span></span>|<span data-ttu-id="c69b4-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c69b4-110">**Type**</span></span>|<span data-ttu-id="c69b4-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c69b4-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c69b4-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="c69b4-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="c69b4-113">Requerido</span><span class="sxs-lookup"><span data-stu-id="c69b4-113">Required</span></span> <br/> |<span data-ttu-id="c69b4-114">System.String</span><span class="sxs-lookup"><span data-stu-id="c69b4-114">System.String</span></span>  <br/> | <span data-ttu-id="c69b4-115">La ruta de acceso al archivo ISO de Windows Server 2012 R2. </span><span class="sxs-lookup"><span data-stu-id="c69b4-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="c69b4-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="c69b4-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="c69b4-117">Opcional</span><span class="sxs-lookup"><span data-stu-id="c69b4-117">Optional</span></span>  <br/> |<span data-ttu-id="c69b4-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c69b4-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c69b4-p103">Si se produce un error en el proceso de conversión durante la actualización de Windows, puede intentar configurar una red y un proxy, y actualizar Windows manualmente. Después de completar las tareas manuales, podrá ejecutar este cmdlet con el parámetro -GeneralizeOnly para que finalicen los trabajos restantes. </span><span class="sxs-lookup"><span data-stu-id="c69b4-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="c69b4-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="c69b4-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="c69b4-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="c69b4-122">Optional</span></span>  <br/> |<span data-ttu-id="c69b4-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c69b4-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c69b4-p104">Para actualizar Windows, podría ser necesario realizar una configuración manual de la red o del proxy en la máquina virtual base. El proceso de conversión se pondrá en pausa antes de la actualización de Windows si se proporciona este parámetro. Al finalizar la configuración manual, podrá reanudar el proceso. </span><span class="sxs-lookup"><span data-stu-id="c69b4-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="c69b4-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c69b4-127">Examples</span></span>
<span data-ttu-id="c69b4-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c69b4-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="c69b4-129">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="c69b4-129">Example 1</span></span>

<span data-ttu-id="c69b4-130">El siguiente ejemplo prepara el archivo VHDX base mediante un archivo ISO de Windows Server 2012 R2 que se encuentra en "C:\Windows_Server_2012_R2-EN-US-x64.ISO": </span><span class="sxs-lookup"><span data-stu-id="c69b4-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="c69b4-131">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="c69b4-131">Example 2</span></span>

<span data-ttu-id="c69b4-132">Si se produce un error en el cmdlet Convert-CcIsoToVhdx durante Windows update, es probable que sea debido a una configuración incorrecta o proxy de la red.</span><span class="sxs-lookup"><span data-stu-id="c69b4-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="c69b4-133">Puede seguir las instrucciones del mensaje de error e iniciar sesión en la máquina virtual base para corregir el problema y actualizar Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="c69b4-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="c69b4-134">Después de completar las tareas manuales, ejecute el cmdlet de nuevo con el parámetro -GeneralizeOnly para que finalicen los trabajos restantes:</span><span class="sxs-lookup"><span data-stu-id="c69b4-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="c69b4-135">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="c69b4-135">Example 3</span></span>

<span data-ttu-id="c69b4-136">Si se requiere la configuración manual para actualizar Windows, puede usar el parámetro -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="c69b4-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="c69b4-137">Con este parámetro, el conector de nube hará una pausa antes de que el proceso de actualización de las ventanas.</span><span class="sxs-lookup"><span data-stu-id="c69b4-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="c69b4-138">Después podrá completar la configuración manual y reanudar el proceso de conversión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c69b4-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="c69b4-139">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="c69b4-139">Detailed Description</span></span>
<span data-ttu-id="c69b4-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c69b4-140"></span></span>

<span data-ttu-id="c69b4-141">El cmdlet Convert-CcIsoToVhdx crea una base de que máquina virtual en primer lugar, instala algunos componentes básicos que depende de conector en la nube y, a continuación, instala actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="c69b4-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="c69b4-142">Por último, generaliza la máquina virtual (sysprep) para obtener un archivo VHDX base que se utilizará en las máquinas virtuales de un dispositivo de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="c69b4-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="c69b4-143">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="c69b4-143">Input Types</span></span>
<span data-ttu-id="c69b4-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c69b4-144"></span></span>

<span data-ttu-id="c69b4-p108">Ninguno. El cmdlet Convert-CcIsoToVhdx no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="c69b4-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="c69b4-147">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="c69b4-147">Return Types</span></span>
<span data-ttu-id="c69b4-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c69b4-148"></span></span>

<span data-ttu-id="c69b4-149">Ninguno </span><span class="sxs-lookup"><span data-stu-id="c69b4-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c69b4-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c69b4-150">See also</span></span>
<span data-ttu-id="c69b4-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c69b4-151"></span></span>

<span data-ttu-id="c69b4-152">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c69b4-152">None</span></span>
  

