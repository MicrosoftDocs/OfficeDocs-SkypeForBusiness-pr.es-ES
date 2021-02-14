---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: El Exit-CcUpdate cmdlet sale del modo de mantenimiento de actualización en el servidor host de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801770"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="e95cf-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e95cf-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="e95cf-104">El Exit-CcUpdate cmdlet sale del modo de mantenimiento de actualización en el servidor host de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="e95cf-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="e95cf-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e95cf-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="e95cf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e95cf-106">Parameters</span></span>

<span data-ttu-id="e95cf-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e95cf-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e95cf-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e95cf-108">Examples</span></span>
<span data-ttu-id="e95cf-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e95cf-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e95cf-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e95cf-110">Example 1</span></span>

<span data-ttu-id="e95cf-111">El siguiente comando coloca el dispositivo en el que se ejecuta de nuevo en modo de producción:</span><span class="sxs-lookup"><span data-stu-id="e95cf-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="e95cf-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="e95cf-112">Detailed Description</span></span>
<span data-ttu-id="e95cf-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e95cf-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e95cf-114">Si tiene dispositivos que ha puesto en modo de mantenimiento especificando el cmdlet Enter-CcUpdate, el cmdlet Exit-CcUpdate los volverá a poner en modo de producción.</span><span class="sxs-lookup"><span data-stu-id="e95cf-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="e95cf-115">Para obtener más información acerca de cómo poner dispositivos en modo de mantenimiento, vea Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="e95cf-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e95cf-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e95cf-116">Input Types</span></span>
<span data-ttu-id="e95cf-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e95cf-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e95cf-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e95cf-118">None.</span></span> <span data-ttu-id="e95cf-119">El Exit-CcUpdate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e95cf-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e95cf-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e95cf-120">Return Types</span></span>
<span data-ttu-id="e95cf-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e95cf-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e95cf-122">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e95cf-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e95cf-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e95cf-123">See also</span></span>
<span data-ttu-id="e95cf-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e95cf-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e95cf-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e95cf-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

