---
title: Tabla VideoClientEvent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contiene el evento de cliente para un extremo en una videollamada. Normalmente, una llamada tiene dos registros, uno para el llamador y otro para el destinatario de la llamada.
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a><span data-ttu-id="2fe39-104">Tabla VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="2fe39-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="2fe39-105">Cada registro contiene el evento de cliente para un extremo en una videollamada.</span><span class="sxs-lookup"><span data-stu-id="2fe39-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="2fe39-106">Normalmente, una llamada tiene dos registros, uno para el llamador y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2fe39-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="2fe39-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2fe39-107">**Column**</span></span>|<span data-ttu-id="2fe39-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2fe39-108">**Data Type**</span></span>|<span data-ttu-id="2fe39-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="2fe39-109">**Key/Index**</span></span>|<span data-ttu-id="2fe39-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="2fe39-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2fe39-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="2fe39-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="2fe39-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2fe39-112">datetime</span></span>  <br/> |<span data-ttu-id="2fe39-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2fe39-113">Primary</span></span>  <br/> |<span data-ttu-id="2fe39-114">Referencia de la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="2fe39-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="2fe39-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="2fe39-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="2fe39-116">int</span><span class="sxs-lookup"><span data-stu-id="2fe39-116">int</span></span>  <br/> |<span data-ttu-id="2fe39-117">Primary</span><span class="sxs-lookup"><span data-stu-id="2fe39-117">Primary</span></span>  <br/> |<span data-ttu-id="2fe39-118">Referencia de la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="2fe39-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="2fe39-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="2fe39-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="2fe39-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="2fe39-120">tinyint</span></span>  <br/> |<span data-ttu-id="2fe39-121">Primary</span><span class="sxs-lookup"><span data-stu-id="2fe39-121">Primary</span></span>  <br/> |<span data-ttu-id="2fe39-122">Referencia de la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="2fe39-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="2fe39-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="2fe39-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="2fe39-124">bit</span><span class="sxs-lookup"><span data-stu-id="2fe39-124">bit</span></span>  <br/> |<span data-ttu-id="2fe39-125">Primary</span><span class="sxs-lookup"><span data-stu-id="2fe39-125">Primary</span></span>  <br/> |<span data-ttu-id="2fe39-126">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="2fe39-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="2fe39-127">1: datos del llamador</span><span class="sxs-lookup"><span data-stu-id="2fe39-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="2fe39-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="2fe39-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="2fe39-129">Porcentaje de sesión que se desencadenó el evento LowBandwidth para el estado 'Bad'.</span><span class="sxs-lookup"><span data-stu-id="2fe39-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="2fe39-130">El ancho de banda disponible no es suficiente para una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="2fe39-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="2fe39-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="2fe39-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="2fe39-132">Porcentaje de sesión que se desencadenó el evento ReceiveSendQuality para el estado 'Bad'.</span><span class="sxs-lookup"><span data-stu-id="2fe39-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="2fe39-133">Calidad de la red en términos de pérdida de paquete o Vibración es grave y afecta a la calidad del audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="2fe39-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

