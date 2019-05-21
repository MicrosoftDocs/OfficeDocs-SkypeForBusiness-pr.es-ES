---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Devuelve la versión del dispositivo de conector de nube. Get-CCVersion solo se puede usar en la máquina host del conector en la nube.
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287254"
---
# <a name="get-ccversion"></a><span data-ttu-id="00ce5-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="00ce5-104">Get-CcVersion</span></span>
 
<span data-ttu-id="00ce5-105">Devuelve la versión del dispositivo de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="00ce5-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="00ce5-106">Get-CCVersion solo se puede usar en la máquina host del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="00ce5-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="00ce5-107">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="00ce5-107">Detailed Description</span></span>

<span data-ttu-id="00ce5-108">Devuelve la versión del dispositivo de conector de nube en función de los scripts de PowerShell instalados, los archivos del directorio del equipo y las máquinas virtuales implementadas en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="00ce5-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="00ce5-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00ce5-109">Parameters</span></span>

|<span data-ttu-id="00ce5-110">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="00ce5-110">**Parameter**</span></span>|<span data-ttu-id="00ce5-111">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="00ce5-111">**Required**</span></span>|<span data-ttu-id="00ce5-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="00ce5-112">**Type**</span></span>|<span data-ttu-id="00ce5-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="00ce5-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="00ce5-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="00ce5-114">VersionType</span></span>  <br/> |<span data-ttu-id="00ce5-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="00ce5-115">Optional</span></span>  <br/> |<span data-ttu-id="00ce5-116">System.String</span><span class="sxs-lookup"><span data-stu-id="00ce5-116">System.String</span></span>  <br/> |<span data-ttu-id="00ce5-117">Tipo de versión.</span><span class="sxs-lookup"><span data-stu-id="00ce5-117">Type of version.</span></span> <span data-ttu-id="00ce5-118">El valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o ALL.</span><span class="sxs-lookup"><span data-stu-id="00ce5-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="00ce5-119">El valor predeterminado es RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="00ce5-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="00ce5-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="00ce5-120">Examples</span></span>
<span data-ttu-id="00ce5-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="00ce5-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="00ce5-122">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="00ce5-122">Example 1</span></span>

<span data-ttu-id="00ce5-123">En el ejemplo siguiente se muestra la versión del conector de nube del script que se está ejecutando actualmente en la consola de PowerShell abierta:</span><span class="sxs-lookup"><span data-stu-id="00ce5-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="00ce5-124">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="00ce5-124">Example 2</span></span>

<span data-ttu-id="00ce5-125">En el ejemplo siguiente se muestra la versión de conector de nube de los binarios que se han implementado en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="00ce5-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="00ce5-126">Puede ver la versión en los nombres de la máquina virtual en ejecución en el administrador de Hyper-v:</span><span class="sxs-lookup"><span data-stu-id="00ce5-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="00ce5-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="00ce5-127">Input Types</span></span>
<span data-ttu-id="00ce5-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="00ce5-128"></span></span>

<span data-ttu-id="00ce5-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="00ce5-129">None.</span></span> <span data-ttu-id="00ce5-130">El cmdlet Get-CcVersion no acepta la entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="00ce5-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="00ce5-131">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="00ce5-131">Return Types</span></span>
<span data-ttu-id="00ce5-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="00ce5-132"></span></span>

<span data-ttu-id="00ce5-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="00ce5-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00ce5-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00ce5-134">See also</span></span>
<span data-ttu-id="00ce5-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="00ce5-135"></span></span>

<span data-ttu-id="00ce5-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="00ce5-136">None.</span></span>
  

