---
title: Tabla Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabla de extremos es una tabla de soporte que almacena información sobre los puntos de conexión que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un punto final.
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809558"
---
# <a name="endpoint-table"></a><span data-ttu-id="dec46-104">Tabla Endpoint</span><span class="sxs-lookup"><span data-stu-id="dec46-104">Endpoint table</span></span>
 
<span data-ttu-id="dec46-105">La tabla de extremos es una tabla de soporte que almacena información sobre los puntos de conexión que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dec46-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="dec46-106">Cada registro de la tabla representa un punto final.</span><span class="sxs-lookup"><span data-stu-id="dec46-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="dec46-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dec46-107">**Column**</span></span>|<span data-ttu-id="dec46-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="dec46-108">**Data Type**</span></span>|<span data-ttu-id="dec46-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="dec46-109">**Key/Index**</span></span>|<span data-ttu-id="dec46-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="dec46-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dec46-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="dec46-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="dec46-112">int</span><span class="sxs-lookup"><span data-stu-id="dec46-112">int</span></span>  <br/> |<span data-ttu-id="dec46-113">Primary</span><span class="sxs-lookup"><span data-stu-id="dec46-113">Primary</span></span>  <br/> |<span data-ttu-id="dec46-114">Número único que identifica este punto final.</span><span class="sxs-lookup"><span data-stu-id="dec46-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="dec46-115">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="dec46-115">**Name**</span></span> <br/> |<span data-ttu-id="dec46-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dec46-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="dec46-117">Solo</span><span class="sxs-lookup"><span data-stu-id="dec46-117">Unique</span></span>  <br/> |<span data-ttu-id="dec46-118">Nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="dec46-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="dec46-119">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="dec46-119">**OS**</span></span> <br/> |<span data-ttu-id="dec46-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dec46-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="dec46-121">Sistema operativo (SO) del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="dec46-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="dec46-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="dec46-122">**CPUName**</span></span> <br/> |<span data-ttu-id="dec46-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dec46-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="dec46-124">Nombre de la CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="dec46-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="dec46-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="dec46-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="dec46-126">smallint</span><span class="sxs-lookup"><span data-stu-id="dec46-126">smallint</span></span>  <br/> ||<span data-ttu-id="dec46-127">Número de núcleos de CPU del extremo.</span><span class="sxs-lookup"><span data-stu-id="dec46-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="dec46-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="dec46-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="dec46-129">int</span><span class="sxs-lookup"><span data-stu-id="dec46-129">int</span></span>  <br/> ||<span data-ttu-id="dec46-130">Velocidad del procesador de la CPU del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="dec46-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="dec46-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="dec46-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="dec46-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="dec46-132">tinyint</span></span>  <br/> || <span data-ttu-id="dec46-133">Marcador de bits que indica si el sistema se está ejecutando en un entorno virtualizado:</span><span class="sxs-lookup"><span data-stu-id="dec46-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="dec46-134">0x0000-ninguna</span><span class="sxs-lookup"><span data-stu-id="dec46-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="dec46-135">0x0001: HyperV</span><span class="sxs-lookup"><span data-stu-id="dec46-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="dec46-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="dec46-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="dec46-137">0x0004-Virtual PC</span><span class="sxs-lookup"><span data-stu-id="dec46-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="dec46-138">0x0008: Xen PC</span><span class="sxs-lookup"><span data-stu-id="dec46-138">0x0008 - Xen PC</span></span> <br/> |
   

