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
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabla AppliedBandwidthSource es una tabla de soporte. Cada registro representa un origen.
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295114"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="26981-104">Tabla AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="26981-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="26981-105">La tabla AppliedBandwidthSource es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="26981-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="26981-106">Cada registro representa un origen.</span><span class="sxs-lookup"><span data-stu-id="26981-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="26981-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="26981-107">**Column**</span></span>|<span data-ttu-id="26981-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="26981-108">**Data Type**</span></span>|<span data-ttu-id="26981-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="26981-109">**Key/Index**</span></span>|<span data-ttu-id="26981-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="26981-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26981-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="26981-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="26981-112">int</span><span class="sxs-lookup"><span data-stu-id="26981-112">int</span></span>  <br/> |<span data-ttu-id="26981-113">Primary</span><span class="sxs-lookup"><span data-stu-id="26981-113">Primary</span></span>  <br/> |<span data-ttu-id="26981-114">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="26981-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="26981-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="26981-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="26981-116">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="26981-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="26981-117">Solo</span><span class="sxs-lookup"><span data-stu-id="26981-117">Unique</span></span>  <br/> |<span data-ttu-id="26981-118">Este es el origen del límite de ancho de banda que se impone.</span><span class="sxs-lookup"><span data-stu-id="26981-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="26981-119">Describe de dónde viene el límite de ancho de banda (por ejemplo, "servidor de directivas", "convertir servidor" o "modalidad de moda").</span><span class="sxs-lookup"><span data-stu-id="26981-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

