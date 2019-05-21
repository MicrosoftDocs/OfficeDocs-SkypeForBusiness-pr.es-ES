---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta la configuración de Skype empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Cloud Connector Edition.
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287422"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="b12cf-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12cf-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="b12cf-104">Exporta la configuración de Skype empresarial Cloud Connector Edition a un archivo local en el servidor host de Skype Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b12cf-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="b12cf-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b12cf-105">Examples</span></span>
<span data-ttu-id="b12cf-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b12cf-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b12cf-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="b12cf-107">Example 1</span></span>

<span data-ttu-id="b12cf-108">En el ejemplo siguiente se establece el parámetro Path como una ruta de acceso de archivo completa y se exportan las configuraciones a ese archivo.</span><span class="sxs-lookup"><span data-stu-id="b12cf-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="b12cf-109">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="b12cf-109">Detailed Description</span></span>
<span data-ttu-id="b12cf-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b12cf-110"></span></span>

<span data-ttu-id="b12cf-111">El cmdlet Export-CcConfiguration le permite guardar la configuración del conector de la nube en un archivo en una ruta de acceso seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b12cf-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="b12cf-112">Este comando se introdujo en la versión 2,0 de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b12cf-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b12cf-113">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b12cf-113">Parameters</span></span>
<span data-ttu-id="b12cf-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b12cf-114"></span></span>

|<span data-ttu-id="b12cf-115">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="b12cf-115">**Parameter**</span></span>|<span data-ttu-id="b12cf-116">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="b12cf-116">**Required**</span></span>|<span data-ttu-id="b12cf-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b12cf-117">**Type**</span></span>|<span data-ttu-id="b12cf-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b12cf-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b12cf-119"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="b12cf-119">Path</span></span>  <br/> |<span data-ttu-id="b12cf-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="b12cf-120">Required</span></span>  <br/> |<span data-ttu-id="b12cf-121">System.String</span><span class="sxs-lookup"><span data-stu-id="b12cf-121">System.String</span></span>  <br/> |<span data-ttu-id="b12cf-122">Ruta de acceso completa del archivo donde se almacenarán las configuraciones del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="b12cf-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b12cf-123">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="b12cf-123">Input Types</span></span>
<span data-ttu-id="b12cf-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b12cf-124"></span></span>

<span data-ttu-id="b12cf-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b12cf-125">None.</span></span> <span data-ttu-id="b12cf-126">El cmdlet Export-CcConfiguration no acepta la entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="b12cf-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b12cf-127">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="b12cf-127">Return Types</span></span>
<span data-ttu-id="b12cf-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b12cf-128"></span></span>

<span data-ttu-id="b12cf-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b12cf-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b12cf-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b12cf-130">See also</span></span>
<span data-ttu-id="b12cf-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b12cf-131"></span></span>

<span data-ttu-id="b12cf-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="b12cf-132">Import-CcConfiguration</span></span>
  

