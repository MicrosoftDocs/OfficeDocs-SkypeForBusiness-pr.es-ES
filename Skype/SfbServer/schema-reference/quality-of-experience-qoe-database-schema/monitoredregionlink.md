---
title: Tabla MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabla MonitoredRegionLink es una tabla auxiliar. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806350"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="b1b44-104">Tabla MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="b1b44-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="b1b44-p102">La tabla MonitoredRegionLink es una tabla auxiliar. Cada registro representa un vínculo entre dos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="b1b44-p102">The MonitoredRegionLink table is a supporting table. Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="b1b44-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b1b44-107">**Column**</span></span>|<span data-ttu-id="b1b44-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="b1b44-108">**Data Type**</span></span>|<span data-ttu-id="b1b44-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="b1b44-109">**Key/Index**</span></span>|<span data-ttu-id="b1b44-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="b1b44-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b1b44-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="b1b44-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="b1b44-112">entero</span><span class="sxs-lookup"><span data-stu-id="b1b44-112">int</span></span>  <br/> |<span data-ttu-id="b1b44-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="b1b44-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b1b44-114">Referencia desde la [tabla Región](region.md).</span><span class="sxs-lookup"><span data-stu-id="b1b44-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="b1b44-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="b1b44-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="b1b44-116">entero</span><span class="sxs-lookup"><span data-stu-id="b1b44-116">int</span></span>  <br/> |<span data-ttu-id="b1b44-117">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="b1b44-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b1b44-118">Referencia desde la [tabla Región](region.md).</span><span class="sxs-lookup"><span data-stu-id="b1b44-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

