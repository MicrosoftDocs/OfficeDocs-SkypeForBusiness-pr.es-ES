---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: El cmdlet Set-CcApplianceDirectory establece el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio.
ms.openlocfilehash: a410d20c41fbb0bfef88449aaac96be727218add
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824226"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="e1149-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="e1149-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="e1149-p102">El cmdlet Set-CcApplianceDirectory establece el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio.</span><span class="sxs-lookup"><span data-stu-id="e1149-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="e1149-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e1149-107">Examples</span></span>
<span data-ttu-id="e1149-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e1149-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e1149-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e1149-109">Example 1</span></span>

<span data-ttu-id="e1149-110">En el siguiente ejemplo se establece el directorio de trabajo del servidor host en c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="e1149-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="e1149-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1149-111">Parameters</span></span>
<span data-ttu-id="e1149-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e1149-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="e1149-113">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="e1149-113">**Parameter**</span></span>|<span data-ttu-id="e1149-114">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="e1149-114">**Required**</span></span>|<span data-ttu-id="e1149-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e1149-115">**Type**</span></span>|<span data-ttu-id="e1149-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e1149-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e1149-117"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="e1149-117">Path</span></span> <br/> | <span data-ttu-id="e1149-118">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e1149-118">Required</span></span> <br/> |<span data-ttu-id="e1149-119">System.String</span><span class="sxs-lookup"><span data-stu-id="e1149-119">System.String</span></span>  <br/> | <span data-ttu-id="e1149-120"> Especifica la ruta de acceso en la que se almacenan todos los archivos de implementación.</span><span class="sxs-lookup"><span data-stu-id="e1149-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e1149-121">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e1149-121">Input Types</span></span>
<span data-ttu-id="e1149-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1149-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e1149-p103">Ninguno. El cmdlet Set-CcApplianceDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e1149-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e1149-125">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e1149-125">Return Types</span></span>
<span data-ttu-id="e1149-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1149-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e1149-127">Ninguno </span><span class="sxs-lookup"><span data-stu-id="e1149-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1149-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1149-128">See also</span></span>
<span data-ttu-id="e1149-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1149-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e1149-130">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e1149-130">None</span></span>
  

