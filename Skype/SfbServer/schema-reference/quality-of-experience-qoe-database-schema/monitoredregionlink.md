---
title: Tabla MonitoredRegionLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: En la tabla MonitoredRegionLink es una tabla de apoyo. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212463"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="d7332-104">Tabla MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="d7332-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="d7332-105">En la tabla MonitoredRegionLink es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="d7332-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="d7332-106">Cada registro representa un vínculo entre dos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="d7332-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="d7332-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d7332-107">**Column**</span></span>|<span data-ttu-id="d7332-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d7332-108">**Data Type**</span></span>|<span data-ttu-id="d7332-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d7332-109">**Key/Index**</span></span>|<span data-ttu-id="d7332-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d7332-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7332-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="d7332-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="d7332-112">int</span><span class="sxs-lookup"><span data-stu-id="d7332-112">int</span></span>  <br/> |<span data-ttu-id="d7332-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="d7332-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d7332-114">Referencia de la [tabla de región](region.md).</span><span class="sxs-lookup"><span data-stu-id="d7332-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="d7332-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="d7332-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="d7332-116">int</span><span class="sxs-lookup"><span data-stu-id="d7332-116">int</span></span>  <br/> |<span data-ttu-id="d7332-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="d7332-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d7332-118">Referencia de la [tabla de región](region.md).</span><span class="sxs-lookup"><span data-stu-id="d7332-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

