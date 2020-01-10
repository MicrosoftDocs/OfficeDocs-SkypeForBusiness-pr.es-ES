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
ms.openlocfilehash: f79023c50e951e6678abdccc29b12cb30a329dfc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003450"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="e59d8-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e59d8-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="e59d8-104">El cmdlet Exit-CcUpdate sale del modo de mantenimiento en el servidor host de Skype Empresarial Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="e59d8-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="e59d8-105">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e59d8-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="e59d8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e59d8-106">Parameters</span></span>

<span data-ttu-id="e59d8-107">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e59d8-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e59d8-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e59d8-108">Examples</span></span>
<span data-ttu-id="e59d8-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e59d8-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="e59d8-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e59d8-110">Example 1</span></span>

<span data-ttu-id="e59d8-111">El siguiente comando vuelve a poner el dispositivo en el que se ejecuta en modo de producción: </span><span class="sxs-lookup"><span data-stu-id="e59d8-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="e59d8-112">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="e59d8-112">Detailed Description</span></span>
<span data-ttu-id="e59d8-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e59d8-113"></span></span>

<span data-ttu-id="e59d8-114">Si tiene dispositivos que ha puesto en modo de mantenimiento mediante el cmdlet Enter-CcUpdate, el cmdlet Exit-CcUpdate los volverá a poner en modo de producción. </span><span class="sxs-lookup"><span data-stu-id="e59d8-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="e59d8-115">Para obtener más información sobre cómo poner los dispositivos en modo de mantenimiento, vea Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="e59d8-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e59d8-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e59d8-116">Input Types</span></span>
<span data-ttu-id="e59d8-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e59d8-117"></span></span>

<span data-ttu-id="e59d8-p101">Ninguno. El cmdlet Exit-CcUpdate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e59d8-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e59d8-120">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e59d8-120">Return Types</span></span>
<span data-ttu-id="e59d8-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e59d8-121"></span></span>

<span data-ttu-id="e59d8-122">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e59d8-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e59d8-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e59d8-123">See also</span></span>
<span data-ttu-id="e59d8-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e59d8-124"></span></span>

[<span data-ttu-id="e59d8-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e59d8-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

