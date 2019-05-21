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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'El cmdlet Exit-CcUpdate sale del modo de mantenimiento en el servidor host de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: b3558a81e1d4bc6c833cca157c2b31f2f252b595
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287429"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="e8ace-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e8ace-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="e8ace-104">El cmdlet Exit-CcUpdate sale del modo de mantenimiento en el servidor host de Skype Empresarial Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="e8ace-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="e8ace-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e8ace-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="e8ace-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8ace-106">Parameters</span></span>

<span data-ttu-id="e8ace-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e8ace-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e8ace-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e8ace-108">Examples</span></span>
<span data-ttu-id="e8ace-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ace-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="e8ace-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e8ace-110">Example 1</span></span>

<span data-ttu-id="e8ace-111">El siguiente comando vuelve a poner el dispositivo en el que se ejecuta en modo de producción: </span><span class="sxs-lookup"><span data-stu-id="e8ace-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="e8ace-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="e8ace-112">Detailed Description</span></span>
<span data-ttu-id="e8ace-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ace-113"></span></span>

<span data-ttu-id="e8ace-114">Si tiene dispositivos que ha puesto en modo de mantenimiento mediante el cmdlet Enter-CcUpdate, el cmdlet Exit-CcUpdate los volverá a poner en modo de producción. </span><span class="sxs-lookup"><span data-stu-id="e8ace-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="e8ace-115">Para obtener más información sobre cómo poner los dispositivos en modo de mantenimiento, vea Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="e8ace-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e8ace-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e8ace-116">Input Types</span></span>
<span data-ttu-id="e8ace-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ace-117"></span></span>

<span data-ttu-id="e8ace-p101">Ninguno. El cmdlet Exit-CcUpdate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e8ace-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e8ace-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e8ace-120">Return Types</span></span>
<span data-ttu-id="e8ace-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ace-121"></span></span>

<span data-ttu-id="e8ace-122">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e8ace-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e8ace-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8ace-123">See also</span></span>
<span data-ttu-id="e8ace-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ace-124"></span></span>

[<span data-ttu-id="e8ace-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e8ace-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

