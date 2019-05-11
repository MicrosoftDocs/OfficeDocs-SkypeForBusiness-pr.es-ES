---
title: Tabla Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: En la tabla de conferencia es una tabla de apoyo. Cada registro representa una conferencia o sesión de punto a punto.
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920169"
---
# <a name="conference-table"></a><span data-ttu-id="3b0d7-104">Tabla Conference</span><span class="sxs-lookup"><span data-stu-id="3b0d7-104">Conference table</span></span>
 
<span data-ttu-id="3b0d7-105">En la tabla de conferencia es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="3b0d7-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="3b0d7-106">Cada registro representa una conferencia o sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3b0d7-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="3b0d7-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3b0d7-107">**Column**</span></span>|<span data-ttu-id="3b0d7-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3b0d7-108">**Data Type**</span></span>|<span data-ttu-id="3b0d7-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="3b0d7-109">**Key/Index**</span></span>|<span data-ttu-id="3b0d7-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3b0d7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b0d7-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="3b0d7-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="3b0d7-112">int</span><span class="sxs-lookup"><span data-stu-id="3b0d7-112">int</span></span>  <br/> |<span data-ttu-id="3b0d7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3b0d7-113">Primary</span></span>  <br/> |<span data-ttu-id="3b0d7-114">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="3b0d7-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="3b0d7-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="3b0d7-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="3b0d7-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3b0d7-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3b0d7-117">único</span><span class="sxs-lookup"><span data-stu-id="3b0d7-117">unique</span></span>  <br/> |<span data-ttu-id="3b0d7-118">Si se trata de una conferencia, o DialogID, si este de URI de conferencia es una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3b0d7-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="3b0d7-119">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="3b0d7-119">**Checksum**</span></span> <br/> |<span data-ttu-id="3b0d7-120">int</span><span class="sxs-lookup"><span data-stu-id="3b0d7-120">int</span></span>  <br/> |<span data-ttu-id="3b0d7-121">índice</span><span class="sxs-lookup"><span data-stu-id="3b0d7-121">index</span></span>  <br/> |<span data-ttu-id="3b0d7-122">Suma de comprobación de la URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="3b0d7-122">Checksum of the conference URI.</span></span> <span data-ttu-id="3b0d7-123">Se usa internamente.</span><span class="sxs-lookup"><span data-stu-id="3b0d7-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="3b0d7-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="3b0d7-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="3b0d7-125">datetime</span><span class="sxs-lookup"><span data-stu-id="3b0d7-125">datetime</span></span>  <br/> ||<span data-ttu-id="3b0d7-126">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="3b0d7-126">For internal use only.</span></span>  <br/> |
   

