---
title: Tabla Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: En la tabla de servidor es una tabla de apoyo. Cada registro representa un servidor.
ms.openlocfilehash: c0031e7181bb39895edadc40748f61626621f00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920134"
---
# <a name="server-table"></a><span data-ttu-id="43323-104">Tabla Server</span><span class="sxs-lookup"><span data-stu-id="43323-104">Server table</span></span>
 
<span data-ttu-id="43323-105">En la tabla de servidor es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="43323-105">The Server table is a supporting table.</span></span> <span data-ttu-id="43323-106">Cada registro representa un servidor.</span><span class="sxs-lookup"><span data-stu-id="43323-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="43323-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="43323-107">**Column**</span></span>|<span data-ttu-id="43323-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="43323-108">**Data Type**</span></span>|<span data-ttu-id="43323-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="43323-109">**Key/Index**</span></span>|<span data-ttu-id="43323-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="43323-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43323-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="43323-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="43323-112">int</span><span class="sxs-lookup"><span data-stu-id="43323-112">int</span></span>  <br/> |<span data-ttu-id="43323-113">Primary</span><span class="sxs-lookup"><span data-stu-id="43323-113">Primary</span></span>  <br/> |<span data-ttu-id="43323-114">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="43323-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="43323-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="43323-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="43323-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="43323-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="43323-117">índice</span><span class="sxs-lookup"><span data-stu-id="43323-117">index</span></span>  <br/> |<span data-ttu-id="43323-118">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="43323-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="43323-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="43323-119">**ServerType**</span></span> <br/> |<span data-ttu-id="43323-120">int</span><span class="sxs-lookup"><span data-stu-id="43323-120">int</span></span>  <br/> |<span data-ttu-id="43323-121">Externa</span><span class="sxs-lookup"><span data-stu-id="43323-121">Foreign</span></span>  <br/> |<span data-ttu-id="43323-122">1: servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="43323-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="43323-123">2: A / V conferencia Server16394: A V perimetral v32769: puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="43323-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="43323-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="43323-124">**PoolName**</span></span> <br/> |<span data-ttu-id="43323-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="43323-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="43323-126">El servidor pertenece al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="43323-126">Pool the server belongs to.</span></span> <span data-ttu-id="43323-127">Solo se aplica en lugar de A y servidor de conferencia A/v.</span><span class="sxs-lookup"><span data-stu-id="43323-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="43323-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="43323-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="43323-129">datetime</span><span class="sxs-lookup"><span data-stu-id="43323-129">datetime</span></span>  <br/> ||<span data-ttu-id="43323-130">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="43323-130">For internal use only.</span></span>  <br/> |
   

