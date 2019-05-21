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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla del servidor es una tabla de soporte técnico. Cada registro representa un servidor.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294715"
---
# <a name="server-table"></a><span data-ttu-id="0f0b1-104">Tabla Server</span><span class="sxs-lookup"><span data-stu-id="0f0b1-104">Server table</span></span>
 
<span data-ttu-id="0f0b1-105">La tabla del servidor es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="0f0b1-105">The Server table is a supporting table.</span></span> <span data-ttu-id="0f0b1-106">Cada registro representa un servidor.</span><span class="sxs-lookup"><span data-stu-id="0f0b1-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="0f0b1-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-107">**Column**</span></span>|<span data-ttu-id="0f0b1-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-108">**Data Type**</span></span>|<span data-ttu-id="0f0b1-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-109">**Key/Index**</span></span>|<span data-ttu-id="0f0b1-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0f0b1-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="0f0b1-112">int</span><span class="sxs-lookup"><span data-stu-id="0f0b1-112">int</span></span>  <br/> |<span data-ttu-id="0f0b1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0f0b1-113">Primary</span></span>  <br/> |<span data-ttu-id="0f0b1-114">Número único que identifica el servidor.</span><span class="sxs-lookup"><span data-stu-id="0f0b1-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="0f0b1-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="0f0b1-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0f0b1-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f0b1-117">clasificación</span><span class="sxs-lookup"><span data-stu-id="0f0b1-117">index</span></span>  <br/> |<span data-ttu-id="0f0b1-118">Cadena de dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="0f0b1-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="0f0b1-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-119">**ServerType**</span></span> <br/> |<span data-ttu-id="0f0b1-120">int</span><span class="sxs-lookup"><span data-stu-id="0f0b1-120">int</span></span>  <br/> |<span data-ttu-id="0f0b1-121">Extranjero</span><span class="sxs-lookup"><span data-stu-id="0f0b1-121">Foreign</span></span>  <br/> |<span data-ttu-id="0f0b1-122">1: servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="0f0b1-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="0f0b1-123">2: Server16394 de conferencia a/V: service32769 Edge: Gateway</span><span class="sxs-lookup"><span data-stu-id="0f0b1-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="0f0b1-124">**Nombredegrupo**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-124">**PoolName**</span></span> <br/> |<span data-ttu-id="0f0b1-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="0f0b1-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="0f0b1-126">Grupo al que pertenece el servidor.</span><span class="sxs-lookup"><span data-stu-id="0f0b1-126">Pool the server belongs to.</span></span> <span data-ttu-id="0f0b1-127">Solo es aplicable para el servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="0f0b1-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="0f0b1-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="0f0b1-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0f0b1-129">datetime</span><span class="sxs-lookup"><span data-stu-id="0f0b1-129">datetime</span></span>  <br/> ||<span data-ttu-id="0f0b1-130">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0f0b1-130">For internal use only.</span></span>  <br/> |
   

