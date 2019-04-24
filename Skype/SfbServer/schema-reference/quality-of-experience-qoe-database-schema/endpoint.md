---
title: Tabla Endpoint
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: En la tabla de extremo es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa uno de los extremos.
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212245"
---
# <a name="endpoint-table"></a><span data-ttu-id="80873-104">Tabla Endpoint</span><span class="sxs-lookup"><span data-stu-id="80873-104">Endpoint table</span></span>
 
<span data-ttu-id="80873-105">En la tabla de extremo es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="80873-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="80873-106">Cada registro de la tabla representa uno de los extremos.</span><span class="sxs-lookup"><span data-stu-id="80873-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="80873-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="80873-107">**Column**</span></span>|<span data-ttu-id="80873-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="80873-108">**Data Type**</span></span>|<span data-ttu-id="80873-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="80873-109">**Key/Index**</span></span>|<span data-ttu-id="80873-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="80873-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80873-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="80873-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="80873-112">int</span><span class="sxs-lookup"><span data-stu-id="80873-112">int</span></span>  <br/> |<span data-ttu-id="80873-113">Primary</span><span class="sxs-lookup"><span data-stu-id="80873-113">Primary</span></span>  <br/> |<span data-ttu-id="80873-114">Número único que identifica este extremo.</span><span class="sxs-lookup"><span data-stu-id="80873-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="80873-115">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="80873-115">**Name**</span></span> <br/> |<span data-ttu-id="80873-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="80873-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="80873-117">Único</span><span class="sxs-lookup"><span data-stu-id="80873-117">Unique</span></span>  <br/> |<span data-ttu-id="80873-118">Nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="80873-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="80873-119">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="80873-119">**OS**</span></span> <br/> |<span data-ttu-id="80873-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="80873-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="80873-121">Sistema operativo (SO) del extremo.</span><span class="sxs-lookup"><span data-stu-id="80873-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="80873-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="80873-122">**CPUName**</span></span> <br/> |<span data-ttu-id="80873-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="80873-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="80873-124">Nombre de la CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="80873-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="80873-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="80873-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="80873-126">smallint</span><span class="sxs-lookup"><span data-stu-id="80873-126">smallint</span></span>  <br/> ||<span data-ttu-id="80873-127">Número de núcleos de CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="80873-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="80873-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="80873-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="80873-129">int</span><span class="sxs-lookup"><span data-stu-id="80873-129">int</span></span>  <br/> ||<span data-ttu-id="80873-130">Velocidad del procesador de CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="80873-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="80873-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="80873-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="80873-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="80873-132">tinyint</span></span>  <br/> || <span data-ttu-id="80873-133">Indicador de bits que indica si el sistema se está ejecutando en un entorno virtualizado:</span><span class="sxs-lookup"><span data-stu-id="80873-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="80873-134">0 x 0000 - ninguno</span><span class="sxs-lookup"><span data-stu-id="80873-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="80873-135">0 x 0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="80873-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="80873-136">0 x 0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="80873-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="80873-137">0 x 0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="80873-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="80873-138">0 x 0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="80873-138">0x0008 - Xen PC</span></span> <br/> |
   

