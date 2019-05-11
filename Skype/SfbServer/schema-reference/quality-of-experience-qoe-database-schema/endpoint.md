---
title: Tabla Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: En la tabla de extremo es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa uno de los extremos.
ms.openlocfilehash: 4917b0817d8fcedbc3a20b2c41d3ed62ce468c5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920113"
---
# <a name="endpoint-table"></a><span data-ttu-id="73a68-104">Tabla Endpoint</span><span class="sxs-lookup"><span data-stu-id="73a68-104">Endpoint table</span></span>
 
<span data-ttu-id="73a68-105">En la tabla de extremo es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="73a68-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="73a68-106">Cada registro de la tabla representa uno de los extremos.</span><span class="sxs-lookup"><span data-stu-id="73a68-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="73a68-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="73a68-107">**Column**</span></span>|<span data-ttu-id="73a68-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="73a68-108">**Data Type**</span></span>|<span data-ttu-id="73a68-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="73a68-109">**Key/Index**</span></span>|<span data-ttu-id="73a68-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="73a68-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73a68-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="73a68-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="73a68-112">int</span><span class="sxs-lookup"><span data-stu-id="73a68-112">int</span></span>  <br/> |<span data-ttu-id="73a68-113">Primary</span><span class="sxs-lookup"><span data-stu-id="73a68-113">Primary</span></span>  <br/> |<span data-ttu-id="73a68-114">Número único que identifica este extremo.</span><span class="sxs-lookup"><span data-stu-id="73a68-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="73a68-115">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="73a68-115">**Name**</span></span> <br/> |<span data-ttu-id="73a68-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="73a68-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="73a68-117">Único</span><span class="sxs-lookup"><span data-stu-id="73a68-117">Unique</span></span>  <br/> |<span data-ttu-id="73a68-118">Nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="73a68-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="73a68-119">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="73a68-119">**OS**</span></span> <br/> |<span data-ttu-id="73a68-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="73a68-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="73a68-121">Sistema operativo (SO) del extremo.</span><span class="sxs-lookup"><span data-stu-id="73a68-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="73a68-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="73a68-122">**CPUName**</span></span> <br/> |<span data-ttu-id="73a68-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="73a68-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="73a68-124">Nombre de la CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="73a68-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="73a68-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="73a68-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="73a68-126">smallint</span><span class="sxs-lookup"><span data-stu-id="73a68-126">smallint</span></span>  <br/> ||<span data-ttu-id="73a68-127">Número de núcleos de CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="73a68-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="73a68-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="73a68-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="73a68-129">int</span><span class="sxs-lookup"><span data-stu-id="73a68-129">int</span></span>  <br/> ||<span data-ttu-id="73a68-130">Velocidad del procesador de CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="73a68-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="73a68-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="73a68-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="73a68-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="73a68-132">tinyint</span></span>  <br/> || <span data-ttu-id="73a68-133">Indicador de bits que indica si el sistema se está ejecutando en un entorno virtualizado:</span><span class="sxs-lookup"><span data-stu-id="73a68-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="73a68-134">0 x 0000 - ninguno</span><span class="sxs-lookup"><span data-stu-id="73a68-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="73a68-135">0 x 0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="73a68-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="73a68-136">0 x 0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="73a68-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="73a68-137">0 x 0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="73a68-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="73a68-138">0 x 0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="73a68-138">0x0008 - Xen PC</span></span> <br/> |
   

