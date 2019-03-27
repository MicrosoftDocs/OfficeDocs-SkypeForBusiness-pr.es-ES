---
title: Tabla SessionCorrelation
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: En la tabla SessionCorrelation es una tabla de apoyo. Cada registro representa una CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884666"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="bbbf7-104">Tabla SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="bbbf7-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="bbbf7-105">En la tabla SessionCorrelation es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="bbbf7-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="bbbf7-106">Cada registro representa una CorrelationID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="bbbf7-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="bbbf7-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="bbbf7-107">**Column**</span></span>|<span data-ttu-id="bbbf7-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="bbbf7-108">**Data Type**</span></span>|<span data-ttu-id="bbbf7-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="bbbf7-109">**Key/Index**</span></span>|<span data-ttu-id="bbbf7-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="bbbf7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bbbf7-111">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="bbbf7-111">**Checksum**</span></span> <br/> |<span data-ttu-id="bbbf7-112">int</span><span class="sxs-lookup"><span data-stu-id="bbbf7-112">int</span></span>  <br/> |||
|<span data-ttu-id="bbbf7-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="bbbf7-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="bbbf7-114">int</span><span class="sxs-lookup"><span data-stu-id="bbbf7-114">int</span></span>  <br/> |<span data-ttu-id="bbbf7-115">Primary</span><span class="sxs-lookup"><span data-stu-id="bbbf7-115">Primary</span></span>  <br/> |<span data-ttu-id="bbbf7-116">Número único que identifica este / servidor de conferencia A/v.</span><span class="sxs-lookup"><span data-stu-id="bbbf7-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="bbbf7-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="bbbf7-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="bbbf7-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bbbf7-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bbbf7-119">Único</span><span class="sxs-lookup"><span data-stu-id="bbbf7-119">Unique</span></span>  <br/> |<span data-ttu-id="bbbf7-120">Las sesiones correlacionadas tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="bbbf7-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="bbbf7-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="bbbf7-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bbbf7-122">datetime</span><span class="sxs-lookup"><span data-stu-id="bbbf7-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="bbbf7-123">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="bbbf7-123">For internal use only.</span></span>  <br/> |
   

