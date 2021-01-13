---
title: Tabla Server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla Server es una tabla auxiliar. Cada registro representa a un servidor.
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802710"
---
# <a name="server-table"></a><span data-ttu-id="c15c3-104">Tabla Server</span><span class="sxs-lookup"><span data-stu-id="c15c3-104">Server table</span></span>
 
<span data-ttu-id="c15c3-p102">La tabla Server es una tabla auxiliar. Cada registro representa a un servidor.</span><span class="sxs-lookup"><span data-stu-id="c15c3-p102">The Server table is a supporting table. Each record represents one server.</span></span> 
  
|<span data-ttu-id="c15c3-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c15c3-107">**Column**</span></span>|<span data-ttu-id="c15c3-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c15c3-108">**Data Type**</span></span>|<span data-ttu-id="c15c3-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="c15c3-109">**Key/Index**</span></span>|<span data-ttu-id="c15c3-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c15c3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c15c3-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="c15c3-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="c15c3-112">entero</span><span class="sxs-lookup"><span data-stu-id="c15c3-112">int</span></span>  <br/> |<span data-ttu-id="c15c3-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c15c3-113">Primary</span></span>  <br/> |<span data-ttu-id="c15c3-114">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="c15c3-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="c15c3-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="c15c3-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="c15c3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c15c3-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c15c3-117">index</span><span class="sxs-lookup"><span data-stu-id="c15c3-117">index</span></span>  <br/> |<span data-ttu-id="c15c3-118">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="c15c3-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="c15c3-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="c15c3-119">**ServerType**</span></span> <br/> |<span data-ttu-id="c15c3-120">entero</span><span class="sxs-lookup"><span data-stu-id="c15c3-120">int</span></span>  <br/> |<span data-ttu-id="c15c3-121">Externo</span><span class="sxs-lookup"><span data-stu-id="c15c3-121">Foreign</span></span>  <br/> |<span data-ttu-id="c15c3-122">1: Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="c15c3-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="c15c3-123">2: Servidor de conferencia A/V16394: Servicio perimetral A/V32769: Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="c15c3-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="c15c3-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="c15c3-124">**PoolName**</span></span> <br/> |<span data-ttu-id="c15c3-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="c15c3-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="c15c3-p103">Grupo al que pertenece el servidor. Solo aplicable para el servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="c15c3-p103">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="c15c3-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="c15c3-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="c15c3-129">datetime</span><span class="sxs-lookup"><span data-stu-id="c15c3-129">datetime</span></span>  <br/> ||<span data-ttu-id="c15c3-130">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="c15c3-130">For internal use only.</span></span>  <br/> |
   

