---
title: Tabla Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: En la tabla de servidor es una tabla de apoyo. Cada registro representa un servidor.
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212112"
---
# <a name="server-table"></a><span data-ttu-id="097eb-104">Tabla Server</span><span class="sxs-lookup"><span data-stu-id="097eb-104">Server table</span></span>
 
<span data-ttu-id="097eb-105">En la tabla de servidor es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="097eb-105">The Server table is a supporting table.</span></span> <span data-ttu-id="097eb-106">Cada registro representa un servidor.</span><span class="sxs-lookup"><span data-stu-id="097eb-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="097eb-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="097eb-107">**Column**</span></span>|<span data-ttu-id="097eb-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="097eb-108">**Data Type**</span></span>|<span data-ttu-id="097eb-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="097eb-109">**Key/Index**</span></span>|<span data-ttu-id="097eb-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="097eb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="097eb-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="097eb-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="097eb-112">int</span><span class="sxs-lookup"><span data-stu-id="097eb-112">int</span></span>  <br/> |<span data-ttu-id="097eb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="097eb-113">Primary</span></span>  <br/> |<span data-ttu-id="097eb-114">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="097eb-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="097eb-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="097eb-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="097eb-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="097eb-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="097eb-117">índice</span><span class="sxs-lookup"><span data-stu-id="097eb-117">index</span></span>  <br/> |<span data-ttu-id="097eb-118">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="097eb-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="097eb-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="097eb-119">**ServerType**</span></span> <br/> |<span data-ttu-id="097eb-120">int</span><span class="sxs-lookup"><span data-stu-id="097eb-120">int</span></span>  <br/> |<span data-ttu-id="097eb-121">Externa</span><span class="sxs-lookup"><span data-stu-id="097eb-121">Foreign</span></span>  <br/> |<span data-ttu-id="097eb-122">1: servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="097eb-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="097eb-123">2: A / V conferencia Server16394: A V perimetral v32769: puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="097eb-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="097eb-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="097eb-124">**PoolName**</span></span> <br/> |<span data-ttu-id="097eb-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="097eb-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="097eb-126">El servidor pertenece al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="097eb-126">Pool the server belongs to.</span></span> <span data-ttu-id="097eb-127">Solo se aplica en lugar de A y servidor de conferencia A/v.</span><span class="sxs-lookup"><span data-stu-id="097eb-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="097eb-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="097eb-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="097eb-129">datetime</span><span class="sxs-lookup"><span data-stu-id="097eb-129">datetime</span></span>  <br/> ||<span data-ttu-id="097eb-130">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="097eb-130">For internal use only.</span></span>  <br/> |
   

