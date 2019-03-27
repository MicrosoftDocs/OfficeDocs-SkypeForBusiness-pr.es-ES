---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta el Skype para la configuración del conector de nube Business Edition a un archivo local en el Skype para servidor de host de Business Edition de conector en la nube.
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894240"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="39768-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="39768-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="39768-104">Exporta el Skype para la configuración del conector de nube Business Edition a un archivo local en el Skype para servidor de host de Business Edition de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="39768-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="39768-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="39768-105">Examples</span></span>
<span data-ttu-id="39768-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39768-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="39768-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="39768-107">Example 1</span></span>

<span data-ttu-id="39768-108">En el ejemplo siguiente se establece el parámetro de ruta de acceso como una ruta de acceso completa al archivo y exporta configuraciones a ese archivo.</span><span class="sxs-lookup"><span data-stu-id="39768-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="39768-109">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="39768-109">Detailed Description</span></span>
<span data-ttu-id="39768-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39768-110"></span></span>

<span data-ttu-id="39768-111">El cmdlet Export-CcConfiguration permite guardar la configuración del conector de nube en un archivo en una ruta de acceso seleccionado.</span><span class="sxs-lookup"><span data-stu-id="39768-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="39768-112">Este comando se introdujo en la nube conector Edition versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="39768-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="39768-113">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39768-113">Parameters</span></span>
<span data-ttu-id="39768-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39768-114"></span></span>

|<span data-ttu-id="39768-115">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="39768-115">**Parameter**</span></span>|<span data-ttu-id="39768-116">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="39768-116">**Required**</span></span>|<span data-ttu-id="39768-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="39768-117">**Type**</span></span>|<span data-ttu-id="39768-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="39768-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39768-119"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="39768-119">Path</span></span>  <br/> |<span data-ttu-id="39768-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="39768-120">Required</span></span>  <br/> |<span data-ttu-id="39768-121">System.String</span><span class="sxs-lookup"><span data-stu-id="39768-121">System.String</span></span>  <br/> |<span data-ttu-id="39768-122">Ruta de acceso completa al archivo donde se almacenarán las configuraciones de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="39768-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="39768-123">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="39768-123">Input Types</span></span>
<span data-ttu-id="39768-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39768-124"></span></span>

<span data-ttu-id="39768-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="39768-125">None.</span></span> <span data-ttu-id="39768-126">El cmdlet Export-CcConfiguration no acepta entradas transferidas.</span><span class="sxs-lookup"><span data-stu-id="39768-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="39768-127">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="39768-127">Return Types</span></span>
<span data-ttu-id="39768-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39768-128"></span></span>

<span data-ttu-id="39768-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="39768-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39768-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39768-130">See also</span></span>
<span data-ttu-id="39768-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39768-131"></span></span>

<span data-ttu-id="39768-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="39768-132">Import-CcConfiguration</span></span>
  

