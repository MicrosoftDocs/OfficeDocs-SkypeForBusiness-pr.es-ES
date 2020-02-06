---
title: Tabla MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabla MonitoredRegionLink es una tabla de soporte. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807818"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="d88ea-104">Tabla MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="d88ea-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="d88ea-105">La tabla MonitoredRegionLink es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="d88ea-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="d88ea-106">Cada registro representa un vínculo entre dos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="d88ea-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="d88ea-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d88ea-107">**Column**</span></span>|<span data-ttu-id="d88ea-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d88ea-108">**Data Type**</span></span>|<span data-ttu-id="d88ea-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d88ea-109">**Key/Index**</span></span>|<span data-ttu-id="d88ea-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d88ea-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d88ea-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="d88ea-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="d88ea-112">int</span><span class="sxs-lookup"><span data-stu-id="d88ea-112">int</span></span>  <br/> |<span data-ttu-id="d88ea-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d88ea-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d88ea-114">Se hace referencia a ella desde la [tabla region](region.md).</span><span class="sxs-lookup"><span data-stu-id="d88ea-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="d88ea-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="d88ea-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="d88ea-116">int</span><span class="sxs-lookup"><span data-stu-id="d88ea-116">int</span></span>  <br/> |<span data-ttu-id="d88ea-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="d88ea-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d88ea-118">Se hace referencia a ella desde la [tabla region](region.md).</span><span class="sxs-lookup"><span data-stu-id="d88ea-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

