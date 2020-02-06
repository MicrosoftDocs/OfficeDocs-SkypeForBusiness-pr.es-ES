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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabla de conferencia es una tabla de soporte técnico. Cada registro representa una sesión de conferencia o de punto a punto.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810308"
---
# <a name="conference-table"></a><span data-ttu-id="6ee04-104">Tabla Conference</span><span class="sxs-lookup"><span data-stu-id="6ee04-104">Conference table</span></span>
 
<span data-ttu-id="6ee04-105">La tabla de conferencia es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="6ee04-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="6ee04-106">Cada registro representa una sesión de conferencia o de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="6ee04-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="6ee04-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6ee04-107">**Column**</span></span>|<span data-ttu-id="6ee04-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6ee04-108">**Data Type**</span></span>|<span data-ttu-id="6ee04-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="6ee04-109">**Key/Index**</span></span>|<span data-ttu-id="6ee04-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="6ee04-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6ee04-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="6ee04-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="6ee04-112">int</span><span class="sxs-lookup"><span data-stu-id="6ee04-112">int</span></span>  <br/> |<span data-ttu-id="6ee04-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6ee04-113">Primary</span></span>  <br/> |<span data-ttu-id="6ee04-114">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="6ee04-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="6ee04-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="6ee04-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="6ee04-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6ee04-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6ee04-117">solo</span><span class="sxs-lookup"><span data-stu-id="6ee04-117">unique</span></span>  <br/> |<span data-ttu-id="6ee04-118">URI de conferencia si se trata de una conferencia o DialogID si se trata de una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="6ee04-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="6ee04-119">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="6ee04-119">**Checksum**</span></span> <br/> |<span data-ttu-id="6ee04-120">int</span><span class="sxs-lookup"><span data-stu-id="6ee04-120">int</span></span>  <br/> |<span data-ttu-id="6ee04-121">clasificación</span><span class="sxs-lookup"><span data-stu-id="6ee04-121">index</span></span>  <br/> |<span data-ttu-id="6ee04-122">Suma de comprobación del URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="6ee04-122">Checksum of the conference URI.</span></span> <span data-ttu-id="6ee04-123">Esto se usa internamente.</span><span class="sxs-lookup"><span data-stu-id="6ee04-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="6ee04-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="6ee04-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6ee04-125">datetime</span><span class="sxs-lookup"><span data-stu-id="6ee04-125">datetime</span></span>  <br/> ||<span data-ttu-id="6ee04-126">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6ee04-126">For internal use only.</span></span>  <br/> |
   

