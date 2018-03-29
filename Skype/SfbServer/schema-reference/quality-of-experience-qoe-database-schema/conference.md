---
title: Tabla Conference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La mesa de conferencias es una tabla de soporte. Cada registro representa a una conferencia o sesión de peer-to-peer.
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a><span data-ttu-id="ed156-104">Tabla Conference</span><span class="sxs-lookup"><span data-stu-id="ed156-104">Conference table</span></span>
 
<span data-ttu-id="ed156-105">La mesa de conferencias es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="ed156-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="ed156-106">Cada registro representa a una conferencia o sesión de peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ed156-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="ed156-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ed156-107">**Column**</span></span>|<span data-ttu-id="ed156-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ed156-108">**Data Type**</span></span>|<span data-ttu-id="ed156-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ed156-109">**Key/Index**</span></span>|<span data-ttu-id="ed156-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ed156-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ed156-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="ed156-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="ed156-112">int</span><span class="sxs-lookup"><span data-stu-id="ed156-112">int</span></span>  <br/> |<span data-ttu-id="ed156-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ed156-113">Primary</span></span>  <br/> |<span data-ttu-id="ed156-114">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ed156-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="ed156-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="ed156-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="ed156-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ed156-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ed156-117">único</span><span class="sxs-lookup"><span data-stu-id="ed156-117">unique</span></span>  <br/> |<span data-ttu-id="ed156-118">Conferencia URI si se trata de una conferencia o DialogID si esta es una sesión de peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ed156-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="ed156-119">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="ed156-119">**Checksum**</span></span> <br/> |<span data-ttu-id="ed156-120">int</span><span class="sxs-lookup"><span data-stu-id="ed156-120">int</span></span>  <br/> |<span data-ttu-id="ed156-121">índice</span><span class="sxs-lookup"><span data-stu-id="ed156-121">index</span></span>  <br/> |<span data-ttu-id="ed156-122">Suma de comprobación de la conferencia URI.</span><span class="sxs-lookup"><span data-stu-id="ed156-122">Checksum of the conference URI.</span></span> <span data-ttu-id="ed156-123">Se utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="ed156-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="ed156-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ed156-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ed156-125">datetime</span><span class="sxs-lookup"><span data-stu-id="ed156-125">datetime</span></span>  <br/> ||<span data-ttu-id="ed156-126">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="ed156-126">For internal use only.</span></span>  <br/> |
   

