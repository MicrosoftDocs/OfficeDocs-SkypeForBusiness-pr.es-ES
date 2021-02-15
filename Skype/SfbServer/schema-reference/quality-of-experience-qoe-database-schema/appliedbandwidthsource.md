---
title: Tabla AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831410"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="0d752-104">Tabla AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="0d752-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="0d752-p102">La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.</span><span class="sxs-lookup"><span data-stu-id="0d752-p102">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>
  
|<span data-ttu-id="0d752-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0d752-107">**Column**</span></span>|<span data-ttu-id="0d752-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0d752-108">**Data Type**</span></span>|<span data-ttu-id="0d752-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="0d752-109">**Key/Index**</span></span>|<span data-ttu-id="0d752-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0d752-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0d752-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="0d752-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="0d752-112">entero</span><span class="sxs-lookup"><span data-stu-id="0d752-112">int</span></span>  <br/> |<span data-ttu-id="0d752-113">Principal</span><span class="sxs-lookup"><span data-stu-id="0d752-113">Primary</span></span>  <br/> |<span data-ttu-id="0d752-114">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="0d752-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="0d752-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="0d752-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="0d752-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="0d752-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="0d752-117">Única</span><span class="sxs-lookup"><span data-stu-id="0d752-117">Unique</span></span>  <br/> |<span data-ttu-id="0d752-118">Origen del límite de ancho de banda impuesto.</span><span class="sxs-lookup"><span data-stu-id="0d752-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="0d752-119">Describe de dónde viene el límite de ancho de banda (por ejemplo, "Servidor de directivas", "Servidor TURN" o "Modalidad").</span><span class="sxs-lookup"><span data-stu-id="0d752-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

