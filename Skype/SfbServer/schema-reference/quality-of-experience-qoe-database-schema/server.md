---
title: Tabla Server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla del servidor es una tabla de soporte técnico. Cada registro representa un servidor.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806138"
---
# <a name="server-table"></a><span data-ttu-id="a21d9-104">Tabla Server</span><span class="sxs-lookup"><span data-stu-id="a21d9-104">Server table</span></span>
 
<span data-ttu-id="a21d9-105">La tabla del servidor es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="a21d9-105">The Server table is a supporting table.</span></span> <span data-ttu-id="a21d9-106">Cada registro representa un servidor.</span><span class="sxs-lookup"><span data-stu-id="a21d9-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="a21d9-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a21d9-107">**Column**</span></span>|<span data-ttu-id="a21d9-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="a21d9-108">**Data Type**</span></span>|<span data-ttu-id="a21d9-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="a21d9-109">**Key/Index**</span></span>|<span data-ttu-id="a21d9-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="a21d9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a21d9-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="a21d9-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="a21d9-112">int</span><span class="sxs-lookup"><span data-stu-id="a21d9-112">int</span></span>  <br/> |<span data-ttu-id="a21d9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a21d9-113">Primary</span></span>  <br/> |<span data-ttu-id="a21d9-114">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="a21d9-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="a21d9-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="a21d9-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="a21d9-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a21d9-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a21d9-117">clasificación</span><span class="sxs-lookup"><span data-stu-id="a21d9-117">index</span></span>  <br/> |<span data-ttu-id="a21d9-118">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="a21d9-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="a21d9-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="a21d9-119">**ServerType**</span></span> <br/> |<span data-ttu-id="a21d9-120">int</span><span class="sxs-lookup"><span data-stu-id="a21d9-120">int</span></span>  <br/> |<span data-ttu-id="a21d9-121">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a21d9-121">Foreign</span></span>  <br/> |<span data-ttu-id="a21d9-122">1: servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a21d9-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="a21d9-123">2: Server16394 de conferencia a/V: service32769 Edge: Gateway</span><span class="sxs-lookup"><span data-stu-id="a21d9-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="a21d9-124">**Nombredegrupo**</span><span class="sxs-lookup"><span data-stu-id="a21d9-124">**PoolName**</span></span> <br/> |<span data-ttu-id="a21d9-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="a21d9-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="a21d9-126">Grupo al que pertenece el servidor.</span><span class="sxs-lookup"><span data-stu-id="a21d9-126">Pool the server belongs to.</span></span> <span data-ttu-id="a21d9-127">Solo es aplicable para el servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="a21d9-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="a21d9-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="a21d9-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="a21d9-129">datetime</span><span class="sxs-lookup"><span data-stu-id="a21d9-129">datetime</span></span>  <br/> ||<span data-ttu-id="a21d9-130">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="a21d9-130">For internal use only.</span></span>  <br/> |
   

