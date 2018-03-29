---
title: Get-CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Devuelve la versión del dispositivo conector de nube. Get CCVersion sólo puede utilizarse en el equipo host del conector de la nube.
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a><span data-ttu-id="2d160-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="2d160-104">Get-CcVersion</span></span>
 
<span data-ttu-id="2d160-105">Devuelve la versión del dispositivo conector de nube.</span><span class="sxs-lookup"><span data-stu-id="2d160-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="2d160-106">Get CCVersion sólo puede utilizarse en el equipo host del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="2d160-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="2d160-107">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="2d160-107">Detailed Description</span></span>

<span data-ttu-id="2d160-108">Devuelve la versión del dispositivo conector de nube basado en secuencias de comandos de PowerShell instalados, los archivos en el directorio del dispositivo y las máquinas virtuales implementadas en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="2d160-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2d160-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d160-109">Parameters</span></span>

|<span data-ttu-id="2d160-110">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="2d160-110">**Parameter**</span></span>|<span data-ttu-id="2d160-111">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="2d160-111">**Required**</span></span>|<span data-ttu-id="2d160-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2d160-112">**Type**</span></span>|<span data-ttu-id="2d160-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2d160-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d160-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="2d160-114">VersionType</span></span>  <br/> |<span data-ttu-id="2d160-115">Opcional </span><span class="sxs-lookup"><span data-stu-id="2d160-115">Optional</span></span>  <br/> |<span data-ttu-id="2d160-116">System.String</span><span class="sxs-lookup"><span data-stu-id="2d160-116">System.String</span></span>  <br/> |<span data-ttu-id="2d160-117">Tipo de versión.</span><span class="sxs-lookup"><span data-stu-id="2d160-117">Type of version.</span></span> <span data-ttu-id="2d160-118">Valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o todos.</span><span class="sxs-lookup"><span data-stu-id="2d160-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="2d160-119">Valor predeterminado es RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="2d160-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="2d160-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2d160-120">Examples</span></span>
<span data-ttu-id="2d160-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2d160-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="2d160-122">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="2d160-122">Example 1</span></span>

<span data-ttu-id="2d160-123">En el ejemplo siguiente se muestra la versión de conector de nube de script se ejecuta actualmente en la consola de PowerShell abierta:</span><span class="sxs-lookup"><span data-stu-id="2d160-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="2d160-124">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="2d160-124">Example 2</span></span>

<span data-ttu-id="2d160-125">En el ejemplo siguiente se muestra la versión del conector de nube de los binarios de ejecución implementadas en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="2d160-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="2d160-126">Puede ver la versión en los nombres de máquina virtual de ejecución en el Administrador de Hyper-v:</span><span class="sxs-lookup"><span data-stu-id="2d160-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="2d160-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2d160-127">Input Types</span></span>
<span data-ttu-id="2d160-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2d160-128"></span></span>

<span data-ttu-id="2d160-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d160-129">None.</span></span> <span data-ttu-id="2d160-130">El cmdlet Get-CcVersion no acepta entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="2d160-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2d160-131">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="2d160-131">Return Types</span></span>
<span data-ttu-id="2d160-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2d160-132"></span></span>

<span data-ttu-id="2d160-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d160-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d160-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d160-134">See also</span></span>
<span data-ttu-id="2d160-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2d160-135"></span></span>

<span data-ttu-id="2d160-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d160-136">None.</span></span>
  

