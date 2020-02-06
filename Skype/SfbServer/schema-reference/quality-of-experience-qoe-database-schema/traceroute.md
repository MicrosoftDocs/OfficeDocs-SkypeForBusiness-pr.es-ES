---
title: Tabla TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La tabla TraceRoute contiene información de enrutamiento de las llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805118"
---
# <a name="traceroute-table"></a><span data-ttu-id="d058f-104">Tabla TraceRoute</span><span class="sxs-lookup"><span data-stu-id="d058f-104">TraceRoute table</span></span>
 
<span data-ttu-id="d058f-105">La tabla TraceRoute contiene información de enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="d058f-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="d058f-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d058f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d058f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d058f-107">**Column**</span></span>|<span data-ttu-id="d058f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d058f-108">**Data Type**</span></span>|<span data-ttu-id="d058f-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d058f-109">**Key/Index**</span></span>|<span data-ttu-id="d058f-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d058f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d058f-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d058f-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d058f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d058f-112">datetime</span></span>  <br/> |<span data-ttu-id="d058f-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d058f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d058f-114">Fecha y hora en que comenzó la llamada.</span><span class="sxs-lookup"><span data-stu-id="d058f-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="d058f-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d058f-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d058f-116">int</span><span class="sxs-lookup"><span data-stu-id="d058f-116">int</span></span>  <br/> |<span data-ttu-id="d058f-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d058f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d058f-118">Identificador único que se usa para distinguir entre varias llamadas que podrían haber comenzado en la misma fecha y al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d058f-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="d058f-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="d058f-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="d058f-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d058f-120">tinyint</span></span>  <br/> |<span data-ttu-id="d058f-121">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d058f-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d058f-122">Representa el tipo de línea de vídeo que se usa en la llamada.</span><span class="sxs-lookup"><span data-stu-id="d058f-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="d058f-123">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="d058f-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="d058f-124">0: audio</span><span class="sxs-lookup"><span data-stu-id="d058f-124">0 - Audio</span></span>  <br/> <span data-ttu-id="d058f-125">1-video</span><span class="sxs-lookup"><span data-stu-id="d058f-125">1 - Video</span></span>  <br/> <span data-ttu-id="d058f-126">2-video panorámico</span><span class="sxs-lookup"><span data-stu-id="d058f-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="d058f-127">3-uso compartido de aplicaciones y escritorio</span><span class="sxs-lookup"><span data-stu-id="d058f-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="d058f-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="d058f-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="d058f-129">bit</span><span class="sxs-lookup"><span data-stu-id="d058f-129">bit</span></span>  <br/> |<span data-ttu-id="d058f-130">Primary</span><span class="sxs-lookup"><span data-stu-id="d058f-130">Primary</span></span>  <br/> |<span data-ttu-id="d058f-131">Extremo que hizo la llamada.</span><span class="sxs-lookup"><span data-stu-id="d058f-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="d058f-132">**Únicos**</span><span class="sxs-lookup"><span data-stu-id="d058f-132">**Hop**</span></span> <br/> |<span data-ttu-id="d058f-133">int</span><span class="sxs-lookup"><span data-stu-id="d058f-133">int</span></span>  <br/> ||<span data-ttu-id="d058f-134">Salto de red/</span><span class="sxs-lookup"><span data-stu-id="d058f-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="d058f-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="d058f-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="d058f-136">int</span><span class="sxs-lookup"><span data-stu-id="d058f-136">int</span></span>  <br/> |<span data-ttu-id="d058f-137">Extranjero</span><span class="sxs-lookup"><span data-stu-id="d058f-137">Foreign</span></span>  <br/> |<span data-ttu-id="d058f-138">Identificador único de la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="d058f-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="d058f-139">La información de la dirección IP se almacena en la [tabla dirección](ipaddress.md)IP.</span><span class="sxs-lookup"><span data-stu-id="d058f-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="d058f-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="d058f-140">**RTT**</span></span> <br/> |<span data-ttu-id="d058f-141">int</span><span class="sxs-lookup"><span data-stu-id="d058f-141">int</span></span>  <br/> ||<span data-ttu-id="d058f-142">Tiempo de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="d058f-142">Roundtrip time.</span></span> <span data-ttu-id="d058f-143">El tiempo de ida y vuelta mide la cantidad de tiempo que se tarda en llegar un paquete de voz a su destino y, a continuación, se envía una notificación de que se ha recibido.</span><span class="sxs-lookup"><span data-stu-id="d058f-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

