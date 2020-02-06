---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: El cmdlet Stop-CcLogging detiene la generación del registro de llamadas entrantes y salientes de un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824164"
---
# <a name="stop-cclogging"></a><span data-ttu-id="72eb7-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="72eb7-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="72eb7-104">El cmdlet Stop-CcLogging detiene la generación del registro de llamadas entrantes y salientes de un dispositivo de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="72eb7-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="72eb7-105">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="72eb7-105">Examples</span></span>
<span data-ttu-id="72eb7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="72eb7-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="72eb7-107">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="72eb7-107">Example 1</span></span>

<span data-ttu-id="72eb7-108">En el siguiente ejemplo se detiene la generación del registro de llamadas entrantes y salientes: </span><span class="sxs-lookup"><span data-stu-id="72eb7-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="72eb7-109">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="72eb7-109">Example 2</span></span>

<span data-ttu-id="72eb7-110">En el siguiente ejemplo se detiene la generación del registro de llamadas entrantes y salientes, y se limpian los archivos caché:</span><span class="sxs-lookup"><span data-stu-id="72eb7-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="72eb7-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="72eb7-111">Detailed Description</span></span>
<span data-ttu-id="72eb7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="72eb7-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="72eb7-113">El cmdlet Stop-CcLogging detiene el registro de llamadas entrantes y salientes en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72eb7-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="72eb7-114">De manera predeterminada, el registro se detendrá automáticamente después de cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="72eb7-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="72eb7-115">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72eb7-115">Parameters</span></span>
<span data-ttu-id="72eb7-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="72eb7-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="72eb7-117">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="72eb7-117">**Parameter**</span></span>|<span data-ttu-id="72eb7-118">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="72eb7-118">**Required**</span></span>|<span data-ttu-id="72eb7-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="72eb7-119">**Type**</span></span>|<span data-ttu-id="72eb7-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="72eb7-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="72eb7-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="72eb7-121">RemoveCache</span></span> <br/> | <span data-ttu-id="72eb7-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="72eb7-122">Optional</span></span> <br/> | <span data-ttu-id="72eb7-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="72eb7-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="72eb7-124">Elimina los archivos caché del registro.</span><span class="sxs-lookup"><span data-stu-id="72eb7-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="72eb7-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="72eb7-125">Input Types</span></span>
<span data-ttu-id="72eb7-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="72eb7-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="72eb7-p102">Ninguno. El cmdlet Stop-CcLogging no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="72eb7-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="72eb7-129">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="72eb7-129">Return Types</span></span>
<span data-ttu-id="72eb7-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="72eb7-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="72eb7-131">Ninguno</span><span class="sxs-lookup"><span data-stu-id="72eb7-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="72eb7-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72eb7-132">See also</span></span>
<span data-ttu-id="72eb7-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="72eb7-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="72eb7-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="72eb7-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="72eb7-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="72eb7-135">Start-CcLogging</span></span>](start-cclogging.md)
  

