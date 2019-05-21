---
title: Tabla Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabla de conferencia es una tabla de soporte técnico. Cada registro representa una sesión de conferencia o de punto a punto.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295016"
---
# <a name="conference-table"></a><span data-ttu-id="d07c0-104">Tabla Conference</span><span class="sxs-lookup"><span data-stu-id="d07c0-104">Conference table</span></span>
 
<span data-ttu-id="d07c0-105">La tabla de conferencia es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="d07c0-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="d07c0-106">Cada registro representa una sesión de conferencia o de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="d07c0-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="d07c0-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d07c0-107">**Column**</span></span>|<span data-ttu-id="d07c0-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d07c0-108">**Data Type**</span></span>|<span data-ttu-id="d07c0-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d07c0-109">**Key/Index**</span></span>|<span data-ttu-id="d07c0-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d07c0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d07c0-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="d07c0-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="d07c0-112">int</span><span class="sxs-lookup"><span data-stu-id="d07c0-112">int</span></span>  <br/> |<span data-ttu-id="d07c0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d07c0-113">Primary</span></span>  <br/> |<span data-ttu-id="d07c0-114">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d07c0-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="d07c0-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="d07c0-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="d07c0-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d07c0-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d07c0-117">solo</span><span class="sxs-lookup"><span data-stu-id="d07c0-117">unique</span></span>  <br/> |<span data-ttu-id="d07c0-118">URI de conferencia si se trata de una conferencia o DialogID si se trata de una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="d07c0-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="d07c0-119">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="d07c0-119">**Checksum**</span></span> <br/> |<span data-ttu-id="d07c0-120">int</span><span class="sxs-lookup"><span data-stu-id="d07c0-120">int</span></span>  <br/> |<span data-ttu-id="d07c0-121">clasificación</span><span class="sxs-lookup"><span data-stu-id="d07c0-121">index</span></span>  <br/> |<span data-ttu-id="d07c0-122">Suma de comprobación del URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="d07c0-122">Checksum of the conference URI.</span></span> <span data-ttu-id="d07c0-123">Esto se usa internamente.</span><span class="sxs-lookup"><span data-stu-id="d07c0-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="d07c0-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d07c0-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d07c0-125">datetime</span><span class="sxs-lookup"><span data-stu-id="d07c0-125">datetime</span></span>  <br/> ||<span data-ttu-id="d07c0-126">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="d07c0-126">For internal use only.</span></span>  <br/> |
   

