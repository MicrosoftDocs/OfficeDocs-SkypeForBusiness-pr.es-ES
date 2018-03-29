---
title: Conjunto de CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: El cmdlet Set-CcApplianceDirectory establece el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio.
ms.openlocfilehash: 67fda4f1ef7da0f9a7e61b1099c7edb3b96ad62c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="5d6ab-104">Conjunto de CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="5d6ab-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="5d6ab-p102">El cmdlet Set-CcApplianceDirectory establece el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="5d6ab-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5d6ab-107">Examples</span></span>
<span data-ttu-id="5d6ab-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5d6ab-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="5d6ab-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="5d6ab-109">Example 1</span></span>

<span data-ttu-id="5d6ab-110">En el siguiente ejemplo se establece el directorio de trabajo del servidor host en c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="5d6ab-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="5d6ab-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d6ab-111">Parameters</span></span>
<span data-ttu-id="5d6ab-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5d6ab-112"></span></span>

|<span data-ttu-id="5d6ab-113">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="5d6ab-113">**Parameter**</span></span>|<span data-ttu-id="5d6ab-114">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="5d6ab-114">**Required**</span></span>|<span data-ttu-id="5d6ab-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5d6ab-115">**Type**</span></span>|<span data-ttu-id="5d6ab-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5d6ab-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5d6ab-117"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="5d6ab-117">Path</span></span> <br/> | <span data-ttu-id="5d6ab-118"> Obligatorio</span><span class="sxs-lookup"><span data-stu-id="5d6ab-118">Required</span></span> <br/> |<span data-ttu-id="5d6ab-119">System.String</span><span class="sxs-lookup"><span data-stu-id="5d6ab-119">System.String</span></span>  <br/> | <span data-ttu-id="5d6ab-120"> Especifica la ruta de acceso en la que se almacenan todos los archivos de implementación.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5d6ab-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="5d6ab-121">Input Types</span></span>
<span data-ttu-id="5d6ab-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5d6ab-122"></span></span>

<span data-ttu-id="5d6ab-p103">Ninguno. El cmdlet Set-CcApplianceDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5d6ab-125">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="5d6ab-125">Return Types</span></span>
<span data-ttu-id="5d6ab-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5d6ab-126"></span></span>

<span data-ttu-id="5d6ab-127">Ninguno</span><span class="sxs-lookup"><span data-stu-id="5d6ab-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d6ab-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d6ab-128">See also</span></span>
<span data-ttu-id="5d6ab-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5d6ab-129"></span></span>

<span data-ttu-id="5d6ab-130">Ninguno</span><span class="sxs-lookup"><span data-stu-id="5d6ab-130">None</span></span>
  

