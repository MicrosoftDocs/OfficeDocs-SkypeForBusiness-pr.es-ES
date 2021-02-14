---
title: Start-CcLogging
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
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: El cmdlet Start-CcLogging genera el registro de llamadas entrantes y salientes para un dispositivo de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824174"
---
# <a name="start-cclogging"></a><span data-ttu-id="312e7-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="312e7-103">Start-CcLogging</span></span>
 
<span data-ttu-id="312e7-104">El cmdlet Start-CcLogging genera el registro de llamadas entrantes y salientes para un dispositivo de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="312e7-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="312e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="312e7-105">Parameters</span></span>

<span data-ttu-id="312e7-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="312e7-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="312e7-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="312e7-107">Examples</span></span>
<span data-ttu-id="312e7-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="312e7-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="312e7-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="312e7-109">Example 1</span></span>

<span data-ttu-id="312e7-110">En el siguiente ejemplo se genera el registro de llamadas entrantes y salientes:</span><span class="sxs-lookup"><span data-stu-id="312e7-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="312e7-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="312e7-111">Detailed Description</span></span>
<span data-ttu-id="312e7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="312e7-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="312e7-113">El cmdlet Start-CcLogging permite a los administradores iniciar el registro de llamadas entrantes y salientes en un dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="312e7-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="312e7-114">De forma predeterminada, el registro se detendrá automáticamente después de cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="312e7-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="312e7-115">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="312e7-115">Input Types</span></span>
<span data-ttu-id="312e7-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="312e7-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="312e7-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="312e7-117">None.</span></span> <span data-ttu-id="312e7-118">El Start-CcLogging no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="312e7-118">The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="312e7-119">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="312e7-119">Return Types</span></span>
<span data-ttu-id="312e7-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="312e7-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="312e7-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="312e7-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="312e7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="312e7-122">See also</span></span>
<span data-ttu-id="312e7-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="312e7-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="312e7-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="312e7-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="312e7-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="312e7-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

