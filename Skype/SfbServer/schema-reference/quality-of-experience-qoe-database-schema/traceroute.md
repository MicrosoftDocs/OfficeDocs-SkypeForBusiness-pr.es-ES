---
title: Tabla TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La tabla TraceRoute contiene información de enrutamiento de las llamadas. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831330"
---
# <a name="traceroute-table"></a><span data-ttu-id="63e72-104">Tabla TraceRoute</span><span class="sxs-lookup"><span data-stu-id="63e72-104">TraceRoute table</span></span>
 
<span data-ttu-id="63e72-105">La tabla TraceRoute contiene información de enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="63e72-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="63e72-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63e72-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="63e72-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="63e72-107">**Column**</span></span>|<span data-ttu-id="63e72-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="63e72-108">**Data Type**</span></span>|<span data-ttu-id="63e72-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="63e72-109">**Key/Index**</span></span>|<span data-ttu-id="63e72-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="63e72-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63e72-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="63e72-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="63e72-112">datetime</span><span class="sxs-lookup"><span data-stu-id="63e72-112">datetime</span></span>  <br/> |<span data-ttu-id="63e72-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="63e72-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="63e72-114">Fecha y hora en que empezó la llamada.</span><span class="sxs-lookup"><span data-stu-id="63e72-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="63e72-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="63e72-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="63e72-116">entero</span><span class="sxs-lookup"><span data-stu-id="63e72-116">int</span></span>  <br/> |<span data-ttu-id="63e72-117">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="63e72-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="63e72-118">Identificador único que se usa para diferenciar varias llamadas que pueden haber empezado el mismo día a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="63e72-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="63e72-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="63e72-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="63e72-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="63e72-120">tinyint</span></span>  <br/> |<span data-ttu-id="63e72-121">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="63e72-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="63e72-p103">Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="63e72-p103">Represents the type of video line used in the call. Allowed values are:</span></span>  <br/> <span data-ttu-id="63e72-124">0- Audio</span><span class="sxs-lookup"><span data-stu-id="63e72-124">0 - Audio</span></span>  <br/> <span data-ttu-id="63e72-125">1 - Vídeo</span><span class="sxs-lookup"><span data-stu-id="63e72-125">1 - Video</span></span>  <br/> <span data-ttu-id="63e72-126">2- Vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="63e72-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="63e72-127">3- Uso compartido de aplicaciones y escritorio</span><span class="sxs-lookup"><span data-stu-id="63e72-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="63e72-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="63e72-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="63e72-129">bit</span><span class="sxs-lookup"><span data-stu-id="63e72-129">bit</span></span>  <br/> |<span data-ttu-id="63e72-130">Principal</span><span class="sxs-lookup"><span data-stu-id="63e72-130">Primary</span></span>  <br/> |<span data-ttu-id="63e72-131">Extremo que ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="63e72-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="63e72-132">**Salto**</span><span class="sxs-lookup"><span data-stu-id="63e72-132">**Hop**</span></span> <br/> |<span data-ttu-id="63e72-133">entero</span><span class="sxs-lookup"><span data-stu-id="63e72-133">int</span></span>  <br/> ||<span data-ttu-id="63e72-134">Salto de red.</span><span class="sxs-lookup"><span data-stu-id="63e72-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="63e72-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="63e72-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="63e72-136">entero</span><span class="sxs-lookup"><span data-stu-id="63e72-136">int</span></span>  <br/> |<span data-ttu-id="63e72-137">Externo</span><span class="sxs-lookup"><span data-stu-id="63e72-137">Foreign</span></span>  <br/> |<span data-ttu-id="63e72-138">Identificador único de la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="63e72-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="63e72-139">La información de la dirección IP se almacena en la [tabla IPAddress](ipaddress.md).</span><span class="sxs-lookup"><span data-stu-id="63e72-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="63e72-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="63e72-140">**RTT**</span></span> <br/> |<span data-ttu-id="63e72-141">entero</span><span class="sxs-lookup"><span data-stu-id="63e72-141">int</span></span>  <br/> ||<span data-ttu-id="63e72-p105">Tiempo de ida y vuelta. El tiempo de ida y vuelta mide el tiempo que tarda el paquete de voz en llegar a su destino y devolver una notificación que informe de que se ha recibido.</span><span class="sxs-lookup"><span data-stu-id="63e72-p105">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

