---
title: Tabla Conference
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802790"
---
# <a name="conference-table"></a><span data-ttu-id="285af-104">Tabla Conference</span><span class="sxs-lookup"><span data-stu-id="285af-104">Conference table</span></span>
 
<span data-ttu-id="285af-p102">La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="285af-p102">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="285af-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="285af-107">**Column**</span></span>|<span data-ttu-id="285af-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="285af-108">**Data Type**</span></span>|<span data-ttu-id="285af-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="285af-109">**Key/Index**</span></span>|<span data-ttu-id="285af-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="285af-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="285af-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="285af-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="285af-112">entero</span><span class="sxs-lookup"><span data-stu-id="285af-112">int</span></span>  <br/> |<span data-ttu-id="285af-113">Principal</span><span class="sxs-lookup"><span data-stu-id="285af-113">Primary</span></span>  <br/> |<span data-ttu-id="285af-114">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="285af-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="285af-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="285af-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="285af-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="285af-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="285af-117">único</span><span class="sxs-lookup"><span data-stu-id="285af-117">unique</span></span>  <br/> |<span data-ttu-id="285af-118">ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="285af-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="285af-119">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="285af-119">**Checksum**</span></span> <br/> |<span data-ttu-id="285af-120">entero</span><span class="sxs-lookup"><span data-stu-id="285af-120">int</span></span>  <br/> |<span data-ttu-id="285af-121">index</span><span class="sxs-lookup"><span data-stu-id="285af-121">index</span></span>  <br/> |<span data-ttu-id="285af-p103">Suma de comprobación del URI de conferencia. Para uso interno.</span><span class="sxs-lookup"><span data-stu-id="285af-p103">Checksum of the conference URI. This is used internally.</span></span>  <br/> |
|<span data-ttu-id="285af-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="285af-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="285af-125">datetime</span><span class="sxs-lookup"><span data-stu-id="285af-125">datetime</span></span>  <br/> ||<span data-ttu-id="285af-126">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="285af-126">For internal use only.</span></span>  <br/> |
   

