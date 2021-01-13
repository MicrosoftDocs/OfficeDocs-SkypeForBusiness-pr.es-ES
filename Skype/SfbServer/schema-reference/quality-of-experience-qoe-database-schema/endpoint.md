---
title: Tabla Endpoint
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabla Endpoint es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un extremo.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823070"
---
# <a name="endpoint-table"></a><span data-ttu-id="116a4-104">Tabla Endpoint</span><span class="sxs-lookup"><span data-stu-id="116a4-104">Endpoint table</span></span>
 
<span data-ttu-id="116a4-105">La tabla Endpoint es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="116a4-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="116a4-106">Cada registro de la tabla representa un extremo.</span><span class="sxs-lookup"><span data-stu-id="116a4-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="116a4-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="116a4-107">**Column**</span></span>|<span data-ttu-id="116a4-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="116a4-108">**Data Type**</span></span>|<span data-ttu-id="116a4-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="116a4-109">**Key/Index**</span></span>|<span data-ttu-id="116a4-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="116a4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="116a4-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="116a4-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="116a4-112">entero</span><span class="sxs-lookup"><span data-stu-id="116a4-112">int</span></span>  <br/> |<span data-ttu-id="116a4-113">Principal</span><span class="sxs-lookup"><span data-stu-id="116a4-113">Primary</span></span>  <br/> |<span data-ttu-id="116a4-114">Número único que identifica este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="116a4-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="116a4-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="116a4-115">**Name**</span></span> <br/> |<span data-ttu-id="116a4-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="116a4-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="116a4-117">Única</span><span class="sxs-lookup"><span data-stu-id="116a4-117">Unique</span></span>  <br/> |<span data-ttu-id="116a4-118">Nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="116a4-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="116a4-119">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="116a4-119">**OS**</span></span> <br/> |<span data-ttu-id="116a4-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="116a4-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="116a4-121">Sistema operativo (SO) del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="116a4-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="116a4-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="116a4-122">**CPUName**</span></span> <br/> |<span data-ttu-id="116a4-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="116a4-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="116a4-124">Nombre de CPU del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="116a4-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="116a4-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="116a4-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="116a4-126">smallint</span><span class="sxs-lookup"><span data-stu-id="116a4-126">smallint</span></span>  <br/> ||<span data-ttu-id="116a4-127">Número de núcleos de CPU del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="116a4-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="116a4-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="116a4-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="116a4-129">entero</span><span class="sxs-lookup"><span data-stu-id="116a4-129">int</span></span>  <br/> ||<span data-ttu-id="116a4-130">Velocidad del procesador de CPU del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="116a4-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="116a4-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="116a4-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="116a4-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="116a4-132">tinyint</span></span>  <br/> || <span data-ttu-id="116a4-133">Marca de bits que indica si el sistema se ejecuta en un entorno virtualizado:</span><span class="sxs-lookup"><span data-stu-id="116a4-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="116a4-134">0x0000 - Ninguno</span><span class="sxs-lookup"><span data-stu-id="116a4-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="116a4-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="116a4-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="116a4-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="116a4-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="116a4-137">0x0004 - Virtual PC</span><span class="sxs-lookup"><span data-stu-id="116a4-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="116a4-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="116a4-138">0x0008 - Xen PC</span></span> <br/> |
   

