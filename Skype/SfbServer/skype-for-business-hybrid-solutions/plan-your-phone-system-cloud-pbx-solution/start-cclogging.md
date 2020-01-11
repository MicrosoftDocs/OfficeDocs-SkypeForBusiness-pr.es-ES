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
localization_priority: Normal
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: 'El cmdlet Start-CcLogging genera el registro de llamadas entrantes y salientes de un dispositivo de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: 2064fa4efd730812b5073821784ff5c524056341
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003180"
---
# <a name="start-cclogging"></a><span data-ttu-id="7a4fd-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="7a4fd-103">Start-CcLogging</span></span>
 
<span data-ttu-id="7a4fd-104">El cmdlet Start-CcLogging genera el registro de llamadas entrantes y salientes de un dispositivo de Skype Empresarial Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="7a4fd-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="7a4fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a4fd-105">Parameters</span></span>

<span data-ttu-id="7a4fd-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7a4fd-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="7a4fd-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a4fd-107">Examples</span></span>
<span data-ttu-id="7a4fd-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7a4fd-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="7a4fd-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="7a4fd-109">Example 1</span></span>

<span data-ttu-id="7a4fd-110">En el siguiente ejemplo se genera el registro de llamadas entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="7a4fd-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="7a4fd-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="7a4fd-111">Detailed Description</span></span>
<span data-ttu-id="7a4fd-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7a4fd-112"></span></span>

<span data-ttu-id="7a4fd-113">El cmdlet Start-CcLogging permite a los administradores iniciar el registro de llamadas entrantes y salientes en un dispositivo de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="7a4fd-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="7a4fd-114">De manera predeterminada, el registro se detendrá automáticamente después de cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="7a4fd-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="7a4fd-115">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="7a4fd-115">Input Types</span></span>
<span data-ttu-id="7a4fd-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7a4fd-116"></span></span>

<span data-ttu-id="7a4fd-p102">Ninguno. El cmdlet Start-CcLogging no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="7a4fd-p102">None. The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7a4fd-119">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="7a4fd-119">Return Types</span></span>
<span data-ttu-id="7a4fd-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7a4fd-120"></span></span>

<span data-ttu-id="7a4fd-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7a4fd-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a4fd-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a4fd-122">See also</span></span>
<span data-ttu-id="7a4fd-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7a4fd-123"></span></span>

[<span data-ttu-id="7a4fd-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="7a4fd-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="7a4fd-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="7a4fd-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

