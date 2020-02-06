---
title: Tabla AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabla AppliedBandwidthSource es una tabla de soporte. Cada registro representa un origen.
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811448"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="09282-104">Tabla AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="09282-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="09282-105">La tabla AppliedBandwidthSource es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="09282-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="09282-106">Cada registro representa un origen.</span><span class="sxs-lookup"><span data-stu-id="09282-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="09282-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="09282-107">**Column**</span></span>|<span data-ttu-id="09282-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="09282-108">**Data Type**</span></span>|<span data-ttu-id="09282-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="09282-109">**Key/Index**</span></span>|<span data-ttu-id="09282-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="09282-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09282-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="09282-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="09282-112">int</span><span class="sxs-lookup"><span data-stu-id="09282-112">int</span></span>  <br/> |<span data-ttu-id="09282-113">Primary</span><span class="sxs-lookup"><span data-stu-id="09282-113">Primary</span></span>  <br/> |<span data-ttu-id="09282-114">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="09282-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="09282-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="09282-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="09282-116">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="09282-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="09282-117">Solo</span><span class="sxs-lookup"><span data-stu-id="09282-117">Unique</span></span>  <br/> |<span data-ttu-id="09282-118">Este es el origen del límite de ancho de banda que se impone.</span><span class="sxs-lookup"><span data-stu-id="09282-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="09282-119">Describe de dónde viene el límite de ancho de banda (por ejemplo, "servidor de directivas", "convertir servidor" o "modalidad de moda").</span><span class="sxs-lookup"><span data-stu-id="09282-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

