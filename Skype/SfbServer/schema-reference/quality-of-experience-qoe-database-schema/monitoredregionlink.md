---
title: Tabla MonitoredRegionLink
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabla MonitoredRegionLink es un auxiliar. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: 471291788dabee412bffef641624afad2a2c10b4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="6811c-104">Tabla MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="6811c-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="6811c-105">La tabla MonitoredRegionLink es un auxiliar.</span><span class="sxs-lookup"><span data-stu-id="6811c-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="6811c-106">Cada registro representa un vínculo entre dos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="6811c-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="6811c-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6811c-107">**Column**</span></span>|<span data-ttu-id="6811c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6811c-108">**Data Type**</span></span>|<span data-ttu-id="6811c-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="6811c-109">**Key/Index**</span></span>|<span data-ttu-id="6811c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="6811c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6811c-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="6811c-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="6811c-112">int</span><span class="sxs-lookup"><span data-stu-id="6811c-112">int</span></span>  <br/> |<span data-ttu-id="6811c-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="6811c-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6811c-114">Referencia de la [tabla de la región](region.md).</span><span class="sxs-lookup"><span data-stu-id="6811c-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="6811c-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="6811c-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="6811c-116">int</span><span class="sxs-lookup"><span data-stu-id="6811c-116">int</span></span>  <br/> |<span data-ttu-id="6811c-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="6811c-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6811c-118">Referencia de la [tabla de la región](region.md).</span><span class="sxs-lookup"><span data-stu-id="6811c-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

