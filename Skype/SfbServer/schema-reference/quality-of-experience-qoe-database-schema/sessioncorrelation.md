---
title: Tabla SessionCorrelation
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabla SessionCorrelation es un auxiliar. Cada registro representa un CorrelationID que se utiliza para relacionar varias sesiones.
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="d0731-104">Tabla SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="d0731-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="d0731-105">La tabla SessionCorrelation es un auxiliar.</span><span class="sxs-lookup"><span data-stu-id="d0731-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="d0731-106">Cada registro representa un CorrelationID que se utiliza para relacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="d0731-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="d0731-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d0731-107">**Column**</span></span>|<span data-ttu-id="d0731-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0731-108">**Data Type**</span></span>|<span data-ttu-id="d0731-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d0731-109">**Key/Index**</span></span>|<span data-ttu-id="d0731-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d0731-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0731-111">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="d0731-111">**Checksum**</span></span> <br/> |<span data-ttu-id="d0731-112">int</span><span class="sxs-lookup"><span data-stu-id="d0731-112">int</span></span>  <br/> |||
|<span data-ttu-id="d0731-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="d0731-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="d0731-114">int</span><span class="sxs-lookup"><span data-stu-id="d0731-114">int</span></span>  <br/> |<span data-ttu-id="d0731-115">Primary</span><span class="sxs-lookup"><span data-stu-id="d0731-115">Primary</span></span>  <br/> |<span data-ttu-id="d0731-116">Número único que identifica este A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="d0731-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="d0731-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="d0731-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="d0731-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d0731-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d0731-119">Único</span><span class="sxs-lookup"><span data-stu-id="d0731-119">Unique</span></span>  <br/> |<span data-ttu-id="d0731-120">Las sesiones que se correlacionan tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="d0731-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="d0731-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d0731-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d0731-122">datetime</span><span class="sxs-lookup"><span data-stu-id="d0731-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="d0731-123">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="d0731-123">For internal use only.</span></span>  <br/> |
   

