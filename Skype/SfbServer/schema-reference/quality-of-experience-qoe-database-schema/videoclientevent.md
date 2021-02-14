---
title: Tabla VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contiene el evento de cliente para un extremo en una videollamada. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821400"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="5cf82-104">Tabla VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="5cf82-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="5cf82-105">Cada registro contiene el evento de cliente para un extremo en una videollamada.</span><span class="sxs-lookup"><span data-stu-id="5cf82-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="5cf82-106">Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5cf82-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="5cf82-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5cf82-107">**Column**</span></span>|<span data-ttu-id="5cf82-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="5cf82-108">**Data Type**</span></span>|<span data-ttu-id="5cf82-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="5cf82-109">**Key/Index**</span></span>|<span data-ttu-id="5cf82-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="5cf82-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5cf82-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="5cf82-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="5cf82-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5cf82-112">datetime</span></span>  <br/> |<span data-ttu-id="5cf82-113">Principal</span><span class="sxs-lookup"><span data-stu-id="5cf82-113">Primary</span></span>  <br/> |<span data-ttu-id="5cf82-114">Se hace referencia desde la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5cf82-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5cf82-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="5cf82-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="5cf82-116">entero</span><span class="sxs-lookup"><span data-stu-id="5cf82-116">int</span></span>  <br/> |<span data-ttu-id="5cf82-117">Principal</span><span class="sxs-lookup"><span data-stu-id="5cf82-117">Primary</span></span>  <br/> |<span data-ttu-id="5cf82-118">Se hace referencia desde la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5cf82-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5cf82-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="5cf82-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="5cf82-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="5cf82-120">tinyint</span></span>  <br/> |<span data-ttu-id="5cf82-121">Principal</span><span class="sxs-lookup"><span data-stu-id="5cf82-121">Primary</span></span>  <br/> |<span data-ttu-id="5cf82-122">Se hace referencia desde la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="5cf82-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="5cf82-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="5cf82-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="5cf82-124">bit</span><span class="sxs-lookup"><span data-stu-id="5cf82-124">bit</span></span>  <br/> |<span data-ttu-id="5cf82-125">Principal</span><span class="sxs-lookup"><span data-stu-id="5cf82-125">Primary</span></span>  <br/> |<span data-ttu-id="5cf82-126">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="5cf82-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="5cf82-127">1: Datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="5cf82-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="5cf82-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="5cf82-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="5cf82-129">Porcentaje de sesión en la que se deseó el evento LowBandwidth para el estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="5cf82-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="5cf82-130">El ancho de banda disponible no es suficiente para una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="5cf82-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="5cf82-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="5cf82-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="5cf82-132">Porcentaje de sesión en la que se deseó el evento ReceiveSendQuality para el estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="5cf82-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="5cf82-133">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="5cf82-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

