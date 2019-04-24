---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Devuelve la versión del dispositivo de conector en la nube. Get-CCVersion sólo puede utilizarse en el equipo host del conector en la nube.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233760"
---
# <a name="get-ccversion"></a><span data-ttu-id="59573-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="59573-104">Get-CcVersion</span></span>
 
<span data-ttu-id="59573-105">Devuelve la versión del dispositivo de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="59573-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="59573-106">Get-CCVersion sólo puede utilizarse en el equipo host del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="59573-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="59573-107">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="59573-107">Detailed Description</span></span>

<span data-ttu-id="59573-108">Devuelve la versión del dispositivo de conector en la nube basado en los scripts de PowerShell instalados, los archivos en el directorio del dispositivo y las máquinas virtuales que se implementan en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="59573-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="59573-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59573-109">Parameters</span></span>

|<span data-ttu-id="59573-110">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="59573-110">**Parameter**</span></span>|<span data-ttu-id="59573-111">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="59573-111">**Required**</span></span>|<span data-ttu-id="59573-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="59573-112">**Type**</span></span>|<span data-ttu-id="59573-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="59573-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59573-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="59573-114">VersionType</span></span>  <br/> |<span data-ttu-id="59573-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="59573-115">Optional</span></span>  <br/> |<span data-ttu-id="59573-116">System.String</span><span class="sxs-lookup"><span data-stu-id="59573-116">System.String</span></span>  <br/> |<span data-ttu-id="59573-117">Tipo de versión.</span><span class="sxs-lookup"><span data-stu-id="59573-117">Type of version.</span></span> <span data-ttu-id="59573-118">Valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o todos.</span><span class="sxs-lookup"><span data-stu-id="59573-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="59573-119">Valor predeterminado es RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="59573-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="59573-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="59573-120">Examples</span></span>
<span data-ttu-id="59573-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="59573-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="59573-122">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="59573-122">Example 1</span></span>

<span data-ttu-id="59573-123">En el ejemplo siguiente se muestra la versión de conector en la nube de la secuencia de comandos que se está ejecutando en la consola de PowerShell abierta:</span><span class="sxs-lookup"><span data-stu-id="59573-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="59573-124">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="59573-124">Example 2</span></span>

<span data-ttu-id="59573-125">En el ejemplo siguiente se muestra la versión de conector en la nube de los archivos binarios que se está ejecutando de implementada en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="59573-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="59573-126">Puede ver la versión en los nombres de máquina virtual que se está ejecutando en el Administrador de Hyper-v:</span><span class="sxs-lookup"><span data-stu-id="59573-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="59573-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="59573-127">Input Types</span></span>
<span data-ttu-id="59573-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="59573-128"></span></span>

<span data-ttu-id="59573-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59573-129">None.</span></span> <span data-ttu-id="59573-130">El cmdlet Get-CcVersion no acepta entradas transferidas.</span><span class="sxs-lookup"><span data-stu-id="59573-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="59573-131">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="59573-131">Return Types</span></span>
<span data-ttu-id="59573-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="59573-132"></span></span>

<span data-ttu-id="59573-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59573-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="59573-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59573-134">See also</span></span>
<span data-ttu-id="59573-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="59573-135"></span></span>

<span data-ttu-id="59573-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59573-136">None.</span></span>
  

