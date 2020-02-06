---
title: Tabla VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Cada registro contiene un evento de cliente para un punto final en una videollamada. Generalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario.'
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804998"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="bab54-104">Tabla VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="bab54-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="bab54-105">Cada registro contiene un evento de cliente para un punto final en una videollamada.</span><span class="sxs-lookup"><span data-stu-id="bab54-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="bab54-106">Generalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario.</span><span class="sxs-lookup"><span data-stu-id="bab54-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="bab54-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="bab54-107">**Column**</span></span>|<span data-ttu-id="bab54-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="bab54-108">**Data Type**</span></span>|<span data-ttu-id="bab54-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="bab54-109">**Key/Index**</span></span>|<span data-ttu-id="bab54-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="bab54-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bab54-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="bab54-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="bab54-112">datetime</span><span class="sxs-lookup"><span data-stu-id="bab54-112">datetime</span></span>  <br/> |<span data-ttu-id="bab54-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bab54-113">Primary</span></span>  <br/> |<span data-ttu-id="bab54-114">Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="bab54-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="bab54-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="bab54-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="bab54-116">int</span><span class="sxs-lookup"><span data-stu-id="bab54-116">int</span></span>  <br/> |<span data-ttu-id="bab54-117">Primary</span><span class="sxs-lookup"><span data-stu-id="bab54-117">Primary</span></span>  <br/> |<span data-ttu-id="bab54-118">Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="bab54-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="bab54-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="bab54-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="bab54-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="bab54-120">tinyint</span></span>  <br/> |<span data-ttu-id="bab54-121">Primary</span><span class="sxs-lookup"><span data-stu-id="bab54-121">Primary</span></span>  <br/> |<span data-ttu-id="bab54-122">Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="bab54-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="bab54-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="bab54-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="bab54-124">bit</span><span class="sxs-lookup"><span data-stu-id="bab54-124">bit</span></span>  <br/> |<span data-ttu-id="bab54-125">Primary</span><span class="sxs-lookup"><span data-stu-id="bab54-125">Primary</span></span>  <br/> |<span data-ttu-id="bab54-126">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="bab54-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="bab54-127">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="bab54-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="bab54-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="bab54-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="bab54-129">Porcentaje de sesión el evento LowBandwidth se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="bab54-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="bab54-130">El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="bab54-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="bab54-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="bab54-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="bab54-132">Porcentaje de sesión el evento ReceiveSendQuality se activó por el estado "incorrecto".</span><span class="sxs-lookup"><span data-stu-id="bab54-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="bab54-133">La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta la calidad de audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="bab54-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

