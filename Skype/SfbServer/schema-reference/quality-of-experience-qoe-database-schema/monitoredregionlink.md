---
title: Tabla MonitoredRegionLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: En la tabla MonitoredRegionLink es una tabla de apoyo. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920155"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="ff933-104">Tabla MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="ff933-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="ff933-105">En la tabla MonitoredRegionLink es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="ff933-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="ff933-106">Cada registro representa un vínculo entre dos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="ff933-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="ff933-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ff933-107">**Column**</span></span>|<span data-ttu-id="ff933-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ff933-108">**Data Type**</span></span>|<span data-ttu-id="ff933-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ff933-109">**Key/Index**</span></span>|<span data-ttu-id="ff933-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ff933-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ff933-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="ff933-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="ff933-112">int</span><span class="sxs-lookup"><span data-stu-id="ff933-112">int</span></span>  <br/> |<span data-ttu-id="ff933-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="ff933-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ff933-114">Referencia de la [tabla de región](region.md).</span><span class="sxs-lookup"><span data-stu-id="ff933-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="ff933-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="ff933-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="ff933-116">int</span><span class="sxs-lookup"><span data-stu-id="ff933-116">int</span></span>  <br/> |<span data-ttu-id="ff933-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="ff933-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ff933-118">Referencia de la [tabla de región](region.md).</span><span class="sxs-lookup"><span data-stu-id="ff933-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

