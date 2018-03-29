---
title: Convertir CcIsoToVhdx
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
ms.openlocfilehash: 9bf27e7161a3d5c74cc972df12246c36226be8cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="ac673-104">Convertir CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="ac673-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="ac673-p102">El cmdlet Convert-CcIsoToVhdx crea un archivo de disco duro virtual base (VHDX) mediante un archivo ISO de Windows Server 2012 R2 proporcionado por el cliente. El archivo VHDX se usará durante la implementación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="ac673-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="ac673-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac673-107">Parameters</span></span>

|<span data-ttu-id="ac673-108">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="ac673-108">**Parameter**</span></span>|<span data-ttu-id="ac673-109">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="ac673-109">**Required**</span></span>|<span data-ttu-id="ac673-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ac673-110">**Type**</span></span>|<span data-ttu-id="ac673-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ac673-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac673-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="ac673-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="ac673-113">Requerido</span><span class="sxs-lookup"><span data-stu-id="ac673-113">Required</span></span> <br/> |<span data-ttu-id="ac673-114">System.String</span><span class="sxs-lookup"><span data-stu-id="ac673-114">System.String</span></span>  <br/> | <span data-ttu-id="ac673-115">La ruta de acceso al archivo ISO de Windows Server 2012 R2. </span><span class="sxs-lookup"><span data-stu-id="ac673-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="ac673-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="ac673-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="ac673-117">Opcional</span><span class="sxs-lookup"><span data-stu-id="ac673-117">Optional</span></span>  <br/> |<span data-ttu-id="ac673-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ac673-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="ac673-p103">Si se produce un error en el proceso de conversión durante la actualización de Windows, puede intentar configurar una red y un proxy, y actualizar Windows manualmente. Después de completar las tareas manuales, podrá ejecutar este cmdlet con el parámetro -GeneralizeOnly para que finalicen los trabajos restantes. </span><span class="sxs-lookup"><span data-stu-id="ac673-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="ac673-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="ac673-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="ac673-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="ac673-122">Optional</span></span>  <br/> |<span data-ttu-id="ac673-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ac673-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="ac673-p104">Para actualizar Windows, podría ser necesario realizar una configuración manual de la red o del proxy en la máquina virtual base. El proceso de conversión se pondrá en pausa antes de la actualización de Windows si se proporciona este parámetro. Al finalizar la configuración manual, podrá reanudar el proceso. </span><span class="sxs-lookup"><span data-stu-id="ac673-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="ac673-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ac673-127">Examples</span></span>
<span data-ttu-id="ac673-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ac673-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="ac673-129">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ac673-129">Example 1</span></span>

<span data-ttu-id="ac673-130">El siguiente ejemplo prepara el archivo VHDX base mediante un archivo ISO de Windows Server 2012 R2 que se encuentra en "C:\Windows_Server_2012_R2-EN-US-x64.ISO": </span><span class="sxs-lookup"><span data-stu-id="ac673-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="ac673-131">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="ac673-131">Example 2</span></span>

<span data-ttu-id="ac673-132">Si se produce un error en el cmdlet Convert CcIsoToVhdx durante Windows update, probablemente es debido a la configuración del proxy de red incorrecta.</span><span class="sxs-lookup"><span data-stu-id="ac673-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="ac673-133">Puede seguir las instrucciones del mensaje de error e iniciar sesión en la máquina virtual base para corregir el problema y actualizar Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="ac673-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="ac673-134">Después de completar las tareas manuales, ejecute el cmdlet de nuevo con el parámetro -GeneralizeOnly para que finalicen los trabajos restantes:</span><span class="sxs-lookup"><span data-stu-id="ac673-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="ac673-135">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="ac673-135">Example 3</span></span>

<span data-ttu-id="ac673-136">Si se requiere la configuración manual para actualizar Windows, puede usar el parámetro -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="ac673-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="ac673-137">Con este parámetro, conector de nube hará una pausa antes de que el proceso de actualización de Windows.</span><span class="sxs-lookup"><span data-stu-id="ac673-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="ac673-138">Después podrá completar la configuración manual y reanudar el proceso de conversión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ac673-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="ac673-139">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="ac673-139">Detailed Description</span></span>
<span data-ttu-id="ac673-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ac673-140"></span></span>

<span data-ttu-id="ac673-141">El cmdlet Convert CcIsoToVhdx crea una base de que VM en primer lugar, instala algunos componentes básicos que nube conector depende de y, a continuación, instala las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="ac673-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="ac673-142">Por último, generaliza la máquina virtual (sysprep) para obtener un archivo base de VHDX que se utilizarán en las máquinas virtuales de un aparato de nube de conector.</span><span class="sxs-lookup"><span data-stu-id="ac673-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="ac673-143">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ac673-143">Input Types</span></span>
<span data-ttu-id="ac673-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ac673-144"></span></span>

<span data-ttu-id="ac673-p108">Ninguno. El cmdlet Convert-CcIsoToVhdx no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="ac673-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="ac673-147">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="ac673-147">Return Types</span></span>
<span data-ttu-id="ac673-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ac673-148"></span></span>

<span data-ttu-id="ac673-149">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ac673-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac673-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac673-150">See also</span></span>
<span data-ttu-id="ac673-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ac673-151"></span></span>

<span data-ttu-id="ac673-152">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ac673-152">None</span></span>
  

