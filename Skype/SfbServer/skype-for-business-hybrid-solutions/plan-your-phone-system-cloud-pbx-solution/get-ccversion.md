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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Devuelve la versión del dispositivo de Cloud Connector. Get-CCVersion solo se puede usar en el equipo host de Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799850"
---
# <a name="get-ccversion"></a><span data-ttu-id="60272-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="60272-104">Get-CcVersion</span></span>
 
<span data-ttu-id="60272-105">Devuelve la versión del dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="60272-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="60272-106">Get-CCVersion solo se puede usar en el equipo host de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="60272-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="60272-107">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="60272-107">Detailed Description</span></span>

<span data-ttu-id="60272-108">Devuelve la versión del dispositivo de Cloud Connector basada en scripts de PowerShell instalados, archivos en el directorio de dispositivos y las máquinas virtuales implementadas en el servidor host.</span><span class="sxs-lookup"><span data-stu-id="60272-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="60272-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60272-109">Parameters</span></span>

|<span data-ttu-id="60272-110">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="60272-110">**Parameter**</span></span>|<span data-ttu-id="60272-111">**Required**</span><span class="sxs-lookup"><span data-stu-id="60272-111">**Required**</span></span>|<span data-ttu-id="60272-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="60272-112">**Type**</span></span>|<span data-ttu-id="60272-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="60272-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="60272-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="60272-114">VersionType</span></span>  <br/> |<span data-ttu-id="60272-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="60272-115">Optional</span></span>  <br/> |<span data-ttu-id="60272-116">System.String</span><span class="sxs-lookup"><span data-stu-id="60272-116">System.String</span></span>  <br/> |<span data-ttu-id="60272-117">Tipo de versión.</span><span class="sxs-lookup"><span data-stu-id="60272-117">Type of version.</span></span> <span data-ttu-id="60272-118">El valor del parámetro puede ser RunningScripts, RunningBits, BackupBits o All.</span><span class="sxs-lookup"><span data-stu-id="60272-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="60272-119">El valor predeterminado es RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="60272-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="60272-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="60272-120">Examples</span></span>
<span data-ttu-id="60272-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="60272-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="60272-122">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="60272-122">Example 1</span></span>

<span data-ttu-id="60272-123">En el siguiente ejemplo se muestra la versión de Cloud Connector del script que se está ejecutando actualmente en la consola de PowerShell abierta:</span><span class="sxs-lookup"><span data-stu-id="60272-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="60272-124">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="60272-124">Example 2</span></span>

<span data-ttu-id="60272-125">En el siguiente ejemplo se muestra la versión de Cloud Connector de los archivos binarios actualmente en ejecución implementados en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="60272-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="60272-126">Puede ver la versión en los nombres de máquina virtual en ejecución en el Administrador de Hyper-v:</span><span class="sxs-lookup"><span data-stu-id="60272-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="60272-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="60272-127">Input Types</span></span>
<span data-ttu-id="60272-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="60272-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="60272-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="60272-129">None.</span></span> <span data-ttu-id="60272-130">El Get-CcVersion no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="60272-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="60272-131">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="60272-131">Return Types</span></span>
<span data-ttu-id="60272-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="60272-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="60272-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="60272-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="60272-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="60272-134">See also</span></span>
<span data-ttu-id="60272-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="60272-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="60272-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="60272-136">None.</span></span>
  

