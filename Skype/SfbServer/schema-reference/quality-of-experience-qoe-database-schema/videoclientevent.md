---
title: Tabla VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contiene eventos de cliente para uno de los extremos en una llamada de vídeo. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: 58179630534733985e062bbe0fafa1bbfd8499db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906829"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="d852a-104">Tabla VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="d852a-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="d852a-105">Cada registro contiene eventos de cliente para uno de los extremos en una llamada de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d852a-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="d852a-106">Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d852a-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="d852a-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d852a-107">**Column**</span></span>|<span data-ttu-id="d852a-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d852a-108">**Data Type**</span></span>|<span data-ttu-id="d852a-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d852a-109">**Key/Index**</span></span>|<span data-ttu-id="d852a-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d852a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d852a-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d852a-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d852a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d852a-112">datetime</span></span>  <br/> |<span data-ttu-id="d852a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d852a-113">Primary</span></span>  <br/> |<span data-ttu-id="d852a-114">Referencia de la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d852a-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d852a-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d852a-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d852a-116">int</span><span class="sxs-lookup"><span data-stu-id="d852a-116">int</span></span>  <br/> |<span data-ttu-id="d852a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d852a-117">Primary</span></span>  <br/> |<span data-ttu-id="d852a-118">Referencia de la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d852a-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d852a-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="d852a-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="d852a-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d852a-120">tinyint</span></span>  <br/> |<span data-ttu-id="d852a-121">Primary</span><span class="sxs-lookup"><span data-stu-id="d852a-121">Primary</span></span>  <br/> |<span data-ttu-id="d852a-122">Referencia de la [tabla MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d852a-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d852a-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="d852a-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="d852a-124">bit</span><span class="sxs-lookup"><span data-stu-id="d852a-124">bit</span></span>  <br/> |<span data-ttu-id="d852a-125">Primary</span><span class="sxs-lookup"><span data-stu-id="d852a-125">Primary</span></span>  <br/> |<span data-ttu-id="d852a-126">0: datos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="d852a-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="d852a-127">1: datos del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="d852a-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="d852a-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d852a-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d852a-129">Porcentaje de sesión que se desencadenó el evento LowBandwidth para estado 'Bad'.</span><span class="sxs-lookup"><span data-stu-id="d852a-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="d852a-130">El ancho de banda disponible no es suficiente para obtener una experiencia de voz aceptable.</span><span class="sxs-lookup"><span data-stu-id="d852a-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="d852a-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d852a-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d852a-132">Porcentaje de sesión que se desencadenó el evento ReceiveSendQuality para estado 'Bad'.</span><span class="sxs-lookup"><span data-stu-id="d852a-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="d852a-133">Calidad de red en cuanto a vibración o pérdida de paquetes es baja y afecta a la calidad del audio que se recibe.</span><span class="sxs-lookup"><span data-stu-id="d852a-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

