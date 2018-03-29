---
title: Tabla Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla de servidor es una tabla de soporte. Cada registro representa a un servidor.
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a><span data-ttu-id="31c6e-104">Tabla Server</span><span class="sxs-lookup"><span data-stu-id="31c6e-104">Server table</span></span>
 
<span data-ttu-id="31c6e-105">La tabla de servidor es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="31c6e-105">The Server table is a supporting table.</span></span> <span data-ttu-id="31c6e-106">Cada registro representa a un servidor.</span><span class="sxs-lookup"><span data-stu-id="31c6e-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="31c6e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="31c6e-107">**Column**</span></span>|<span data-ttu-id="31c6e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="31c6e-108">**Data Type**</span></span>|<span data-ttu-id="31c6e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="31c6e-109">**Key/Index**</span></span>|<span data-ttu-id="31c6e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="31c6e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="31c6e-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="31c6e-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="31c6e-112">int</span><span class="sxs-lookup"><span data-stu-id="31c6e-112">int</span></span>  <br/> |<span data-ttu-id="31c6e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="31c6e-113">Primary</span></span>  <br/> |<span data-ttu-id="31c6e-114">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="31c6e-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="31c6e-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="31c6e-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="31c6e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="31c6e-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="31c6e-117">índice</span><span class="sxs-lookup"><span data-stu-id="31c6e-117">index</span></span>  <br/> |<span data-ttu-id="31c6e-118">Cadena de la dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="31c6e-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="31c6e-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="31c6e-119">**ServerType**</span></span> <br/> |<span data-ttu-id="31c6e-120">int</span><span class="sxs-lookup"><span data-stu-id="31c6e-120">int</span></span>  <br/> |<span data-ttu-id="31c6e-121">Externa</span><span class="sxs-lookup"><span data-stu-id="31c6e-121">Foreign</span></span>  <br/> |<span data-ttu-id="31c6e-122">1: servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="31c6e-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="31c6e-123">2: A / V conferencia Server16394: A / V borde service32769: puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="31c6e-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="31c6e-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="31c6e-124">**PoolName**</span></span> <br/> |<span data-ttu-id="31c6e-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="31c6e-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="31c6e-126">Grupo al que pertenece el servidor.</span><span class="sxs-lookup"><span data-stu-id="31c6e-126">Pool the server belongs to.</span></span> <span data-ttu-id="31c6e-127">Sólo aplicable en lugar de A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="31c6e-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="31c6e-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="31c6e-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="31c6e-129">datetime</span><span class="sxs-lookup"><span data-stu-id="31c6e-129">datetime</span></span>  <br/> ||<span data-ttu-id="31c6e-130">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="31c6e-130">For internal use only.</span></span>  <br/> |
   

