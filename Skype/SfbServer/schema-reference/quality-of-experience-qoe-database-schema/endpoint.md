---
title: Tabla Endpoint
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabla de extremo es un auxiliar que almacena información sobre los extremos que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa un extremo.
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a><span data-ttu-id="0aa55-104">Tabla Endpoint</span><span class="sxs-lookup"><span data-stu-id="0aa55-104">Endpoint table</span></span>
 
<span data-ttu-id="0aa55-105">La tabla de extremo es un auxiliar que almacena información sobre los extremos que han participado en las sesiones que se registran en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0aa55-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0aa55-106">Cada registro de la tabla representa un extremo.</span><span class="sxs-lookup"><span data-stu-id="0aa55-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="0aa55-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0aa55-107">**Column**</span></span>|<span data-ttu-id="0aa55-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0aa55-108">**Data Type**</span></span>|<span data-ttu-id="0aa55-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0aa55-109">**Key/Index**</span></span>|<span data-ttu-id="0aa55-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0aa55-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0aa55-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="0aa55-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="0aa55-112">int</span><span class="sxs-lookup"><span data-stu-id="0aa55-112">int</span></span>  <br/> |<span data-ttu-id="0aa55-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0aa55-113">Primary</span></span>  <br/> |<span data-ttu-id="0aa55-114">Número único que identifica este extremo.</span><span class="sxs-lookup"><span data-stu-id="0aa55-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="0aa55-115">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="0aa55-115">**Name**</span></span> <br/> |<span data-ttu-id="0aa55-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0aa55-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0aa55-117">Único</span><span class="sxs-lookup"><span data-stu-id="0aa55-117">Unique</span></span>  <br/> |<span data-ttu-id="0aa55-118">Nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="0aa55-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="0aa55-119">**SISTEMA OPERATIVO**</span><span class="sxs-lookup"><span data-stu-id="0aa55-119">**OS**</span></span> <br/> |<span data-ttu-id="0aa55-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="0aa55-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="0aa55-121">Sistema operativo (OS) del extremo.</span><span class="sxs-lookup"><span data-stu-id="0aa55-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="0aa55-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="0aa55-122">**CPUName**</span></span> <br/> |<span data-ttu-id="0aa55-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="0aa55-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="0aa55-124">Nombre de la CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="0aa55-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="0aa55-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="0aa55-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="0aa55-126">smallint</span><span class="sxs-lookup"><span data-stu-id="0aa55-126">smallint</span></span>  <br/> ||<span data-ttu-id="0aa55-127">Número de núcleos de CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="0aa55-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="0aa55-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="0aa55-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="0aa55-129">int</span><span class="sxs-lookup"><span data-stu-id="0aa55-129">int</span></span>  <br/> ||<span data-ttu-id="0aa55-130">Velocidad de procesador de la CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="0aa55-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="0aa55-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="0aa55-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="0aa55-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="0aa55-132">tinyint</span></span>  <br/> || <span data-ttu-id="0aa55-133">Indicador de bits que indica si el sistema se está ejecutando en un entorno virtualizado:</span><span class="sxs-lookup"><span data-stu-id="0aa55-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="0aa55-134">0 x 0000 - ninguno</span><span class="sxs-lookup"><span data-stu-id="0aa55-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="0aa55-135">0 x 0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="0aa55-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="0aa55-136">0 x 0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="0aa55-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="0aa55-137">0 x 0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="0aa55-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="0aa55-138">0 x 0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="0aa55-138">0x0008 - Xen PC</span></span> <br/> |
   

