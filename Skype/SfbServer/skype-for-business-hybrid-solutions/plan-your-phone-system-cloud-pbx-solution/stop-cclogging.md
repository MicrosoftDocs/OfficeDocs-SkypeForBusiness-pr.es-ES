---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: El cmdlet Stop-CcLogging detiene la generación del registro de llamadas entrantes y salientes de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: eaccde49421cd22e32b23b89d8b5ea42dd073912
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879626"
---
# <a name="stop-cclogging"></a><span data-ttu-id="f7bb2-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="f7bb2-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="f7bb2-104">El cmdlet Stop-CcLogging detiene la generación del registro de llamadas entrantes y salientes de un dispositivo de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="f7bb2-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="f7bb2-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f7bb2-105">Examples</span></span>
<span data-ttu-id="f7bb2-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f7bb2-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="f7bb2-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f7bb2-107">Example 1</span></span>

<span data-ttu-id="f7bb2-108">En el siguiente ejemplo se detiene la generación del registro de llamadas entrantes y salientes: </span><span class="sxs-lookup"><span data-stu-id="f7bb2-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="f7bb2-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="f7bb2-109">Example 2</span></span>

<span data-ttu-id="f7bb2-110">En el siguiente ejemplo se detiene la generación del registro de llamadas entrantes y salientes, y se limpian los archivos caché:</span><span class="sxs-lookup"><span data-stu-id="f7bb2-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="f7bb2-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="f7bb2-111">Detailed Description</span></span>
<span data-ttu-id="f7bb2-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f7bb2-112"></span></span>

<span data-ttu-id="f7bb2-113">El cmdlet Stop-CcLogging detiene el registro de llamadas entrantes y salientes en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7bb2-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="f7bb2-114">De manera predeterminada, el registro se detendrá automáticamente después de cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="f7bb2-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f7bb2-115">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7bb2-115">Parameters</span></span>
<span data-ttu-id="f7bb2-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f7bb2-116"></span></span>

|<span data-ttu-id="f7bb2-117">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="f7bb2-117">**Parameter**</span></span>|<span data-ttu-id="f7bb2-118">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="f7bb2-118">**Required**</span></span>|<span data-ttu-id="f7bb2-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f7bb2-119">**Type**</span></span>|<span data-ttu-id="f7bb2-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f7bb2-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f7bb2-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="f7bb2-121">RemoveCache</span></span> <br/> | <span data-ttu-id="f7bb2-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="f7bb2-122">Optional</span></span> <br/> | <span data-ttu-id="f7bb2-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f7bb2-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="f7bb2-124">Elimina los archivos caché del registro.</span><span class="sxs-lookup"><span data-stu-id="f7bb2-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f7bb2-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f7bb2-125">Input Types</span></span>
<span data-ttu-id="f7bb2-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f7bb2-126"></span></span>

<span data-ttu-id="f7bb2-p102">Ninguno. El cmdlet Stop-CcLogging no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="f7bb2-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f7bb2-129">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="f7bb2-129">Return Types</span></span>
<span data-ttu-id="f7bb2-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f7bb2-130"></span></span>

<span data-ttu-id="f7bb2-131">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f7bb2-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7bb2-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7bb2-132">See also</span></span>
<span data-ttu-id="f7bb2-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f7bb2-133"></span></span>

[<span data-ttu-id="f7bb2-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="f7bb2-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="f7bb2-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="f7bb2-135">Start-CcLogging</span></span>](start-cclogging.md)
  

